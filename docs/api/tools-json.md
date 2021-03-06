---
title: 用于发现 nuget.exe 版本 tools.json
description: 为终结点
author: jver
ms.author: jver
ms.date: 08/16/2018
ms.topic: conceptual
ms.reviewer: kraigb
ms.openlocfilehash: 003139abac7808dbdaef4aa66119e09772db2b4f
ms.sourcegitcommit: b6efd4b210d92bf163c67e412ca9a5a018d117f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56852528"
---
# <a name="toolsjson-for-discovering-nugetexe-versions"></a>用于发现 nuget.exe 版本 tools.json

如今，有几种方法获取 nuget.exe 的最新版本以可编写脚本的方式在计算机上。 例如，可以下载并提取[ `NuGet.CommandLine` ](https://www.nuget.org/packages/NuGet.CommandLine/)从 nuget.org 的包。这具有某种程度的复杂性，因为它也需要已有 nuget.exe (对于`nuget.exe install`) 或您必须将使用基本解压缩工具.nupkg 解压缩并查找二进制的内部。

如果已有 nuget.exe，还可以使用`nuget.exe update -self`，但此操作还需要具有 nuget.exe 的现有副本。 这种方法也更新到最新版本。 它不允许使用特定版本。

`tools.json`终结点可供同时解决启动问题并使你下载的 nuget.exe 的版本控制。 这可以用于 CI/CD 环境或自定义脚本中发现和下载 nuget.exe 任何已发布的版本。

`tools.json`可以使用未经身份验证的 HTTP 请求获取终结点 (例如`Invoke-WebRequest`在 PowerShell 中或`wget`)。 可以分析使用 JSON 反序列化程序，还可以使用提取 Url 的后续 nuget.exe 下载未经身份验证的 HTTP 请求。

终结点可以使用提取`GET`方法：

    GET https://dist.nuget.org/tools.json

[JSON 架构](http://json-schema.org/)为此处提供了终结点：

    GET https://dist.nuget.org/tools.schema.json

## <a name="response"></a>响应

响应是 nuget.exe 的包含所有可用版本的 JSON 文档。

根 JSON 对象具有以下属性：

name      | 类型             | 必需
--------- | ---------------- | --------
nuget.exe | 对象的数组 | 是

在每个对象`nuget.exe`数组具有以下属性：

name     | 类型   | 必需 | 说明
-------- | ------ | -------- | -----
version  | string | 是      | SemVer 2.0.0 字符串
URL      | string | 是      | 下载此版本的 nuget.exe 绝对 URL
阶段    | string | 是      | 枚举字符串
上传 | string | 是      | 版本何时进行可用一个近似的 ISO 8601 时间戳

将按降序，SemVer 2.0.0 排序数组中的项。 这一保证旨在减少客户端感兴趣的最高版本号的负担。 但是这意味着列表不按时间顺序排序。 例如，如果在某个日期晚于更高版本的主版本，较低的主版本已得到处理，此服务的版本将不出现在列表顶部。 如果想要发布的最新版本*时间戳*，只需对数组进行排序`uploaded`字符串。 这样做的原因`uploaded`时间戳处于[ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)格式，它可以通过使用按字典编辑顺序排序 （即简单的字符串排序） 按时间顺序排序。

`stage`属性指示如何审查该版本的工具是。 

阶段              | 含义
------------------ | ------
EarlyAccessPreview | 在上尚不可见[下载网页](https://www.nuget.org/downloads)和应由合作伙伴验证
Released（已释放）           | 下载站点上的可用但尚未广泛使用建议
ReleasedAndBlessed | 下载站点上可用，建议使用

具有最新的一个简单的方法，建议的版本是所要采取的第一个版本列表，其中包含`stage`的值`ReleasedAndBlessed`。 这有效，因为版本 SemVer 2.0.0 顺序进行排序。

`NuGet.CommandLine` Nuget.org 上的包通常只会更新与`ReleasedAndBlessed`版本。

### <a name="sample-request"></a>示例请求

    GET https://dist.nuget.org/tools.json

### <a name="sample-response"></a>示例响应

[!code-JSON [tools-json.json](./_data/tools-json.json)]
