---
title: PowerShell を使用した MBAM 1.0 の管理
description: PowerShell を使用した MBAM 1.0 の管理
author: dansimp
ms.assetid: 3bf2eca5-4ab7-4e84-9e80-c0c7d709647b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3547bee9b2efc58252bb6f0a1cb0aa4c484e4e80
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825137"
---
# <span data-ttu-id="bb4d7-103">PowerShell を使用した MBAM 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="bb4d7-103">Administering MBAM 1.0 by Using PowerShell</span></span>


<span data-ttu-id="bb4d7-104">Microsoft BitLocker の管理と監視 (MBAM) には、次の Windows PowerShell コマンドレットのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="bb4d7-105">管理者は、これらの PowerShell コマンドレットを使って、MBAM 管理 web サイトではなく、コマンドプロンプトからさまざまな MBAM サーバータスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-105">Administrators can use these PowerShell cmdlets to perform various MBAM server tasks from the command prompt rather than from the MBAM administration website.</span></span>

## <span data-ttu-id="bb4d7-106">PowerShell を使用して MBAM を管理する方法</span><span class="sxs-lookup"><span data-stu-id="bb4d7-106">How to administer MBAM by using PowerShell</span></span>


<span data-ttu-id="bb4d7-107">MBAM を管理するには、ここで説明した PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-107">Use the PowerShell cmdlets described here to administer MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb4d7-108">名前</span><span class="sxs-lookup"><span data-stu-id="bb4d7-108">Name</span></span></th>
<th align="left"><span data-ttu-id="bb4d7-109">説明</span><span class="sxs-lookup"><span data-stu-id="bb4d7-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb4d7-110">追加-Mbamハードウェアタイプ</span><span class="sxs-lookup"><span data-stu-id="bb4d7-110">Add-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-111">MBAM ハードウェアインベントリに新しいハードウェアモデルを追加します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-111">Adds a new hardware model to the MBAM hardware inventory.</span></span> <span data-ttu-id="bb4d7-112">このコマンドレットでは、BitLocker ドライブ暗号化のハードウェアがサポートされているかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-112">This cmdlet can also specify whether the hardware is supported or unsupported for BitLocker drive encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb4d7-113">Get-MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="bb4d7-113">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-114">ユーザーがコンピューターまたは暗号化されたドライブのロックを解除できるようにする MBAM 回復キーを要求します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-114">Requests an MBAM recovery key that will enable a user to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb4d7-115">ダウンロード-Mbamハードウェアタイプ</span><span class="sxs-lookup"><span data-stu-id="bb4d7-115">Get-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-116">ハードウェアモデルに互換性があるか、BitLocker ドライブ暗号化との互換性がないかを示すデータを含むマスターハードウェアインベントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-116">Gets a master hardware inventory that contains data that indicates whether hardware models are compatible or incompatible with BitLocker drive encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb4d7-117">Get-MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="bb4d7-117">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-118">ユーザーが TPM (Trusted Platform Module) アクセスを管理するための TPM 所有者パスワードを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-118">Provides a TPM owner password for a user to manage their TPM (Trusted Platform Module) access.</span></span> <span data-ttu-id="bb4d7-119">TPM がロックされている場合、ユーザーは PIN を受け入れなくなります。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-119">Helps users when TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb4d7-120">インストール-Mbam</span><span class="sxs-lookup"><span data-stu-id="bb4d7-120">Install-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-121">高度なグループポリシー、暗号化、キーの回復、コンプライアンスレポートのツールを提供する MBAM 機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-121">Installs MBAM features that provide advanced group policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb4d7-122">削除-Mbamハードウェアタイプ</span><span class="sxs-lookup"><span data-stu-id="bb4d7-122">Remove-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-123">ハードウェアインベントリからハードウェアモデルを削除します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-123">Removes the hardware models from the hardware inventory.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb4d7-124">Set-Mbamハードウェアタイプ</span><span class="sxs-lookup"><span data-stu-id="bb4d7-124">Set-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-125">マスターハードウェアインベントリを管理することで、ハードウェアモデルが BitLocker 暗号化を実行できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-125">Allows management of a master hardware inventory to designate whether or not hardware models are capable or incapable to perform BitLocker encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb4d7-126">アンインストール-Mbam</span><span class="sxs-lookup"><span data-stu-id="bb4d7-126">Uninstall-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb4d7-127">高度なポリシー、暗号化、キーの回復、コンプライアンスレポートのツールを提供する、以前にインストールされた MBAM 機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="bb4d7-127">Removes previously installed MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="bb4d7-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bb4d7-128">Related topics</span></span>


[<span data-ttu-id="bb4d7-129">MBAM 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="bb4d7-129">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





