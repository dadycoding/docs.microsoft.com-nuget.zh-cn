---
title: "NuGet 2.6.1 for WebMatrix 发行说明 |Microsoft 文档"
author: karann-msft
ms.author: karann-msft
manager: ghogen
ms.date: 11/11/2016
ms.topic: article
ms.prod: nuget
ms.technology: 
ms.assetid: 119ea65b-b38b-4a8c-a4ed-6ea06f1aad09
description: "NuGet 2.6.1 为 WebMatrix 包括已知的问题、 bug 修复、 增加的功能，以及 DCRs 的发行说明。"
keywords: "NuGet 2.6.1 WebMatrix 发行说明、 bug 修复、 已知的问题，添加了一些功能，DCRs"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 9c37ddc998378b8aaa477dd5df814bab6f0b3c58
ms.sourcegitcommit: 262d026beeffd4f3b6fc47d780a2f701451663a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="nuget-261-for-webmatrix-release-notes"></a><span data-ttu-id="2fd76-104">NuGet 2.6.1 for WebMatrix 发行说明</span><span class="sxs-lookup"><span data-stu-id="2fd76-104">NuGet 2.6.1 for WebMatrix Release Notes</span></span>

<span data-ttu-id="2fd76-105">[NuGet 2.6 发行说明](../release-notes/nuget-2.6.md) | [NuGet 2.7 发行说明](../release-notes/nuget-2.7.md)</span><span class="sxs-lookup"><span data-stu-id="2fd76-105">[NuGet 2.6 Release Notes](../release-notes/nuget-2.6.md) | [NuGet 2.7 Release Notes](../release-notes/nuget-2.7.md)</span></span>

