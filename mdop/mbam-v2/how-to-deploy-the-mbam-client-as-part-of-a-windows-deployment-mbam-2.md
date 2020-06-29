---
title: Windows 展開の一部として MBAM クライアントを展開する方法
description: Windows 展開の一部として MBAM クライアントを展開する方法
author: dansimp
ms.assetid: 67387de7-8b02-4412-9850-3b8d8e5c18af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d75e5748167d2d4866f98e9d3611584067ecd418
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824624"
---
# <span data-ttu-id="178f6-103">Windows 展開の一部として MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="178f6-103">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="178f6-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="178f6-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="178f6-105">トラステッドプラットフォームモジュール (TPM) チップが搭載されているコンピューターの場合、イメージングと Windows 展開プロセスの一部としてクライアントコンピューター上の BitLocker 管理と暗号化を有効にすることで、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="178f6-105">If computers that have a Trusted Platform Module (TPM) chip, the BitLocker client can be integrated into an organization by enabling BitLocker management and encryption on client computers as part of the imaging and Windows deployment process.</span></span>

**<span data-ttu-id="178f6-106">注</span><span class="sxs-lookup"><span data-stu-id="178f6-106">Note</span></span>**  
<span data-ttu-id="178f6-107">Microsoft BitLocker 管理およびクライアントシステム要件の監視については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="178f6-107">To review the Microsoft BitLocker Administration and Monitoring Client system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>



<span data-ttu-id="178f6-108">Windows 展開の最初のイメージングステージで BitLocker を使用してクライアントコンピューターを暗号化すると、組織に MBAM を実装するために必要な管理オーバーヘッドを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="178f6-108">Encrypting client computers with BitLocker during the initial imaging stage of a Windows deployment can lower the administrative overhead necessary for implementing MBAM in an organization.</span></span> <span data-ttu-id="178f6-109">また、展開されているすべてのコンピューターに、既に BitLocker が実行されており、正しく構成されていることも確認します。</span><span class="sxs-lookup"><span data-stu-id="178f6-109">It also ensures that every computer that is deployed already has BitLocker running and is configured correctly.</span></span>

**<span data-ttu-id="178f6-110">注</span><span class="sxs-lookup"><span data-stu-id="178f6-110">Note</span></span>**  
<span data-ttu-id="178f6-111">このトピックの手順では、Windows レジストリの変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="178f6-111">The procedure in this topic describes modifying the Windows registry.</span></span> <span data-ttu-id="178f6-112">レジストリエディターを誤って使用すると、Windows の再インストールが必要になる深刻な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="178f6-112">Using Registry Editor incorrectly can cause serious problems that may require you to reinstall Windows.</span></span> <span data-ttu-id="178f6-113">Microsoft は、レジストリエディターの不正使用によって発生した問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="178f6-113">Microsoft cannot guarantee that problems resulting from the incorrect use of Registry Editor can be solved.</span></span> <span data-ttu-id="178f6-114">レジストリエディターは、各自の責任において使用してください。</span><span class="sxs-lookup"><span data-stu-id="178f6-114">Use Registry Editor at your own risk.</span></span>



**<span data-ttu-id="178f6-115">Windows 展開の一部としてコンピューターを暗号化するには</span><span class="sxs-lookup"><span data-stu-id="178f6-115">To encrypt a computer as part of Windows deployment</span></span>**

