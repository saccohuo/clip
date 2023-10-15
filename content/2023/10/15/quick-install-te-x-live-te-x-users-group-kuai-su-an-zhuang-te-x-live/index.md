---
title: "TeX Live - Quick install for Unix | TeX Live - 用于 Unix 的快速安装"
date: 2023-10-15T14:24:39+08:00
updated: 2023-10-15T14:24:39+08:00
taxonomies:
  tags: []
extra:
  source: chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/_generated_background_page.html
  hostname: ppllidagbplgbhkogcabhendhefjcmea
  author: 
  original_title: "Quick install - TeX Live - TeX Users Group --- 快速安装 - TeX Live"
  original_lang: und
---

    Quick install - TeX Live - TeX Users Group --- 快速安装 - TeX Live - TeX 用户组  set 限制解除

## TeX Live - Quick install for Unix  

TeX Live - 用于 Unix 的快速安装

If you don't want to bother reading the [full install documentation](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/texlive-en/texlive-en.html#installation) and just want to install everything in TeX Live, on a Unix-like system, a minimal recipe follows.  

如果你不想费力阅读完整的安装文档，只想在类似 Unix 的系统上安装 TeX Live 中的所有内容，下面是一个最简单的方法。

-   For macOS (and MacOSX), we recommend installing [MacTeX](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/mactex/), which contains all of TeX Live (and a few Mac-specific additions).  
    
    对于 macOS（和 MacOSX），我们建议安装 MacTeX，它包含 TeX Live 的全部内容（以及一些 Mac 专用的附加功能）。
