---
title: 在 Visual Studio 中配置 Linux CMake 项目 | Microsoft Docs
description: 如何在 Visual Studio 中配置 Linux CMake 项目
ms.custom: ''
ms.date: 07/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 743f15cdb9fe8b0233f5b59ca399c0f47704d441
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269535"
---
# <a name="configure-a-linux-cmake-project"></a>配置 Linux CMake 项目

**Visual Studio 2017 版本 15.4 及更高版本**  
为 Visual Studio 安装 Linux C++ 工作负载时，会默认选中对 Linux 的 CMake 支持。 现在即可处理使用 CMake 的现有基本代码，无需将其转换为 Visual Studio 项目。 如果基本代码为跨平台代码，则从 Visual Studio 中可同时面向 Windows 和 Linux。

本主题假定你基本了解 Visual Studio 中的 CMake 支持。 有关详细信息，请参阅 [Visual C++ 的 CMake 工具](../ide/cmake-tools-for-visual-cpp.md)。 有关 CMake 本身的详细信息，请参阅[使用 CMake 生成、测试并打包软件](https://cmake.org/)。

> [!NOTE]  
> 使用 Visual Studio 中的 CMake 支持需要 CMake 3.8 中引入的服务器模式支持。 如果包管理器提供旧版 CMake，解决方法为[从源生成 CMake](#build-a-supported-cmake release-from-source)，或从官方 [CMake 下载页](https://cmake.org/download/)下载它。 如需支持 Visual Studio 中 [CMake 目标视图](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/)窗格的，由 Microsoft 提供的 CMake 变体，请在 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) 下载最新预生成二进制文件。

## <a name="open-a-folder"></a>打开文件夹

首先，依次选择主菜单中的“文件” > “打开” > “文件夹”，或在命令行中键入“`devenv.exe <foldername>`”。 打开的文件夹中应该有一个 CMakeLists.txt 文件，以及你的源代码。
以下示例显示了一个简单的 CMakeLists.txt 文件和 .cpp 文件：

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt：

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>选择 Linux 目标

只要打开文件夹，Visual Studio 就会分析 CMakeLists.txt 文件，并指定“x86 调试”以定目标到 Windows。 若要定目标到 Linux，请将项目设置更改为“Linux 调试”或“Linux 发布”。

默认情况下，Visual Studio 会选择“工具” > “选项” > “跨平台” > “连接管理器”下列表中的第一个远程系统。 如果未找到任何远程连接，那么系统会提示你进行创建。

指定 Linux 目标后，会将源复制到你的 Linux 计算机。 然后，CMake 在 Linux 计算机上运行，为项目生成 CMake 缓存。

![在 Linux 上生成 CMake 缓存](media/cmake-linux-1.png "Generate the CMake cache on Linux")

**Visual Studio 2017 版本 15.7 及更高版本：**  
为了向远程头提供 IntelliSense 支持，Visual Studio 会自动将远程头复制到本地 Windows 计算机上的目录中。 有关详细信息，请参阅[远程标头的 IntelliSense](configure-a-linux-project.md#remote_intellisense)。

## <a name="debug-the-project"></a>调试项目

若要在远程系统上调试代码，请设置断点，并在项目设置旁边的工具栏菜单中选择“CMake 目标”作为启动项，再选择工具栏中的“&#x23f5; 开始”，或按 F5。

若要自定义程序的命令行参数，请右键单击解决方案资源管理器中的可执行文件，并选择“调试和启动设置”。 这会打开或创建 launch.vs.json 配置文件，其中包含程序信息。 若要指定其他参数，请以 `args` JSON 数组形式添加它们。 有关详细信息，请参阅 [Visual C++ 中的“打开文件夹”项目](https://docs.microsoft.com/en-us/cpp/ide/non-msbuild-projects)。

## <a name="configure-cmake-settings-for-linux"></a>配置适用于 Linux 的 CMake 设置

若要更改默认的 CMake 设置，请从主菜单依次选择“CMake”|“更改 CMake 设置”|“CMakeLists.txt”，或右键单击“解决方案资源管理器”中的“CMakeSettings.txt”，然后选择“更改 CMake 设置”。 然后，Visual Studio 在名为 `CMakeSettings.json` 的文件夹中创建一个新文件，并使用项目设置菜单项中列出的默认配置进行填充。 以下示例显示了基于上述代码示例的 Linux 调试的默认配置：

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

可按需设置 `name` 值。 `remoteMachineName` 值指定了目标远程系统（以防存在多个系统）。 此字段启用了 IntelliSense，可帮助你选择正确的系统。 字段 `remoteCMakeListsRoot` 指定将项目源复制到远程系统上的何处。 字段 `remoteBuildRoot` 是远程系统上生成“生成输出”的位置。 还会在本地将该输出复制到由 `buildRoot` 指定的位置。

## <a name="build-a-supported-cmake-release-from-source"></a>从源生成受支持的 CMake 版本

Linux 计算机所需的最低 CMake 版本是 3.8，并它还必须支持服务器模式。 若要进行验证，请运行此命令：

```cmd
cmake --version
```

若要验证是否启用了该服务器模式，请运行：

```cmd
cmake -E capabilities
```

在输出中，查找“‘serverMode’:true”。 请注意，即使按如下所述从源编译 CMake，也应该在完成后检查各项功能。 Linux 系统可能存在限制，会阻止启用服务器模式。

若要在 Linux 系统 shell 中开始从源生成 CMake，请确保包管理器为最新版，且 git 和 cmake 均可用。

首先，从我们用于维护 Visual Studio CMake 支持分支的 [Microsoft CMake 存储库](https://github.com/Microsoft/CMake)中克隆 CMake 源：

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

接下来，若要生成最新版 CMake，并将它安装到 /usr/local/bin，请运行下面这些命令：

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

接下来，运行下面的命令，以验证版本是否不低于 3.8，且是否已启用服务器模式：

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>请参阅

[使用项目属性](../ide/working-with-project-properties.md)  
[Visual C++ 的 CMake 工具](../ide/cmake-tools-for-visual-cpp.md)  
