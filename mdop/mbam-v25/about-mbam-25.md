---
title: MBAM 2.5 の概要
description: MBAM 2.5 の概要
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824214"
---
# <span data-ttu-id="d3d3d-103">MBAM 2.5 の概要</span><span class="sxs-lookup"><span data-stu-id="d3d3d-103">About MBAM 2.5</span></span>


<span data-ttu-id="d3d3d-104">Microsoft BitLocker の管理と監視 (MBAM) 2.5 は、BitLocker ドライブ暗号化用の簡素化された管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-104">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 provides a simplified administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="d3d3d-105">BitLocker は、紛失または盗難になったコンピューターのデータ盗難またはデータ漏洩に対する保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="d3d3d-106">BitLocker は、Windows オペレーティングシステムボリュームとドライブに保存されているすべてのデータを暗号化し、データドライブを構成します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-106">BitLocker encrypts all data that is stored on the Windows operating system volumes and drives and configured data drives.</span></span>

## <span data-ttu-id="d3d3d-107">MBAM の概要</span><span class="sxs-lookup"><span data-stu-id="d3d3d-107">Overview of MBAM</span></span>


<span data-ttu-id="d3d3d-108">MBAM 2.5 には次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-108">MBAM 2.5 has the following features:</span></span>

-   <span data-ttu-id="d3d3d-109">管理者は、企業全体のクライアント コンピューター上のボリュームを暗号化するプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-109">Enables administrators to automate the process of encrypting volumes on client computers across the enterprise.</span></span>

-   <span data-ttu-id="d3d3d-110">セキュリティ担当者は、個々のコンピューターまたは企業全体の準拠状態をすばやく判断できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-110">Enables security officers to quickly determine the compliance state of individual computers or even of the enterprise itself.</span></span>

-   <span data-ttu-id="d3d3d-111">Microsoft System Center Configuration Manager により、一元的なレポートおよびハードウェア管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-111">Provides centralized reporting and hardware management with Microsoft System Center Configuration Manager.</span></span>

-   <span data-ttu-id="d3d3d-112">ヘルプデスクの作業負荷を減らし、BitLocker PIN と回復キー要求を使ってエンドユーザーを支援します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-112">Reduces the workload on the Help Desk to assist end users with BitLocker PIN and recovery key requests.</span></span>

-   <span data-ttu-id="d3d3d-113">エンド ユーザーは、セルフ サービス ポータルを使って、暗号化されたデバイスを自分で回復できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-113">Enables end users to recover encrypted devices independently by using the Self-Service Portal.</span></span>

-   <span data-ttu-id="d3d3d-114">セキュリティ責任者が、重要な情報を回復するためのアクセスを簡単に監査できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-114">Enables security officers to easily audit access to recover key information.</span></span>

-   <span data-ttu-id="d3d3d-115">企業データの保護を保証することにより、Windows Enterprise ユーザーがどこにいても作業を継続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-115">Empowers Windows Enterprise users to continue working anywhere with the assurance that their corporate data is protected.</span></span>

<span data-ttu-id="d3d3d-116">MBAM は、企業に対して設定した BitLocker 暗号化ポリシーオプションを適用し、それらのポリシーでクライアントコンピューターのコンプライアンスを監視し、企業および個人のコンピューターの暗号化状態に関するレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-116">MBAM enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of the enterprise’s and individual’s computers.</span></span> <span data-ttu-id="d3d3d-117">また、ユーザーが PIN やパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合は、MBAM を使用して回復キーの情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-117">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot records change.</span></span>

<span data-ttu-id="d3d3d-118">次のグループは、BitLocker を管理するために MBAM を使用することに関心を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-118">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="d3d3d-119">管理者、IT セキュリティの専門家、および機密データが承認されずに公開されないように責任を持つコンプライアンス責任者</span><span class="sxs-lookup"><span data-stu-id="d3d3d-119">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="d3d3d-120">リモートまたは支店でコンピューターのセキュリティを担当する管理者</span><span class="sxs-lookup"><span data-stu-id="d3d3d-120">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="d3d3d-121">Windows を実行しているクライアントコンピューターに責任を持つ管理者</span><span class="sxs-lookup"><span data-stu-id="d3d3d-121">Administrators who are responsible for client computers that are running Windows</span></span>

<span data-ttu-id="d3d3d-122">**注** この MBAM 文書では、BitLocker について詳しくは説明していません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-122">**Note** BitLocker is not explained in detail in this MBAM documentation.</span></span> <span data-ttu-id="d3d3d-123">詳細については、「 [BitLocker ドライブの暗号化の概要](https://go.microsoft.com/fwlink/p/?LinkId=225013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-123">For more information, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

## <a href="" id="what-s-new-in-mbam-2-5"></a><span data-ttu-id="d3d3d-124">MBAM 2.5 の新機能</span><span class="sxs-lookup"><span data-stu-id="d3d3d-124">What’s new in MBAM 2.5</span></span>


<span data-ttu-id="d3d3d-125">このセクションでは、MBAM 2.5 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-125">This section describes the new features in MBAM 2.5.</span></span>

### <span data-ttu-id="d3d3d-126">Microsoft SQL Server 2014 のサポート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-126">Support for Microsoft SQL Server 2014</span></span>

<span data-ttu-id="d3d3d-127">MBAM は、以前のバージョンの MBAM でサポートされているものと同じソフトウェアも、Microsoft SQL Server 2014 のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-127">MBAM adds support for Microsoft SQL Server 2014, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> <span data-ttu-id="d3d3d-128">別々にダウンロードされた MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-128">MBAM Group Policy Templates downloaded separately</span></span>

