---
title: "NuGet PowerShell 参考 |Microsoft 文档"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 10/2/2017
ms.topic: reference
ms.prod: nuget
ms.technology: 
ms.assetid: cd08b869-44c6-480e-90f7-494a6d08e6d0
description: "对 Visual Studio 中的 NuGet 包管理器控制台中可用的 PowerShell 命令的完整引用。"
keywords: "NuGet 包管理器控制台，NuGet Powershell 命令，NuGet Powershell 参考"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: c0da5c88447784fdd49d824bbd03b11f73c22ebc
ms.sourcegitcommit: d0ba99bfe019b779b75731bafdca8a37e35ef0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2017
---
# <a name="powershell-reference"></a><span data-ttu-id="27626-104">PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="27626-104">PowerShell reference</span></span>

<span data-ttu-id="27626-105">程序包管理器控制台提供下面的 PowerShell 接口，以特定的命令通过 NuGet 进行交互的 Windows 上的 Visual Studio 中列出。</span><span class="sxs-lookup"><span data-stu-id="27626-105">The Package Manager Console provides a PowerShell interface within Visual Studio on Windows to interact with NuGet through the specific commands listed below.</span></span> <span data-ttu-id="27626-106">（控制台不是在 Visual Studio for mac。 目前可用的）有关如何使用控制台的指南，请参阅[程序包管理器控制台](../tools/package-manager-console.md)主题。</span><span class="sxs-lookup"><span data-stu-id="27626-106">(The console is not presently available in Visual Studio for Mac.) For a guide to using the console, see the [Package Manager Console](../tools/package-manager-console.md) topic.</span></span>

> [!Tip]
> <span data-ttu-id="27626-107">仅与包消耗相关的所有 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="27626-107">All PowerShell commands relate only to package consumption.</span></span> <span data-ttu-id="27626-108">任何 PowerShell 命令不与创建和发布除外的包的范围内包也可以是其他包的使用者。</span><span class="sxs-lookup"><span data-stu-id="27626-108">No PowerShell commands relate to creating and publishing packages except to the extent that a package can also be a consumer of other packages.</span></span>

> [!Important]
> <span data-ttu-id="27626-109">此处列出的命令是特定于 Visual Studio 中的包管理器控制台，区别[软件包管理模块命令](https://msdn.microsoft.com/powershell/reference/6/packagemanagement/packagemanagement)常规 PowerShell 环境中提供。</span><span class="sxs-lookup"><span data-stu-id="27626-109">The commands listed here are specific to the Package Manager Console in Visual Studio, and differ from the [Package Management module commands](https://msdn.microsoft.com/powershell/reference/6/packagemanagement/packagemanagement) that are available in a general PowerShell environment.</span></span> <span data-ttu-id="27626-110">具体而言，每个环境包含在另一个中, 不可用的命令，并具有相同名称的命令也可能在特定自变量而异。</span><span class="sxs-lookup"><span data-stu-id="27626-110">Specifically, each environment has commands that are not available in the other, and commands with the same name may also differ in their specific arguments.</span></span> <span data-ttu-id="27626-111">当使用 Visual Studio 中的包管理控制台，将应用的命令和参数中存在本文所述。</span><span class="sxs-lookup"><span data-stu-id="27626-111">When using the Package Management Console in Visual Studio, the commands and arguments documented in this present topic apply.</span></span>

| <span data-ttu-id="27626-112">常见的命令</span><span class="sxs-lookup"><span data-stu-id="27626-112">Common Commands</span></span> | <span data-ttu-id="27626-113">描述</span><span class="sxs-lookup"><span data-stu-id="27626-113">Description</span></span> | <span data-ttu-id="27626-114">NuGet 版本</span><span class="sxs-lookup"><span data-stu-id="27626-114">NuGet Version</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="27626-115">安装包</span><span class="sxs-lookup"><span data-stu-id="27626-115">Install-Package</span></span>](ps-ref-install-package.md) | <span data-ttu-id="27626-116">在项目中安装包和其依赖项。</span><span class="sxs-lookup"><span data-stu-id="27626-116">Installs a package and its dependencies into the project.</span></span> | <span data-ttu-id="27626-117">全部</span><span class="sxs-lookup"><span data-stu-id="27626-117">All</span></span> |
| [<span data-ttu-id="27626-118">更新包</span><span class="sxs-lookup"><span data-stu-id="27626-118">Update-Package</span></span>](ps-ref-update-package.md) | <span data-ttu-id="27626-119">更新包和其依赖项或在项目中的所有包。</span><span class="sxs-lookup"><span data-stu-id="27626-119">Updates a package and its dependencies, or all packages in a project.</span></span> | <span data-ttu-id="27626-120">全部</span><span class="sxs-lookup"><span data-stu-id="27626-120">All</span></span> |
| [<span data-ttu-id="27626-121">查找包</span><span class="sxs-lookup"><span data-stu-id="27626-121">Find-Package</span></span>](ps-ref-find-package.md) | <span data-ttu-id="27626-122">搜索包源使用的包 ID 或关键字。</span><span class="sxs-lookup"><span data-stu-id="27626-122">Searches a package source using a package ID or keywords.</span></span> | <span data-ttu-id="27626-123">3.0+</span><span class="sxs-lookup"><span data-stu-id="27626-123">3.0+</span></span> |
| [<span data-ttu-id="27626-124">获取包</span><span class="sxs-lookup"><span data-stu-id="27626-124">Get-Package</span></span>](ps-ref-get-package.md) | <span data-ttu-id="27626-125">检索安装在本地存储库，包的列表或列出从包源提供的程序包。</span><span class="sxs-lookup"><span data-stu-id="27626-125">Retrieves the list of packages installed in the local repository, or lists packages available from a package source.</span></span> | <span data-ttu-id="27626-126">全部</span><span class="sxs-lookup"><span data-stu-id="27626-126">All</span></span> |