1.  <span data-ttu-id="178f6-116">組織で、BitLocker のトラステッドプラットフォームモジュール (TPM) プロテクターまたは TPM + PIN プロテクターオプションの使用を計画している場合は、最初の MBAM の展開前に TPM チップをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="178f6-116">If your organization is planning to use the Trusted Platform Module (TPM) protector or the TPM + PIN protector options in BitLocker, you must activate the TPM chip before the initial deployment of MBAM.</span></span> <span data-ttu-id="178f6-117">TPM チップをアクティブ化すると、プロセスの後の再起動が不要になり、TPM チップが組織の要件に従って適切に構成されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="178f6-117">When you activate the TPM chip, you avoid a reboot later in the process, and you ensure that the TPM chips are correctly configured according to the requirements of your organization.</span></span> <span data-ttu-id="178f6-118">コンピューターの BIOS で TPM チップを手動で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="178f6-118">You must activate the TPM chip manually in the BIOS of the computer.</span></span>

    **<span data-ttu-id="178f6-119">注</span><span class="sxs-lookup"><span data-stu-id="178f6-119">Note</span></span>**  
    <span data-ttu-id="178f6-120">一部のベンダーは、オペレーティングシステム内から BIOS で TPM チップを有効にしてアクティブ化するためのツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="178f6-120">Some vendors provide tools to turn on and activate the TPM chip in the BIOS from within the operating system.</span></span> <span data-ttu-id="178f6-121">TPM チップの構成方法の詳細については、製造元のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="178f6-121">Refer to the manufacturer documentation for more details about how to configure the TPM chip.</span></span>



2.  <span data-ttu-id="178f6-122">Microsoft BitLocker 管理および監視クライアントエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="178f6-122">Install the Microsoft BitLocker Administration and Monitoring client agent.</span></span>

3.  <span data-ttu-id="178f6-123">コンピューターをドメインに参加させる (推奨)。</span><span class="sxs-lookup"><span data-stu-id="178f6-123">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="178f6-124">コンピューターがドメインに参加していない場合、回復パスワードは MBAM キーの回復サービスに保存されません。</span><span class="sxs-lookup"><span data-stu-id="178f6-124">If the computer is not joined to the domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="178f6-125">既定では、MBAM は、回復キーが保存されていない限り、暗号化を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="178f6-125">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="178f6-126">コンピューターが、MBAM サーバーに回復キーが保存される前に回復モードで起動した場合、コンピューターを再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="178f6-126">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, the computer has to be reimaged.</span></span> <span data-ttu-id="178f6-127">使用できる回復方法はありません。</span><span class="sxs-lookup"><span data-stu-id="178f6-127">No recovery method is available.</span></span>

4.  <span data-ttu-id="178f6-128">管理者としてコマンドプロンプトを実行し、MBAM サービスを停止してから、サービスを**手動**または**オンデマンド**に設定してから、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="178f6-128">Run the command prompt as an administrator, stop the MBAM service, and then set the service to **manual** or **on demand**, and then start by typing the following commands:</span></span>

    **<span data-ttu-id="178f6-129">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="178f6-129">net stop mbamagent</span></span>**

    **<span data-ttu-id="178f6-130">sc config mbamagent start = demand</span><span class="sxs-lookup"><span data-stu-id="178f6-130">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="178f6-131">MBAM エージェントのレジストリ設定を設定して、グループポリシーを無視し、**オペレーティングシステムのみの暗号化**については、 **Regedit**を実行して TPM を実行してから、このレジストリキーテンプレートを、c/c/1/30/30/30/@/一度インポートします。</span><span class="sxs-lookup"><span data-stu-id="178f6-131">Set the registry settings for the MBAM agent to ignore Group Policy and run the TPM for **operating system only encryption** by running **Regedit**, and then importing the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