<span data-ttu-id="d3d3d-129">Mbam グループポリシーテンプレートは、MBAM インストールとは別にダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-129">The MBAM Group Policy Templates must be downloaded separately from the MBAM installation.</span></span> <span data-ttu-id="d3d3d-130">以前のバージョンの MBAM では、mbam installer に MBAM ポリシーテンプレートが含まれています。このテンプレートには、BitLocker ドライブ暗号化の MBAM 実装設定を定義する、必要な MBAM 固有のグループポリシーオブジェクト (Gpo) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-130">In previous versions of MBAM, the MBAM installer included an MBAM Policy Template, which contained the required MBAM-specific Group Policy Objects (GPOs) that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="d3d3d-131">これらの Gpo は、MBAM インストーラーから削除されています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-131">These GPOs have been removed from the MBAM installer.</span></span> <span data-ttu-id="d3d3d-132">次に、MBAM クライアントのインストールを開始する前に、 [MDOP グループポリシー (admx) テンプレートを取得](https://go.microsoft.com/fwlink/p/?LinkId=393941)してサーバーまたはワークステーションにコピーする方法から gpo をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-132">You now download the GPOs from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation before you begin the MBAM Client installation.</span></span> <span data-ttu-id="d3d3d-133">グループポリシーテンプレートは、サポートされているバージョンの Windows サーバーまたは Windows オペレーティングシステムを実行している任意のサーバーまたはワークステーションにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-133">You can copy the Group Policy Templates to any server or workstation that is running a supported version of the Windows Server or Windows operating system.</span></span>

<span data-ttu-id="d3d3d-134">**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-134">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="d3d3d-135">[ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に Bitlocker ドライブ暗号化設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-135">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the BitLocker Drive Encryption settings for you.</span></span>

 

<span data-ttu-id="d3d3d-136">サーバーまたはワークステーションにコピーする必要があるテンプレートファイルは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-136">The template files that you need to copy to a server or workstation are:</span></span>

-   <span data-ttu-id="d3d3d-137">BitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="d3d3d-137">BitLockerManagement.adml</span></span>

-   <span data-ttu-id="d3d3d-138">BitLockerManagement の admx</span><span class="sxs-lookup"><span data-stu-id="d3d3d-138">BitLockerManagement.admx</span></span>

-   <span data-ttu-id="d3d3d-139">BitLockerUserManagement</span><span class="sxs-lookup"><span data-stu-id="d3d3d-139">BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="d3d3d-140">BitLockerUserManagement。 admx</span><span class="sxs-lookup"><span data-stu-id="d3d3d-140">BitLockerUserManagement.admx</span></span>

<span data-ttu-id="d3d3d-141">目的に合った場所にテンプレートファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-141">Copy the template files to the location that best meets your needs.</span></span> <span data-ttu-id="d3d3d-142">言語固有のファイルの場合、言語固有のフォルダーにコピーする必要があります。そのためには、ファイルを表示するためにグループポリシー管理コンソールが必要です。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-142">For the language-specific files, which must be copied to a language-specific folder, the Group Policy Management Console is required to view the files.</span></span>

- <span data-ttu-id="d3d3d-143">テンプレートファイルをサーバーまたはワークステーションにローカルにインストールするには、次のいずれかの場所にファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-143">To install the template files locally on a server or workstation, copy the files to one of the following locations.</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left"><span data-ttu-id="d3d3d-144">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="d3d3d-144">File type</span></span></th>
  <th align="left"><span data-ttu-id="d3d3d-145">ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="d3d3d-145">File location</span></span></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="d3d3d-146">ニュートラル言語 (admx)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-146">language neutral (.admx)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="d3d3d-147">% systemroot% </em> \ ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="d3d3d-147">%systemroot%</em>\policyDefinitions</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="d3d3d-148">言語固有の (adml)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-148">language specific (.adml)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="d3d3d-149">% systemroot% </em> \ policydefinitions [ <em> MUIculture </em> ] (たとえば、米国英語言語固有のファイルは、 <em> % systemroot% &lt; /em ポリシー定義に保存されます &gt; )</span><span class="sxs-lookup"><span data-stu-id="d3d3d-149">%systemroot%</em>\policyDefinitions[<em>MUIculture</em>] (for example, the U.S. English language specific file will be stored in <em>%systemroot%&lt;/em&gt;policyDefinitions\en-us)</span></span></p></td>
  </tr>
  </tbody>
  </table>

     

- <span data-ttu-id="d3d3d-150">ドメイン内のすべてのグループポリシー管理者がテンプレートを利用できるようにするには、ドメインコントローラー上の次のいずれかの場所にファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-150">To make the templates available to all Group Policy administrators in a domain, copy the files to one of the following locations on a domain controller.</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left"><span data-ttu-id="d3d3d-151">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="d3d3d-151">File type</span></span></th>
  <th align="left"><span data-ttu-id="d3d3d-152">ドメインコントローラーファイルの場所</span><span class="sxs-lookup"><span data-stu-id="d3d3d-152">Domain controller file location</span></span></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="d3d3d-153">ニュートラル言語 (admx)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-153">Language neutral (.admx)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="d3d3d-154">% systemroot% </em> sysvol\domain\policies\PolicyDefinitions</span><span class="sxs-lookup"><span data-stu-id="d3d3d-154">%systemroot%</em>sysvol\domain\policies\PolicyDefinitions</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="d3d3d-155">言語固有の (adml)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-155">Language specific (.adml)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="d3d3d-156">% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] (たとえば、米国英語の言語固有のファイルは <em> % systemroot% \sysvol\domain\policies\PolicyDefinitions\en-us に保存されます </em> )</span><span class="sxs-lookup"><span data-stu-id="d3d3d-156">%systemroot%</em>\sysvol\domain\policies\PolicyDefinitions[<em>MUIculture</em>] (for example, the U.S. English language-specific file will be stored in <em>%systemroot%</em>\sysvol\domain\policies\PolicyDefinitions\en-us)</span></span></p></td>
  </tr>
  </tbody>
  </table>

     