-   Cygwin users can follow the instructions for Unix-like systems, but make sure you have the [Cygwin prerequisites](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/texlive-en/texlive-en.html#cygwin) before beginning the installation.  
    
    Cygwin 用户可以按照类 Unix 系统的说明进行操作，但在开始安装之前，请确保已具备 Cygwin 的先决条件。
-   Other Windows users: please consult the [TeX Live on Windows page](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/windows.html) instead.  
    
    其他 Windows 用户：请查阅 Windows 上的 TeX Live 页面。

For more details on the commands given here, just keep scrolling down this page.  

有关此处提供的命令的更多详情，请继续向下滚动本页。

### tl;dr: Unix(ish)

Non-interactive default installation on anything but Windows:  

除 Windows 系统外，在其他系统上均为非交互式默认安装：

1.  cd /tmp # working directory of your choice  
    
    cd /tmp # 您选择的工作目录
2.  wget [https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz](https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz) \# or curl instead of wget
3.  zcat < install-tl-unx.tar.gz | tar xf -
4.  cd install-tl-\*
5.  perl ./install-tl --no-interaction # as root or with [writable destination](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/_generated_background_page.html#running)
6.  Finally, prepend /usr/local/texlive/YYYY/bin/PLATFORM to your PATH,  
    
    最后，在 PATH 中添加 /usr/local/texlive/YYYY/bin/PLATFORM 、  
    
    e.g., /usr/local/texlive/2023/bin/x86\_64-linux 例如， /usr/local/texlive/2023/bin/x86\_64-linux

Changing defaults:  更改默认设置：

-   The default paper size is a4. If you want the default to be letter, add \--paper=letter to the install-tl command.  
    
    默认纸张尺寸为 a4。如果希望默认为 Letter，请在 install-tl 命令中添加 \--paper=letter 。
-   By default, everything is installed (7+GB).  
    
    默认情况下，所有内容都已安装（7+GB）。
    -   To install a smaller scheme, pass \--scheme=_scheme_ to install-tl. For example, \--scheme=small corresponds to the [BasicTeX variant of MacTeX](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/mactex/morepackages.html).  
        
        要安装较小的方案，请将 \--scheme= 方案传递给 install-tl 。.例如， \--scheme=small 对应 MacTeX 的 BasicTeX 变体。
    -   To omit installation of the documentation resp. source files, pass \--no-doc-install \--no-src-install to install-tl.  
        
        要省略文档和源文件的安装，请通过 \--no-doc-install \--no-src-install 到 install-tl 。.
-   To change the main installation directories (rarely needed), add \--texdir=/install/dir to the install-tl command. To change the location of the per-user directories (where TEXMFHOME and others will be found), specify \--texuserdir=/your/dir.  
    
    要更改主安装目录（很少需要），请在 install-tl 命令中添加 \--texdir=/install/dir 。要更改每个用户目录的位置（TEXMFHOME 和其他目录的位置），请指定 \--texuserdir=/your/dir .
-   To change anything and everything else, omit the \--no-interaction. Then you are dropped into an interactive installation menu.  
    
    要更改任何其他内容，请省略 \--no-interaction 。.然后就会进入交互式安装菜单。

### tl;dr: Mac 简要说明：Mac

The Unix instructions work. If you prefer a native Mac installer, use [MacTeX](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/mactex/) instead.  

使用 Unix 说明即可。如果你更喜欢 Mac 原生安装程序，请使用 MacTeX。

### tl;dr: Windows

1.  Download [https://mirror.ctan.org/systems/texlive/tlnet/install-tl-windows.exe](https://mirror.ctan.org/systems/texlive/tlnet/install-tl-windows.exe)  
    
    下载 https://mirror.ctan.org/systems/texlive/tlnet/install-tl-windows.exe
2.  Execute the newly-downloaded install-tl-windows.exe.  
    
    执行新下载的 install-tl-windows.exe 。.
3.  Change settings as desired and install.  
    
    根据需要更改设置并安装。
4.  [Additional Windows-specific info](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/windows.html).  
    
    其他 Windows 专用信息

___

The rest of this page explains the above in more detail.  

本页其余部分将详细解释上述内容。

### Pre-install: download, cleanup  

预安装：下载、清理

You do not need to remove an installation of a previous release, or any system-provided TeX; multiple releases of TL can coexist on the same system without conflict.  

您不需要移除以前版本的安装，也不需要移除任何系统提供的 TeX；多个 TL 版本可以在同一系统上共存，而不会发生冲突。

A separate page describes [various ways to acquire the software](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/acquire.html). It boils down to either [getting the DVD](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/acquire-dvd.html) from a [TeX user group](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/usergroups.html) (ideally by [becoming a member](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/join.html)), or [downloading in various ways](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/acquire-netinstall.html). Except on Windows, your system must provide a standard Perl installation with the usual core modules. (For Windows, TeX Live comes with its own Perl.)  

另有一页介绍了获取软件的各种方法。归根结底，可以从 TeX 用户组（最好是成为成员）获得 DVD，或者通过各种方式下载。除 Windows 系统外，您的系统必须安装带有常用核心模块的标准 Perl。(对于 Windows，TeX Live 自带 Perl）。

For regular installations via download, we highly [recommend installing the LWP Perl package](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/acquire-netinstall.html#netlwp) if you don't have it.  

对于通过下载进行的常规安装，如果您没有 LWP Perl 软件包，我们强烈建议您安装该软件包。

If you're re-installing after a previous attempt, be sure to completely remove your failed installation. By default, this would be in these two directories (on Unix-like systems):  

如果您是在前一次尝试后重新安装的，请确保完全删除失败的安装。默认情况下，会在这两个目录中（在类 Unix 系统上）：

```
rm -rf /usr/local/texlive/2023
rm -rf ~/.texlive2023

```

### Running the installer 运行安装程序

You do not need to be root (administrator on Windows) to install, use, or manage TeX Live. Indeed, we recommend installing it as a normal user, except on macOS, where it's conventional to install as administrator. ([Information about shared installations](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/texlive-en/texlive-en.html#tlsharedinstall).) As always, you need to have permission to write into the destination directory, but TeX Live itself does not care if you are root or not.  

安装、使用或管理 TeX Live 不需要 root 用户（Windows 上为管理员）身份。事实上，我们建议以普通用户身份安装，但 macOS 除外，在 macOS 上，常规安装方式是以管理员身份安装（关于共享安装的信息）。(与往常一样，你需要有写入目标目录的权限，但 TeX Live 本身并不关心你是否是 root 用户。

Once you have the TeX Live distribution, run the [install-tl](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/install-tl.html) script to install (on Windows, install-tl-windows), like this:  

获得 TeX Live 发行版后，运行 install-tl 脚本进行安装（在 Windows 系统中， install-tl-windows ），如下所示：

```
cd /your/unpacked/directory
perl install-tl
[... messages omitted ...]
Enter command: i
[... when done, see below for post-install ...]
cd /your/unpacked/directory
perl install-tl
[... 消息省略...]
输入命令：i
[......完成后，请参阅下面的安装后......］

```

To change the installation directories or other options, read the prompts and instructions. The default is to install into parallel directories named by the release year, so that any given release can be run independently, merely by adjusting the search path.  

要更改安装目录或其他选项，请阅读提示和说明。默认情况下，程序会安装到按发布年份命名的并行目录中，因此只需调整搜索路径，就能独立运行任何特定版本。

### Interfaces to the installer: text, GUI, batch  

安装界面：文本、图形用户界面、批处理

The installer supports text, graphical, and batch interfaces:  

安装程序支持文本、图形和批处理界面：

-   install-tl -gui text  
    
    uses a plain text interface (command line) mode. This is the default on Unix-ish systems, including Macs.  
    
    使用纯文本界面（命令行）模式。这是包括 Mac 在内的 Unix 系统的默认模式。
-   install-tl -gui  
    
    is the default graphical GUI. At startup it offers very few options, but there is an ‘Advanced’ button for more configurability. This is the default on Windows and on Macs. It requires Tcl/Tk, which is present on pre-Monterey versions of MacOS and is provided for Windows.  
    
    是默认的图形用户界面。启动时提供的选项很少，但有一个 "高级 "按钮，可以进行更多配置。这是 Windows 和 Mac 的默认设置。它需要 Tcl/Tk，这在 MacOS 的前蒙特雷版本中就有，在 Windows 中也有提供。
-   install-tl --profile=_profile_  
    
    does a batch (unattended) installation. To create such a [profile file](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/install-tl.html#PROFILES), it's easiest to start with the tlpkg/texlive.profile file which the installer writes at the end of any successful installation.  
    
    进行批量（无人值守）安装。要创建这样的配置文件，最简单的方法是从 tlpkg/texlive.profile 文件开始，安装程序会在成功安装后写入该文件。

For information on all of the installer options, run install-tl --help, or see the [install-tl documentation page](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/install-tl.html).  

有关安装程序所有选项的信息，请运行 install-tl --help ，或查看 install-tl 文档页面。或查看 install-tl 文档页面。

### Choosing a download host  

选择下载主机

It can take an hour or more to copy all the files, depending on the installation method. If you are downloading over the network, by default a nearby [CTAN mirror](https://ctan.org/mirrors) is automatically chosen. If you have problems, we recommend choosing a specific mirror and then run install-tl --location http://mirror.example.org/ctan/path/systems/texlive/tlnet instead of relying on the automatic redirection.  

复制所有文件可能需要一个小时或更长时间，这取决于安装方法。如果通过网络下载，默认情况下会自动选择附近的 CTAN 镜像。如果遇到问题，建议选择特定镜像，然后运行 install-tl --location http://mirror.example.org/ctan/path/systems/texlive/tlnet 而不是依赖自动重定向。

### Post-install: setting PATH  

安装后：设置 PATH

After the installation finishes, you must add the directory of TeX Live binaries to your PATH—except on Windows, where the installer takes care of this. The installer shows the exact lines that should be added. As an example, for Bourne-compatible shells (e.g., in ~/.profile or ~/.bashrc):  

安装完成后，您必须将 TeX Live 二进制文件目录添加到您的 PATH 中--Windows 系统除外，安装程序会负责此工作。安装程序会显示应添加的确切行数。例如，对于兼容 Bourne 的 shell（如在 ~/.profile 或 ~/.bashrc 中）：  

  PATH=/usr/local/texlive/2023/bin/x86\_64-linux:$PATH  

Use the initialization file and syntax for your shell, your installation directory, and your binary platform name instead of x86\_64-linux. After editing the init file, log out and log back in.  

使用 shell、安装目录和二进制平台名称的初始化文件和语法，而不是 x86\_64-linux 。.编辑初始化文件后，注销并重新登录。

If you have multiple TeX installations on a given machine, you need to change the search path to switch between them—[except on MacOSX](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/mactex/multipletexdistributions.html).  

如果在一台机器上安装了多个 TeX，则需要更改搜索路径才能在它们之间切换--MacOSX 除外。

### Post-install: setting the default paper size  

安装后：设置默认纸张大小

The default is to configure the programs for the A4 paper size. To make the default be 8.5x11 letter-size paper, you can use the ‘o’ menu option before i(nstalling), or run tlmgr paper letter after installation (and after setting your PATH).  

程序默认配置为 A4 纸张大小。要将默认设置设为 8.5x11 Letter 尺寸的纸张，可以在安装前使用 "o "菜单选项，或在安装后运行 tlmgr paper letter （并设置 PATH）。

### Testing 测试

After a successful installation, please try processing simple test documents, such as latex small2e.  

安装成功后，请尝试处理简单的测试文档，如 latex small2e 。.

If you're looking for a front-end with which to edit files: TeX Live installs [TeXworks](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/texworks/) on Windows, and MacTeX installs [TeXShop](https://pages.uoregon.edu/koch/texshop/). A [plethora of dedicated TeX editors](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/interest.html#editors) are also available. In addition, any plain text editor will work.  

如果您正在寻找用于编辑文件的前端：TeX Live 可在 Windows 上安装 TeXworks，MacTeX 可安装 TeXShop。还有大量专用的 TeX 编辑器可供使用。此外，任何纯文本编辑器都可以使用。

### Getting updates 获取更新

If you want to update packages from CTAN after installation, see these [examples of using tlmgr](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/tlmgr.html#EXAMPLES). This is not required, or even necessarily recommended; it's up to you to decide if it makes sense to get continuing updates in your particular situation.  

如果您想在安装后从 CTAN 更新软件包，请参阅这些使用 tlmgr 的示例。这不是必须的，甚至不一定是推荐的；您可以自行决定在您的特定情况下继续获得更新是否有意义。

Typically the main binaries are not updated in TeX Live between major releases. If you want to get updates for LuaTeX and other packages and programs that aren't officially released yet, they may be available in the [TLContrib repository](http://contrib.texlive.info/), or you may need to [compile the sources](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/svn/) yourself.  

通常情况下，TeX Live 的主要二进制文件不会在重大版本之间更新。如果你想获得 LuaTeX 以及其他尚未正式发布的软件包和程序的更新，它们可能会在 TLContrib 软件源中提供，或者你可能需要自己编译源代码。

### Reporting problems 报告问题

Please see the [known issues](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/bugs.html) page for bug reporting info. And please [check the documentation](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/doc/texlive-en/texlive-en.html).  

有关错误报告信息，请参阅已知问题页面。请查看文档。

___

$Date: 2023/03/19 21:57:06 $; [TeX Live](chrome-extension://ppllidagbplgbhkogcabhendhefjcmea/index.html);  

日期：2023/03/19 21:57:06 $; TeX Live；
