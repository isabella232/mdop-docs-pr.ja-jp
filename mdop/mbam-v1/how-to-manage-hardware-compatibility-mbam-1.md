---
title: ハードウェアの互換性を管理する方法
description: ハードウェアの互換性を管理する方法
author: dansimp
ms.assetid: c74b96b9-8161-49bc-b5bb-4838734e7df5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf9e2c5b2b33ea93d9834a81700bd2be8a9b9757
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812986"
---
# <span data-ttu-id="db18d-103">ハードウェアの互換性を管理する方法</span><span class="sxs-lookup"><span data-stu-id="db18d-103">How to Manage Hardware Compatibility</span></span>


<span data-ttu-id="db18d-104">Microsoft BitLocker の管理と監視 (MBAM) では、[ハードウェア互換性チェックを許可する] グループポリシーを展開した後に、クライアントコンピューターの製造元とモデルに関する情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="db18d-104">Microsoft BitLocker Administration and Monitoring (MBAM) can collect information about the manufacturer and model of client computers after you deploy the Allow Hardware Compatibility Checking Group Policy.</span></span> <span data-ttu-id="db18d-105">このポリシーを構成した場合、mbam クライアントがクライアントコンピューターに展開されると、mbam エージェントによって、コンピューターの製造元とモデル情報が MBAM サーバーに報告されます。</span><span class="sxs-lookup"><span data-stu-id="db18d-105">If you configure this policy, the MBAM agent reports the computer make and model information to the MBAM Server when the MBAM Client is deployed on a client computer.</span></span>

<span data-ttu-id="db18d-106">ハードウェア互換性機能は、組織が、トラステッドプラットフォームモジュール (TPM) チップをサポートしていない旧式のコンピューターハードウェアまたはコンピューターを使用している場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="db18d-106">The Hardware Compatibility feature is helpful when your organization has older computer hardware or computers that do not support Trusted Platform Module (TPM) chips.</span></span> <span data-ttu-id="db18d-107">このような場合は、ハードウェア互換性機能を使って、BitLocker 暗号化がサポートされているコンピューターモデルにのみ適用されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="db18d-107">In these cases, you can use the Hardware Compatibility feature to ensure that BitLocker encryption is applied only to computer models that support it.</span></span> <span data-ttu-id="db18d-108">組織内のすべてのコンピューターで BitLocker がサポートされる場合は、ハードウェア互換性機能を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db18d-108">If all computers in your organization will support BitLocker, you do not have to use the Hardware Compatibility feature.</span></span>