<span data-ttu-id="d3d3d-157">テンプレートファイルの詳細については、「[グループポリシーの ADMX ファイルを管理する](https://go.microsoft.com/fwlink/?LinkId=392818)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-157">For more information about template files, see [Managing Group Policy ADMX Files Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=392818).</span></span>

### <span data-ttu-id="d3d3d-158">オペレーティングシステムと固定データドライブで暗号化ポリシーを適用する機能</span><span class="sxs-lookup"><span data-stu-id="d3d3d-158">Ability to enforce encryption policies on operating system and fixed data drives</span></span>

<span data-ttu-id="d3d3d-159">MBAM 2.5 では、オペレーティングシステムと固定データドライブについて、組織内のコンピューターの暗号化ポリシーを適用し、MBAM 暗号化ポリシーに準拠するために要件の延期を要求できる日数を制限できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-159">MBAM2.5 enables you to enforce encryption policies on operating system and fixed data drives for computers in your organization and limit the number of days that end users can request a postponement of the requirement to comply with MBAM encryption policies.</span></span>

<span data-ttu-id="d3d3d-160">暗号化ポリシーの強制を構成できるようにするため、[暗号化ポリシーの強制設定] と呼ばれる新しいグループポリシー設定が、オペレーティングシステムドライブと固定データドライブに追加されています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-160">To enable you to configure encryption policy enforcement, a new Group Policy setting, called Encryption Policy Enforcement Settings, has been added for operating system drives and fixed data drives.</span></span> <span data-ttu-id="d3d3d-161">このポリシーについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-161">This policy is described in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d3d3d-162">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="d3d3d-162">Group Policy setting</span></span></th>
<th align="left"><span data-ttu-id="d3d3d-163">説明</span><span class="sxs-lookup"><span data-stu-id="d3d3d-163">Description</span></span></th>
<th align="left"><span data-ttu-id="d3d3d-164">この設定を構成するために使用されるグループポリシーノード</span><span class="sxs-lookup"><span data-stu-id="d3d3d-164">Group Policy node used to configure this setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3d3d-165">暗号化ポリシーの適用設定 (オペレーティングシステムドライブ)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-165">Encryption Policy Enforcement Settings (Operating System Drive)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-166">この設定では、[オペレーティングシステムドライブの猶予期間の日数を設定する] オプションを使用して、 <strong> </strong> 猶予期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-166">For this setting, use the option <strong>Configure the number of noncompliance grace period days for operating system drives</strong> to configure a grace period.</span></span></p>
<p><span data-ttu-id="d3d3d-167">猶予期間は、ドライブが非準拠として検出された後、エンドユーザーが、使用しているオペレーティングシステムドライブの MBAM ポリシーに準拠することを可能にする日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-167">The grace period specifies the number of days that end users can postpone compliance with MBAM policies for their operating system drive after the drive is first detected as noncompliant.</span></span></p>
<p><span data-ttu-id="d3d3d-168">設定された猶予期間の有効期限が切れた後は、ユーザーは必要な操作を延期したり、除外を要求したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-168">After the configured grace period expires, users cannot postpone the required action or request an exemption from it.</span></span></p>
<p><span data-ttu-id="d3d3d-169">ユーザーの操作が必要な場合 (たとえば、トラステッドプラットフォームモジュール (TPM) + PIN を使用している場合、またはパスワードプロテクターを使用している場合) は、ダイアログボックスが表示され、ユーザーが必要な情報を入力するまで閉じることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-169">If user interaction is required (for example, if you are using the Trusted Platform Module (TPM) + PIN or using a password protector), a dialog box appears, and users cannot close it until they provide the required information.</span></span> <span data-ttu-id="d3d3d-170">プロテクターが TPM のみの場合は、ユーザー入力なしで暗号化がバックグラウンドで直ちに開始されます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-170">If the protector is TPM only, encryption begins immediately in the background without user input.</span></span></p>
<p><span data-ttu-id="d3d3d-171">ユーザーは、BitLocker 暗号化ウィザードを使って、除外を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-171">Users cannot request exemptions through the BitLocker encryption wizard.</span></span> <span data-ttu-id="d3d3d-172">代わりに、ヘルプデスクに問い合わせるか、組織が除外要求に使用するプロセスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-172">Instead, they must contact their Help Desk or use whatever process their organization uses for exemption requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-173">コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; Windows コンポーネント &gt; MDOP Mbam (BitLocker 管理) &gt; オペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="d3d3d-173">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; Windows Components &gt; MDOP MBAM (BitLocker Management) &gt; Operating System Drive</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3d3d-174">暗号化ポリシーの適用設定 (固定データドライブ)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-174">Encryption Policy Enforcement Settings (Fixed Data Drives)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-175">この設定では、[固定ドライブの猶予期間の日数を設定する] オプションを使用して、 <strong> </strong> 猶予期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-175">For this setting, use the option <strong>Configure the number of noncompliance grace period days for fixed drives</strong> to configure a grace period.</span></span></p>
<p><span data-ttu-id="d3d3d-176">猶予期間は、ドライブが非準拠として検出された後、エンドユーザーが、固定ドライブの MBAM ポリシーに準拠することを延期できる日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-176">The grace period specifies the number of days that end users can postpone compliance with MBAM policies for their fixed drive after the drive is first detected as noncompliant.</span></span></p>
<p><span data-ttu-id="d3d3d-177">猶予期間は、固定ドライブが準拠していないと判断されたときに始まります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-177">The grace period begins when the fixed drive is determined to be noncompliant.</span></span> <span data-ttu-id="d3d3d-178">自動ロック解除を使用している場合は、オペレーティングシステムドライブが準拠するまでポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-178">If you are using auto-unlock, the policy will not be enforced until the operating system drive is compliant.</span></span> <span data-ttu-id="d3d3d-179">ただし、自動ロック解除を使っていない場合は、オペレーティングシステムドライブが完全に暗号化される前に、固定データドライブの暗号化が開始されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-179">However, if you are not using auto-unlock, encryption of the fixed data drive can begin before the operating system drive is fully encrypted.</span></span></p>
<p><span data-ttu-id="d3d3d-180">設定された猶予期間の有効期限が切れた後は、ユーザーは必要な操作を延期したり、除外を要求したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-180">After the configured grace period expires, users cannot postpone the required action or request an exemption from it.</span></span> <span data-ttu-id="d3d3d-181">ユーザーの操作が必要な場合は、ダイアログボックスが表示され、ユーザーが必要な情報を提供するまでそのダイアログボックスを閉じることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-181">If user interaction is required, a dialog box appears and users cannot close it until they provide the required information.</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-182">コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; Windows コンポーネント &gt; MDOP Mbam (BitLocker 管理) &gt; 固定ドライブ</span><span class="sxs-lookup"><span data-stu-id="d3d3d-182">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; Windows Components &gt; MDOP MBAM (BitLocker Management) &gt; Fixed Drive</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="d3d3d-183">BitLocker ドライブ暗号化ウィザードの URL を指定して、セキュリティポリシーをポイントする機能</span><span class="sxs-lookup"><span data-stu-id="d3d3d-183">Ability to provide a URL in the BitLocker Drive Encryption wizard to point to your security policy</span></span>

<span data-ttu-id="d3d3d-184">新しいグループポリシー設定である [**セキュリティポリシー] リンクの url を指定**すると、[**会社セキュリティポリシー**] というリンクとしてエンドユーザーに表示される url を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-184">A new Group Policy setting, **Provide the URL for the Security Policy link**, enables you to configure a URL that will be presented to end users as a link called **Company Security Policy**.</span></span> <span data-ttu-id="d3d3d-185">このリンクは、MBAM がユーザーにボリュームの暗号化を要求したときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-185">This link will appear when MBAM prompts users to encrypt a volume.</span></span>

<span data-ttu-id="d3d3d-186">このポリシー設定を有効にした場合、**会社のセキュリティポリシー**のリンクの URL を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-186">If you enable this policy setting, you can configure the URL for the **Company Security Policy** link.</span></span> <span data-ttu-id="d3d3d-187">このポリシー設定を無効にした場合、または構成しなかった場合、[**会社セキュリティポリシー** ] リンクはユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-187">If you disable or do not configure this policy setting, the **Company Security Policy** link is not displayed to users.</span></span>

<span data-ttu-id="d3d3d-188">新しいグループポリシー設定は、次の GPO ノードにあります。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理) &gt; クライアントの管理**。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-188">The new Group Policy setting is located in the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management) &gt; Client Management**.</span></span>

