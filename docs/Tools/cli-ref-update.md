---
title: "NuGet CLI 更新命令 |Microsoft 文档"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.date: 12/07/2017
ms.topic: reference
ms.prod: nuget
ms.technology: 
ms.assetid: 61fde945-6983-46a5-8636-da0fada4e641
description: "Nuget.exe 更新命令参考"
keywords: "nuget 更新引用，更新包命令"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 654144e93a99a4a4f8d79c0db5660cfb7c6c308e
ms.sourcegitcommit: d0ba99bfe019b779b75731bafdca8a37e35ef0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2017
---
# <a name="update-command-nuget-cli"></a><span data-ttu-id="aa179-104">(NuGet CLI) 中的更新命令</span><span class="sxs-lookup"><span data-stu-id="aa179-104">update command (NuGet CLI)</span></span>

<span data-ttu-id="aa179-105">**适用于：**打包消耗&bullet;**受支持的版本：**所有</span><span class="sxs-lookup"><span data-stu-id="aa179-105">**Applies to:** package consumption &bullet; **Supported versions:** all</span></span>

<span data-ttu-id="aa179-106">更新的项目中的所有包 (使用`packages.config`) 到其最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="aa179-106">Updates all packages in a project (using `packages.config`) to their latest available versions.</span></span> <span data-ttu-id="aa179-107">建议运行[还原](#restore)之前运行`update`。</span><span class="sxs-lookup"><span data-stu-id="aa179-107">It is recommended to run ['restore'](#restore) before running the `update`.</span></span> <span data-ttu-id="aa179-108">(若要更新的单个包，使用[ `nuget install` ](cli-ref-install.md)而无需指定的版本号，在其中事例 NuGet 安装最新版本。)</span><span class="sxs-lookup"><span data-stu-id="aa179-108">(To update an individual package, use [`nuget install`](cli-ref-install.md) without specifying a version number, in which case NuGet installs the latest version.)</span></span>

<span data-ttu-id="aa179-109">注意：`update`并不适用于在 Mono （Mac OSX 或 Linux） 下运行的 CLI。</span><span class="sxs-lookup"><span data-stu-id="aa179-109">Note: `update` does not work with the CLI running under Mono (Mac OSX or Linux).</span></span> <span data-ttu-id="aa179-110">该命令还并不适用于使用项目`project.json`或 PackageReference 管理格式。</span><span class="sxs-lookup"><span data-stu-id="aa179-110">The command also does not work with projects using `project.json` or PackageReference management formats.</span></span>

<span data-ttu-id="aa179-111">`update`命令还会更新项目文件中的程序集引用、 提供这些引用已存在。</span><span class="sxs-lookup"><span data-stu-id="aa179-111">The `update` command also updates assembly references in the project file, provided those references already exist.</span></span> <span data-ttu-id="aa179-112">如果更新后的包已添加的程序集，新的引用的是*不*添加。</span><span class="sxs-lookup"><span data-stu-id="aa179-112">If an updated package has an added assembly, a new reference is *not* added.</span></span> <span data-ttu-id="aa179-113">新的包依赖关系还没有添加其程序集引用。</span><span class="sxs-lookup"><span data-stu-id="aa179-113">New package dependencies also don't have their assembly references added.</span></span> <span data-ttu-id="aa179-114">若要更新的一部分中包括这些操作，更新使用程序包管理器 UI 或包管理器控制台的 Visual Studio 中的包。</span><span class="sxs-lookup"><span data-stu-id="aa179-114">To include these operations as part of an update, update the package in Visual Studio using the Package Manager UI or the Package Manager Console.</span></span>

<span data-ttu-id="aa179-115">此命令还可以用于更新 nuget.exe 本身使用*-自助*标志。</span><span class="sxs-lookup"><span data-stu-id="aa179-115">This command can also be used to update nuget.exe itself using the *-self* flag.</span></span>

## <a name="usage"></a><span data-ttu-id="aa179-116">用法</span><span class="sxs-lookup"><span data-stu-id="aa179-116">Usage</span></span>

```
nuget update <configPath> [options]
```

<span data-ttu-id="aa179-117">其中`<configPath>`标识是`packages.config`或列出了项目的依赖关系的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="aa179-117">where `<configPath>` identifies either a `packages.config` or solution file that lists the project's dependencies.</span></span>

## <a name="options"></a><span data-ttu-id="aa179-118">选项</span><span class="sxs-lookup"><span data-stu-id="aa179-118">Options</span></span>

| <span data-ttu-id="aa179-119">选项</span><span class="sxs-lookup"><span data-stu-id="aa179-119">Option</span></span> | <span data-ttu-id="aa179-120">描述</span><span class="sxs-lookup"><span data-stu-id="aa179-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="aa179-121">ConfigFile</span><span class="sxs-lookup"><span data-stu-id="aa179-121">ConfigFile</span></span> | <span data-ttu-id="aa179-122">*（2.5 +)* NuGet 要应用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="aa179-122">*(2.5+)* The NuGet configuration file to apply.</span></span> <span data-ttu-id="aa179-123">如果未指定， *%AppData%\NuGet\NuGet.Config*使用。</span><span class="sxs-lookup"><span data-stu-id="aa179-123">If not specified, *%AppData%\NuGet\NuGet.Config* is used.</span></span> |
| <span data-ttu-id="aa179-124">FileConflictAction</span><span class="sxs-lookup"><span data-stu-id="aa179-124">FileConflictAction</span></span> | <span data-ttu-id="aa179-125">*（2.5 +)*指定当系统询问是覆盖还是忽略所引用的项目的现有文件时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="aa179-125">*(2.5+)* Specifies the action to take when asked to overwrite or ignore existing files referenced by the project.</span></span> <span data-ttu-id="aa179-126">值为*覆盖，请忽略，无*。</span><span class="sxs-lookup"><span data-stu-id="aa179-126">Values are *overwrite, ignore, none*.</span></span> |
| <span data-ttu-id="aa179-127">ForceEnglishOutput</span><span class="sxs-lookup"><span data-stu-id="aa179-127">ForceEnglishOutput</span></span> | <span data-ttu-id="aa179-128">*（3.5 +)*强制 nuget.exe 运行使用固定的、 基于英语的区域性。</span><span class="sxs-lookup"><span data-stu-id="aa179-128">*(3.5+)* Forces nuget.exe to run using an invariant, English-based culture.</span></span> |
| <span data-ttu-id="aa179-129">帮助</span><span class="sxs-lookup"><span data-stu-id="aa179-129">Help</span></span> | <span data-ttu-id="aa179-130">显示的帮助命令的信息。</span><span class="sxs-lookup"><span data-stu-id="aa179-130">Displays help information for the command.</span></span> |
| <span data-ttu-id="aa179-131">Id</span><span class="sxs-lookup"><span data-stu-id="aa179-131">Id</span></span> | <span data-ttu-id="aa179-132">指定的包 Id，以更新的列表。</span><span class="sxs-lookup"><span data-stu-id="aa179-132">Specifies a list of package IDs to update.</span></span> |
| <span data-ttu-id="aa179-133">MSBuildPath</span><span class="sxs-lookup"><span data-stu-id="aa179-133">MSBuildPath</span></span> | <span data-ttu-id="aa179-134">*（4.0 +)*指定 MSBuild 使用执行命令，优先于的路径`-MSBuildVersion`。</span><span class="sxs-lookup"><span data-stu-id="aa179-134">*(4.0+)* Specifies the path of MSBuild to use with the command, taking precedence over `-MSBuildVersion`.</span></span> |
| <span data-ttu-id="aa179-135">MSBuildVersion</span><span class="sxs-lookup"><span data-stu-id="aa179-135">MSBuildVersion</span></span> | <span data-ttu-id="aa179-136">*（3.2 +)*指定要用于此命令的 MSBuild 的版本。</span><span class="sxs-lookup"><span data-stu-id="aa179-136">*(3.2+)* Specifies the version of MSBuild to be used with this command.</span></span> <span data-ttu-id="aa179-137">支持的值为 4、 12、 14、 15。</span><span class="sxs-lookup"><span data-stu-id="aa179-137">Supported values are 4, 12, 14, 15.</span></span> <span data-ttu-id="aa179-138">默认情况下，选择你的路径中的 MSBuild，否则，它默认为最高的已安装版本的 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="aa179-138">By default the MSBuild in your path is picked, otherwise it defaults to the highest installed version of MSBuild.</span></span> |
| <span data-ttu-id="aa179-139">非交互式</span><span class="sxs-lookup"><span data-stu-id="aa179-139">NonInteractive</span></span> | <span data-ttu-id="aa179-140">取消显示提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="aa179-140">Suppresses prompts for user input or confirmations.</span></span> |
| <span data-ttu-id="aa179-141">预发行版</span><span class="sxs-lookup"><span data-stu-id="aa179-141">PreRelease</span></span> | <span data-ttu-id="aa179-142">允许更新到的预发布版本。</span><span class="sxs-lookup"><span data-stu-id="aa179-142">Allows updating to prerelease versions.</span></span> <span data-ttu-id="aa179-143">如果更新已安装的预发行包，则不需要此标志。</span><span class="sxs-lookup"><span data-stu-id="aa179-143">This flag is not required when updating prerelease packages that are already installed.</span></span> |
| <span data-ttu-id="aa179-144">RepositoryPath</span><span class="sxs-lookup"><span data-stu-id="aa179-144">RepositoryPath</span></span> | <span data-ttu-id="aa179-145">指定包的安装位置的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa179-145">Specifies the local folder where packages are installed.</span></span> |
| <span data-ttu-id="aa179-146">安全</span><span class="sxs-lookup"><span data-stu-id="aa179-146">Safe</span></span> | <span data-ttu-id="aa179-147">指定仅更新在相同的主版本号和次版本中可用的最高版本的已安装的程序包将安装。</span><span class="sxs-lookup"><span data-stu-id="aa179-147">Specifies that only updates with the highest version available within the same major and minor version as the installed package will be installed.</span></span> |
| <span data-ttu-id="aa179-148">自助</span><span class="sxs-lookup"><span data-stu-id="aa179-148">Self</span></span> | <span data-ttu-id="aa179-149">*（1.4 +)* Nuget.exe 更新到最新版本; 将忽略所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="aa179-149">*(1.4+)* Updates nuget.exe to the latest version; all other arguments are ignored.</span></span> |
| <span data-ttu-id="aa179-150">源</span><span class="sxs-lookup"><span data-stu-id="aa179-150">Source</span></span> | <span data-ttu-id="aa179-151">指定包源的列表 （作为 Url) 若要使用的更新。</span><span class="sxs-lookup"><span data-stu-id="aa179-151">Specifies the list of package sources (as URLs) to use for the updates.</span></span> <span data-ttu-id="aa179-152">如果省略，则该命令使用在配置文件中提供的源，请参阅[配置 NuGet 行为](../Consume-Packages/Configuring-NuGet-Behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="aa179-152">If omitted, the command uses the sources provided in configuration files, see [Configuring NuGet behavior](../Consume-Packages/Configuring-NuGet-Behavior.md).</span></span> |
| <span data-ttu-id="aa179-153">详细级别</span><span class="sxs-lookup"><span data-stu-id="aa179-153">Verbosity</span></span> | <span data-ttu-id="aa179-154">指定的输出中显示的详细信息量：*正常*， *quiet*，*详细 （2.5 +）*。</span><span class="sxs-lookup"><span data-stu-id="aa179-154">Specifies the amount of detail displayed in the output: *normal*, *quiet*, *detailed (2.5+)*.</span></span> |
| <span data-ttu-id="aa179-155">版本</span><span class="sxs-lookup"><span data-stu-id="aa179-155">Version</span></span> | <span data-ttu-id="aa179-156">当与一个包 ID 一起使用，指定要更新的包的版本。</span><span class="sxs-lookup"><span data-stu-id="aa179-156">When used with one package ID, specifies the version of the package to update.</span></span> |

<span data-ttu-id="aa179-157">另请参阅[环境变量](cli-ref-environment-variables.md)</span><span class="sxs-lookup"><span data-stu-id="aa179-157">Also see [Environment variables](cli-ref-environment-variables.md)</span></span>

## <a name="examples"></a><span data-ttu-id="aa179-158">示例</span><span class="sxs-lookup"><span data-stu-id="aa179-158">Examples</span></span>

```
nuget update

# update packages installed in solution.sln, using MSBuild version 14.0 to load the solution and its project(s).
nuget update solution.sln -MSBuildVersion 14

nuget update -safe

nuget update -self
```