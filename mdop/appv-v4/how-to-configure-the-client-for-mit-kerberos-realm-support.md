---
title: MIT Kerberos 認証用のレルムをサポートするようにクライアントを構成する方法
description: MIT Kerberos 認証用のレルムをサポートするようにクライアントを構成する方法
author: dansimp
ms.assetid: 46102f4c-270c-4115-8eb4-7ff5ae3be32d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ae5cd73d00f340bc50070fdd0a5fd3e038cc3789
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817814"
---
# <span data-ttu-id="65e60-103">MIT Kerberos 認証用のレルムをサポートするようにクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="65e60-103">How to Configure the Client for MIT Kerberos Realm Support</span></span>


<span data-ttu-id="65e60-104">Application Virtualization (App-v) 4.5 SP1 では、MIT Kerberos 領域のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="65e60-104">In Application Virtualization (App-V) 4.5 SP1, support was added for MIT Kerberos realms.</span></span> <span data-ttu-id="65e60-105">このトピックでは、そのサポートを有効にする方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="65e60-105">This topic provides detailed information on how to enable that support.</span></span>

**<span data-ttu-id="65e60-106">MIT Kerberos 領域のサポートを有効にするには</span><span class="sxs-lookup"><span data-stu-id="65e60-106">To enable support for MIT Kerberos Realms</span></span>**

-   <span data-ttu-id="65e60-107">次のように、DWORD の**UseMitKerberos**という名前の新しいレジストリキーを作成して、値1に設定します。</span><span class="sxs-lookup"><span data-stu-id="65e60-107">Create a new registry key named **UseMitKerberos** of type DWORD, as follows, and then set it to a value of 1.</span></span>

    <span data-ttu-id="65e60-108">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\UseMitKerberos</span><span class="sxs-lookup"><span data-stu-id="65e60-108">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\UseMitKerberos</span></span>

 

 





