---
title: MBAM 2.0 の概要
description: MBAM 2.0 の概要
author: dansimp
ms.assetid: b43a0ba9-1c83-4854-a2c5-14eea0070e36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7bdf24d1f375dd1fa8b18ac90c2fc49d2887c6c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824317"
---
# <span data-ttu-id="a9430-103">MBAM 2.0 の概要</span><span class="sxs-lookup"><span data-stu-id="a9430-103">About MBAM 2.0</span></span>


<span data-ttu-id="a9430-104">Microsoft BitLockerAdministration/Monitoring (MBAM) 2.0 は、BitLocker ドライブ暗号化のための簡素化された管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a9430-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 provides a simplified administrative interface to BitLocker drive encryption.</span></span> <span data-ttu-id="a9430-105">BitLocker は、紛失または盗難になったコンピューターのデータ盗難またはデータ漏洩に対する保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="a9430-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="a9430-106">BitLocker は、Windows オペレーティングシステムボリュームと構成済みのデータボリュームに保存されているすべてのデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="a9430-106">BitLocker encrypts all data that is stored on the Windows operating system volume and configured data volumes.</span></span>

## <span data-ttu-id="a9430-107">MBAM 2.0 について</span><span class="sxs-lookup"><span data-stu-id="a9430-107">About MBAM2.0</span></span>


<span data-ttu-id="a9430-108">BitLockerAdministration と Monitoring 2.0 では、エンタープライズに設定した BitLocker 暗号化ポリシーオプションが適用され、それらのポリシーでクライアントコンピューターのコンプライアンスが監視され、企業と個々のコンピューターの両方の暗号化状態が報告されます。</span><span class="sxs-lookup"><span data-stu-id="a9430-108">BitLockerAdministration and Monitoring2.0 enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of both the enterprise and the individual computers.</span></span> <span data-ttu-id="a9430-109">また、ユーザーが PIN またはパスワードを忘れた場合や、BIOS やブートレコードが変更された場合は、MBAM を使用して回復キーの情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9430-109">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot record changes.</span></span>

