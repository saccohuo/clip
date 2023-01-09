---
title: "分辨率和丢帧检测的自动测试"
date: 2023-01-09T21:23:17+08:00
updated: 2023-01-09T21:23:17+08:00
taxonomies:
  tags: []
extra:
  source: https://blog.galowicz.de/2023/01/09/automatic-testing-of-display-resolution-and-frame-drop-detection/
  hostname: blog.galowicz.de
  author: 
  original_title: "Jacek's Blog · Automatic Testing of Display Resolution and Frame Drop Detection --- Jacek 的博客 · 显示分辨率和丢帧检测的自动测试"
  original_lang: en
---

January 9, 2023 Tags: [nix](https://blog.galowicz.de/tags/nix.html "All pages tagged 'nix'.") [python](https://blog.galowicz.de/tags/python.html "All pages tagged 'python'.") [testing](https://blog.galowicz.de/tags/testing.html "All pages tagged 'testing'.")  
尼克斯蟒蛇测试  

This week, I like to share a project with you that started as a very interesting challenge and developed into an interdisciplinary, productive, and fun experience: A fully automatic multi-display end-to-end customer test prototype. In the end, it was surprising to see what parts of the code the most effort went into.

本周，我想与大家分享一个项目，该项目最初是一个非常有趣的挑战，后来发展成为一种跨学科、富有成效且有趣的体验：全自动多显示器端到端客户测试原型。最后，令人惊讶的是代码的哪些部分投入了最多的精力。

## Initial Situation 初始情况

![The impact of bad news gets worse the later it arrives](developer-qa.webp)

The project partner’s business sells laptops with customized operating system support. Before every release, custom operating system images have to be tested against the software and hardware combinations that are certified and shipped with and for the supported laptop models. These tests have so far been executed manually in a dedicated QA department. Manual testing introduces unwanted delays in the product cycles, so the project partner’s challenge was: How to automate the most time-consuming part of it? Concentrating on the manual, most time-consuming, and costly phases of the software release process is strategically the best way to improve the throughput of the organization, as we might already have learned from the [three ways in the book “The Phoenix Project”](https://blog.galowicz.de/2022/12/19/book-review-the-phoenix-project).

项目合作伙伴的业务销售具有定制操作系统支持的笔记本电脑。在每次发布之前，自定义操作系统映像都必须针对经过认证并随支持的笔记本电脑型号一起提供的软件和硬件组合进行测试。到目前为止，这些测试都是在专门的 QA 部门手动执行的。手动测试会在产品周期中引入不必要的延迟，因此项目合作伙伴面临的挑战是：如何自动化其中最耗时的部分？从战略上讲，专注于软件发布过程中最耗时且成本最高的手动阶段是提高组织吞吐量的最佳方法，正如我们可能已经从《凤凰计划》一书中的三种方法中了解到的那样。

After each successful test phase, professionals of the QA department sign the test result documentation _personally_ (autograph signature, not (yet) cryptographic signature). For this reason, automated testing not only had implications for the development department but also legal ones for the QA: We could improve the processes by automating phases that have been performed manually before and then have developers use those earlier and frequently to reduce the number of bugs in release phases in the final test runs. But this had to happen step by step, so the test method had to be designed in a way that the non-programmers, who still have to _sign_ the test results before every release, trust the automated test approach to be equivalent to manual testing in its validation of tested functionality. If we failed this constraint, we would just produce another stage somewhere in the existing processes. It would slowly drift away from what happens in actual pre-release QA over time and all the investment would miss its target.

在每个成功的测试阶段之后，QA 部门的专业人员亲自签署测试结果文档（亲笔签名，而不是（尚未）加密签名）。出于这个原因，自动化测试不仅对开发部门有影响，而且对 QA 也有法律意义：我们可以通过自动化之前手动执行的阶段来改进流程，然后让开发人员更早和更频繁地使用这些阶段来减少最终测试运行中发布阶段的错误。但这必须一步一步进行，因此测试方法的设计方式必须让非程序员（他们仍然必须在每次发布前签署测试结果）相信自动化测试方法等同于手动测试它对测试功能的验证。如果我们未能满足此约束条件，我们只会在现有流程的某处产生另一个阶段。随着时间的推移，它会慢慢偏离实际预发布 QA 中发生的事情，所有投资都将无法达到目标。

This constraint made the overall problem much harder. I see this as a side effect of change being more difficult in big corporations compared to smaller startups: You typically face multiple stakeholders with sometimes contradicting incentives, often combined with a big portion of risk avoidance. In such committee-like environments, no one can take full ownership and “just decide” requirements - instead, solutions are discussed until everyone agrees. This often leads to extremely complex solutions with the risk of missing the point.

这种约束使整个问题变得更加困难。我认为这是与小型初创公司相比，大公司变革更加困难的一个副作用：你通常会面对多个利益相关者，他们的动机有时会相互矛盾，而且通常会结合很大一部分风险规避。在这种类似于委员会的环境中，没有人可以拥有完全的所有权并“只决定”需求——相反，解决方案将被讨论直到每个人都同意为止。这通常会导致极其复杂的解决方案，并有可能错过重点。

> This part of the story reminded me of the [“Remember the Vasa!” paper by Bjarne Stroustrup in the C++ committee](https://www.stroustrup.com/P0977-remember-the-vasa.pdf). The [Wikipedia article about the Vasa story](https://en.wikipedia.org/wiki/Vasa_(ship)) is also worth reading.
> 
> 故事的这一部分让我想起了“记住瓦萨！” Bjarne Stroustrup 在 C++ 委员会发表的论文。关于瓦萨故事的维基百科文章也值得一读。

## Technical Problem Description 技术问题描述

![Many systems are exclusively designed for use by humans](im-not-a-robot.webp)

The manual process that should be automated, starts with installing a release candidate image on a laptop, then booting into the installed OS. From there, all the basic things like network/internet access, display support, suspend-resume support, video playback performance, etc., etc. had to be tested. The whole test process resembled multiple phases of a typical day in the life of the product:

应该自动化的手动过程首先是在笔记本电脑上安装候选发布映像，然后启动到已安装的操作系统。从那里开始，必须测试所有基本的东西，如网络/互联网访问、显示支持、暂停-恢复支持、视频播放性能等。整个测试过程类似于产品生命周期中典型一天的多个阶段：

-   The image is installed on the laptop under test (unattended USB installer)  
    该图像安装在被测笔记本电脑上（无人值守的 USB 安装程序）  
    
-   The laptop gets power cycled and boots into the OS  
    笔记本电脑重新启动并启动进入操作系统  
    
-   LAN and Wi-Fi connectivity are verified  
    LAN 和 Wi-Fi 连接已验证  
    
-   external screens are plugged, in different variations:  
    外部屏幕被插入，有不同的变化：  
    -   different order of plugging 不同的插拔顺序
    -   unplugging all screens must result in an automatic system suspend, if and only if the laptop lid is closed  
        拔下所有屏幕必须导致系统自动挂起，当且仅当笔记本电脑盖子关闭时  
        
    -   the system has to properly wake up with/without external screens when the power button is actuated or respectively the laptop lid was opened
        
        当启动电源按钮或分别打开笔记本电脑盖子时，系统必须在有/没有外部屏幕的情况下正确唤醒
        
-   VMs are launched, and their network connectivity verified  
    启动 VM，并验证其网络连接  
    
-   Multiple display resolutions have to be tried and verified that each tested display model shows the right picture (multi-display context: orientation and ordering) with the right resolution
    
    必须尝试并验证多种显示分辨率，以确保每个测试的显示模型以正确的分辨率显示正确的图片（多显示上下文：方向和排序）
    
-   HD Videos are launched inside/outside VMs and verified for playback with good frame rate  
    高清视频在 VM 内部/外部启动，并经过验证可以以良好的帧速率播放  
    

After the iterative process of thinking of and proposing solutions, the following technical requirements for the automatic test process were defined:

经过反复思考和提出解决方案的过程，定义了以下自动化测试流程的技术需求：

-   Network access via both cable and Wi-Fi has to be verified  
    必须验证通过电缆和 Wi-Fi 进行的网络访问  
    
-   Plugging in and out displays must happen physically, i.e. the electric cable contact shall be cut instead of doing it in software or switching off the displays
    
    插入和拔出显示器必须以物理方式进行，即应切断电缆触点，而不是在软件中进行或关闭显示器
    
-   Similar to the displays, laptop docking and undocking must look from a hardware perspective as if happened physically  
    与显示器类似，笔记本电脑对接和断开连接必须从硬件的角度来看，就好像发生在物理上一样  
    
-   Laptop lid closing and opening must happen physically  
    笔记本电脑盖子的关闭和打开必须通过物理方式进行  
    
-   Automated installation of the test image may be performed via network boot  
    可以通过网络启动自动安装测试映像  
    
-   The product including software and hardware must not differ from the shipped production version for the test as this would impede the validity of the test results. The only exceptions are:
    
    包括软件和硬件在内的产品不得与用于测试的发货生产版本不同，因为这会影响测试结果的有效性。唯一的例外是：
    
    -   Remote control of operating system and applications can be done via a specific service (developed and used by the project partner’s development department) that is reachable via serial line
        
        操作系统和应用程序的远程控制可以通过可通过串行线访问的特定服务（由项目合作伙伴的开发部门开发和使用）完成
        
    -   We can solder an electrical cable to the power buttons of the laptop models to simulate users powering the device on/off and suspending to RAM, as [Intel AMT](https://en.wikipedia.org/wiki/Intel_Active_Management_Technology) was disabled for security reasons
        
        我们可以将电缆焊接到笔记本电脑型号的电源按钮，以模拟用户打开/关闭设备电源和挂起到 RAM，因为出于安全原因禁用了 Intel AMT
        
-   The _real physical_ display output has to be captured for different display models  
    必须为不同的显示模型捕获真实的物理显示输出  
    -   For this reason, video capture devices as HDMI/DP grabbers were ruled out by the project partner  
        出于这个原因，项目合作伙伴排除了作为 HDMI/DP 采集器的视频捕获设备  
        

The result must provide the users (Developer, QA specialist) a REST interface to upload an installer image and trigger a full test run. After the test has finished, the test results must be available for download. In the beginning, the result document must be human-readable, printable HTML (and in that sense, signable). All screenshots and videos must be attached to it as proof. In the future, this would happen without human interaction, and instead being triggered by CI pipelines as part of a quality gate that each product change must go through.

结果必须为用户（开发人员、QA 专家）提供一个 REST 接口来上传安装程序映像并触发完整的测试运行。测试完成后，测试结果必须可供下载。一开始，结果文档必须是人类可读、可打印的 HTML（从这个意义上说，是可签名的）。必须附上所有屏幕截图和视频作为证明。将来，这将在没有人为干预的情况下发生，而是由 CI 管道触发，作为每个产品变更必须通过的质量门的一部分。

## Solution 解决方案

The prototype design we came up with, roughly followed this schema:  
我们想出的原型设计，大致遵循这样的模式：  

![Schematic System and Display Test Setup](multi-display-setup.png)

The **Test Controller** was a normal Linux computer with enough USB plugs and bandwidth to withstand multiple USB webcam HD streams and a serial cable adapter. It also had to have two LAN connections: One to the system under test for DHCP, PXE boot, and general network gateway, as well as one to the outside that provides the REST interface. Also, it had to provide Wi-Fi to be configured as an access point.

测试控制器是一台普通的 Linux 计算机，具有足够的 USB 插头和带宽来承受多个 USB 网络摄像头高清流和一个串行电缆适配器。它还必须有两个 LAN 连接：一个连接到用于 DHCP、PXE 启动和通用网络网关的被测系统，以及一个连接到提供 REST 接口的外部。此外，它必须提供 Wi-Fi 才能配置为接入点。

The **I/O Control** module was a Raspberry Pi due to its easily programmable general-purpose I/O ports and USB OTG functionality. The USB OTG functionality was not yet used in the prototype. In later versions, it should be used for booting official installer images via USB.

I/O 控制模块是一个 Raspberry Pi，因为它具有易于编程的通用 I/O 端口和 USB OTG 功能。 USB OTG 功能尚未在原型中使用。在以后的版本中，它应该用于通过 USB 启动官方安装程序映像。

The first physical setup was just enough to verify the feasibility of the whole project as quickly as possible:  
第一次物理设置足以尽快验证整个项目的可行性：  

![Physical Prototype System and Display Test Setup: The odd part of this project are these hand-crafted display frames that hold the webcams in the right place.](setup.jpg)

The most important hardware setup details are:  
最重要的硬件设置细节是：  

-   The display port switch was a hardware Y-switch with a button that was connected to the Raspi’s [GPIO ports](https://en.wikipedia.org/wiki/General-purpose_input/output)
    
    显示端口开关是一个硬件 Y 型开关，带有一个连接到 Raspi 的 GPIO 端口的按钮
    
-   For HDMI, which was more complicated because [HDMI is encrypted](https://en.wikipedia.org/wiki/HDMI#Content_protection_(HDCP)), we did not find such devices, so we used a remote-controllable HDMI switch. It turned out that this device was _not_ matching the requirements. The project partner accepted that we design a new board that fits the requirements as a follow-up after this prototype.
    
    对于HDMI，由于HDMI是加密的，比较复杂，我们没有找到这样的设备，所以我们使用了一个可远程控制的HDMI开关。结果发现这个设备不符合要求。项目合作伙伴接受我们设计一个符合要求的新电路板作为此原型之后的后续产品。
    
-   The docking station’s power plug state was controlled via a remote-controllable power socket  
    扩展坞的电源插头状态通过远程控制电源插座进行控制  
    
-   The webcams were simply mounted on quick-to-build aluminum frames. These were the most unusual part of the whole setup and regularly drew intrigued looks. The bigger the screen, the bigger the minimal distance of the webcam to the screen had to be to fully capture the full display. Being made of aluminum and very light wood, the displays would not tilt under the webcam’s weight.
    
    网络摄像头被简单地安装在快速组装的铝制框架上。这些是整个设置中最不寻常的部分，经常吸引好奇的目光。屏幕越大，网络摄像头到屏幕的最小距离就必须越大，才能完全捕捉到完整的显示画面。显示屏由铝和非常轻的木材制成，不会因网络摄像头的重量而倾斜。
    

The last detail is how we automated the laptop lid opening and closing. Most laptops have a [hall sensor](https://en.wikipedia.org/wiki/Hall_effect_sensor), so we installed an electromagnet that could be triggered by another one of the raspi’s GPIO pins:

最后一个细节是我们如何自动打开和关闭笔记本电脑的盖子。大多数笔记本电脑都有一个霍尔传感器，所以我们安装了一个电磁铁，它可以被 raspi 的另一个 GPIO 引脚触发：

![Most laptop lids have Hall Sensors that can be triggered with magnets](laptop-lid-magnet.png)

After all physical setup and connections were put in place, the remaining work was “only” software. Setting up the raspberry so that it would accept I/O commands over network, and the test controller so that it would be a DHCP and PXE boot server, control all the webcams, the Raspberry Pi, the remote power socket, etc. was a lot of system configuration. Using [NixOS](https://nixos.org/), the configuration of both systems was simple and could be performed in a short time with only a few hundred lines of NixOS configuration modules. The best thing about this approach was that we could commit the configuration with the code, and it was trivially reproducible on other machines.

在所有物理设置和连接就位后，剩下的工作“只有”软件。设置树莓派使其接受网络上的 I/O 命令，并设置测试控制器使其成为 DHCP 和 PXE 启动服务器，控制所有网络摄像头、树莓派、远程电源插座等。很多系统配置。使用 NixOS，两个系统的配置都很简单，只需几百行 NixOS 配置模块即可在短时间内完成。这种方法最好的一点是我们可以使用代码提交配置，而且它可以在其他机器上轻松重现。

The bulk of the work was now in the software development of a service that runs a REST interface to accept uploads of new installer images, creates and schedules test runs from those, and then executes them. The professionals in the project partner’s department who would later work with this were already familiar with the Python language and ecosystem. This made Python a natural choice.

现在的大部分工作是在服务的软件开发中，该服务运行 REST 接口以接受新安装程序映像的上传，从中创建和安排测试运行，然后执行它们。项目合作伙伴部门中后来从事此工作的专业人员已经熟悉 Python 语言和生态系统。这使得 Python 成为自然的选择。

### Display Resolution Verification 显示分辨率验证

How to determine if a screen shows the right display solution? Typically, one would query the X/Wayland server or video driver for this information. Previously, it was common to check this manually during the manual test phase: If the resolution was wrong, the experienced human tester would be able to recognize this at the first glance. In the end, the prototype had to verify that with the selected display model, the resolution that is visible to the end user is _really_ the one that the driver claims.

如何判断一个屏幕是否显示正确的显示方案？通常，人们会向 X/Wayland 服务器或视频驱动程序查询此信息。以前，通常是在手动测试阶段手动检查：如果分辨率有误，经验丰富的人工测试人员一眼就能识别出来。最后，原型必须使用选定的显示模型验证最终用户可见的分辨率是否确实是驱动程序声称的分辨率。

To accomplish this task, the following problems had to be solved in that order:  
要完成此任务，必须按顺序解决以下问题：  

1.  Take a photo of the physical display using the mounted webcam  
    使用安装的网络摄像头拍摄物理显示器的照片  
    
2.  Identify the display’s corners and normalize the photo, so it contains only the display’s “screenshot” portion  
    识别显示器的角落并对照片进行标准化处理，使其仅包含显示器的“屏幕截图”部分  
    
3.  Evaluate the screenshot’s content: Is it the right picture and resolution?  
    评估屏幕截图的内容：图片和分辨率是否正确？  
    

Steps 1 and 2 were straightforward as the test controller could dictate what the laptop under test should display on which screen. This way the test script would ask the OS under test to set up the screen(s) with specific ordering and resolutions and then display some test images for further verification.

第 1 步和第 2 步非常简单，因为测试控制器可以指示被测笔记本电脑应该在哪个屏幕上显示什么。这样，测试脚本会要求被测操作系统设置具有特定顺序和分辨率的屏幕，然后显示一些测试图像以供进一步验证。

We chose to use the Python version of the [OpenCV](https://opencv.org/) library, which provides [ArUco codes](https://docs.opencv.org/4.x/d5/dae/tutorial_aruco_detection.html) and image recognition functions to detect them:

我们选择使用 Python 版本的 OpenCV 库，它提供了 ArUco 代码和图像识别功能来检测它们：

![Example ArUco Markers from docs.opencv.org](aruco-markers-example.jpg)

Different information can be extracted from detected ArUco codes on photos:  
可以从照片上检测到的 ArUco 代码中提取不同的信息：  

The code’s ID 代码的ID

This can be freely chosen depending on the number of “blocks” the code consists of. To choose the number of blocks, library users would select so-called ArUco dictionaries. Dictionaries with bigger blocks are easier to detect even on bad photos or from a far distance but transport smaller ranges of ID numbers.

这可以根据代码包含的“块”的数量自由选择。要选择块数，图书馆用户会选择所谓的 ArUco 词典。具有较大块的字典即使在质量差的照片上或从很远的距离也更容易检测到，但传输的 ID 号范围较小。

The pixel position of all the corners of each code  
每个代码所有角的像素位置  

The size or distance can be calculated from those  
大小或距离可以从那些计算  

The code’s geometric orientation as a euclidean XYZ-vector  
代码的几何方向作为欧几里德 XYZ 向量  

In our case, this was useful for normalizing slightly crooked photos, as the mounted webcam is never perfectly aligned  
在我们的例子中，这对于规范化轻微弯曲的照片很有用，因为安装的网络摄像头永远不会完全对齐  

![Detected ArUco markers with added orientation docs.opencv.org](aruco-markers-orientation-example.jpg)

So, to quickly evaluate how well OpenCV would work for us, I printed an ArUco code and glued it onto my vacuum bot at home. Then, I wrote an OpenCV script that “normalizes” the image in a way that the ArUco code gets translated to the middle of the output image:

因此，为了快速评估 OpenCV 对我们的效果如何，我打印了一个 ArUco 代码并将其粘在家里的真空机器人上。然后，我编写了一个 OpenCV 脚本，以将 ArUco 代码转换到输出图像中间的方式“规范化”图像：

<iframe width="1000" height="400" src="https://www.youtube.com/embed/d6SpXS115fg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen="" data-immersive-translate-mark="1"></iframe>

Left side: The original video. Right side: The “corrected” version of the same video with the intention to always have the ArUco code upright and straight in the video.

左侧：原始视频。右侧：同一视频的“修正”版本，目的是让 ArUco 代码在视频中始终保持直立。

The vacuum bot proof-of-concept was more a fun project for me than a serious demonstrator for display-corner detection. To present the project partner with how solid this approach would be, I created the next demo, which was more relevant for actual screen recording. The script turned out to be robust in such extreme examples. Our use case would be “boring” in contrast.

vacuum bot 概念验证对我来说是一个有趣的项目，而不是用于显示角检测的严肃演示程序。为了向项目合作伙伴展示这种方法的可靠性，我创建了下一个演示，它与实际的屏幕录制更相关。在这样的极端例子中，脚本被证明是健壮的。相比之下，我们的用例将是“无聊的”。

<iframe width="1000" height="280" src="https://www.youtube.com/embed/pCcIABQVBUU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen="" data-immersive-translate-mark="1"></iframe>

Left side: The original video. Right side: The “corrected” version of the same video with the intention to always have a straight view of the display’s content.

左侧：原始视频。右侧：同一视频的“更正”版本，目的是始终直视显示的内容。

So that was steps 1 and 2. How to verify the display resolution? We did this:  
这就是第 1 步和第 2 步。如何验证显示分辨率？我们这样做了：  

![Test Pilot Image with Display Resolution Encoding: The green numbers show how we encoded the information that the display ought to have a resolution of 1920x1080 pixels. The “primary” bit was for differentiating between different displays.](pilot-image.png)

We decomposed the image resolution to transport it encoded in the IDs of multiple ArUco codes, which then could easily be composed back from the webcam photos.

我们分解了图像分辨率，将其编码为多个 ArUco 代码的 ID，然后可以很容易地从网络摄像头照片中组合回来。

> At this point, this information was redundant because the test system already knew at any point in time which display resolution it is testing. However, adding some redundancy allowed us to greatly decompose the system’s parts into more independent and reusable modules.
> 
> 此时，此信息是多余的，因为测试系统在任何时间点都已经知道它正在测试的显示分辨率。然而，添加一些冗余使我们能够将系统的各个部分大大分解为更独立和可重用的模块。

From knowing the nominal display resolution, we can calculate how many percent of the picture the black ArUco code square size may occupy. This is even possible without knowing the display’s physical size. Fortunately, algorithms like this are trivially unit-testable with synthesized and real-life input samples.

知道了标称显示分辨率，我们就可以计算出黑色ArUco代码方块大小可能占图片的百分之多少。这甚至在不知道显示器的物理尺寸的情况下也是可能的。幸运的是，像这样的算法可以用合成的和现实生活中的输入样本进行简单的单元测试。

Another remaining problem was that the webcams tried to automatically refocus and readjust contrast whenever the display content changed (especially from dark to bright or the other way around), and often would not find the focus for a long time. Even on really bad photos, the ArUco codes with big blocks were easy to identify, so it was technically very easy to distinguish if the display is already displaying the right content, _but_ the webcam has still not finished re-focusing. The firmware does officially allow disabling autofocus via the [V4L](https://www.kernel.org/doc/html/v4.8/media/v4l-drivers/index.html) interface, but it did not work for us - it was unclear to us if this was due to the camera model, a firmware bug, or whatever. In the limited project time, we made it work with robust error handling and wait phases. These could simply be dropped in future efforts of fixing the autofocus.

另一个遗留问题是，每当显示内容发生变化（尤其是从暗到亮或相反）时，网络摄像头会尝试自动重新聚焦和重新调整对比度，并且通常会长时间找不到焦点。即使在非常糟糕的照片上，带有大块的 ArUco 代码也很容易识别，因此在技术上很容易区分显示器是否已经在显示正确的内容，但网络摄像头仍未完成重新对焦。固件确实允许通过 V4L 接口禁用自动对焦，但它对我们不起作用——我们不清楚这是由于相机型号、固件错误还是其他原因造成的。在有限的项目时间内，我们让它与强大的错误处理和等待阶段一起工作。这些可以在未来修复自动对焦的工作中简单地删除。

### Automatic Frame Drop Detection 自动丢帧检测

To check if video playback is fluid, we had to select an approach where the video itself can be chosen by the project partner’s customers: If end-users experience some video to be stuttering, the partner desired to be able to embed it in their testing to give developers a way to verify their fix.

为了检查视频播放是否流畅，我们必须选择一种方法，让项目合作伙伴的客户可以选择视频本身：如果最终用户体验到某些视频卡顿，合作伙伴希望能够将其嵌入到他们的测试中为开发人员提供一种方法来验证他们的修复。

We wrote code that takes the provided video and slightly adapts it by adding multiple ArUco codes. By defining how fast (i.e. how many pixels per frame) the ArUco codes move, we were able to determine if and how many frames were dropped during playback.

我们编写的代码采用提供的视频并通过添加多个 ArUco 代码对其进行稍微调整。通过定义 ArUco 代码移动的速度（即每帧多少像素），我们能够确定播放期间是否丢失了帧以及丢失了多少帧。

<iframe width="1000" height="575" src="https://www.youtube.com/embed/y2YUuynf9AE" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen="" data-immersive-translate-mark="1"></iframe>

The ArUco codes move at a predefined speed. This video has artificial stutters added to test the accuracy of the algorithm.

ArUco 代码以预定义的速度移动。该视频添加了人工口吃以测试算法的准确性。

As the display’s and the webcam’s image buildup are not synchronized, there’s some probability for one or the other frame to contain a distorted ArUco code. So we added four codes of which the majority stays undistorted, which made the frame drop detection very solid on every frame.

由于显示器和网络摄像头的图像构建不同步，因此一个或另一个帧可能包含失真的 ArUco 代码。所以我们添加了四个代码，其中大部分保持不失真，这使得帧丢失检测在每一帧上都非常可靠。

During manual testing, testers were able to say if a video stutters or not, and maybe quantify it by “stutters a lot” or “only a bit”. The output of the algorithm allowed us to count the _frequency_ of frame drops as well as the _quantity_ of dropped frames. Objective quality metrics using histograms could be considered from this point, which enhances the whole QA phase through rich automatic quantitative analysis. We did not go too crazy on the analysis here because it was yet unclear which exact metrics developers would later ask for (if at all) when analyzing low frame rates.

在手动测试期间，测试人员能够判断视频是否卡顿，并可能通过“卡顿很多”或“只有一点”来量化。该算法的输出使我们能够计算丢帧的频率以及丢帧的数量。可以从这一点考虑使用直方图的客观质量指标，通过丰富的自动定量分析增强整个 QA 阶段。我们在这里的分析并没有太过疯狂，因为尚不清楚开发人员稍后在分析低帧速率时会要求（如果有的话）哪些确切指标。

## Learnings 学识

The whole project took roughly three months. The parts that were initially thought to be the most complex - the image & video processing - were done in a few weeks, including all trial & error.

整个项目大约耗时三个月。最初被认为是最复杂的部分——图像和视频处理——在几周内就完成了，包括所有的试错。

There was no _specific_ part that contributed the most complexity - it was the mix of all disciplines: System setup, network (LAN and Wi-Fi) configuration, dynamic network boot, control of primitive I/O, photo and video stream capture, remote control, VM configuration, etc., etc. Setting up a system with so many moving parts is simply complex.

没有哪个特定部分的复杂性最高——它是所有学科的混合：系统设置、网络（LAN 和 Wi-Fi）配置、动态网络启动、原始 I/O 控制、照片和视频流捕获、远程控制、虚拟机配置等等。设置一个有这么多活动部件的系统非常复杂。

Maybe the most important consideration that went into all spots of all library code that was written for this project, was **error handling**. In this project, errors could come from _everywhere_: Some cable might get loose, some network connection might not work, some webcam might need extraordinarily long to focus, some VM might start up with abnormal delay, the Wi-Fi connection takes longer than normal despite lab conditions, etc. - all the cases needed to be handled with care.

在为这个项目编写的所有库代码的所有位置，可能最重要的考虑是错误处理。在这个项目中，错误可能无处不在：一些电缆可能松动，一些网络连接可能无法正常工作，一些网络摄像头可能需要特别长的时间才能聚焦，一些虚拟机可能启动异常延迟，Wi-Fi 连接时间比正常时间长尽管有实验室条件等 - 所有情况都需要小心处理。

We rigorously worked on the clean discrimination between two general kinds of errors:  
我们严格区分两种常见错误：  

-   Infrastructure failures: The test setup failed, not the product under test.  
    基础设施故障：测试设置失败，而不是被测产品。  
    
-   Test failures: The product under test behaves incorrectly, hence a bug is discovered.  
    测试失败：被测产品行为不正确，因此发现了错误。  
    

![](prove-improve.webp)

The whole prototype had to be rock solid in all cases every single time. Flaky test infrastructure eventually results in more cost than value. The project was part of an effort to optimize the overall throughput of the development and QA departments. Running such an automatism for years and gaining experience with it would expose further optimization potential. To facilitate that this proof-of-concept is just the start of an ongoing journey to faster and more reliable testing, it had to be designed in a way that it is obvious at all times where things fall apart, and how often. With this information, the operators of such automatic infrastructure would be able to fix outages as fast as possible, and also improve its mechanisms to continuously reduce failure potential.

在所有情况下，整个原型每次都必须坚如磐石。不稳定的测试基础设施最终会导致成本大于价值。该项目是优化开发和 QA 部门整体吞吐量的努力的一部分。多年来运行这样的自动化并获得经验将揭示进一步的优化潜力。为了促进这种概念验证只是持续进行更快、更可靠的测试之旅的开始，它的设计方式必须能够在任何时候都清楚地表明哪里出了问题，以及出现问题的频率。有了这些信息，此类自动化基础设施的运营商将能够尽快修复中断，并改进其机制以持续减少故障可能性。

Every line of code that makes the product more testable saves you hundreds and thousands of lines of testing code. So far, _testability_ was mostly considered on the level of unit tests, but looking at higher levels of the integration chain, testability as a concept vanished more and more. This is understandable, considering that programmers have less and less influence the farther away the integration of their components is away from them - but in the end, it’s only the programmers who can make a software product testable as this has to happen at the beginning, in the code. If not only builds and unit tests but the integration of components is within reach for software developers, it starts to make sense to put the design of higher-level integration tests into their definition of done. This is, of course, the idea of putting _Dev_ and _Ops_ together to _DevOps_. In many companies, this is more said than done, because management is not made aware or does not understand the commitment and restructuring of departments that this requires. _Restructuring_ as a word is also mostly frowned upon by all participating parties.

使产品更具可测试性的每一行代码都可以为您节省成百上千行测试代码。到目前为止，可测试性主要是在单元测试的层面上考虑的，但是从集成链的更高层次来看，可测试性作为一个概念越来越消失了。这是可以理解的，考虑到程序员的影响力越来越小，组件的集成离他们越远 - 但最终，只有程序员才能使软件产品可测试，因为这必须在一开始就发生，在代码中。如果不仅构建和单元测试而且组件的集成对于软件开发人员来说都是触手可及的，那么将更高级别的集成测试的设计纳入他们的完成定义就开始有意义了。这当然是将 Dev 和 Ops 放在一起的想法 DevOps。在许多公司中，这说的比做的多，因为管理层没有意识到或不理解这需要部门的承诺和重组。重组这个词也大多被所有参与方所反对。

Talking about integration and ops of products: This new test automatism was in some sense a little product itself that needs continuous improvement, integration, and deployment, too. A big stack of Python code (we also reused some existing C++ and Haskell code) is not yet a running deployment. But this turned out to be rather simple due to our technology choice: Interestingly, using [NixOS](https://nixos.org/) helped us a **lot** in defining what the running configuration looks like. Finishing this product in this time frame with something else than the dependency and package management of nix, as well as the compositional way to define system configurations of NixOS, is hardly imaginable. While developing complex scripts that operate on many different technical domains, nix also helped us with its [huge and up-to-date package collection](https://repology.org/repositories/graphs). Duplicating the lab setup with slightly different hardware in the project partner’s lab was a smooth process due to the nature of NixOS configurations.

谈论产品的集成和操作：这种新的测试自动化在某种意义上是一个小产品本身，也需要不断改进、集成和部署。一大堆 Python 代码（我们还重用了一些现有的 C++ 和 Haskell 代码）尚未运行部署。但由于我们的技术选择，这变得相当简单：有趣的是，使用 NixOS 对我们定义运行配置的外观有很大帮助。在这个时间框架内完成这个产品，除了 nix 的依赖和包管理，以及定义 NixOS 系统配置的组合方式，是很难想象的。在开发在许多不同技术领域运行的复杂脚本时，nix 还通过其庞大的最新包集合帮助我们。由于 NixOS 配置的性质，在项目合作伙伴实验室中使用略有不同的硬件复制实验室设置是一个顺利的过程。

## Summary 概括

The project acceptance meeting and its big demo were delightful and fun for both sides. The project partner was happy that it all worked out as planned and accepted the follow-ups that resulted from building the prototype. We were happy with how well it went and the amount of complexity we got under control with a relatively slick system design.

项目验收会和大型演示让双方都感到愉快和有趣。项目合作伙伴很高兴一切都按计划进行，并接受了构建原型所产生的后续行动。我们对它的进展情况以及我们通过相对灵活的系统设计控制的复杂性感到满意。

![](production.webp)

Apart from the follow-ups, it is now in their hands to run and integrate this automated test infrastructure deeper into their processes, and scale it up over time in the ongoing quest to increase the overall throughput of their software pipeline. Whenever the next improvement or reorganization comes along, we stand by as a helping partner.

除了后续行动之外，现在由他们来运行这个自动化测试基础设施并将其更深入地集成到他们的流程中，并随着时间的推移扩大它，以不断寻求增加他们软件管道的整体吞吐量。每当下一次改进或重组出现时，我们都会作为帮助伙伴随时待命。

I think it is very important to understand that [shift-left testing](https://en.wikipedia.org/wiki/Shift-left_testing), [SCRUM](https://en.wikipedia.org/wiki/Scrum_(software_development)), [Extreme Programming](https://en.wikipedia.org/wiki/Extreme_programming), [Agile](https://en.wikipedia.org/wiki/Agile_software_development) and [Lean](https://en.wikipedia.org/wiki/Lean_software_development) software development, etc. are not approaches that work well with short-term actionism. If you encounter problematic releases, quality problems, or eternal lead times for new features and bug fixes in your company, then this is most certainly not solvable with short projects that are thrown on the problem. The solution always lies in the change of existing structures: Such problems are often just a symptom of the fact that the existing structures no longer scale on the current level. Changing structures is very problematic, especially in big companies, and can not result in perfection after the first step. External helpers with new perspectives can help with the question of _what_ scalable structures for your situation look like and _how_ to get there step by step.

我认为了解左移测试、SCRUM、极限编程、敏捷和精益软件开发等都不是适合短期行动主义的方法非常重要。如果您在公司中遇到有问题的发布、质量问题或新功能和错误修复的永恒交货期，那么这肯定无法通过针对该问题的短期项目来解决。解决方案始终在于改变现有结构：此类问题通常只是现有结构不再在当前水平上扩展这一事实的征兆。改变结构是非常有问题的，尤其是在大公司，并且不可能在第一步之后达到完美。具有新视角的外部帮助者可以帮助解决以下问题：适合您的情况的可扩展结构是什么样的以及如何逐步实现。
