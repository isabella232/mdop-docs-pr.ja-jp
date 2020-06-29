---
title: Windows PowerShell を使用した MBAM 2.5 の管理
description: Windows PowerShell を使用した MBAM 2.5 の管理
author: dansimp
ms.assetid: 64668e76-2cba-433d-8d2d-50df0a4b2997
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 8db305bfbdf79723da2b186dd5cc00406a4089cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812738"
---
# <span data-ttu-id="9e6cc-103">Windows PowerShell を使用した MBAM 2.5 の管理</span><span class="sxs-lookup"><span data-stu-id="9e6cc-103">Using Windows PowerShell to Administer MBAM 2.5</span></span>


<span data-ttu-id="9e6cc-104">このトピックでは、ユーザーがロックアウトされたときのコンピューターまたはドライブの回復に関連する、Microsoft BitLocker 管理と監視 (MBAM) 用の Windows PowerShell コマンドレットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-104">This topic describes Windows PowerShell cmdlets for Microsoft BitLocker Administration and Monitoring (MBAM) that relate to recovering computers or drives when users get locked out.</span></span>

<span data-ttu-id="9e6cc-105">MBAM サーバー機能を構成するために使用するコマンドレットについては、「 [Windows PowerShell を使用して mbam 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-105">For cmdlets that you use to configure MBAM Server features, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

## <a href="" id="cmdlets-for-recovering-computers-or-drives-that-are-managed-by-mbam-"></a><span data-ttu-id="9e6cc-106">MBAM で管理されているコンピューターまたはドライブを回復するためのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="9e6cc-106">Cmdlets for recovering computers or drives that are managed by MBAM</span></span>


<span data-ttu-id="9e6cc-107">MBAM で管理されているコンピューターまたはドライブを回復するには、次の Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-107">Use the following Windows PowerShell cmdlets to recover computers or drives that are managed by MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9e6cc-108">名前</span><span class="sxs-lookup"><span data-stu-id="9e6cc-108">Name</span></span></th>
<th align="left"><span data-ttu-id="9e6cc-109">説明</span><span class="sxs-lookup"><span data-stu-id="9e6cc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e6cc-110">Get-MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="9e6cc-110">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e6cc-111">ユーザーがコンピューターまたは暗号化されたドライブのロックを解除できるようにする MBAM 回復キーを要求します。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-111">Requests an MBAM recovery key that enables users to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e6cc-112">Get-MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="9e6cc-112">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e6cc-113">Tpm がロックアウトされているときに、トラステッドプラットフォームモジュール (TPM) のロックを解除するために使うことができる TPM 所有者パスワードをユーザーに提供します。これにより、tpm がロックアウトされ、PIN が受け入れられなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-113">Provides users with a TPM owner password that they can use to unlock a Trusted Platform Module (TPM) when the TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-cmdlet-help"></a> <span data-ttu-id="9e6cc-114">MBAM コマンドレットのヘルプ</span><span class="sxs-lookup"><span data-stu-id="9e6cc-114">MBAM cmdlet Help</span></span>


<span data-ttu-id="9e6cc-115">MBAM コマンドレットの Windows PowerShell ヘルプは、次の形式で利用できます。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-115">Windows PowerShell Help for MBAM cmdlets is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9e6cc-116">Windows PowerShell ヘルプの形式</span><span class="sxs-lookup"><span data-stu-id="9e6cc-116">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="9e6cc-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9e6cc-117">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e6cc-118">Windows PowerShell コマンドプロンプトで、「 <strong> Get-ヘルプ </strong> &lt; <em> コマンドレット」と入力します。</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="9e6cc-118">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e6cc-119">最新の Windows PowerShell コマンドレットをアップロードするには、「 <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"> Windows Powershell を使用して MBAM 2.5 サーバー機能を構成する」の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-119">To upload the latest Windows PowerShell cmdlets, follow the instructions in <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e6cc-120">Web ページとしての TechNet の場合</span><span class="sxs-lookup"><span data-stu-id="9e6cc-120">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e6cc-121">Word の .docx ファイルとしてダウンロードセンターで</span><span class="sxs-lookup"><span data-stu-id="9e6cc-121">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e6cc-122">.Pdf ファイルとしてダウンロードセンターで</span><span class="sxs-lookup"><span data-stu-id="9e6cc-122">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 



## <span data-ttu-id="9e6cc-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9e6cc-123">Related topics</span></span>


[<span data-ttu-id="9e6cc-124">MBAM 2.5 機能の管理</span><span class="sxs-lookup"><span data-stu-id="9e6cc-124">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)

[<span data-ttu-id="9e6cc-125">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="9e6cc-125">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 

## <span data-ttu-id="9e6cc-126">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-126">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9e6cc-127">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-127">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9e6cc-128">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="9e6cc-128">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