<span data-ttu-id="a9430-110">**注** このガイドでは、BitLocker について詳しくは説明していません。</span><span class="sxs-lookup"><span data-stu-id="a9430-110">**Note** BitLocker is not covered in detail in this guide.</span></span> <span data-ttu-id="a9430-111">BitLocker の概要については、「 [Bitlocker ドライブ暗号化の概要](https://go.microsoft.com/fwlink/p/?LinkId=225013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9430-111">For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

<span data-ttu-id="a9430-112">次のグループは、BitLocker を管理するために MBAM を使用することに関心を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9430-112">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="a9430-113">管理者、IT セキュリティの専門家、および機密データが承認されずに公開されないように責任を持つコンプライアンス責任者</span><span class="sxs-lookup"><span data-stu-id="a9430-113">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="a9430-114">リモートまたは支店でコンピューターのセキュリティを担当する管理者</span><span class="sxs-lookup"><span data-stu-id="a9430-114">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="a9430-115">Windows を実行しているクライアントコンピューターに責任を持つ管理者</span><span class="sxs-lookup"><span data-stu-id="a9430-115">Administrators who are responsible for client computers that are running Windows</span></span>

## <a href="" id="what-s-new-in-mbam-2-0"></a><span data-ttu-id="a9430-116">MBAM 2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="a9430-116">What’s New in MBAM2.0</span></span>


<span data-ttu-id="a9430-117">MBAM 2.0 には、次のような新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a9430-117">MBAM2.0 provides the following new features and functionality.</span></span>

### <span data-ttu-id="a9430-118">System Center Configuration Manager と MBAM の統合</span><span class="sxs-lookup"><span data-stu-id="a9430-118">Integration of System Center Configuration Manager with MBAM</span></span>

<span data-ttu-id="a9430-119">MBAM は System Center Configuration Manager との統合をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9430-119">MBAM now supports integration with System Center Configuration Manager.</span></span> <span data-ttu-id="a9430-120">この統合は、MBAM コンプライアンスインフラストラクチャを Configuration Manager のネイティブ環境に移行します。</span><span class="sxs-lookup"><span data-stu-id="a9430-120">This integration moves the MBAM compliance infrastructure into the native environment of Configuration Manager.</span></span> <span data-ttu-id="a9430-121">企業の Configuration Manager を使用する IT 管理者は、Microsoft 管理コンソールで企業のコンプライアンスの状態を表示し、レポートを表示して個々のコンピューターを表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9430-121">IT administrators who use Configuration Manager in their enterprise can now view the compliance status of their enterprise in the Microsoft Management Console and drill into reports to view individual computers.</span></span>

### <span data-ttu-id="a9430-122">ハードウェアの互換性は、Configuration Manager の統合トポロジでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9430-122">Hardware Compatibility is Available Only in the Configuration Manager Integration Topology</span></span>

<span data-ttu-id="a9430-123">構成マネージャーと MBAM を統合すると、mbam での特定の種類のハードウェアの使用を許可または禁止する Configuration Manager の機能が有効になり、MBAM 1.0 で提供されたハードウェア互換性よりも柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="a9430-123">Integrating Configuration Manager with MBAM enables Configuration Manager capabilities that allow or prohibit the use of certain hardware types with MBAM and provides more flexibility than the hardware compatibility that was available in MBAM 1.0.</span></span> <span data-ttu-id="a9430-124">IT 管理者は、独自のコレクションを作成してハードウェアを制限し、MBAM 構成基準をこれらのコレクションに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a9430-124">IT administrators can create their own collections to limit hardware and can deploy the MBAM configuration baseline to those collections.</span></span> <span data-ttu-id="a9430-125">MBAM 1.0 で提供されていた MBAM ハードウェアの互換性は、MBAM Configuration Manager トポロジでのみ利用できるようになり、構成マネージャーから管理されます。</span><span class="sxs-lookup"><span data-stu-id="a9430-125">The MBAM hardware compatibility that was present in MBAM 1.0 is now available only in the MBAM Configuration Manager topology and is administered from Configuration Manager.</span></span>

### <span data-ttu-id="a9430-126">プロテクターの柔軟なポリシー</span><span class="sxs-lookup"><span data-stu-id="a9430-126">Protectors Flexible Policy</span></span>

<span data-ttu-id="a9430-127">プロテクター (TPM + PIN、自動ロック解除、パスワードなど) で既に暗号化されていて、その暗号化のサブセット (TPM または自動ロック解除など) を必要とする MBAM ポリシーを受信したコンピューターは、準拠していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="a9430-127">Computers that are already encrypted with a protector (for example, TPM + PIN or Auto-Unlock and password) and that receive an MBAM policy that requires a subset of that encryption (for example, TPM or Auto-Unlock) are considered compliant.</span></span> <span data-ttu-id="a9430-128">上の例では、IT 管理者がこれらの機能を明示的に定義していない限り、PIN とパスワードは自動的には削除されません。</span><span class="sxs-lookup"><span data-stu-id="a9430-128">In the example above, PIN and password would not be removed automatically unless the IT administrator specifically defines these features as no longer allowed.</span></span>

<span data-ttu-id="a9430-129">暗号化されておらず、MBAM ポリシー (TPM または自動ロック解除など) を受け取るコンピューターは、それに応じて暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a9430-129">Computers that are not encrypted and that receive an MBAM policy (for example, TPM or Auto-Unlock) are encrypted accordingly.</span></span> <span data-ttu-id="a9430-130">ローカル管理者であるユーザーは、BitLocker ツール (コントロールパネル項目の BitLocker ドライブ暗号化または管理-bde) を使って、既存のプロテクター (TPM + PIN、自動ロック解除、パスワードなど) を追加または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a9430-130">Users who are local administrators are allowed to use the BitLocker tools (Control Panel item BitLocker Drive Encryption or Manage-bde) to add or modify the existing protectors (for example, TPM + PIN or Auto-Unlock and password).</span></span> <span data-ttu-id="a9430-131">MBAM ポリシーで明確に定義されている場合を除き、準拠したままになります。</span><span class="sxs-lookup"><span data-stu-id="a9430-131">They remain compliant unless MBAM policies specifically define them.</span></span>

### <span data-ttu-id="a9430-132">MBAM クライアントのアップグレード機能</span><span class="sxs-lookup"><span data-stu-id="a9430-132">Ability to Upgrade the MBAM Client</span></span>

<span data-ttu-id="a9430-133">MBAM 2.0 クライアント Windows Installer は、既存のクライアントのバージョンを検出し、以前のバージョンから MBAM 2.0 クライアントにアップグレードするために必要な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9430-133">The MBAM2.0 Client Windows Installer detects the version of the existing client and performs the required steps to upgrade to the MBAM2.0 Client from previous versions.</span></span>

### <span data-ttu-id="a9430-134">以前のバージョンから MBAM Server にアップグレードする機能</span><span class="sxs-lookup"><span data-stu-id="a9430-134">Ability to Upgrade the MBAM Server from Previous Versions</span></span>

<span data-ttu-id="a9430-135">MBAM 2.0 Server インフラストラクチャは、以前のバージョンの MBAM から次のようにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="a9430-135">You can upgrade the MBAM2.0 Server infrastructure from previous versions of MBAM as follows:</span></span>

<span data-ttu-id="a9430-136">**手動のインプレースサーバー交換**–既存の mbam サーバーインフラストラクチャを手動でアンインストールしてから、mbam 2.0 サーバーインフラストラクチャをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9430-136">**Manual in-place server replacement** – You must manually uninstall the existing MBAM server infrastructure, and then install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="a9430-137">アップグレードを実行するためにデータベースを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a9430-137">You do not have to remove the databases to do the upgrade.</span></span> <span data-ttu-id="a9430-138">代わりに、以前のバージョンの MBAM クライアントで作成された既存のデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9430-138">Instead, you select the existing databases, which the previous version of the MBAM Client created.</span></span> <span data-ttu-id="a9430-139">MBAM 2.0 アップグレードインストールでは、既存のデータベースを MBAM 2.0 に移行します。</span><span class="sxs-lookup"><span data-stu-id="a9430-139">The MBAM2.0 upgrade installation then migrates the existing databases to MBAM 2.0.</span></span>

<span data-ttu-id="a9430-140">**分散クライアントアップグレード**–スタンドアロンの mbam トポロジを使用している場合は、mbam 2.0 サーバーインフラストラクチャをインストールした後に、Mbam クライアントを段階的にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="a9430-140">**Distributed client upgrade** – If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="a9430-141">MBAM 2.0 サーバーによって、既存のクライアントのバージョンが検出され、2.0 クライアントにアップグレードするために必要な手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a9430-141">The MBAM 2.0 Server detects the version of the existing Client and performs the required steps to upgrade to the 2.0 Client.</span></span>

<span data-ttu-id="a9430-142">Mbam 2.0 サーバーインフラストラクチャをアップグレードした後、MBAM 1.0 クライアントは、escrowing の回復データを正常に2.0 報告し続けますが、コンプライアンスは MBAM 1.0 のポリシーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a9430-142">After you upgrade the MBAM 2.0 Server infrastructure, MBAM 1.0 Clients continue to report to the MBAM 2.0 Server successfully, escrowing recovery data, but compliance will be based on the policies in MBAM 1.0.</span></span> <span data-ttu-id="a9430-143">クライアントコンピューターで MBAM 2.0 ポリシーに準拠したコンプライアンスを正確に報告するには、クライアントを MBAM 2.0 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9430-143">You must upgrade clients to MBAM 2.0 to have client computers accurately report compliance against the MBAM 2.0 policies.</span></span> <span data-ttu-id="a9430-144">クライアントは、以前のクライアントをアンインストールせずに MBAM 2.0 クライアントにアップグレードできます。クライアントは、MBAM 2.0 ポリシーの適用と報告を開始します。</span><span class="sxs-lookup"><span data-stu-id="a9430-144">You can upgrade the clients to the MBAM 2.0 Client without uninstalling the previous client, and the client will start to apply and report MBAM 2.0 policies.</span></span>

<span data-ttu-id="a9430-145">MBAM を Configuration Manager で使用している場合は、MBAM 1.0 クライアントを MBAM 2.0 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9430-145">If you are using MBAM with Configuration Manager, you must upgrade the MBAM 1.0 clients to MBAM 2.0.</span></span>

### <a href="" id="mbam-support-for-bitlocker-s-enterprise-scenarios-on-the-windows-8-platform"></a><span data-ttu-id="a9430-146">Windows 8 プラットフォームでの BitLocker のエンタープライズシナリオの MBAM サポート</span><span class="sxs-lookup"><span data-stu-id="a9430-146">MBAM Support for BitLocker’s Enterprise Scenarios on the Windows 8 Platform</span></span>

<span data-ttu-id="a9430-147">MBAM は、MBAM クライアントインストールのターゲットプラットフォームとして、Windows 8 オペレーティングシステムをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a9430-147">MBAM supports the Windows 8 operating system as a target platform for the MBAM Client installation.</span></span> <span data-ttu-id="a9430-148">このサポートにより、IT 管理者は MBAM エージェントのインストール、Windows 8 オペレーティングシステムドライブの暗号化、コンピューターのコンプライアンスの報告などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9430-148">This support enables IT administrators to install the MBAM agent, to encrypt Windows 8 operating system drives, and to report on the compliance of the computers.</span></span> <span data-ttu-id="a9430-149">MBAM は、TPM と TPM + PIN プロテクターを活用して、windows 7 オペレーティングシステムと同様に Windows 8 オペレーティングシステムを管理します。</span><span class="sxs-lookup"><span data-stu-id="a9430-149">MBAM leverages the TPM and TPM+PIN protectors to manage the Windows 8 operating system just as it does the Windows 7 operating system.</span></span> <span data-ttu-id="a9430-150">MBAM 2.0 では、Windows To Go クライアントの暗号化のサポートも追加されています。</span><span class="sxs-lookup"><span data-stu-id="a9430-150">MBAM2.0 also adds support for encrypting Windows To Go clients.</span></span>

### <span data-ttu-id="a9430-151">セルフサービスポータルの追加</span><span class="sxs-lookup"><span data-stu-id="a9430-151">Addition of the Self-Service Portal</span></span>

<span data-ttu-id="a9430-152">エンドユーザーは、セルフサービスポータルを使用して回復キーを回復できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9430-152">End users can now use the Self-Service Portal to recover their recovery keys.</span></span> <span data-ttu-id="a9430-153">セルフサービスポータルは、他の MBAM 機能を備えた1台のサーバーに展開することも、必要に応じて、IT 管理者がユーザーに対してセルフサーバーポータルを公開する柔軟性を持つ個別のサーバーに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9430-153">The Self-Service Portal can be deployed on a single server with the other MBAM features, or on a separate server that gives IT administrators the flexibility to expose the Self-Server Portal to users, as required.</span></span> <span data-ttu-id="a9430-154">セルフサービスポータルがユーザーを認証した後、ユーザーは回復キーを受け取るには、回復キー ID の最初の8桁だけを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9430-154">After the Self-Service Portal authenticates users, users have to enter only the first eight digits of the recovery key ID to receive their recovery key.</span></span>

<span data-ttu-id="a9430-155">MBAM は、ユーザーがキーを回復することをユーザーに許可することによってキーをセキュリティで保護します。これにより、他のユーザーがアクセス権を不正に取得するリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="a9430-155">MBAM also secures the key by allowing users to recover keys only for those computers on which they are users, which reduces the risk that other users gain unauthorized access.</span></span>

### <span data-ttu-id="a9430-156">BitLocker 保護を中断状態から自動的に再開する機能</span><span class="sxs-lookup"><span data-stu-id="a9430-156">Ability to Automatically Resume BitLocker Protection from a Suspended State</span></span>

<span data-ttu-id="a9430-157">MBAM は、IT 管理者は BitLocker を中断して、長期間保護されないようにすることができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a9430-157">MBAM no longer allows IT administrators to keep BitLocker suspended and unprotected for prolonged periods of time.</span></span> <span data-ttu-id="a9430-158">IT 管理者が BitLocker を中断すると、コンピューターが再起動されると、MBAM によって自動的に再度有効になります。これにより、コンピューターが攻撃を受ける可能性が低減されます。</span><span class="sxs-lookup"><span data-stu-id="a9430-158">If an IT administrator suspends BitLocker, MBAM re-enables it automatically when the computer is rebooted, which reduces the risk that the computer can be attacked.</span></span>

### <span data-ttu-id="a9430-159">固定データドライブは、パスワードなしで自動的にロックを解除するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="a9430-159">Fixed Data Drives Can Be Configured to Automatically Unlock Without a Password</span></span>

<span data-ttu-id="a9430-160">固定データドライブ (FDD) ポリシーを設定して、パスワードなしでドライブの自動ロック解除を行うことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9430-160">A Fixed Data Drive (FDD) policy can now be configured to allow automatic unlocking of the drive without a password.</span></span> <span data-ttu-id="a9430-161">FDD が暗号化される前に、パスワードの入力を求めるメッセージは表示されません。また、FDD はセキュリティで保護され、オペレーティングシステムのドライブで自動的にロック解除されます。</span><span class="sxs-lookup"><span data-stu-id="a9430-161">Users are not prompted for a password before the FDD is encrypted, and the FDD will be secured and auto-unlocked with the operating system drive.</span></span>

## <a href="" id="---------mbam-2-0-release-notes"></a> <span data-ttu-id="a9430-162">MBAM 2.0 リリースノート</span><span class="sxs-lookup"><span data-stu-id="a9430-162">MBAM2.0 Release Notes</span></span>


<span data-ttu-id="a9430-163">詳細と、ドキュメントに記載されていない最新ニュースについては、「 [MBAM 2.0 のリリースノート](release-notes-for-mbam-20-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9430-163">For more information, and for late-breaking news that is not included in the documentation, see the [Release Notes for MBAM 2.0](release-notes-for-mbam-20-mbam-2.md).</span></span>

## <span data-ttu-id="a9430-164">MBAM 2.0 の入手方法</span><span class="sxs-lookup"><span data-stu-id="a9430-164">How to Get MBAM2.0</span></span>


<span data-ttu-id="a9430-165">この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9430-165">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="a9430-166">企業のお客様は、Microsoft ソフトウェアアシュアランスで MDOP を入手できます。</span><span class="sxs-lookup"><span data-stu-id="a9430-166">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="a9430-167">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/p/?LinkId=322049)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9430-167">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/p/?LinkId=322049)</span></span>

## <span data-ttu-id="a9430-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a9430-168">Related topics</span></span>


[<span data-ttu-id="a9430-169">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="a9430-169">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





