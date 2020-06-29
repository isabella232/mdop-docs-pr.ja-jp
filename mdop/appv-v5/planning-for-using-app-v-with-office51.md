---
title: APP-V で Office を使用するための計画
description: APP-V で Office を使用するための計画
author: dansimp
ms.assetid: e7a19b43-1746-469f-bad6-8e75cf4b3f67
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/16/2017
ms.openlocfilehash: ae225db3c47faca5fba790fb9963bfd4dc2c66b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813411"
---
# <span data-ttu-id="591b6-103">APP-V で Office を使用するための計画</span><span class="sxs-lookup"><span data-stu-id="591b6-103">Planning for Using App-V with Office</span></span>


<span data-ttu-id="591b6-104">Microsoft Application Virtualization (App-v) 5.1 を使用して Office を展開する方法を計画するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="591b6-104">Use the following information to plan how to deploy Office by using Microsoft Application Virtualization (App-V) 5.1.</span></span> <span data-ttu-id="591b6-105">この記事の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="591b6-105">This article includes:</span></span>

-   [<span data-ttu-id="591b6-106">言語パック用の app-v サポート</span><span class="sxs-lookup"><span data-stu-id="591b6-106">App-V support for Language Packs</span></span>](#bkmk-lang-pack)

-   [<span data-ttu-id="591b6-107">サポートされている Microsoft Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="591b6-107">Supported versions of Microsoft Office</span></span>](#bkmk-office-vers-supp-appv)

-   [<span data-ttu-id="591b6-108">共存バージョンの Office での App-v の使用を計画する</span><span class="sxs-lookup"><span data-stu-id="591b6-108">Planning for using App-V with coexisting versions of Office</span></span>](#bkmk-plan-coexisting)

-   [<span data-ttu-id="591b6-109">Office を展開するときに Office を展開するときに Windows と統合する方法</span><span class="sxs-lookup"><span data-stu-id="591b6-109">How Office integrates with Windows when you deploy use App-V to deploy Office</span></span>](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a><span data-ttu-id="591b6-110">言語パック用の app-v サポート</span><span class="sxs-lookup"><span data-stu-id="591b6-110">App-V support for Language Packs</span></span>


<span data-ttu-id="591b6-111">アプリ-V 5.1 Sequencer を使って、言語パック、言語インターフェイスパック、校正ツール、ポップヒント言語用のプラグインパッケージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="591b6-111">You can use the App-V 5.1 Sequencer to create plug-in packages for Language Packs, Language Interface Packs, Proofing Tools and ScreenTip Languages.</span></span> <span data-ttu-id="591b6-112">その後、Office 展開ツールキットを使って作成した Office 2013 パッケージと共に、接続グループにプラグインパッケージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="591b6-112">You can then include the plug-in packages in a Connection Group, along with the Office 2013 package that you create by using the Office Deployment Toolkit.</span></span> <span data-ttu-id="591b6-113">Office アプリケーションとプラグイン言語パックは、接続グループで一緒にグループ化されている他のパッケージと同じように、同じ接続グループでシームレスにやり取りされます。</span><span class="sxs-lookup"><span data-stu-id="591b6-113">The Office applications and the plug-in Language Packs interact seamlessly in the same connection group, just like any other packages that are grouped together in a connection group.</span></span>

><span data-ttu-id="591b6-114">**注** Microsoft Visio および Microsoft Project は、タイ語言語パックのサポートを提供していません。</span><span class="sxs-lookup"><span data-stu-id="591b6-114">**Note** Microsoft Visio and Microsoft Project do not provide support for the Thai Language Pack.</span></span>

 

## <a href="" id="bkmk-office-vers-supp-appv"></a><span data-ttu-id="591b6-115">サポートされている Microsoft Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="591b6-115">Supported versions of Microsoft Office</span></span>

<span data-ttu-id="591b6-116">サポートされている Office 製品のリストについては、「 [app-v でサポートされている Microsoft Office 製品 id](https://support.microsoft.com/help/2842297/product-ids-that-are-supported-by-the-office-deployment-tool-for-click) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="591b6-116">See [Microsoft Office Product IDs that App-V supports](https://support.microsoft.com/help/2842297/product-ids-that-are-supported-by-the-office-deployment-tool-for-click) for a list of supported Office products.</span></span>
><span data-ttu-id="591b6-117">**Note** &nbsp; 注 &nbsp;Enterprise 用 Microsoft 365 アプリ用の App-v パッケージを作成するには、Office 展開ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="591b6-117">**Note**&nbsp;&nbsp;You must use the Office Deployment Tool to create App-V packages for Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="591b6-118">ボリュームライセンス版の Office Professional Plus または Office Standard のパッケージの作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="591b6-118">Creating packages for the volume-licensed versions of Office Professional Plus or Office Standard is not supported.</span></span> <span data-ttu-id="591b6-119">App-v Sequencer は使用できません。</span><span class="sxs-lookup"><span data-stu-id="591b6-119">You cannot use the App-V Sequencer.</span></span>

 

## <a href="" id="bkmk-plan-coexisting"></a><span data-ttu-id="591b6-120">共存バージョンの Office での App-v の使用を計画する</span><span class="sxs-lookup"><span data-stu-id="591b6-120">Planning for using App-V with coexisting versions of Office</span></span>


<span data-ttu-id="591b6-121">"Microsoft Office の共存" を使用すると、同じコンピューターに複数のバージョンの Microsoft Office を同時にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="591b6-121">You can install more than one version of Microsoft Office side by side on the same computer by using “Microsoft Office coexistence.”</span></span> <span data-ttu-id="591b6-122">Windows Installer ベース (MSi) バージョンの Office、クイック実行、および App-v 5.1 を使用して、office のすべての主要バージョンとインストール方法 (該当する場合) を組み合わせて共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="591b6-122">You can implement Office coexistence with combinations of all major versions of Office and with installation methods, as applicable, by using the Windows Installer-based (MSi) version of Office, Click-to-Run, and App-V 5.1.</span></span> <span data-ttu-id="591b6-123">ただし、Microsoft では Office の共存を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="591b6-123">However, using Office coexistence is not recommended by Microsoft.</span></span>

<span data-ttu-id="591b6-124">Microsoft の推奨されるベストプラクティスは、互換性の問題を回避するために、Office を完全に共存させないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="591b6-124">Microsoft’s recommended best practice is to avoid Office coexistence completely to prevent compatibility issues.</span></span> <span data-ttu-id="591b6-125">ただし、新しいバージョンの Office に移行する場合は、すぐに解決できない問題が発生する可能性があるため、一時的に共存を実装して、最新の製品バージョンへの移行を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="591b6-125">However, when you are migrating to a newer version of Office, issues occasionally arise that can’t be resolved immediately, so you can temporarily implement coexistence to help facilitate a faster migration to the latest product version.</span></span> <span data-ttu-id="591b6-126">長期ベースで Office の共存を使用することはお勧めしません。また、組織では、すぐに完全に移行するための計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="591b6-126">Using Office coexistence on a long-term basis is never recommended, and your organization should have a plan to fully transition in the immediate future.</span></span>

### <span data-ttu-id="591b6-127">Office の共存を実装する前に</span><span class="sxs-lookup"><span data-stu-id="591b6-127">Before you implement Office coexistence</span></span>

<span data-ttu-id="591b6-128">Office の共存を実装する前に、次の Office ドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="591b6-128">Before implementing Office coexistence, review the following Office documentation.</span></span> <span data-ttu-id="591b6-129">共存を実装する予定の最新バージョンの Office に対応する記事を選択します。</span><span class="sxs-lookup"><span data-stu-id="591b6-129">Choose the article that corresponds to the newest version of Office for which you plan to implement coexistence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="591b6-130">Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="591b6-130">Office version</span></span></th>
<th align="left"><span data-ttu-id="591b6-131">ガイダンスへのリンク</span><span class="sxs-lookup"><span data-stu-id="591b6-131">Link to guidance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-132">Office 2013</span><span class="sxs-lookup"><span data-stu-id="591b6-132">Office 2013</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)"><span data-ttu-id="591b6-133">他のバージョンの Office を実行しているコンピューターで Office 2013 スイートとプログラム (MSI 展開) を使用する方法についての情報</span><span class="sxs-lookup"><span data-stu-id="591b6-133">Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-134">Office 2010</span><span class="sxs-lookup"><span data-stu-id="591b6-134">Office 2010</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)"><span data-ttu-id="591b6-135">他のバージョンの Office を実行しているコンピューターで Office 2010 スイートとプログラムを使用する方法についての情報</span><span class="sxs-lookup"><span data-stu-id="591b6-135">Information about how to use Office 2010 suites and programs on a computer that is running another version of Office</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="591b6-136">Office ドキュメントでは、Windows Installer ベース (MSi) およびクイック実行インストールの Office の共存に関する広範なガイダンスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="591b6-136">The Office documentation provides extensive guidance on coexistence for Windows Installer-based (MSi) and Click-to-Run installations of Office.</span></span> <span data-ttu-id="591b6-137">このアプリの共存に関するこのトピックでは、App-v の展開に固有の情報を使用して Office ガイダンスを補足します。</span><span class="sxs-lookup"><span data-stu-id="591b6-137">This App-V topic on coexistence supplements the Office guidance with information that is more specific to App-V deployments.</span></span>

### <span data-ttu-id="591b6-138">サポートされている Office の共存シナリオ</span><span class="sxs-lookup"><span data-stu-id="591b6-138">Supported Office coexistence scenarios</span></span>

<span data-ttu-id="591b6-139">次の表は、サポートされている共存シナリオをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="591b6-139">The following tables summarize the supported coexistence scenarios.</span></span> <span data-ttu-id="591b6-140">これらは、最初に使用しているバージョンと展開方法と、移行するバージョンおよび展開方法に従って構成されます。</span><span class="sxs-lookup"><span data-stu-id="591b6-140">They are organized according to the version and deployment method you’re starting with and the version and deployment method you are migrating to.</span></span> <span data-ttu-id="591b6-141">実働の対象ユーザーに展開する前に、すべての共存ソリューションを完全にテストしてください。</span><span class="sxs-lookup"><span data-stu-id="591b6-141">Be sure to fully test all coexistence solutions before deploying them to a production audience.</span></span>

><span data-ttu-id="591b6-142">**注** Microsoft は、リモートデスクトップセッションホストの役割サービスが有効になっている Windows Server 環境での複数バージョンの Office の使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="591b6-142">**Note** Microsoft does not support the use of multiple versions of Office in Windows Server environments that have the Remote Desktop Session Host role service enabled.</span></span> <span data-ttu-id="591b6-143">Office の共存シナリオを実行するには、この役割サービスを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="591b6-143">To run Office coexistence scenarios, you must disable this role service.</span></span>

 

### <span data-ttu-id="591b6-144">Windows 統合 & Office の共存</span><span class="sxs-lookup"><span data-stu-id="591b6-144">Windows integrations & Office coexistence</span></span>

<span data-ttu-id="591b6-145">Windows Installer ベースおよびクイック実行の Office インストール方法は、基になる Windows オペレーティングシステムの特定のポイントと統合されます。</span><span class="sxs-lookup"><span data-stu-id="591b6-145">The Windows Installer-based and Click-to-Run Office installation methods integrate with certain points of the underlying Windows operating system.</span></span> <span data-ttu-id="591b6-146">共存を使用すると、2つの Office バージョン間での一般的なオペレーティングシステムの統合が競合し、互換性とユーザーエクスペリエンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="591b6-146">When you use coexistence, common operating system integrations between two Office versions can conflict, causing compatibility and user experience issues.</span></span> <span data-ttu-id="591b6-147">App-v では、特定のバージョンの Office をシーケンスして、統合を除外し、オペレーティングシステムから "分離" することができます。</span><span class="sxs-lookup"><span data-stu-id="591b6-147">With App-V, you can sequence certain versions of Office to exclude integrations, thereby “isolating” them from the operating system.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="591b6-148">このバージョンの Office を順序指定できるモード (App-v)</span><span class="sxs-lookup"><span data-stu-id="591b6-148">Mode in which App-V can sequence this version of Office</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-149">Office 2007</span><span class="sxs-lookup"><span data-stu-id="591b6-149">Office 2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-150">常に統合されていない。</span><span class="sxs-lookup"><span data-stu-id="591b6-150">Always non-integrated.</span></span> <span data-ttu-id="591b6-151">App-v は、仮想化されたバージョンの Office 2007 とのオペレーティングシステム統合を提供しません。</span><span class="sxs-lookup"><span data-stu-id="591b6-151">App-V does not offer any operating system integrations with a virtualized version of Office 2007.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-152">Office 2010</span><span class="sxs-lookup"><span data-stu-id="591b6-152">Office 2010</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-153">統合モードと非統合モード。</span><span class="sxs-lookup"><span data-stu-id="591b6-153">Integrated and non-integrated mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-154">Office 2013</span><span class="sxs-lookup"><span data-stu-id="591b6-154">Office 2013</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-155">常に統合されます。</span><span class="sxs-lookup"><span data-stu-id="591b6-155">Always integrated.</span></span> <span data-ttu-id="591b6-156">Windows オペレーティングシステムの統合を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="591b6-156">Windows operating system integrations cannot be disabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="591b6-157">Microsoft では、統合された Office インスタンスを1つだけ使用して Office を共存させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="591b6-157">Microsoft recommends that you deploy Office coexistence with only one integrated Office instance.</span></span> <span data-ttu-id="591b6-158">たとえば、Office 2010 と Office 2013 を展開するために App-v を使っている場合は、非統合モードで Office 2010 をシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="591b6-158">For example, if you’re using App-V to deploy Office 2010 and Office 2013, you should sequence Office 2010 in non-integrated mode.</span></span> <span data-ttu-id="591b6-159">統合されていない (分離) モードでの Office の優先順位については、「microsoft [Application Virtualization 5.0 で Microsoft office 2010 の順序を付ける方法](https://support.microsoft.com/kb/2830069)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="591b6-159">For more information about sequencing Office in non-integration (isolated) mode, see [How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0](https://support.microsoft.com/kb/2830069).</span></span>

### <span data-ttu-id="591b6-160">Office の共存シナリオの既知の制限事項</span><span class="sxs-lookup"><span data-stu-id="591b6-160">Known limitations of Office coexistence scenarios</span></span>

<span data-ttu-id="591b6-161">以下のセクションでは、App-v を使用して Office との共存を実装するときに発生する可能性のあるいくつかの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="591b6-161">The following sections describe some issues that you might encounter when using App-V to implement coexistence with Office.</span></span>

### <span data-ttu-id="591b6-162">Windows Installer ベースまたはクイック実行および App-v Office の共存シナリオに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="591b6-162">Limitations common to Windows Installer-based/Click-to-Run and App-V Office coexistence scenarios</span></span>

<span data-ttu-id="591b6-163">同じコンピューターに次のバージョンの Office をインストールすると、次のような制限が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="591b6-163">The following limitations can occur when you install the following versions of Office on the same computer:</span></span>

-   <span data-ttu-id="591b6-164">Windows インストーラーベースのバージョンを使用した Office 2010 の場合</span><span class="sxs-lookup"><span data-stu-id="591b6-164">Office 2010 by using the Windows Installer-based version</span></span>

-   <span data-ttu-id="591b6-165">Office 2013 (app-v を使用)</span><span class="sxs-lookup"><span data-stu-id="591b6-165">Office 2013 by using App-V</span></span>

<span data-ttu-id="591b6-166">以前のバージョンの Windows Installer ベースの Office 2010 を使用して、Office 2013 を side-by-side 使用して公開した後、Windows インストーラーが起動されることがあります。</span><span class="sxs-lookup"><span data-stu-id="591b6-166">After you publish Office 2013 by using App-V side by side with an earlier version of the Windows Installer-based Office 2010 might also cause the Windows Installer to start.</span></span> <span data-ttu-id="591b6-167">これは、Windows Installer ベースまたはクイック実行バージョンの Office 2010 が、自動的にそのコンピューターに登録しようとしているためです。</span><span class="sxs-lookup"><span data-stu-id="591b6-167">This is because the Windows Installer-based or Click-to-Run version of Office 2010 is trying to automatically register itself to the computer.</span></span>

<span data-ttu-id="591b6-168">ネイティブ Word 2010 の自動登録操作をバイパスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="591b6-168">To bypass the auto-registration operation for native Word 2010, follow these steps:</span></span>

1.  <span data-ttu-id="591b6-169">Word 2010 を終了します。</span><span class="sxs-lookup"><span data-stu-id="591b6-169">Exit Word 2010.</span></span>

2.  <span data-ttu-id="591b6-170">次の操作を行って、レジストリエディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="591b6-170">Start the Registry Editor by doing the following:</span></span>

    -   <span data-ttu-id="591b6-171">Windows 7 の場合: [**スタート**] ボタンをクリックし、[検索の開始] ボックスに「 **regedit** 」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="591b6-171">In Windows 7: Click **Start**, type **regedit** in the Start Search box, and then press Enter.</span></span>

    -   <span data-ttu-id="591b6-172">Windows 8.1 または Windows 10 では、「 **regedit** 」と入力し、スタートページで enter キーを押します。次に、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="591b6-172">In Windows 8.1 or Windows 10, type **regedit** press Enter on the Start page and then press Enter.</span></span>

    <span data-ttu-id="591b6-173">管理者パスワードまたは確認のメッセージが表示された場合は、パスワードを入力するか、[**続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="591b6-173">If you are prompted for an administrator password or for a confirmation, type the password, or click **Continue**.</span></span>

3.  <span data-ttu-id="591b6-174">次のレジストリサブキーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="591b6-174">Locate and then select the following registry subkey:</span></span>

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  <span data-ttu-id="591b6-175">[**編集**] メニューの [**新規作成**] をクリックし、[ **DWORD 値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="591b6-175">On the **Edit** menu, click **New**, and then click **DWORD Value**.</span></span>

5.  <span data-ttu-id="591b6-176">「 **NoReReg**」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="591b6-176">Type **NoReReg**, and then press Enter.</span></span>

6.  <span data-ttu-id="591b6-177">[ **NoReReg** ] を右クリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="591b6-177">Right-click **NoReReg** and then click **Modify**.</span></span>

7.  <span data-ttu-id="591b6-178">[ **Valuedata** ] ボックスに「 **1**」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="591b6-178">In the **Valuedata** box, type **1**, and then click **OK**.</span></span>

8.  <span data-ttu-id="591b6-179">[ファイル] メニューの [**終了**] をクリックして、レジストリエディターを終了します。</span><span class="sxs-lookup"><span data-stu-id="591b6-179">On the File menu, click **Exit** to close Registry Editor.</span></span>

## <a href="" id="bkmk-office-integration-win"></a><span data-ttu-id="591b6-180">App-v を使用して Office を展開するときの、Office と Windows との統合方法</span><span class="sxs-lookup"><span data-stu-id="591b6-180">How Office integrates with Windows when you use App-V to deploy Office</span></span>


<span data-ttu-id="591b6-181">App-v を使用して Office 2013 を展開すると、Office はオペレーティングシステムと完全に統合されます。これにより、office は、アプリを展開した場合と同じ機能と機能をエンドユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="591b6-181">When you deploy Office 2013 by using App-V, Office is fully integrated with the operating system, which provides end users with the same features and functionality as Office has when it is deployed without App-V.</span></span>

<span data-ttu-id="591b6-182">Office 2013 App-v パッケージでは、次の統合ポイントが Windows オペレーティングシステムと共にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="591b6-182">The Office 2013 App-V package supports the following integration points with the Windows operating system:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="591b6-183">拡張点</span><span class="sxs-lookup"><span data-stu-id="591b6-183">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="591b6-184">説明</span><span class="sxs-lookup"><span data-stu-id="591b6-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-185">Firefox および Chrome 用の Lync 会議参加プラグイン</span><span class="sxs-lookup"><span data-stu-id="591b6-185">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-186">ユーザーは Firefox と Chrome から Lync 会議に参加できます</span><span class="sxs-lookup"><span data-stu-id="591b6-186">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-187">OneNote プリンタードライバーに送信されました</span><span class="sxs-lookup"><span data-stu-id="591b6-187">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-188">ユーザーは OneNote に印刷できます</span><span class="sxs-lookup"><span data-stu-id="591b6-188">User can print to OneNote</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-189">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="591b6-189">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-190">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="591b6-190">OneNote Linked Notes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-191">OneNote Internet Explorer アドインに送る</span><span class="sxs-lookup"><span data-stu-id="591b6-191">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-192">ユーザーは IE から OneNote に送信できます</span><span class="sxs-lookup"><span data-stu-id="591b6-192">User can send to OneNote from IE</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-193">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="591b6-193">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-194">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="591b6-194">Firewall Exception for Lync and Outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-195">MAPI クライアント</span><span class="sxs-lookup"><span data-stu-id="591b6-195">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-196">ネイティブアプリとアドインは、MAPI 経由で仮想 Outlook を操作できます。</span><span class="sxs-lookup"><span data-stu-id="591b6-196">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-197">Firefox 用 SharePoint プラグイン</span><span class="sxs-lookup"><span data-stu-id="591b6-197">SharePoint Plug-in for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-198">ユーザーは Firefox の SharePoint 機能を使用できる</span><span class="sxs-lookup"><span data-stu-id="591b6-198">User can use SharePoint features in Firefox</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-199">メールコントロールパネルアプレット</span><span class="sxs-lookup"><span data-stu-id="591b6-199">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-200">ユーザーが Outlook の [メールコントロールパネル] アプレットを取得します</span><span class="sxs-lookup"><span data-stu-id="591b6-200">User gets the mail control panel applet in Outlook</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-201">プライマリ相互運用機能アセンブリ</span><span class="sxs-lookup"><span data-stu-id="591b6-201">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-202">マネージアドインのサポート</span><span class="sxs-lookup"><span data-stu-id="591b6-202">Support managed add-ins</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-203">Office ドキュメントキャッシュハンドラー</span><span class="sxs-lookup"><span data-stu-id="591b6-203">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-204">Office アプリケーションのドキュメントキャッシュを許可します</span><span class="sxs-lookup"><span data-stu-id="591b6-204">Allows Document Cache for Office applications</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-205">Outlook プロトコルの検索ハンドラー</span><span class="sxs-lookup"><span data-stu-id="591b6-205">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-206">ユーザーが outlook で検索できる</span><span class="sxs-lookup"><span data-stu-id="591b6-206">User can search in outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-207">Active X コントロール:</span><span class="sxs-lookup"><span data-stu-id="591b6-207">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-208">ActiveX コントロールの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex コントロール API リファレンス」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="591b6-208">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-209">Groove の各モバイルの場合</span><span class="sxs-lookup"><span data-stu-id="591b6-209">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-210">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-210">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-211">PortalConnect サイト</span><span class="sxs-lookup"><span data-stu-id="591b6-211">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-212">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-212">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-213">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="591b6-213">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-214">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-214">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-215">SharePoint のエクスポートデータベース</span><span class="sxs-lookup"><span data-stu-id="591b6-215">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-216">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-216">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-217">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="591b6-217">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-218">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-218">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-219">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="591b6-219">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-220">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-220">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-221">SharePoint. DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="591b6-221">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-222">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-222">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-223">SharePoint. DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="591b6-223">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-224">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-224">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-225">Sharepoint の OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="591b6-225">Sharepoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-226">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-226">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-227">Sharepoint のクリップボード Ctl</span><span class="sxs-lookup"><span data-stu-id="591b6-227">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-228">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-228">Active X control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-229">WinProj</span><span class="sxs-lookup"><span data-stu-id="591b6-229">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-230">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-230">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-231">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="591b6-231">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-232">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-232">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-233">STSUPld</span><span class="sxs-lookup"><span data-stu-id="591b6-233">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-234">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-234">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-235">CommunicatorMeetingJoinAx マネージャー</span><span class="sxs-lookup"><span data-stu-id="591b6-235">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-236">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-236">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="591b6-237">LISTNETListnet</span><span class="sxs-lookup"><span data-stu-id="591b6-237">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-238">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="591b6-238">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="591b6-239">OneDrive Pro ブラウザーヘルパー</span><span class="sxs-lookup"><span data-stu-id="591b6-239">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-240">アクティブエックスコントロール]</span><span class="sxs-lookup"><span data-stu-id="591b6-240">Active X Control]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-241">OneDrive Pro アイコンのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="591b6-241">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="591b6-242">ユーザーがフォルダーの OneDrive Pro フォルダーを表示すると、Windows エクスプローラーシェルアイコンがオーバーレイされる</span><span class="sxs-lookup"><span data-stu-id="591b6-242">Windows Explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-243">シェル拡張</span><span class="sxs-lookup"><span data-stu-id="591b6-243">Shell extensions</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="591b6-244">ショートカット</span><span class="sxs-lookup"><span data-stu-id="591b6-244">Shortcuts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="591b6-245">Windows Search</span><span class="sxs-lookup"><span data-stu-id="591b6-245">Windows Search</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





