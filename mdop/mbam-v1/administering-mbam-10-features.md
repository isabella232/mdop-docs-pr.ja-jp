---
title: MBAM 1.0 機能の管理
description: MBAM 1.0 機能の管理
author: dansimp
ms.assetid: dd9a9eff-f1ad-4af3-85d9-c19131a4ad22
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a99ac556227c0f113fb20f3aca32d21c204877b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821224"
---
# <span data-ttu-id="a394b-103">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="a394b-103">Administering MBAM 1.0 Features</span></span>


<span data-ttu-id="a394b-104">必要な Microsoft BitLocker 管理と監視 (MBAM) の計画と展開が完了したら、MBAM を構成して使用して、エンタープライズの BitLocker 暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a394b-104">After you complete all necessary Microsoft BitLocker Administration and Monitoring (MBAM) planning and deployment, you can configure and use MBAM to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="a394b-105">このセクションの情報は、インストール後の日常的な MBAM 機能の操作タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a394b-105">The information in this section describes post-installation day-to-day MBAM feature operations tasks.</span></span>

## <span data-ttu-id="a394b-106">MBAM 管理者の役割を管理する</span><span class="sxs-lookup"><span data-stu-id="a394b-106">Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="a394b-107">すべてのサーバー機能について MBAM セットアップが完了したら、管理ユーザーにこれらのサーバー機能へのアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a394b-107">After MBAM Setup is complete for all server features, administrative users must be granted access to these server features.</span></span> <span data-ttu-id="a394b-108">ベストプラクティスとして、MBAM server 機能を管理または使用する管理者は Active Directory のセキュリティグループに割り当てる必要があります。その後、それらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a394b-108">As a best practice, administrators who will manage or use MBAM server features, should be assigned to Active Directory security groups and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

[<span data-ttu-id="a394b-109">MBAM 管理者ロールを管理する方法</span><span class="sxs-lookup"><span data-stu-id="a394b-109">How to Manage MBAM Administrator Roles</span></span>](how-to-manage-mbam-administrator-roles-mbam-1.md)

## <span data-ttu-id="a394b-110">ハードウェアの互換性を管理する</span><span class="sxs-lookup"><span data-stu-id="a394b-110">Manage Hardware Compatibility</span></span>


<span data-ttu-id="a394b-111">MBAM Hardware Compatibility 機能は、サポートする BitLocker として指定したコンピューターハードウェアだけが暗号化されるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a394b-111">The MBAM Hardware Compatibility feature can help you to ensure that only the computer hardware that you specify as supporting BitLocker will be encrypted.</span></span> <span data-ttu-id="a394b-112">この機能が有効になっている場合、ビット \ _admmontla は互換性があるとマークされているコンピューターのみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="a394b-112">When this feature is turned on, bit\_admmontla will encrypt only computers that are marked as Compatible.</span></span>

<span data-ttu-id="a394b-113">**重要** この機能を無効にすると、MBAM ポリシーが展開されているすべてのコンピューターが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a394b-113">**Important** When this feature is turned off, all computers where the MBAM policy is deployed will be encrypted.</span></span>

 

<span data-ttu-id="a394b-114">MBAM は、"ハードウェア互換性チェックの許可" グループポリシーを展開すると、クライアントコンピューターのメーカーとモデルの両方に関する情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="a394b-114">MBAM can collect information on both the make and model of client computers if you deploy the “Allow Hardware Compatibility Checking” Group Policy.</span></span> <span data-ttu-id="a394b-115">このポリシーを構成した場合、mbam クライアントがクライアントコンピューターに展開されると、mbam エージェントによって、コンピューターの製造元とモデル情報が MBAM サーバーに報告されます。</span><span class="sxs-lookup"><span data-stu-id="a394b-115">If you configure this policy, the MBAM agent reports the computer make and model information to the MBAM Server when the MBAM Client is deployed on a client computer.</span></span>

[<span data-ttu-id="a394b-116">ハードウェアの互換性を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a394b-116">How to Manage Hardware Compatibility</span></span>](how-to-manage-hardware-compatibility-mbam-1.md)

[<span data-ttu-id="a394b-117">ユーザーの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a394b-117">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)

## <span data-ttu-id="a394b-118">BitLocker 暗号化の除外を管理する</span><span class="sxs-lookup"><span data-stu-id="a394b-118">Manage BitLocker encryption exemptions</span></span>


<span data-ttu-id="a394b-119">MBAM は、BitLocker 暗号化から、コンピューターの除外とユーザーの除外という2つの形式の除外を付与できます。</span><span class="sxs-lookup"><span data-stu-id="a394b-119">MBAM can grant two forms of exemption from BitLocker encryption: computer exemption and user exemption.</span></span> <span data-ttu-id="a394b-120">通常、コンピューターの除外は、開発やテストで使用されているコンピューター、または BitLocker をサポートしていない古いコンピューターなど、会社が暗号化する必要がないコンピューターを持っている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a394b-120">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="a394b-121">場合によっては、特定のコンピューターが暗号化されていないことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a394b-121">In some cases, local law may also require that certain computers are not encrypted.</span></span> <span data-ttu-id="a394b-122">不要なユーザーを除外したり、ドライブを暗号化したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a394b-122">You may also choose to exempt users who do not need or want their drives encrypted.</span></span>

[<span data-ttu-id="a394b-123">コンピューターの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a394b-123">How to Manage Computer BitLocker Encryption Exemptions</span></span>](how-to-manage-computer-bitlocker-encryption-exemptions.md)

## <span data-ttu-id="a394b-124">コントロールパネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="a394b-124">Manage MBAM Client BitLocker Encryption Options by using the Control Panel</span></span>


<span data-ttu-id="a394b-125">グループポリシーオブジェクト (GPO) を使って有効にした場合、[BitLocker 暗号化オプション] という名前のカスタム MBAM コントロールパネルは、[**システムとセキュリティ**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a394b-125">If enabled through a Group Policy Objects (GPO), a custom MBAM control panel that is named BitLocker Encryption Options will be available under **System and Security**.</span></span> <span data-ttu-id="a394b-126">このカスタマイズされたコントロールパネルは、既定の Windows BitLocker コントロールパネルに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="a394b-126">This customized control panel replaces the default Windows BitLocker control panel.</span></span> <span data-ttu-id="a394b-127">MBAM コントロールパネルでは、暗号化されたドライブ (固定およびリムーバブル) のロックを解除することができます。また、PIN やパスワードの管理にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a394b-127">The MBAM control panel enables you to unlock encrypted drives (fixed and removable), and also helps you manage your PIN or password.</span></span>

[<span data-ttu-id="a394b-128">コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="a394b-128">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-1.md)

## <span data-ttu-id="a394b-129">MBAM 機能の管理に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="a394b-129">Other resources for Administering MBAM features</span></span>


[<span data-ttu-id="a394b-130">MBAM 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="a394b-130">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





