---
title: PowerShell を使用した MBAM 2.0 の管理
description: PowerShell を使用した MBAM 2.0 の管理
author: dansimp
ms.assetid: d785a8df-0a8c-4d70-abd2-93a762b4f3de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 736943e707b5d033b8ba6c26641393f02f0cdaf8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823504"
---
# <span data-ttu-id="8f775-103">PowerShell を使用した MBAM 2.0 の管理</span><span class="sxs-lookup"><span data-stu-id="8f775-103">Administering MBAM 2.0 Using PowerShell</span></span>


<span data-ttu-id="8f775-104">Microsoft BitLocker の管理と監視 (MBAM) には、次の Windows PowerShell コマンドレットのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8f775-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="8f775-105">管理者は、これらの PowerShell コマンドレットを使用して、MBAM 管理 web サイトではなく、コマンドラインからさまざまな Microsoft BitLocker 管理および監視サーバータスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8f775-105">Administrators can use these PowerShell cmdlets to perform various Microsoft BitLocker Administration and Monitoring server tasks from the command line rather than from the MBAM administration website.</span></span>

## <span data-ttu-id="8f775-106">PowerShell を使用して MBAM を管理する方法</span><span class="sxs-lookup"><span data-stu-id="8f775-106">How to Administer MBAM Using PowerShell</span></span>


<span data-ttu-id="8f775-107">MBAM を管理するには、ここで説明した PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f775-107">Use the PowerShell cmdlets described here to administer MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8f775-108">名前</span><span class="sxs-lookup"><span data-stu-id="8f775-108">Name</span></span></th>
<th align="left"><span data-ttu-id="8f775-109">説明</span><span class="sxs-lookup"><span data-stu-id="8f775-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f775-110">インストール-Mbam</span><span class="sxs-lookup"><span data-stu-id="8f775-110">Install-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f775-111">高度なポリシー、暗号化、キーの回復、コンプライアンスレポートを提供する MBAM 機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f775-111">Installs the MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8f775-112">アンインストール-Mbam</span><span class="sxs-lookup"><span data-stu-id="8f775-112">Uninstall-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f775-113">高度なポリシー、暗号化、キーの回復、コンプライアンスレポートのツールを提供する MBAM 機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="8f775-113">Removes the MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f775-114">Get-MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="8f775-114">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f775-115">ユーザーがコンピューターまたは暗号化されたドライブのロックを解除できるようにする MBAM 回復キーを要求します。</span><span class="sxs-lookup"><span data-stu-id="8f775-115">Requests an MBAM recovery key that will enable users to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8f775-116">Get-MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="8f775-116">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f775-117">Tpm がロックアウトされているときに、トラステッドプラットフォームモジュール (TPM) のロックを解除するために使うことができる TPM 所有者パスワードをユーザーに提供します。これにより、tpm がロックアウトされ、PIN が受け入れられなくなります。</span><span class="sxs-lookup"><span data-stu-id="8f775-117">Provides users with a TPM owner password that they can use to unlock a Trusted Platform Module (TPM) when the TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8f775-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8f775-118">Related topics</span></span>


[<span data-ttu-id="8f775-119">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="8f775-119">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