| <span data-ttu-id="27626-127">辅助命令</span><span class="sxs-lookup"><span data-stu-id="27626-127">Secondary Commands</span></span> | <span data-ttu-id="27626-128">描述</span><span class="sxs-lookup"><span data-stu-id="27626-128">Description</span></span> | <span data-ttu-id="27626-129">NuGet 版本</span><span class="sxs-lookup"><span data-stu-id="27626-129">NuGet Version</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="27626-130">添加 BindingRedirect</span><span class="sxs-lookup"><span data-stu-id="27626-130">Add-BindingRedirect</span></span>](ps-ref-add-bindingredirect.md) | <span data-ttu-id="27626-131">检查项目输出路径中的所有程序集并将添加绑定重定向到`app.config`或`web.config`在必要时。</span><span class="sxs-lookup"><span data-stu-id="27626-131">Examines all assemblies within the output path for a project and adds binding redirects to the `app.config` or `web.config` where necessary.</span></span> | <span data-ttu-id="27626-132">全部</span><span class="sxs-lookup"><span data-stu-id="27626-132">All</span></span> |
| [<span data-ttu-id="27626-133">获取项目</span><span class="sxs-lookup"><span data-stu-id="27626-133">Get-Project</span></span>](ps-ref-get-project.md) | <span data-ttu-id="27626-134">显示的默认值或指定的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="27626-134">Displays information about the default or specified project.</span></span> | <span data-ttu-id="27626-135">3.0+</span><span class="sxs-lookup"><span data-stu-id="27626-135">3.0+</span></span> |
| [<span data-ttu-id="27626-136">打开 PackagePage</span><span class="sxs-lookup"><span data-stu-id="27626-136">Open-PackagePage</span></span>](ps-ref-open-packagepage.md) | <span data-ttu-id="27626-137">将启动默认浏览器中使用项目、 许可证或指定包的报告滥用行为 URL。</span><span class="sxs-lookup"><span data-stu-id="27626-137">Launches the default browser with the project, license, or report abuse URL for the specified package.</span></span> | <span data-ttu-id="27626-138">在 3.0 + 弃用</span><span class="sxs-lookup"><span data-stu-id="27626-138">Deprecated in 3.0+</span></span> |
| [<span data-ttu-id="27626-139">注册 TabExpansion</span><span class="sxs-lookup"><span data-stu-id="27626-139">Register-TabExpansion</span></span>](ps-ref-register-tabexpansion.md) | <span data-ttu-id="27626-140">注册一个命令，使你可以创建自定义的扩展的常用的参数值的参数选项卡扩展。</span><span class="sxs-lookup"><span data-stu-id="27626-140">Registers a tab expansion for the parameters of a command, allowing you to create customized expansions for commonly-used parameter values.</span></span> | <span data-ttu-id="27626-141">全部</span><span class="sxs-lookup"><span data-stu-id="27626-141">All</span></span> |
| [<span data-ttu-id="27626-142">同步包</span><span class="sxs-lookup"><span data-stu-id="27626-142">Sync-Package</span></span>](ps-ref-sync-package.md) | <span data-ttu-id="27626-143">安装从包的版本的 get 指定项目和同步到解决方案中项目的其余部分的版本。</span><span class="sxs-lookup"><span data-stu-id="27626-143">Get the version of installed package from specified project and syncs the version to the rest of projects in the solution.</span></span> | <span data-ttu-id="27626-144">3.0+</span><span class="sxs-lookup"><span data-stu-id="27626-144">3.0+</span></span> |
| [<span data-ttu-id="27626-145">卸载包</span><span class="sxs-lookup"><span data-stu-id="27626-145">Uninstall-Package</span></span>](ps-ref-uninstall-package.md) | <span data-ttu-id="27626-146">从项目中，有选择性地删除其依赖项中删除包。</span><span class="sxs-lookup"><span data-stu-id="27626-146">Removes a package from a project, optionally removing its dependencies.</span></span> | <span data-ttu-id="27626-147">全部</span><span class="sxs-lookup"><span data-stu-id="27626-147">All</span></span> |

