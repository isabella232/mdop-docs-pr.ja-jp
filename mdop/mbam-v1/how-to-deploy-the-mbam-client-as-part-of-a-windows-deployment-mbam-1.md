---
title: Windows 展開の一部として MBAM クライアントを展開する方法
description: Windows 展開の一部として MBAM クライアントを展開する方法
author: dansimp
ms.assetid: 8704bf33-535d-41da-b9b2-45b60754367e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a63311bcc93d84472ceff5c80c9222fefd5445c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824914"
---
# <span data-ttu-id="e0908-103">Windows 展開の一部として MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="e0908-103">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="e0908-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="e0908-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="e0908-105">コンピューターのイメージングと Windows の展開プロセス中にクライアントコンピューターで BitLocker 管理と暗号化を有効にすることにより、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="e0908-105">The BitLocker Client can be integrated into an organization by enabling BitLocker management and encryption on client computers during the computer imaging and Windows deployment process.</span></span>

**<span data-ttu-id="e0908-106">注</span><span class="sxs-lookup"><span data-stu-id="e0908-106">Note</span></span>**  
<span data-ttu-id="e0908-107">MBAM クライアントシステム要件を確認するには、「 [mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0908-107">To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>



<span data-ttu-id="e0908-108">Windows 展開の最初のイメージングステージの間に BitLocker を使用してクライアントコンピューターを暗号化すると、MBAM 実装の管理オーバーヘッドを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="e0908-108">Encryption of client computers with BitLocker during the initial imaging stage of a Windows deployment can lower the administrative overhead for MBAM implementation.</span></span> <span data-ttu-id="e0908-109">この方法では、展開されているすべてのコンピューターに既に BitLocker が実行されており、正しく構成されていることも保証されます。</span><span class="sxs-lookup"><span data-stu-id="e0908-109">This approach also ensures that every computer that is deployed already has BitLocker running and is configured correctly.</span></span>

**<span data-ttu-id="e0908-110">Warning</span><span class="sxs-lookup"><span data-stu-id="e0908-110">Warning</span></span>**  
<span data-ttu-id="e0908-111">このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0908-111">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="e0908-112">Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0908-112">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="e0908-113">レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0908-113">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="e0908-114">Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="e0908-114">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="e0908-115">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="e0908-115">Change the registry at your own risk.</span></span>



**<span data-ttu-id="e0908-116">Windows 展開の一部としてコンピューターを暗号化するには</span><span class="sxs-lookup"><span data-stu-id="e0908-116">To encrypt a computer as part of Windows deployment</span></span>**

1.  <span data-ttu-id="e0908-117">組織で、BitLocker のトラステッドプラットフォームモジュール (TPM) プロテクターまたは TPM + PIN プロテクターオプションの使用を計画している場合は、MBAM の最初の展開前に TPM チップをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0908-117">If your organization plans to use the Trusted Platform Module (TPM) protector or the TPM + PIN protector options in BitLocker, you must activate the TPM chip before the initial deployment of MBAM.</span></span> <span data-ttu-id="e0908-118">TPM チップをアクティブ化すると、プロセスの後の再起動が不要になり、TPM チップが組織の要件に従って適切に構成されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e0908-118">When you activate the TPM chip, you avoid a reboot later in the process, and you ensure that the TPM chips are correctly configured according to the requirements of your organization.</span></span> <span data-ttu-id="e0908-119">コンピューターの BIOS で TPM チップを手動でアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0908-119">You must activate the TPM chip manually in the computer's BIOS.</span></span> <span data-ttu-id="e0908-120">TPM チップの構成方法の詳細については、製造元のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0908-120">Refer to the manufacturer documentation for more details about how to configure the TPM chip.</span></span>

2.  <span data-ttu-id="e0908-121">MBAM クライアントエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e0908-121">Install the MBAM client agent.</span></span>

3.  <span data-ttu-id="e0908-122">コンピューターをドメインに参加させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0908-122">We recommend that you join the computer to a domain...</span></span>

    -   <span data-ttu-id="e0908-123">コンピューターがドメインに参加していない場合は、MBAM キーの回復サービスに回復パスワードは保存されません。</span><span class="sxs-lookup"><span data-stu-id="e0908-123">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="e0908-124">既定では、MBAM は、回復キーが保存されていない限り、暗号化を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0908-124">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="e0908-125">コンピューターが、MBAM サーバーに回復キーが保存される前に回復モードで起動した場合、コンピューターを再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0908-125">If a computer starts in recovery mode before the recovery key is stored on the MBAM server, the computer has to be reimaged.</span></span> <span data-ttu-id="e0908-126">使用できる回復方法はありません。</span><span class="sxs-lookup"><span data-stu-id="e0908-126">No recovery method is available.</span></span>

4.  <span data-ttu-id="e0908-127">管理者としてコマンドプロンプトを開き、MBAM サービスを停止して、サービスを [**手動**] または **[オンデマンド**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0908-127">Open a command prompt as an administrator, stop the MBAM service, and then set the service to **manual** or **on demand**.</span></span> <span data-ttu-id="e0908-128">次に、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0908-128">Then, run the following commands:</span></span>

    **<span data-ttu-id="e0908-129">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="e0908-129">net stop mbamagent</span></span>**

    **<span data-ttu-id="e0908-130">sc config mbamagent start = demand</span><span class="sxs-lookup"><span data-stu-id="e0908-130">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="e0908-131">MBAM エージェントのレジストリ設定を設定して、グループポリシーを無視し、TPM を**オペレーティングシステムのみ暗号化**として実行します。これを行うには、regedit を実行し、次に、 **regedit.exe**を実行して、レジストリキーテンプレートを c/the ¥¥¥¥ files ¥¥¥¥ |</span><span class="sxs-lookup"><span data-stu-id="e0908-131">Set the registry settings for the MBAM agent to ignore Group Policy and run the TPM for **operating system only encryption** To do this, run **regedit**, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

6.  <span data-ttu-id="e0908-132">Regedit で、HKLM\\SOFTWARE\\Microsoft\\MBAM にアクセスし、次の表に示す設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e0908-132">In regedit, go to HKLM\\SOFTWARE\\Microsoft\\MBAM and configure the settings that are listed in the following table.</span></span>

    <span data-ttu-id="e0908-133">レジストリエントリ</span><span class="sxs-lookup"><span data-stu-id="e0908-133">Registry entry</span></span>

    <span data-ttu-id="e0908-134">構成設定</span><span class="sxs-lookup"><span data-stu-id="e0908-134">Configuration settings</span></span>

    <span data-ttu-id="e0908-135">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="e0908-135">DeploymentTime</span></span>

    <span data-ttu-id="e0908-136">0 = オフ</span><span class="sxs-lookup"><span data-stu-id="e0908-136">0 = OFF</span></span>

    <span data-ttu-id="e0908-137">1 = 展開時のポリシー設定を使用する (既定)</span><span class="sxs-lookup"><span data-stu-id="e0908-137">1 = Use deployment time policy settings (default)</span></span>

    <span data-ttu-id="e0908-138">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="e0908-138">UseKeyRecoveryService</span></span>

    <span data-ttu-id="e0908-139">0 = キーエスクローを使わない (この場合、次の2つのレジストリエントリは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="e0908-139">0 = Do not use key escrow (The next two registry entries are not required in this case.)</span></span>

    <span data-ttu-id="e0908-140">1 = キー回復システムでキーエスクローを使用する (既定)</span><span class="sxs-lookup"><span data-stu-id="e0908-140">1 = Use key escrow in Key Recovery system (default)</span></span>

    <span data-ttu-id="e0908-141">推奨: コンピューターは、キー回復サービスと通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0908-141">Recommended: The computer must be able to communicate with the Key Recovery service.</span></span> <span data-ttu-id="e0908-142">続行する前に、コンピューターがサービスと通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0908-142">Verify that the computer can communicate with the service before you proceed.</span></span>

    <span data-ttu-id="e0908-143">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="e0908-143">KeyRecoveryOptions</span></span>

    <span data-ttu-id="e0908-144">0 = 回復キーのみをアップロードする</span><span class="sxs-lookup"><span data-stu-id="e0908-144">0 = Upload Recovery Key Only</span></span>

    <span data-ttu-id="e0908-145">1 = 回復キーとキー回復パッケージ (既定) をアップロードする</span><span class="sxs-lookup"><span data-stu-id="e0908-145">1 = Upload Recovery Key and Key Recovery Package (default)</span></span>

    <span data-ttu-id="e0908-146">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="e0908-146">KeyRecoveryServiceEndPoint</span></span>

    <span data-ttu-id="e0908-147">この値は、キーの回復 web サーバーの URL に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0908-147">Set this value to the URL for the Key Recovery web server.</span></span>

    <span data-ttu-id="e0908-148">例: http:// &lt; computer name &gt; /MBAMRecoveryAndHardwareService/CoreService.svc.</span><span class="sxs-lookup"><span data-stu-id="e0908-148">Example: http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>



~~~
**Note**  
MBAM policy or registry values can be set here to override the previously set values.
~~~



7. <span data-ttu-id="e0908-149">MBAM クライアントを展開するときに、MBAM エージェントはシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e0908-149">The MBAM agent restarts the system during MBAM client deployment.</span></span> <span data-ttu-id="e0908-150">この再起動の準備ができたら、管理者としてコマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0908-150">When you are ready for this reboot, run the following command at a command prompt as an administrator:</span></span>

   **<span data-ttu-id="e0908-151">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="e0908-151">net start mbamagent</span></span>**

8. <span data-ttu-id="e0908-152">コンピューターが再起動し、BIOS によって TPM の変更を許可するかどうかを確認するメッセージが表示されたら、変更を承諾します。</span><span class="sxs-lookup"><span data-stu-id="e0908-152">When the computers restarts and the BIOS prompts you to accept a TPM change, accept the change.</span></span>

9. <span data-ttu-id="e0908-153">Windows クライアントオペレーティングシステムのイメージングプロセスで、暗号化を開始する準備ができたら、MBAM エージェントサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e0908-153">During the Windows client operating system imaging process, when you are ready to start encryption, restart the MBAM agent service.</span></span> <span data-ttu-id="e0908-154">[開始] を [**自動**] に設定するには、管理者としてコマンドプロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0908-154">Then, to set start to **automatic**, open a command prompt as an administrator and run the following commands:</span></span>

   **<span data-ttu-id="e0908-155">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="e0908-155">sc config mbamagent start= auto</span></span>**

   **<span data-ttu-id="e0908-156">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="e0908-156">net start mbamagent</span></span>**

10. <span data-ttu-id="e0908-157">バイパスレジストリ値を削除します。</span><span class="sxs-lookup"><span data-stu-id="e0908-157">Remove the bypass registry values.</span></span> <span data-ttu-id="e0908-158">これを行うには、regedit を実行し、HKLM\\SOFTWARE\\Microsoft レジストリエントリを参照して、 **Mbam**ノードを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0908-158">To do this, run regedit, browse to the HKLM\\SOFTWARE\\Microsoft registry entry, right-click the **MBAM** node, and then click **Delete**.</span></span>

## <span data-ttu-id="e0908-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e0908-159">Related topics</span></span>


[<span data-ttu-id="e0908-160">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="e0908-160">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)