<span data-ttu-id="db18d-109">**注** 既定では、MBAM ハードウェア互換性機能は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="db18d-109">**Note** By default, MBAM Hardware Compatibility feature is not enabled.</span></span> <span data-ttu-id="db18d-110">有効にするには、セットアップ時に [**管理/監視サーバー**機能] の下の [**ハードウェア互換性**] 機能を選びます。</span><span class="sxs-lookup"><span data-stu-id="db18d-110">To enable it, select the **Hardware Compatibility** feature under the **Administration and Monitoring Server** feature during setup.</span></span> <span data-ttu-id="db18d-111">ハードウェアの互換性のセットアップと構成の詳細については、「 [MBAM 1.0 サーバーインフラストラクチャの展開](deploying-the-mbam-10-server-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db18d-111">For more information about how to set up and configure Hardware Compatibility, see [Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md).</span></span>

 

<span data-ttu-id="db18d-112">ハードウェア互換性機能は、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="db18d-112">The Hardware Compatibility feature works in the following way.</span></span>

****

1.  <span data-ttu-id="db18d-113">MBAM クライアントエージェントは、製造元、モデル、BIOS メーカー、BIOS バージョン、TPM メーカー、TPM バージョンなどのコンピューターの基本的な情報を検出し、その情報を MBAM サーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="db18d-113">The MBAM client agent discovers basic computer information such as manufacturer, model, BIOS maker, BIOS version, TPM maker, and TPM version, and then passes this information to the MBAM server.</span></span>

2.  <span data-ttu-id="db18d-114">MBAM サーバーは、クライアントコンピューターの作成とモデルのリストを生成します。これにより、BitLocker をサポートできるものとできないものを区別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="db18d-114">The MBAM server generates a list of client computer makes and models to enable you to differentiate between those that can or cannot support BitLocker</span></span>

3.  <span data-ttu-id="db18d-115">エンタープライズに展開されている MBAM クライアントエージェントは、[**不明**] 状態で検出されたすべての新しいコンピューターによって、このリストを自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="db18d-115">The MBAM client agents that are deployed in the enterprise automatically update this list with all new computer makes and models that are discovered with a state of **Unknown**.</span></span> <span data-ttu-id="db18d-116">その後、管理者は MBAM 管理 web サイトを使用して、特定のコンピューターの作成とモデルに**互換性**があるか**互換性**がないかを指定するように、リストのエントリを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="db18d-116">An administrator can then use the MBAM administration website to change list entries to specify a particular computer make and model as **Compatible** or **Incompatible**.</span></span>

4.  <span data-ttu-id="db18d-117">MBAM クライアントエージェントがドライブの暗号化を開始する前に、エージェントは、実行されているハードウェアの BitLocker 暗号化の互換性を確認します。</span><span class="sxs-lookup"><span data-stu-id="db18d-117">Before the MBAM client agent begins encrypting a drive, the agent first verifies the BitLocker encryption compatibility of the hardware it is running on.</span></span>

    -   <span data-ttu-id="db18d-118">ハードウェアに互換性があるとマークされている場合は、BitLocker 暗号化プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="db18d-118">If the hardware is marked as compatible, the BitLocker encryption process starts.</span></span> <span data-ttu-id="db18d-119">MBAM は、1日に1回、コンピュータのハードウェアの互換性ステータスも再チェックします。</span><span class="sxs-lookup"><span data-stu-id="db18d-119">MBAM will also recheck the hardware compatibility status of the computer one time per day.</span></span>

    -   <span data-ttu-id="db18d-120">ハードウェアに互換性がないとマークされている場合、エージェントはイベントをログに記録し、"ハードウェア免税" の状態をコンプライアンスレポートの一部として渡します。</span><span class="sxs-lookup"><span data-stu-id="db18d-120">If the hardware is marked as incompatible, the agent logs an event and passes a “hardware exempted” state as part of compliance reporting.</span></span> <span data-ttu-id="db18d-121">エージェントは、7日間ごとに、状態が "互換性あり" に変更されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="db18d-121">The agent checks every seven days to see whether the state has changed to “compatible.”</span></span>

    -   <span data-ttu-id="db18d-122">ハードウェアが unknown とマークされている場合、BitLocker 暗号化プロセスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="db18d-122">If the hardware is marked as unknown, the BitLocker encryption process will not begin.</span></span> <span data-ttu-id="db18d-123">MBAM クライアントエージェントは、1日に1回コンピューターのハードウェアの互換性状態を再チェックします。</span><span class="sxs-lookup"><span data-stu-id="db18d-123">The MBAM client agent will recheck the hardware compatibility status of the computer one time per day.</span></span>

<span data-ttu-id="db18d-124">**警告** MBAM クライアントエージェントが、BitLocker ドライブ暗号化をサポートしていないコンピューターを暗号化しようとすると、コンピューターが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db18d-124">**Warning** If the MBAM client agent tries to encrypt a computer that does not support BitLocker drive encryption, there is a possibility that the computer will become corrupted.</span></span> <span data-ttu-id="db18d-125">組織に BitLocker をサポートしていない古いハードウェアがある場合は、ハードウェアの互換性機能が正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db18d-125">Ensure that the hardware compatibility feature is correctly configured when your organization has older hardware that does not support BitLocker.</span></span>

 

**<span data-ttu-id="db18d-126">ハードウェアの互換性を管理するには</span><span class="sxs-lookup"><span data-stu-id="db18d-126">To manage hardware compatibility</span></span>**

1.  <span data-ttu-id="db18d-127">Web ブラウザーを開き、Microsoft BitLocker の管理と監視の web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="db18d-127">Open a web browser and navigate to the Microsoft BitLocker Administration and Monitoring website.</span></span> <span data-ttu-id="db18d-128">左側のメニューバーで、[**ハードウェア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="db18d-128">Select **Hardware** in the left menu bar.</span></span>

2.  <span data-ttu-id="db18d-129">右側のウィンドウで、[**高度な検索**] をクリックし、[フィルター] をクリックして、**機能**の状態が [**不明**] であるすべてのコンピューターモデルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="db18d-129">On the right pane, click **Advanced Search**, and then filter to display a list of all computer models that have a **Capability** status of **Unknown**.</span></span> <span data-ttu-id="db18d-130">検索条件に一致するコンピューターモデルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="db18d-130">A list of computer models matching the search criteria is displayed.</span></span> <span data-ttu-id="db18d-131">管理者は、このページから新しいコンピューターの種類を追加、編集、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="db18d-131">Administrators can add, edit, or remove new computer types from this page.</span></span>

3.  <span data-ttu-id="db18d-132">不明なハードウェア構成を確認して、構成を**互換性**のあるものに設定するべきか、**互換性**のないものかを判断します。</span><span class="sxs-lookup"><span data-stu-id="db18d-132">Review each unknown hardware configuration to determine whether the configuration should be set to **Compatible** or **Incompatible**.</span></span>

4.  <span data-ttu-id="db18d-133">1つまたは複数の行を選択し、[**互換性の設定**] または [互換性のない**設定**] のいずれかをクリックして、選択したコンピューターモデルの BitLocker の互換性 (該当する場合) を設定します。</span><span class="sxs-lookup"><span data-stu-id="db18d-133">Select one or more rows, and then click either **Set Compatible** or **Set Incompatible** to set the BitLocker compatibility, as appropriate, for the selected computer models.</span></span> <span data-ttu-id="db18d-134">**互換性**が設定されている場合、サポートされているモデルに一致するコンピューターに対して、BitLocker はドライブ暗号化ポリシーを強制しようとします。</span><span class="sxs-lookup"><span data-stu-id="db18d-134">If set to **Compatible**, BitLocker tries to enforce drive encryption policy on computers that match the supported model.</span></span> <span data-ttu-id="db18d-135">[**互換性**なし] に設定した場合、BitLocker では、これらのコンピューターに対してドライブ暗号化ポリシーは強制されません。</span><span class="sxs-lookup"><span data-stu-id="db18d-135">If set to **Incompatible**, BitLocker will not enforce drive encryption policy on those computers.</span></span>

    <span data-ttu-id="db18d-136">**注** コンピューターモデルを互換性のあるものとして設定した後、MBAM クライアントがそのハードウェアモデルに一致するコンピューターで BitLocker 暗号化を開始するには、24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="db18d-136">**Note** After you set a computer model as compatible, it can take more than twenty-four hours for the MBAM Client to begin BitLocker encryption on the computers matching that hardware model.</span></span>

     

5.  <span data-ttu-id="db18d-137">管理者は、MBAM エージェントによって検出された新しいモデルを確認するために、ハードウェア互換性リストを定期的に監視する必要があります。その**場合は、** 互換性の設定を適切に更新**してください**。</span><span class="sxs-lookup"><span data-stu-id="db18d-137">Administrators should regularly monitor the hardware compatibility list to review new models that are discovered by the MBAM agent, and then update their compatibility setting to **Compatible** or **Incompatible** as appropriate.</span></span>

## <span data-ttu-id="db18d-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db18d-138">Related topics</span></span>


[<span data-ttu-id="db18d-139">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="db18d-139">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