<span data-ttu-id="27626-148">有关完整的详细帮助其中任何命令，在控制台中，只需运行命令中的名称与以下：</span><span class="sxs-lookup"><span data-stu-id="27626-148">For complete, detailed help on any of these commands within the console, just run the following with the command name in question:</span></span>

```ps
Get-Help <command> -full
```

<span data-ttu-id="27626-149">所有程序包管理器控制台命令都支持以下[常见的 PowerShell 参数](http://go.microsoft.com/fwlink/?LinkID=113216):</span><span class="sxs-lookup"><span data-stu-id="27626-149">All Package Manager Console commands support the following [common PowerShell parameters](http://go.microsoft.com/fwlink/?LinkID=113216):</span></span>

- <span data-ttu-id="27626-150">调试</span><span class="sxs-lookup"><span data-stu-id="27626-150">Debug</span></span>
- <span data-ttu-id="27626-151">ErrorAction</span><span class="sxs-lookup"><span data-stu-id="27626-151">ErrorAction</span></span>
- <span data-ttu-id="27626-152">ErrorVariable</span><span class="sxs-lookup"><span data-stu-id="27626-152">ErrorVariable</span></span>
- <span data-ttu-id="27626-153">OutBuffer</span><span class="sxs-lookup"><span data-stu-id="27626-153">OutBuffer</span></span>
- <span data-ttu-id="27626-154">OutVariable</span><span class="sxs-lookup"><span data-stu-id="27626-154">OutVariable</span></span>
- <span data-ttu-id="27626-155">PipelineVariable</span><span class="sxs-lookup"><span data-stu-id="27626-155">PipelineVariable</span></span>
- <span data-ttu-id="27626-156">详细</span><span class="sxs-lookup"><span data-stu-id="27626-156">Verbose</span></span>
- <span data-ttu-id="27626-157">WarningAction</span><span class="sxs-lookup"><span data-stu-id="27626-157">WarningAction</span></span>
- <span data-ttu-id="27626-158">WarningVariable</span><span class="sxs-lookup"><span data-stu-id="27626-158">WarningVariable</span></span>

<span data-ttu-id="27626-159">有关详细信息，请参阅[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)中的 PowerShell 文档。</span><span class="sxs-lookup"><span data-stu-id="27626-159">For details, refer to [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216) in the PowerShell documentation.</span></span>