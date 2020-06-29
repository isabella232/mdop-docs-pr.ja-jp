---
title: UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元
description: UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元
author: dansimp
ms.assetid: 254a16b1-f186-44a4-8e22-49a4ee87c734
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ae83e0a44f98b66a9930f8c5db2231992a4700
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812378"
---
# <span data-ttu-id="a7dda-103">UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元</span><span class="sxs-lookup"><span data-stu-id="a7dda-103">Restoring Application and Windows Settings Synchronized with UE-V 1.0</span></span>


<span data-ttu-id="a7dda-104">Microsoft User Experience Virtualization (UE-V) の WMI および PowerShell 機能により、設定パッケージを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="a7dda-104">WMI and PowerShell features of Microsoft User Experience Virtualization (UE-V) provide the ability to restore settings packages.</span></span> <span data-ttu-id="a7dda-105">WMI コマンドと PowerShell コマンドを使用すると、アプリケーションと Windows の設定を、UE-V Agent をインストールした後にアプリケーションを初めて起動したときにコンピューター上にあった設定値に復元することができます。</span><span class="sxs-lookup"><span data-stu-id="a7dda-105">WMI and PowerShell commands allow you to restore application and Windows settings to the settings values that were on the computer the first time the application launched after the UE-V Agent was installed.</span></span> <span data-ttu-id="a7dda-106">この復元アクションは、アプリケーションごとまたは Windows の設定ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7dda-106">This restoring action is performed on a per-application or Windows settings basis.</span></span> <span data-ttu-id="a7dda-107">設定は、次回アプリケーションが実行されるとき、またはユーザーがオペレーティングシステムにログオンしたときに復元されます。</span><span class="sxs-lookup"><span data-stu-id="a7dda-107">The settings are restored the next time that the application is run or when the user logs on to the operating system.</span></span>

**<span data-ttu-id="a7dda-108">PowerShell を使用してアプリケーション設定と Windows 設定を復元するには</span><span class="sxs-lookup"><span data-stu-id="a7dda-108">To restore application settings and Windows settings with PowerShell</span></span>**

1.  <span data-ttu-id="a7dda-109">Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7dda-109">Open the Windows PowerShell window.</span></span> <span data-ttu-id="a7dda-110">Microsoft UE-V PowerShell モジュールをインポートするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7dda-110">To import the Microsoft UE-V PowerShell module, enter the following command:</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="a7dda-111">次の PowerShell コマンドレットを入力して、アプリケーションの設定と Windows の設定を復元します。</span><span class="sxs-lookup"><span data-stu-id="a7dda-111">Enter the following PowerShell cmdlet to restore the application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="a7dda-112">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a7dda-112">PowerShell cmdlet</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="a7dda-113">説明</span><span class="sxs-lookup"><span data-stu-id="a7dda-113">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a7dda-114">Restore-UevUserSetting</span><span class="sxs-lookup"><span data-stu-id="a7dda-114">Restore-UevUserSetting</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7dda-115">アプリケーションのユーザー設定を復元するか、Windows 設定のグループを復元します</span><span class="sxs-lookup"><span data-stu-id="a7dda-115">Restores the user settings for an application or restores a group of Windows settings</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="a7dda-116">WMI を使用してアプリケーション設定と Windows 設定を復元するには</span><span class="sxs-lookup"><span data-stu-id="a7dda-116">To restore application settings and Windows settings with WMI</span></span>**

1.  <span data-ttu-id="a7dda-117">PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7dda-117">Open a PowerShell window.</span></span>

2.  <span data-ttu-id="a7dda-118">次の WMI コマンドを入力して、アプリケーションの設定と Windows の設定を復元します。</span><span class="sxs-lookup"><span data-stu-id="a7dda-118">Enter the following WMI command to restore application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="a7dda-119">WMI コマンド</span><span class="sxs-lookup"><span data-stu-id="a7dda-119">WMI command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="a7dda-120">説明</span><span class="sxs-lookup"><span data-stu-id="a7dda-120">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a7dda-121">Root\Microsoft\UEV の呼び出しメソッド-名前空間の UserSettings-Name RestoreByTemplateId-ArgumentList &lt; template_ID&gt;</span><span class="sxs-lookup"><span data-stu-id="a7dda-121">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7dda-122">アプリケーションのユーザー設定を復元するか、Windows 設定のグループを復元します</span><span class="sxs-lookup"><span data-stu-id="a7dda-122">Restores the user settings for an application or restores a group of Windows settings</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="a7dda-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a7dda-123">Related topics</span></span>


[<span data-ttu-id="a7dda-124">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="a7dda-124">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="a7dda-125">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="a7dda-125">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