### <span data-ttu-id="d3d3d-189">FIPS 準拠の回復キーのサポート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-189">Support for FIPS-compliant recovery keys</span></span>

<span data-ttu-id="d3d3d-190">MBAM 2.5、Windows 8.1 オペレーティングシステムを実行しているデバイスで連邦情報処理標準 (FIPS) に準拠する BitLocker 回復キーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-190">MBAM2.5 supports Federal Information Processing Standard (FIPS)-compliant BitLocker recovery keys on devices that are running the Windows8.1 operating system.</span></span> <span data-ttu-id="d3d3d-191">回復キーが以前のバージョンの Windows で FIPS に準拠していませんでした。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-191">The recovery key was not FIPS compliant in earlier versions of Windows.</span></span> <span data-ttu-id="d3d3d-192">この機能拡張により、エンドユーザーが PIN またはパスワードを忘れた場合やコンピューターのロックを解除した場合に、セルフサービスポータルまたは管理と監視の Web サイト (ヘルプデスク) を使ってドライブを回復できるため、FIPS のコンプライアンスが必要な組織内のドライブの回復プロセスが向上します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-192">This enhancement improves the drive recovery process in organizations that require FIPS compliance because it enables end users to use the Self-Service Portal or Administration and Monitoring Website (Help Desk) to recover their drives if they forget their PIN or password or get locked out of their computers.</span></span> <span data-ttu-id="d3d3d-193">新しい FIPS コンプライアンス機能は、パスワード保護機能に拡張されません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-193">The new FIPS compliance feature does not extend to password protectors.</span></span>