<span data-ttu-id="2fd76-106">NuGet 团队在 2014 年 3 月 26 日为 WebMatrix 中发布更新的 NuGet 包管理器扩展。</span><span class="sxs-lookup"><span data-stu-id="2fd76-106">The NuGet team released an updated NuGet Package Manager extension for WebMatrix on March 26, 2014.</span></span>  <span data-ttu-id="2fd76-107">此更新可以从安装[WebMatrix 扩展库](http://extensions.webmatrix.com/packages/NuGetPackageManager/)使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2fd76-107">This update can be installed from the [WebMatrix Extension Gallery](http://extensions.webmatrix.com/packages/NuGetPackageManager/) using the following steps:</span></span>

1. <span data-ttu-id="2fd76-108">打开 WebMatrix 3</span><span class="sxs-lookup"><span data-stu-id="2fd76-108">Open WebMatrix 3</span></span>
2. <span data-ttu-id="2fd76-109">单击主页功能区中的扩展图标</span><span class="sxs-lookup"><span data-stu-id="2fd76-109">Click the Extensions icon in the Home ribbon</span></span>
3. <span data-ttu-id="2fd76-110">选择更新选项卡</span><span class="sxs-lookup"><span data-stu-id="2fd76-110">Select the Updates tab</span></span>
4. <span data-ttu-id="2fd76-111">单击以更新到 2.6.1 的 NuGet 包管理器</span><span class="sxs-lookup"><span data-stu-id="2fd76-111">Click to update NuGet Package Manager to 2.6.1</span></span>
6. <span data-ttu-id="2fd76-112">关闭并重新启动 WebMatrix 3</span><span class="sxs-lookup"><span data-stu-id="2fd76-112">Close and restart WebMatrix 3</span></span>

## <a name="notable-changes"></a><span data-ttu-id="2fd76-113">重大更改</span><span class="sxs-lookup"><span data-stu-id="2fd76-113">Notable Changes</span></span>

<span data-ttu-id="2fd76-114">此扩展更新两个用户的地址的最大问题做出两难 WebMatrix 内的使用 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2fd76-114">This extension update addresses two of the biggest issues users have faced consuming NuGet packages within WebMatrix.</span></span>  <span data-ttu-id="2fd76-115">第一个 NuGet 架构版本错误，并且第二种是通向零字节 Dll bug`bin`文件夹。</span><span class="sxs-lookup"><span data-stu-id="2fd76-115">The first was a NuGet schema version error and the second was a bug leading to zero-byte DLLs in the `bin` folder.</span></span>

### <a name="nuget-schema-version-error"></a><span data-ttu-id="2fd76-116">NuGet 架构版本错误</span><span class="sxs-lookup"><span data-stu-id="2fd76-116">NuGet Schema Version Error</span></span>

<span data-ttu-id="2fd76-117">自发布 WebMatrix 3 后, 到 NuGet 需要新的架构版本为 NuGet 包已引入新功能。</span><span class="sxs-lookup"><span data-stu-id="2fd76-117">Since WebMatrix 3 was released, new features have been introduced into NuGet that require a new schema version for the NuGet packages.</span></span>  <span data-ttu-id="2fd76-118">在尝试管理 NuGet 程序包在您的网站，这些新的包可能导致你将在 WebMatrix 中看到的错误。</span><span class="sxs-lookup"><span data-stu-id="2fd76-118">When trying to manage your NuGet packages in your web site, these new packages can lead to errors that you'll see in WebMatrix.</span></span>

![出现了错误。](./media/NuGet-2.8/webmatrix-schema-version.png)

<span data-ttu-id="2fd76-122">此最新版本提供了与最新的 NuGet 包，阻止发生此错误的兼容性。</span><span class="sxs-lookup"><span data-stu-id="2fd76-122">This latest release provides compatibility with the newest NuGet packages, preventing this error from occurring.</span></span> <span data-ttu-id="2fd76-123">现在可以在 WebMatrix 中安装新版本的包包括 Microsoft.AspNet.WebPages。</span><span class="sxs-lookup"><span data-stu-id="2fd76-123">New versions of packages including Microsoft.AspNet.WebPages can now be installed in WebMatrix.</span></span>  <span data-ttu-id="2fd76-124">这些包的某些已使用 NuGet 功能，如[XDT 配置转换](../release-notes/nuget-2.6.md#xdt)，它不支持在 WebMatrix 中到目前为止。</span><span class="sxs-lookup"><span data-stu-id="2fd76-124">Some of these packages were using NuGet features such as [XDT config transforms](../release-notes/nuget-2.6.md#xdt), which wasn't supported in WebMatrix until now.</span></span>

### <a name="zero-byte-dlls-in-bin-folder"></a><span data-ttu-id="2fd76-125">Bin 文件夹中的零字节 Dll</span><span class="sxs-lookup"><span data-stu-id="2fd76-125">Zero-Byte DLLs in bin Folder</span></span>

<span data-ttu-id="2fd76-126">某些用户报告，之后安装 NuGet 包中包含要装箱，将被复制的 Dll 的 WebMatrix Dll 显示`bin`0 字节的文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2fd76-126">Some users have reported that after installing NuGet packages in WebMatrix that include DLLs that get copied to bin, that the DLLs show up in the `bin` folder as 0-byte files.</span></span>  <span data-ttu-id="2fd76-127">这在运行时将中断应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fd76-127">This breaks the application at runtime.</span></span>

<span data-ttu-id="2fd76-128">[此问题](https://nuget.codeplex.com/workitem/4060)现已修复。</span><span class="sxs-lookup"><span data-stu-id="2fd76-128">[This issue](https://nuget.codeplex.com/workitem/4060) has now been fixed.</span></span>

## <a name="other-recent-improvements"></a><span data-ttu-id="2fd76-129">其他最新改进</span><span class="sxs-lookup"><span data-stu-id="2fd76-129">Other Recent Improvements</span></span>

<span data-ttu-id="2fd76-130">当 NuGet 包管理器 2.8 已发布 for Visual Studio 中时，我们还为 WebMatrix 发布 NuGet 包管理器 2.5.0。</span><span class="sxs-lookup"><span data-stu-id="2fd76-130">When NuGet Package Manager 2.8 was released for Visual Studio, we also released NuGet Package Manager 2.5.0 for WebMatrix.</span></span>  <span data-ttu-id="2fd76-131">虽然这中所述[NuGet 2.8 发行说明](../release-notes/nuget-2.8.md#webmatrix-nuget-client-updates)，我们没有提到特定于新功能引入该更新。</span><span class="sxs-lookup"><span data-stu-id="2fd76-131">While this was mentioned in the [NuGet 2.8 Release Notes](../release-notes/nuget-2.8.md#webmatrix-nuget-client-updates), we didn't mention the specific new features that update introduced.</span></span>

### <a name="update-all"></a><span data-ttu-id="2fd76-132">更新所有</span><span class="sxs-lookup"><span data-stu-id="2fd76-132">Update All</span></span>

<span data-ttu-id="2fd76-133">现在，您可以更新的所有 web 站点的包在一个步骤 ！</span><span class="sxs-lookup"><span data-stu-id="2fd76-133">You can now update all of your web site's packages in one step!</span></span>  <span data-ttu-id="2fd76-134">当你在 WebMatrix 中打开 NuGet 扩展时，你将看到上的库、 安装，然后使用提供的更新的所有程序包的列表。</span><span class="sxs-lookup"><span data-stu-id="2fd76-134">When you open the NuGet extension in WebMatrix, you see the list of all packages on the gallery, those installed, and the ones with updates available.</span></span>  <span data-ttu-id="2fd76-135">以前，每个包需要单独更新，但现在没有显示在更新选项卡的有用"全部更新"按钮。</span><span class="sxs-lookup"><span data-stu-id="2fd76-135">Previously, every package would have to be updated individually but now there is a useful "Update All" button that shows up on the Updates tab.</span></span>

![单击所有更新，以使用可用的更新来更新所有包](./media/NuGet-2.8/webmatrix-update-all.png)

### <a name="overwrite-existing-files"></a><span data-ttu-id="2fd76-137">覆盖现有文件</span><span class="sxs-lookup"><span data-stu-id="2fd76-137">Overwrite Existing Files</span></span>

<span data-ttu-id="2fd76-138">安装程序包包含已在您的网站中存在的文件时，NuGet 具有始终只以无提示方式忽略 （保留现有的文件不动） 这些文件。</span><span class="sxs-lookup"><span data-stu-id="2fd76-138">When installing packages that contain files that already exist in your web site, NuGet has always just silently ignored those files (leaving your existing files alone).</span></span>  <span data-ttu-id="2fd76-139">这可能导致这样的印象包已安装，或当实际上它未正确更新。</span><span class="sxs-lookup"><span data-stu-id="2fd76-139">This could lead to the impression that a package was installed or updated correctly when in fact it wasn't.</span></span>  <span data-ttu-id="2fd76-140">现在，NuGet 将提示输入覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="2fd76-140">NuGet will now prompt for files to be overwritten.</span></span>

![文件冲突解决](./media/NuGet-2.8/webmatrix-overwrite-file.png)