6.  <span data-ttu-id="178f6-132">Regedit で、HKLM\\SOFTWARE\\Microsoft\\MBAM にアクセスし、次の表に記載されている設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="178f6-132">In regedit, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

    <span data-ttu-id="178f6-133">レジストリエントリ</span><span class="sxs-lookup"><span data-stu-id="178f6-133">Registry entry</span></span>

    <span data-ttu-id="178f6-134">構成設定</span><span class="sxs-lookup"><span data-stu-id="178f6-134">Configuration settings</span></span>

    <span data-ttu-id="178f6-135">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="178f6-135">DeploymentTime</span></span>

    <span data-ttu-id="178f6-136">0 = オフ</span><span class="sxs-lookup"><span data-stu-id="178f6-136">0 = OFF</span></span>

    <span data-ttu-id="178f6-137">1 = 展開時のポリシー設定を使用する (既定)</span><span class="sxs-lookup"><span data-stu-id="178f6-137">1 = Use deployment time policy settings (default)</span></span>

    <span data-ttu-id="178f6-138">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="178f6-138">UseKeyRecoveryService</span></span>

    <span data-ttu-id="178f6-139">0 = キーエスクローを使用しません (この場合、次の2つのレジストリエントリは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="178f6-139">0 = Do not use key escrow ( the next two registry entries are not required in this case)</span></span>

    <span data-ttu-id="178f6-140">1 = キー回復システムでキーエスクローを使用する (既定)</span><span class="sxs-lookup"><span data-stu-id="178f6-140">1 = Use key escrow in Key Recovery system (default)</span></span>

    <span data-ttu-id="178f6-141">推奨: コンピューターは、キー回復サービスと通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="178f6-141">Recommended: The computer must be able to communicate with the Key Recovery service.</span></span> <span data-ttu-id="178f6-142">続行する前に、コンピューターがサービスと通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="178f6-142">Verify that the computer can communicate with the service before you proceed.</span></span>

    <span data-ttu-id="178f6-143">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="178f6-143">KeyRecoveryOptions</span></span>

    <span data-ttu-id="178f6-144">0 = 回復キーのみをアップロードする</span><span class="sxs-lookup"><span data-stu-id="178f6-144">0 = Uploads Recovery Key Only</span></span>

    <span data-ttu-id="178f6-145">1 = 回復キーとキー回復パッケージ (既定) をアップロードする</span><span class="sxs-lookup"><span data-stu-id="178f6-145">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

    <span data-ttu-id="178f6-146">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="178f6-146">KeyRecoveryServiceEndPoint</span></span>

    <span data-ttu-id="178f6-147">この値をキー回復 web サーバーの URL に設定します (たとえば、http:// &lt; computer name &gt; /MBAMRecoveryAndHardwareService/CoreService.svc.)。</span><span class="sxs-lookup"><span data-stu-id="178f6-147">Set this value to the URL for the Key Recovery web server, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>



~~~
**Note**  
MBAM policy or registry values can be set here to override previously set values.
~~~



7. <span data-ttu-id="178f6-148">MBAM クライアントを展開するときに、MBAM エージェントはシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="178f6-148">The MBAM agent restarts the system during MBAM client deployment.</span></span> <span data-ttu-id="178f6-149">この再起動の準備ができたら、管理者としてコマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="178f6-149">When you are ready for this reboot, run the following command at a command prompt as an administrator:</span></span>

   **<span data-ttu-id="178f6-150">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="178f6-150">net start mbamagent</span></span>**

8. <span data-ttu-id="178f6-151">コンピューターが再起動し、BIOS によって TPM の変更を許可するかどうかを確認するメッセージが表示されたら、変更を承諾します。</span><span class="sxs-lookup"><span data-stu-id="178f6-151">When the computers restarts, and the BIOS prompts you to accept a TPM change, accept the change.</span></span>

9. <span data-ttu-id="178f6-152">Windows クライアントオペレーティングシステムのイメージングプロセスでは、暗号化を開始する準備ができたら、MBAM agent サービスを再起動し、管理者としてコマンドプロンプトを実行し、次のコマンドを入力して、[開始] を [**自動**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="178f6-152">During the Windows client operating system imaging process, when you are ready to start encryption, restart the MBAM agent service, and set start to **automatic** by running a command prompt as an administrator and typing the following commands:</span></span>

   **<span data-ttu-id="178f6-153">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="178f6-153">sc config mbamagent start= auto</span></span>**

   **<span data-ttu-id="178f6-154">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="178f6-154">net start mbamagent</span></span>**

10. <span data-ttu-id="178f6-155">Regedit を実行し、HKLM\\SOFTWARE\\Microsoft レジストリエントリに移動して、バイパスレジストリ値を削除します。</span><span class="sxs-lookup"><span data-stu-id="178f6-155">Remove the bypass registry values by running Regedit and going to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="178f6-156">**Mbam**ノードを削除するには、ノードを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="178f6-156">To delete the **MBAM** node, right-click the node and click **Delete**.</span></span>

## <span data-ttu-id="178f6-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="178f6-157">Related topics</span></span>


[<span data-ttu-id="178f6-158">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="178f6-158">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)