<span data-ttu-id="d3d3d-194">組織で FIPS のコンプライアンスを有効にするには、連邦情報処理標準 (FIPS) のグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-194">To enable FIPS compliance in your organization, you must configure the Federal Information Processing Standard (FIPS) Group Policy settings.</span></span> <span data-ttu-id="d3d3d-195">構成手順については、「 [BitLocker グループポリシーの設定](https://go.microsoft.com/fwlink/?LinkId=393560)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-195">For configuration instructions, see [BitLocker Group Policy Settings](https://go.microsoft.com/fwlink/?LinkId=393560).</span></span>

<span data-ttu-id="d3d3d-196">Windows8 または Windows7 オペレーティングシステムを実行しているクライアントコンピューターで、[インストール済みの BitLocker 修正プログラム](https://support.microsoft.com/kb/3015477)を使わない場合、IT 管理者は、FIPS に準拠している環境でデータ回復エージェント (DRA) プロテクターを使い続けることができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-196">For client computers that are running the Windows8 or Windows7 operating systems without the [installed BitLocker hotfix](https://support.microsoft.com/kb/3015477), IT administrators will continue to use the Data Recovery Agents (DRA) protector in FIPS-compliant environments.</span></span> <span data-ttu-id="d3d3d-197">DRA の詳細については、「 [BitLocker でデータ回復エージェントを使用する](https://go.microsoft.com/fwlink/?LinkId=393557)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-197">For information about DRA, see [Using Data Recovery Agents with BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).</span></span>

<span data-ttu-id="d3d3d-198">Windows 7 および Windows 8 コンピューター用の BitLocker ホットフィックスをダウンロードしてインストールするには、「 [bitlocker の管理と2.5 監視を行うための修正プログラムパッケージ 2](https://support.microsoft.com/kb/3015477) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-198">See [Hotfix Package 2 for BitLocker Administration and Monitoring 2.5](https://support.microsoft.com/kb/3015477) to download and install the BitLocker hotfix for Windows 7 and Windows 8 computers.</span></span>

### <span data-ttu-id="d3d3d-199">高可用性展開のサポート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-199">Support for high availability deployments</span></span>

<span data-ttu-id="d3d3d-200">MBAM は、標準の 2 server および Configuration Manager の統合トポロジに加えて、次の高可用性シナリオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-200">MBAM supports the following high-availability scenarios in addition to the standard two-server and Configuration Manager Integration topologies:</span></span>

-   <span data-ttu-id="d3d3d-201">SQL Server AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="d3d3d-201">SQL Server AlwaysOn availability groups</span></span>

-   <span data-ttu-id="d3d3d-202">SQL Server クラスタリング</span><span class="sxs-lookup"><span data-stu-id="d3d3d-202">SQL Server clustering</span></span>

-   <span data-ttu-id="d3d3d-203">ネットワーク負荷分散 (NLB)</span><span class="sxs-lookup"><span data-stu-id="d3d3d-203">Network load balancing (NLB)</span></span>

-   <span data-ttu-id="d3d3d-204">SQL Server のミラーリング</span><span class="sxs-lookup"><span data-stu-id="d3d3d-204">SQL Server mirroring</span></span>

-   <span data-ttu-id="d3d3d-205">ボリュームシャドウコピーサービス (VSS) バックアップ</span><span class="sxs-lookup"><span data-stu-id="d3d3d-205">Volume Shadow Copy Service (VSS) Backup</span></span>

<span data-ttu-id="d3d3d-206">これらの機能の詳細については、「 [MBAM 2.5 の高可用性の計画](planning-for-mbam-25-high-availability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-206">For more information about these features, see [Planning for MBAM 2.5 High Availability](planning-for-mbam-25-high-availability.md).</span></span>

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a><span data-ttu-id="d3d3d-207">管理および監視する Web サイトの役割の管理が変更されました</span><span class="sxs-lookup"><span data-stu-id="d3d3d-207">Management of roles for Administration and Monitoring Website changed</span></span>

<span data-ttu-id="d3d3d-208">MBAM 2.5 では、管理と監視の Web サイトへのアクセス権を提供する役割を管理するために、Active Directory ドメインサービス (ADDS) にセキュリティグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-208">In MBAM2.5, you must create security groups in Active Directory Domain Services (ADDS) to manage the roles that provide access rights to the Administration and Monitoring Website.</span></span> <span data-ttu-id="d3d3d-209">役割によって、特定のセキュリティグループに含まれるユーザーは、レポートを表示したり、エンドユーザーによる暗号化されたドライブの回復を支援したりするなど、web サイトでさまざまなタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-209">Roles enable users who are in specific security groups to perform different tasks in the website such as viewing reports or helping end users recover encrypted drives.</span></span> <span data-ttu-id="d3d3d-210">以前のバージョンの MBAM では、役割はローカルグループを使って管理されていました。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-210">In previous versions of MBAM, roles were managed by using local groups.</span></span>

<span data-ttu-id="d3d3d-211">MBAM 2.5 では、以前のバージョンの MBAM で使用されていた "管理者ロール" という用語は、"ロール" という用語に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-211">In MBAM2.5, the term “roles” replaces the term “administrator roles,” which was used in earlier versions of MBAM.</span></span> <span data-ttu-id="d3d3d-212">また、MBAM 2.5 では、"MBAM System Administrator" ロールは削除されています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-212">In addition, in MBAM2.5 the “MBAM System Administrators” role has been removed.</span></span>

<span data-ttu-id="d3d3d-213">次の表は、AD DS で作成する必要があるセキュリティグループの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-213">The following table lists the security groups that you must create in AD DS.</span></span> <span data-ttu-id="d3d3d-214">セキュリティグループには任意の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-214">You can use any name for the security groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d3d3d-215">ロール</span><span class="sxs-lookup"><span data-stu-id="d3d3d-215">Role</span></span></th>
<th align="left"><span data-ttu-id="d3d3d-216">管理と監視の Web サイトでのこのロールのアクセス権</span><span class="sxs-lookup"><span data-stu-id="d3d3d-216">Access rights for this role on the Administration and Monitoring Website</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3d3d-217">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="d3d3d-217">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-218">MBAM 管理と監視 Web サイトの TPM およびドライブの回復領域へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-218">Provides access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="d3d3d-219">これらの領域にアクセスできるユーザーは、いずれかの領域を使用するときにすべてのフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-219">Users who have access to these areas must fill in all fields when they use either area.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3d3d-220">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="d3d3d-220">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-221">管理と監視の Web サイトにあるレポートへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-221">Provides access to the Reports in the Administration and Monitoring Website.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3d3d-222">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="d3d3d-222">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-223">管理と監視の Web サイトにあるすべての領域へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-223">Provides access to all areas in the Administration and Monitoring Website.</span></span> <span data-ttu-id="d3d3d-224">このグループのユーザーは、エンドユーザーがドライブを回復するときに、エンドユーザーのドメインとユーザー名ではなく、回復キーだけを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-224">Users in this group have to enter only the recovery key, not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="d3d3d-225">ユーザーが MBAM ヘルプデスクユーザーグループのメンバーであり、MBAM Advanced ヘルプデスクユーザーグループのメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループのアクセス許可は、MBAM [ヘルプデスクユーザー] グループの権限よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-225">If a user is a member of the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users group permissions.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="d3d3d-226">追加されたセキュリティグループを作成した後で、ユーザーやグループを適切なセキュリティグループに割り当てると、その管理と監視の Web サイトに対して、対応するレベルのアクセスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-226">After you create the security groups in ADDS, assign users and/or groups to the appropriate security group to enable the corresponding level of access to the Administration and Monitoring Website.</span></span> <span data-ttu-id="d3d3d-227">管理と監視の Web サイトにアクセスするために各ロールを持つユーザーを有効にするには、管理と監視の Web サイトを構成するときに、各セキュリティグループも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-227">To enable individuals with each role to access the Administration and Monitoring Website, you must also specify each security group when you are configuring the Administration and Monitoring Website.</span></span>

### <span data-ttu-id="d3d3d-228">MBAM Server 機能を構成するための Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d3d3d-228">Windows PowerShell cmdlets for configuring MBAM Server features</span></span>

<span data-ttu-id="d3d3d-229">MBAM 2.5 用の Windows PowerShell コマンドレットを使用すると、MBAM サーバー機能の構成と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-229">Windows PowerShell cmdlets for MBAM2.5 enable you to configure and manage the MBAM Server features.</span></span> <span data-ttu-id="d3d3d-230">各機能に対応する Windows PowerShell コマンドレットが用意されており、機能の有効化または無効化、またはこの機能に関する情報の取得に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-230">Each feature has a corresponding Windows PowerShell cmdlet that you can use to enable or disable features, or to get information about the feature.</span></span>

<span data-ttu-id="d3d3d-231">Windows PowerShell を使用するための前提条件と前提条件については、「 [Windows Powershell を使用して MBAM 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-231">For prerequisites and prerequisites for using Windows PowerShell, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

**<span data-ttu-id="d3d3d-232">MBAM サーバーソフトウェアをインストールした後に、Windows PowerShell コマンドレットの MBAM 2.5 ヘルプを読み込むには</span><span class="sxs-lookup"><span data-stu-id="d3d3d-232">To load the MBAM 2.5 Help for Windows PowerShell cmdlets after installing the MBAM Server software</span></span>**

1.  <span data-ttu-id="d3d3d-233">Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-233">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="d3d3d-234">「**更新プログラム-ヘルプ-モジュール Microsoft MBAM」と**入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-234">Type **Update-Help –Module Microsoft.MBAM**.</span></span>

<span data-ttu-id="d3d3d-235">Windows PowerShell for MBAM のヘルプは、次の形式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-235">Windows PowerShell Help for MBAM is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d3d3d-236">Windows PowerShell ヘルプの形式</span><span class="sxs-lookup"><span data-stu-id="d3d3d-236">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="d3d3d-237">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3d3d-237">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3d3d-238">Windows PowerShell コマンドプロンプトで、「 <strong> Get-ヘルプ </strong> &lt; <em> コマンドレット」と入力します。</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="d3d3d-238">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d3d3d-239">最新の Windows PowerShell コマンドレットをアップロードするには、前のセクションの手順に従って、MBAM の Windows PowerShell ヘルプを読み込む方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-239">To upload the latest Windows PowerShell cmdlets, follow the instructions in the previous section on how to load Windows PowerShell Help for MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3d3d-240">Web ページとしての TechNet の場合</span><span class="sxs-lookup"><span data-stu-id="d3d3d-240">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d3d3d-241">Word の .docx ファイルとしてダウンロードセンターで</span><span class="sxs-lookup"><span data-stu-id="d3d3d-241">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d3d3d-242">.Pdf ファイルとしてダウンロードセンターで</span><span class="sxs-lookup"><span data-stu-id="d3d3d-242">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="d3d3d-243">ASCII 専用および拡張ピンをサポートし、連続する文字や繰り返し文字を防ぐ機能</span><span class="sxs-lookup"><span data-stu-id="d3d3d-243">Support for ASCII-only and enhanced PINs and ability to prevent sequential and repeating characters</span></span>

**<span data-ttu-id="d3d3d-244">スタートアップグループポリシー設定の拡張 Pin を許可する</span><span class="sxs-lookup"><span data-stu-id="d3d3d-244">Allow enhanced PINs for startup Group Policy setting</span></span>**

<span data-ttu-id="d3d3d-245">[**スタートアップの拡張 pin を許可**する] グループポリシー設定では、拡張されたスタートアップ Pin が BitLocker で使用されるかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-245">The Group Policy setting, **Allow enhanced PINs for startup**, enables you to configure whether enhanced startup PINs are used with BitLocker.</span></span> <span data-ttu-id="d3d3d-246">強化されたスタートアップ Pin を使用すると、大文字と小文字、記号、数字、スペースなど、フルキーボードでキーを入力できます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-246">Enhanced startup PINs permit users to enter any keys on a full keyboard, including uppercase and lowercase letters, symbols, numbers, and spaces.</span></span> <span data-ttu-id="d3d3d-247">このポリシー設定を有効にすると、設定されているすべての新しい BitLocker スタートアップ Pin が拡張ピンになります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-247">If you enable this policy setting, all new BitLocker startup PINs that are set will be enhanced PINs.</span></span> <span data-ttu-id="d3d3d-248">このポリシー設定を無効にした場合、または構成しなかった場合は、強化された Pin は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-248">If you disable or do not configure this policy setting, enhanced PINs cannot be used.</span></span>

<span data-ttu-id="d3d3d-249">すべてのコンピューターで、プレブート実行環境 (PXE) での拡張 Pin の入力がサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-249">Not all computers support the entry of enhanced PINs in the Pre-Boot Execution Environment (PXE).</span></span> <span data-ttu-id="d3d3d-250">組織のためにこのグループポリシー設定を有効にする前に、BitLocker のセットアッププロセス中にシステムの確認を実行して、コンピューターの BIOS で PXE のフルキーボードの使用がサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-250">Before you enable this Group Policy setting for your organization, run a system check during the BitLocker setup process to ensure that the computer’s BIOS supports the use of the full keyboard in PXE.</span></span> <span data-ttu-id="d3d3d-251">詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-251">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

**<span data-ttu-id="d3d3d-252">[ASCII のみの Pin を要求する] チェックボックス</span><span class="sxs-lookup"><span data-stu-id="d3d3d-252">Require ASCII-only PINs check box</span></span>**

<span data-ttu-id="d3d3d-253">[**スタートアップグループポリシーの拡張 pin の使用を許可**する] グループポリシー設定には、[ **ASCII のみの pin を要求**する] チェックボックスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-253">The **Allow enhanced PINs for startup** Group Policy setting also contains a **Require ASCII-only PINs** check box.</span></span> <span data-ttu-id="d3d3d-254">組織内のコンピューターで、PXE のフルキーボードの使用がサポートされていない場合は、[スタートアップグループポリシー**の拡張 pin を許可**する] チェックボックスをオンにし、[ **ascii のみ**の pin を要求する] チェックボックスをオンにして、拡張された pin に印刷可能な ascii 文字のみを使用するように設定します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-254">If the computers in your organization do not support the use of the full keyboard in PXE, you can enable the **Allow enhanced PINs for startup** Group Policy setting, and then select the **Require ASCII-only PINs** check box to require that enhanced PINs use only printable ASCII characters.</span></span>

**<span data-ttu-id="d3d3d-255">連続していない、または繰り返さない文字の使用を強制した</span><span class="sxs-lookup"><span data-stu-id="d3d3d-255">Enforced use of nonsequential and nonrepeating characters</span></span>**

<span data-ttu-id="d3d3d-256">MBAM 2.5 では、エンドユーザーが繰り返しの数値 (1111 など) や連続番号 (1234 など) で構成されるピンを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-256">MBAM2.5 prevents end users from creating PINs that consist of repeating numbers (such as 1111) or sequential numbers (such as 1234).</span></span> <span data-ttu-id="d3d3d-257">エンドユーザーが3つ以上の繰り返しまたは連続した番号を含むパスワードを入力しようとすると、Bitlocker ドライブ暗号化ウィザードでエラーメッセージが表示され、ユーザーが禁止された文字で PIN を入力できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-257">If end users try to enter a password that contains three or more repeating or sequential numbers, the Bitlocker Drive Encryption wizard displays an error message and prevents users from entering a PIN with the prohibited characters.</span></span>

### <span data-ttu-id="d3d3d-258">BitLocker コンピューターのコンプライアンスレポートへの DRA 証明書の追加</span><span class="sxs-lookup"><span data-stu-id="d3d3d-258">Addition of DRA Certificate to BitLocker Computer Compliance report</span></span>

<span data-ttu-id="d3d3d-259">新しいプロテクター型、データ回復エージェント (DRA) 証明書が、Configuration Manager の BitLocker コンピューターのコンプライアンスレポートに追加されました。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-259">A new protector type, the Data Recovery Agent (DRA) Certificate, has been added to the BitLocker Computer Compliance Report in Configuration Manager.</span></span> <span data-ttu-id="d3d3d-260">このプロテクターの種類は、オペレーティングシステムドライブに適用され、[**プロテクターの種類**] 列の [**コンピューターの音量**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-260">This protector type applies to operating system drives, and it appears in the **Computer Volume(s)** section in the **Protector Types** column.</span></span>

### <span data-ttu-id="d3d3d-261">複数フォレストのサポート展開のサポート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-261">Support for multi-forest support deployments</span></span>

<span data-ttu-id="d3d3d-262">MBAM 2.5 は、次の種類のマルチフォレスト展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-262">MBAM 2.5 supports the following types of multi-forest deployments:</span></span>

-   <span data-ttu-id="d3d3d-263">1つのドメインを持つ単一フォレスト</span><span class="sxs-lookup"><span data-stu-id="d3d3d-263">Single forest with single domain</span></span>

-   <span data-ttu-id="d3d3d-264">1つのツリーと複数のドメインがある単一フォレスト</span><span class="sxs-lookup"><span data-stu-id="d3d3d-264">Single forest with a single tree and multiple domains</span></span>

-   <span data-ttu-id="d3d3d-265">複数のツリーと切り離された名前空間を持つ単一フォレスト</span><span class="sxs-lookup"><span data-stu-id="d3d3d-265">Single forest with multiple trees and disjoint namespaces</span></span>

-   <span data-ttu-id="d3d3d-266">中央フォレストトポロジでの複数フォレスト</span><span class="sxs-lookup"><span data-stu-id="d3d3d-266">Multiple forests in a central forest topology</span></span>

-   <span data-ttu-id="d3d3d-267">リソースフォレストトポロジ内の複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="d3d3d-267">Multiple forests in a resource forest topology</span></span>

<span data-ttu-id="d3d3d-268">フォレストの移行はサポートされません (単一から複数の、複数から単一の、1つのフォレストの間でのリソースなど)、またはアップグレードまたはダウングレードを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-268">There is no support for forest migration (going from single to multiple, multiple to single, resource to across the forest, etc.), or upgrade or downgrade.</span></span>

<span data-ttu-id="d3d3d-269">複数フォレスト展開で MBAM を展開するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-269">The prerequisites for deploying MBAM in multi-forest deployments are:</span></span>

-   <span data-ttu-id="d3d3d-270">フォレストは、サポートされているバージョンの Windows Server 上で実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-270">Forest must be running on supported versions of Windows Server.</span></span>

-   <span data-ttu-id="d3d3d-271">双方向または一方向の信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-271">A two-way or one-way trust is required.</span></span> <span data-ttu-id="d3d3d-272">一方向の信頼では、サーバーのドメインがクライアントのドメインを信頼している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-272">One-way trusts require that the server’s domain trusts the client’s domain.</span></span> <span data-ttu-id="d3d3d-273">つまり、サーバーのドメインはクライアントのドメインで示されます。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-273">In other words, the server’s domain is pointed at the client’s domain.</span></span>

### <span data-ttu-id="d3d3d-274">暗号化されたハードドライブ向け MBAM クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-274">MBAM Client support for Encrypted Hard Drives</span></span>

<span data-ttu-id="d3d3d-275">MBAM は、Opal と IEEE 1667 標準の TCG 仕様要件を満たす、暗号化されたハードドライブ上の BitLocker をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-275">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="d3d3d-276">これらのデバイスで BitLocker が有効になっている場合は、暗号化されたドライブでキーを生成し、管理機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-276">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="d3d3d-277">詳細については、「[暗号化されたハードドライブ](https://technet.microsoft.com/library/hh831627.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-277">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>

## <span data-ttu-id="d3d3d-278">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="d3d3d-278">How to Get MDOP Technologies</span></span>


<span data-ttu-id="d3d3d-279">MBAM は Microsoft デスクトップ最適化パック (MDOP) の一部です。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-279">MBAM is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="d3d3d-280">MDOP は、Microsoft ソフトウェアアシュアランスプログラムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-280">MDOP is part of the Microsoft Software Assurance program.</span></span> <span data-ttu-id="d3d3d-281">Microsoft ソフトウェアアシュアランスプログラムと MDOP の入手方法の詳細については、「 [mdop の入手](https://go.microsoft.com/fwlink/?LinkId=322049)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-281">For more information about the Microsoft Software Assurance program and how to acquire the MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <a href="" id="---------mbam-2-5-release-notes"></a> <span data-ttu-id="d3d3d-282">MBAM 2.5 リリースノート</span><span class="sxs-lookup"><span data-stu-id="d3d3d-282">MBAM 2.5 Release Notes</span></span>


<span data-ttu-id="d3d3d-283">このドキュメントに記載されていない詳細および最新ニュースについては、「 [MBAM 2.5 のリリースノート](release-notes-for-mbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-283">For more information and late-breaking news that is not included in this documentation, see [Release Notes for MBAM 2.5](release-notes-for-mbam-25.md).</span></span>

## <span data-ttu-id="d3d3d-284">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-284">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d3d3d-285">[ここ](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub)にフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-285">Send your feedback [here](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub).</span></span> 
- <span data-ttu-id="d3d3d-286">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="d3d3d-286">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="d3d3d-287">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d3d3d-287">Related topics</span></span>


[<span data-ttu-id="d3d3d-288">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="d3d3d-288">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="d3d3d-289">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="d3d3d-289">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

 

 





