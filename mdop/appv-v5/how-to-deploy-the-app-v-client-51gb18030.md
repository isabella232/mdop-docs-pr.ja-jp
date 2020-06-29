---
title: APP-V Client を展開する方法
description: APP-V Client を展開する方法
author: dansimp
ms.assetid: 981f57c9-56c3-45da-8261-0972bfad3e5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ea216f6b86820f752e0c0ac693470eac72cb847a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814123"
---
# <span data-ttu-id="2eae5-103">APP-V Client を展開する方法</span><span class="sxs-lookup"><span data-stu-id="2eae5-103">How to Deploy the App-V Client</span></span>


<span data-ttu-id="2eae5-104">Microsoft Application Virtualization (App-v) 5.1 クライアントとリモートデスクトップサービスクライアントをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.1 client and Remote Desktop Services client.</span></span> <span data-ttu-id="2eae5-105">ターゲットコンピューターのオペレーティングシステムと一致するバージョンのクライアントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eae5-105">You must install the version of the client that matches the operating system of the target computer.</span></span>

<a href="" id="bkmk-clt-install-prereqs"></a>**<span data-ttu-id="2eae5-106">始める前に行うこと</span><span class="sxs-lookup"><span data-stu-id="2eae5-106">What to do before you start</span></span>**

1. <span data-ttu-id="2eae5-107">ソフトウェアの前提条件を確認してインストールします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-107">Review and install the software prerequisites:</span></span>

   <span data-ttu-id="2eae5-108">インストールする App-v のバージョンに対応する必須ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-108">Install the prerequisite software that corresponds to the version of App-V that you are installing:</span></span>

   -   [<span data-ttu-id="2eae5-109">App-V 5.1 について</span><span class="sxs-lookup"><span data-stu-id="2eae5-109">About App-V 5.1</span></span>](about-app-v-51.md)

   -   [<span data-ttu-id="2eae5-110">App-V 5.1 の前提条件</span><span class="sxs-lookup"><span data-stu-id="2eae5-110">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)

2. <span data-ttu-id="2eae5-111">インストールに適用できるように、クライアントの共存とサポートされていないシナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-111">Review the client coexistence and unsupported scenarios, as applicable to your installation:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-112">共存するアプリ-V クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="2eae5-112">Deploying coexisting App-V clients</span></span></p></td>
   <td align="left"><p><a href="planning-for-the-app-v-51-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md)"><span data-ttu-id="2eae5-113">App-V 5.1 Sequencer および Client の展開計画</span><span class="sxs-lookup"><span data-stu-id="2eae5-113">Planning for the App-V 5.1 Sequencer and Client Deployment</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-114">サポートされていない、または限定されたインストールシナリオ</span><span class="sxs-lookup"><span data-stu-id="2eae5-114">Unsupported or limited installation scenarios</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-115">「 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> App-v 5.1 でサポートされる構成」の「クライアント」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eae5-115">See the client section in <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)">App-V 5.1 Supported Configurations</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="2eae5-116">クライアントのレジストリ、ログ、トラブルシューティング情報の場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-116">Review the locations for client registry, log, and troubleshooting information:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eae5-117">クライアントレジストリ情報</span><span class="sxs-lookup"><span data-stu-id="2eae5-117">Client registry information</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="2eae5-118">既定では、App-v 5.1 クライアントをインストールした後、クライアント情報は次のレジストリキーのレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-118">By default, after you install the App-V 5.1 client, the client information is stored in the registry in the following registry key:</span></span></p>
<p><strong><span data-ttu-id="2eae5-119">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ APPV \ クライアント</span><span class="sxs-lookup"><span data-stu-id="2eae5-119">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ APPV \ CLIENT</span></span></strong></p></li>
<li><p><span data-ttu-id="2eae5-120">App-v クライアントを実行しているコンピューターに仮想化されたパッケージを展開すると、関連付けられたパッケージデータは次の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-120">When you deploy a virtualized package to a computer that is running the App-V client, the associated package data is stored in the following location:</span></span></p>
<p><strong><span data-ttu-id="2eae5-121">C: \ ProgramData \ App-V</span><span class="sxs-lookup"><span data-stu-id="2eae5-121">C: \ ProgramData \ App-V</span></span></strong></p>
<p><span data-ttu-id="2eae5-122">ただし、次のレジストリキーを使用して、この場所を再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-122">However, you can reconfigure this location with the following registry key:</span></span></p>
<p><strong><span data-ttu-id="2eae5-123">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ SOFTWARE \ MICROSOFT \ APP-V \ CLIENT \ STREAMING \ PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="2eae5-123">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ SOFTWARE \ MICROSOFT \ APPV \ CLIENT \ STREAMING \ PACKAGEINSTALLATIONROOT</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2eae5-124">クライアントログファイル</span><span class="sxs-lookup"><span data-stu-id="2eae5-124">Client log files</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="2eae5-125">App-v 5.1 クライアントに関連付けられているログファイル情報については、次のログを検索します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-125">For log file information that is associated with the App-V 5.1 Client, search in the following log:</span></span></p>
<p><strong><span data-ttu-id="2eae5-126">イベントログ/アプリケーションとサービスログ/Microsoft/AppV</span><span class="sxs-lookup"><span data-stu-id="2eae5-126">Event logs / Applications and Services Logs / Microsoft / AppV</span></span></strong></p></li>
<li><p><span data-ttu-id="2eae5-127">App-v 5.0 SP3 では、一部のログが統合され、次の場所に移動されました。</span><span class="sxs-lookup"><span data-stu-id="2eae5-127">In App-V 5.0 SP3, some logs were consolidated and moved to the following location:</span></span></p>
<p><strong><span data-ttu-id="2eae5-128">イベントログ/アプリケーションとサービスログ/Microsoft/AppV/ServiceLog</span><span class="sxs-lookup"><span data-stu-id="2eae5-128">Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog</span></span></strong></p>
<p><span data-ttu-id="2eae5-129">移動したログの一覧については、「 <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)"> app-v 5.0 SP3 について」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="2eae5-129">For a list of the moved logs, see <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)">About App-V 5.0 SP3</a>.</span></span></p></li>
<li><p><span data-ttu-id="2eae5-130">App-v 5.1 クライアントを実行しているコンピューターに現在保存されているパッケージは、次の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-130">Packages that are currently stored on computers that run the App-V 5.1 Client are saved to the following location:</span></span></p>
<p><strong><span data-ttu-id="2eae5-131">C:\ProgramData\App-V &amp; lt; パッケージ id &gt; &amp; lt; バージョン id&gt;</span><span class="sxs-lookup"><span data-stu-id="2eae5-131">C:\ProgramData\App-V&amp;lt;package id&gt;&amp;lt;version id&gt;</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2eae5-132">クライアントのインストールのトラブルシューティング情報</span><span class="sxs-lookup"><span data-stu-id="2eae5-132">Client installation troubleshooting information</span></span></p></td>
<td align="left"><p><span data-ttu-id="2eae5-133"><strong>% Temp% フォルダーのエラーログを参照してください </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2eae5-133">See the error log in the <strong>%temp%</strong> folder.</span></span> <span data-ttu-id="2eae5-134">ログファイルを確認するには、[ <strong> スタート] をクリックし、 </strong> 「 <strong> % temp%」と入力して、 </strong> <strong> appv_ ログを探し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-134">To review the log files, click <strong>Start</strong>, type <strong>%temp%</strong>, and then look for the <strong>appv_ log</strong>.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="2eae5-135">App-v 5.1 クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="2eae5-135">To install the App-V 5.1 Client</span></span>**

1.  <span data-ttu-id="2eae5-136">アプリがインストールされているコンピューターに、App-v 5.1 クライアントインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-136">Copy the App-V 5.1 client installation file to the computer on which it will be installed.</span></span> <span data-ttu-id="2eae5-137">次のクライアントの種類から選びます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-137">Choose from the following client types:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="2eae5-138">クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="2eae5-138">Client type</span></span></th>
    <th align="left"><span data-ttu-id="2eae5-139">使用するファイル</span><span class="sxs-lookup"><span data-stu-id="2eae5-139">File to use</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2eae5-140">クライアントの標準バージョン</span><span class="sxs-lookup"><span data-stu-id="2eae5-140">Standard version of the client</span></span></p></td>
    <td align="left"><p><strong><span data-ttu-id="2eae5-141">appv_client_setup.exe</span><span class="sxs-lookup"><span data-stu-id="2eae5-141">appv_client_setup.exe</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2eae5-142">クライアントのリモートデスクトップサービスバージョン</span><span class="sxs-lookup"><span data-stu-id="2eae5-142">Remote Desktop Services version of the client</span></span></p></td>
    <td align="left"><p><strong><span data-ttu-id="2eae5-143">appv_client_setup_rds.exe</span><span class="sxs-lookup"><span data-stu-id="2eae5-143">appv_client_setup_rds.exe</span></span></strong></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="2eae5-144">インストールファイルをダブルクリックし、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-144">Double-click the installation file, and click **Install**.</span></span> <span data-ttu-id="2eae5-145">インストールが開始される前に、インストーラーは、不足している[アプリ– V 5.1 の前提条件](app-v-51-prerequisites.md)をコンピューターで確認します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-145">Before the installation begins, the installer checks the computer for any missing [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

3.  <span data-ttu-id="2eae5-146">ソフトウェアライセンス条項を確認して同意し、Microsoft Update を使用するかどうか、Microsoft カスタマーエクスペリエンス向上プログラムに参加するかどうかを選択して、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-146">Review and accept the Software License Terms, choose whether to use Microsoft Update and whether to participate in the Microsoft Customer Experience Improvement Program, and click **Install**.</span></span>

4.  <span data-ttu-id="2eae5-147">[**セットアップが正常に完了しました**] ページで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-147">On the **Setup completed successfully** page, click **Close**.</span></span>

    <span data-ttu-id="2eae5-148">インストールにより、**プログラム**で次のような app-v クライアントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-148">The installation creates the following entries for the App-V client in **Programs**:</span></span>

    -   **<span data-ttu-id="2eae5-149">.exe</span><span class="sxs-lookup"><span data-stu-id="2eae5-149">.exe</span></span>**

    -   **<span data-ttu-id="2eae5-150">.msi</span><span class="sxs-lookup"><span data-stu-id="2eae5-150">.msi</span></span>**

    -   **<span data-ttu-id="2eae5-151">言語パック</span><span class="sxs-lookup"><span data-stu-id="2eae5-151">language pack</span></span>**

        **<span data-ttu-id="2eae5-152">注</span><span class="sxs-lookup"><span data-stu-id="2eae5-152">Note</span></span>**  
        <span data-ttu-id="2eae5-153">インストール後、.exe ファイルのみをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-153">After the installation, only the .exe file can be uninstalled.</span></span>



**<span data-ttu-id="2eae5-154">スクリプトを使用して App-v 5.1 クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="2eae5-154">To install the App-V 5.1 client using a script</span></span>**

1. <span data-ttu-id="2eae5-155">必要なすべての必須ソフトウェアをターゲットコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-155">Install all of the required prerequisite software on the target computers.</span></span> <span data-ttu-id="2eae5-156">[開始する前に実行する操作を](#bkmk-clt-install-prereqs)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eae5-156">See [What to do before you start](#bkmk-clt-install-prereqs).</span></span> <span data-ttu-id="2eae5-157">.Msi ファイルを使用してクライアントをインストールした場合、前提条件が見つからないと、インストールが失敗します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-157">If you install the client by using an .msi file, the installation will fail if any prerequisites are missing.</span></span>

2. <span data-ttu-id="2eae5-158">スクリプトを使用して App-v 5.1 クライアントをインストールするには、 **appv\_client\_setup.exe**で次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-158">To use a script to install the App-V 5.1 client, use the following parameters with **appv\_client\_setup.exe**.</span></span>

   **<span data-ttu-id="2eae5-159">注</span><span class="sxs-lookup"><span data-stu-id="2eae5-159">Note</span></span>**  
   <span data-ttu-id="2eae5-160">クライアントの Windows インストーラー (.msi) では、 **/log**パラメーターを除き、同じスイッチセットがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2eae5-160">The client Windows Installer (.msi) supports the same set of switches, except for the **/LOG** parameter.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-161">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="2eae5-161">/INSTALLDIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-162">インストールディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-162">Specifies the installation directory.</span></span> <span data-ttu-id="2eae5-163">使用例: <strong> /INSTALLDIR = C:\Program Files\AppV Client</span><span class="sxs-lookup"><span data-stu-id="2eae5-163">Example usage: <strong>/INSTALLDIR=C:\Program Files\AppV Client</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-164">/CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="2eae5-164">/CEIPOPTIN</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-165">カスタマーエクスペリエンス向上プログラムへの参加を可能にします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-165">Enables participation in the Customer Experience Improvement Program.</span></span> <span data-ttu-id="2eae5-166">使用例: <strong> /CEIPOPTIN = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-166">Example usage: <strong>/CEIPOPTIN=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-167">/Muoptin</span><span class="sxs-lookup"><span data-stu-id="2eae5-167">/MUOPTIN</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-168">Microsoft Update を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-168">Enables Microsoft Update.</span></span> <span data-ttu-id="2eae5-169">使用例: <strong> /muoptin = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-169">Example usage: <strong>/MUOPTIN=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-170">/Packageinstallationroot</span><span class="sxs-lookup"><span data-stu-id="2eae5-170">/PACKAGEINSTALLATIONROOT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-171">すべての新しいアプリケーションと更新プログラムをインストールするディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-171">Specifies the directory in which to install all new applications and updates.</span></span> <span data-ttu-id="2eae5-172">使用例: <strong> /packageinstallationroot =&#39;C:\ Apppackages&#39;</span><span class="sxs-lookup"><span data-stu-id="2eae5-172">Example usage: <strong>/PACKAGEINSTALLATIONROOT=&#39;C:\App-V Packages&#39;</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-173">/パッケージ ourceroot</span><span class="sxs-lookup"><span data-stu-id="2eae5-173">/PACKAGESOURCEROOT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-174">パッケージコンテンツをダウンロードするためのソースの場所をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-174">Overrides the source location for downloading package content.</span></span> <span data-ttu-id="2eae5-175">使用例: <strong> /パッケージ ourceroot =&#39;<a href="http://packageStore" data-raw-source="http://packageStore"> http://packageStore </a>&#39;</span><span class="sxs-lookup"><span data-stu-id="2eae5-175">Example usage: <strong>/PACKAGESOURCEROOT=&#39;<a href="http://packageStore" data-raw-source="http://packageStore">http://packageStore</a>&#39;</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-176">/自動ロード</span><span class="sxs-lookup"><span data-stu-id="2eae5-176">/AUTOLOAD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-177">特定のコンピューター上の App-v 5.1 で新しいパッケージを読み込む方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-177">Specifies how new packages will be loaded by App-V 5.1 on a specific computer.</span></span> <span data-ttu-id="2eae5-178">次のオプションが有効になっています: [1];すべてのパッケージを自動的に読み込む [2];または、パッケージを自動的に読み込まない [0] を選びます。 <strong>使用例:/自動ロード = [0 | 1 | 2]</span><span class="sxs-lookup"><span data-stu-id="2eae5-178">The following options are enabled: [1]; automatically load all packages [2]; or automatically load no packages [0].<strong>Example usage: /AUTOLOAD=[0|1|2]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-179">/Sharedcontentstoremode</span><span class="sxs-lookup"><span data-stu-id="2eae5-179">/SHAREDCONTENTSTOREMODE</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-180">ストリーミングされたパッケージコンテンツをローカルのハードディスクに保存しないように指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-180">Specifies that streamed package contents will be not be saved to the local hard disk.</span></span> <span data-ttu-id="2eae5-181">使用例: <strong> /sharedcontentstoremode = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-181">Example usage: <strong>/SHAREDCONTENTSTOREMODE=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-182">/MIGRATIONMODE</span><span class="sxs-lookup"><span data-stu-id="2eae5-182">/MIGRATIONMODE</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-183">以前のバージョンで作成されたパッケージに関連付けられているショートカットと FTAs App-v 5.1 クライアントが変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-183">Allows the App-V 5.1 client to modify the shortcuts and FTAs that are associated with the packages that are created with a previous version.</span></span> <span data-ttu-id="2eae5-184">使用例: <strong> /MIGRATIONMODE = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-184">Example usage: <strong>/MIGRATIONMODE=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-185">/ENABLEPACKAGESCRIPTS</span><span class="sxs-lookup"><span data-stu-id="2eae5-185">/ENABLEPACKAGESCRIPTS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-186">パッケージマニフェストファイルまたは実行する構成ファイルで定義されているスクリプトを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-186">Enables the scripts that are defined in the package manifest file or configuration files that should run.</span></span> <span data-ttu-id="2eae5-187">使用例: <strong> /ENABLEPACKAGESCRIPTS = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-187">Example usage: <strong>/ENABLEPACKAGESCRIPTS=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-188">/ROAMINGREGISTRYEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="2eae5-188">/ROAMINGREGISTRYEXCLUSIONS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-189">ユーザープロファイルでローミングされないレジストリパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-189">Specifies the registry paths that will not roam with a user profile.</span></span> <span data-ttu-id="2eae5-190">使用例: <strong> /ROAMINGREGISTRYEXCLUSIONS = ソフトウェア \ クラス; ソフトウェア \ クライアント</span><span class="sxs-lookup"><span data-stu-id="2eae5-190">Example usage: <strong>/ROAMINGREGISTRYEXCLUSIONS=software\classes;software\clients</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-191">/ROAMINGFILEEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="2eae5-191">/ROAMINGFILEEXCLUSIONS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-192">ユーザー&#39;s プロファイルでローミングしない% userprofile% を基準としたファイルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-192">Specifies the file paths relative to %userprofile% that do not roam with a user&#39;s profile.</span></span> <span data-ttu-id="2eae5-193">使用例: <strong> /ROAMINGFILEEXCLUSIONS &#39;デスクトップ、マイピクチャ&#39;</span><span class="sxs-lookup"><span data-stu-id="2eae5-193">Example usage: <strong>/ROAMINGFILEEXCLUSIONS &#39;desktop;my pictures&#39;</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-194">/S [1-5] 発行サーバー名</span><span class="sxs-lookup"><span data-stu-id="2eae5-194">/S[1-5]PUBLISHINGSERVERNAME</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-195">発行サーバーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-195">Displays the name of the publishing server.</span></span> <span data-ttu-id="2eae5-196">使用例: <strong> /S2PUBLISHINGSERVERNAME = MyPublishingServer</span><span class="sxs-lookup"><span data-stu-id="2eae5-196">Example usage: <strong>/S2PUBLISHINGSERVERNAME=MyPublishingServer</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-197">/S [1-5] 発行する SERVERURL</span><span class="sxs-lookup"><span data-stu-id="2eae5-197">/S[1-5]PUBLISHINGSERVERURL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-198">発行サーバーの URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-198">Displays the URL of the publishing server.</span></span> <span data-ttu-id="2eae5-199">使用例: <strong> /S2PUBLISHINGSERVERURL = \ pubserver</span><span class="sxs-lookup"><span data-stu-id="2eae5-199">Example usage: <strong>/S2PUBLISHINGSERVERURL=\pubserver</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-200">/S [1-5] GLOBALREFRESHENABLED-</span><span class="sxs-lookup"><span data-stu-id="2eae5-200">/S[1-5]GLOBALREFRESHENABLED -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-201">グローバル発行の更新を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-201">Enables a global publishing refresh.</span></span> <span data-ttu-id="2eae5-202">使用例: <strong> /S2GLOBALREFRESHENABLED = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-202">Example usage: <strong>/S2GLOBALREFRESHENABLED=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-203">/S [1-5] GLOBALREFRESHVALU</span><span class="sxs-lookup"><span data-stu-id="2eae5-203">/S[1-5]GLOBALREFRESHONLOGON</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-204">ユーザーがログオンしたときにグローバル公開の更新を開始します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-204">Initiates a global publishing refresh when a user logs on.</span></span> <span data-ttu-id="2eae5-205">使用例: <strong> /S2LOGONREFRESH = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-205">Example usage: <strong>/S2LOGONREFRESH=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-206">/S [1-5] GLOBALREFRESHINTERVAL-</span><span class="sxs-lookup"><span data-stu-id="2eae5-206">/S[1-5]GLOBALREFRESHINTERVAL -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-207">公開の更新間隔を指定し <strong> ます。ここで、0 </strong> は定期的に更新されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-207">Specifies the publishing refresh interval, where <strong>0</strong> indicates do not periodically refresh.</span></span> <span data-ttu-id="2eae5-208">使用例: <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</span><span class="sxs-lookup"><span data-stu-id="2eae5-208">Example usage: <strong>/S2PERIODICREFRESHINTERVAL=[0-744]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-209">/S [1-5] GLOBALREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="2eae5-209">/S[1-5]GLOBALREFRESHINTERVALUNIT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-210">間隔の単位 (時間 [0]、日数 [1]) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-210">Specifies the interval unit (Hours[0], Days[1]).</span></span> <span data-ttu-id="2eae5-211">使用例: <strong> /S2GLOBALREFRESHINTERVALUNIT = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-211">Example usage: <strong>/S2GLOBALREFRESHINTERVALUNIT=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-212">/S [1-5] USERREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="2eae5-212">/S[1-5]USERREFRESHENABLED</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-213">ユーザー公開の更新を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-213">Enables user publishing refresh.</span></span> <span data-ttu-id="2eae5-214">使用例: <strong> /S2USERREFRESHENABLED = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-214">Example usage: <strong>/S2USERREFRESHENABLED=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-215">/S [1-5] USERREFRESHONLOGON 詳細</span><span class="sxs-lookup"><span data-stu-id="2eae5-215">/S[1-5]USERREFRESHONLOGON</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-216">ユーザーがログオンしたときにユーザーの公開更新を開始します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-216">Initiates a user publishing refresh when a user logs on.</span></span> <span data-ttu-id="2eae5-217">使用例: <strong> /S2LOGONREFRESH = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-217">Example usage: <strong>/S2LOGONREFRESH=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-218">/S [1-5] USERREFRESHINTERVAL-</span><span class="sxs-lookup"><span data-stu-id="2eae5-218">/S[1-5]USERREFRESHINTERVAL -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-219">公開の更新間隔を指定し <strong> ます。ここで、0 </strong> は定期的に更新されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-219">Specifies the publishing refresh interval, where <strong>0</strong> indicates do not periodically refresh.</span></span> <span data-ttu-id="2eae5-220">使用例: <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</span><span class="sxs-lookup"><span data-stu-id="2eae5-220">Example usage: <strong>/S2PERIODICREFRESHINTERVAL=[0-744]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-221">/S [1-5] USERREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="2eae5-221">/S[1-5]USERREFRESHINTERVALUNIT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-222">間隔の単位 (時間 [0]、日数 [1]) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-222">Specifies the interval unit (Hours[0], Days[1]).</span></span> <span data-ttu-id="2eae5-223">使用例: <strong> /S2USERREFRESHINTERVALUNIT = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="2eae5-223">Example usage: <strong>/S2USERREFRESHINTERVALUNIT=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-224">/Log</span><span class="sxs-lookup"><span data-stu-id="2eae5-224">/Log</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-225">ログ情報が保存されている場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-225">Specifies a location where the log information is saved.</span></span> <span data-ttu-id="2eae5-226">既定の場所は% Temp% です。</span><span class="sxs-lookup"><span data-stu-id="2eae5-226">The default location is %Temp%.</span></span> <span data-ttu-id="2eae5-227">使用例: <strong> /Log C:\logs\log.log</span><span class="sxs-lookup"><span data-stu-id="2eae5-227">Example usage: <strong>/log C:\logs\log.log</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-228">/q</span><span class="sxs-lookup"><span data-stu-id="2eae5-228">/q</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-229">無人インストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-229">Specifies an unattended installation.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-230">/REPAIR</span><span class="sxs-lookup"><span data-stu-id="2eae5-230">/REPAIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-231">以前のクライアントインストールを修復します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-231">Repairs a previous client installation.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-232">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="2eae5-232">/NORESTART</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-233">クライアントのインストール後にコンピューターが再起動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-233">Prevents the computer from rebooting after the client installation.</span></span></p>
   <p><span data-ttu-id="2eae5-234">このパラメーターを使用すると、各更新プログラムをインストールした後にエンドユーザーのコンピューターが再起動しないようにし、都合のよいときに再起動をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-234">The parameter prevents the end-user computer from rebooting after each update is installed and lets you schedule the reboot at your convenience.</span></span> <span data-ttu-id="2eae5-235">たとえば、Service Pack のインストール後に、再起動しなくても、App-v 5.1 をインストールしてから、修正プログラムパッケージ Y をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-235">For example, you can install App-V 5.1 and then install Hotfix Package Y without rebooting after the Service Pack installation.</span></span> <span data-ttu-id="2eae5-236">インストール後、App-v の使用を開始する前に再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eae5-236">After the installation, you must reboot before you start using App-V.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-237">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="2eae5-237">/UNINSTALL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-238">クライアントをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-238">Uninstalls the client.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-239">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="2eae5-239">/ACCEPTEULA</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-240">ライセンス契約を承諾します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-240">Accepts the license agreement.</span></span> <span data-ttu-id="2eae5-241">これは、無人インストールの場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="2eae5-241">This is required for an unattended installation.</span></span> <span data-ttu-id="2eae5-242">使用例: <strong> /ACCEPTEULA </strong> または <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2eae5-242">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-243">/レイアウト</span><span class="sxs-lookup"><span data-stu-id="2eae5-243">/LAYOUT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-244">関連付けられているレイアウトアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-244">Specifies the associated layout action.</span></span> <span data-ttu-id="2eae5-245">また、Windows インストーラー (.msi) とスクリプトファイルも、App-v 5.1 をインストールせずにフォルダーに展開します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-245">It also extracts the Windows Installer (.msi) and script files to a folder without installing App-V 5.1.</span></span> <span data-ttu-id="2eae5-246">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="2eae5-246">No value is expected.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2eae5-247">/Layoutdir</span><span class="sxs-lookup"><span data-stu-id="2eae5-247">/LAYOUTDIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-248">レイアウトディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-248">Specifies the layout directory.</span></span> <span data-ttu-id="2eae5-249">文字列値が必要です。</span><span class="sxs-lookup"><span data-stu-id="2eae5-249">Requires a string value.</span></span> <span data-ttu-id="2eae5-250">使用例: <strong> /layoutdir = "C:\ Application Virtualization Client" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2eae5-250">Example usage: <strong>/LAYOUTDIR=”C:\Application Virtualization Client”</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2eae5-251">/?、/h、/help</span><span class="sxs-lookup"><span data-stu-id="2eae5-251">/?, /h, /help</span></span></p></td>
   <td align="left"><p><span data-ttu-id="2eae5-252">以前のインストールパラメーターに関するヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-252">Requests help about the previous installation parameters.</span></span></p></td>
   </tr>
   </tbody>
   </table>



**<span data-ttu-id="2eae5-253">Windows インストーラー (.msi) ファイルを使用して App-v 5.1 クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="2eae5-253">To install the App-V 5.1 client by using the Windows Installer (.msi) file</span></span>**

1.  <span data-ttu-id="2eae5-254">ターゲットコンピューターに必要な前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-254">Install the required prerequisites on the target computers.</span></span> <span data-ttu-id="2eae5-255">[開始する前に実行する操作を](#bkmk-clt-install-prereqs)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eae5-255">See [What to do before you start](#bkmk-clt-install-prereqs).</span></span> <span data-ttu-id="2eae5-256">前提条件が満たされていない場合、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-256">If any prerequisites are not met, the installation will fail.</span></span>

2.  <span data-ttu-id="2eae5-257">アプリ-V 5.1 Windows Installer (.msi) ファイルを使用してクライアントをインストールする前に、ターゲットコンピューターに保留中の再起動がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-257">Ensure that the target computers do not have any pending restarts before you install the client using the App-V 5.1 Windows Installer (.msi) files.</span></span> <span data-ttu-id="2eae5-258">Windows インストーラのファイルには、保留中の再起動のフラグは設定されません。</span><span class="sxs-lookup"><span data-stu-id="2eae5-258">The Windows Installer files do not flag a pending restart.</span></span>

3.  <span data-ttu-id="2eae5-259">ターゲットコンピューターに次のいずれかの Windows インストーラーファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-259">Deploy one of the following Windows Installer files to the target computer.</span></span> <span data-ttu-id="2eae5-260">指定するファイルは、ターゲットコンピューターの構成と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eae5-260">The file that you specify must match the configuration of the target computer.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="2eae5-261">展開の種類</span><span class="sxs-lookup"><span data-stu-id="2eae5-261">Type of deployment</span></span></th>
    <th align="left"><span data-ttu-id="2eae5-262">このファイルを展開</span><span class="sxs-lookup"><span data-stu-id="2eae5-262">Deploy this file</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2eae5-263">コンピューターで32ビットの Microsoft Windows オペレーティングシステムが実行されている</span><span class="sxs-lookup"><span data-stu-id="2eae5-263">Computer is running a 32-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2eae5-264">appv_client_MSI_x86.msi</span><span class="sxs-lookup"><span data-stu-id="2eae5-264">appv_client_MSI_x86.msi</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2eae5-265">コンピューターで64ビットの Microsoft Windows オペレーティングシステムが実行されている</span><span class="sxs-lookup"><span data-stu-id="2eae5-265">Computer is running a 64-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2eae5-266">appv_client_MSI_x64.msi</span><span class="sxs-lookup"><span data-stu-id="2eae5-266">appv_client_MSI_x64.msi</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2eae5-267">アプリ-V 5.1 リモートデスクトップサービスクライアントを展開しています</span><span class="sxs-lookup"><span data-stu-id="2eae5-267">You are deploying the App-V 5.1 Remote Desktop Services client</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2eae5-268">appv_client_rds_MSI_x64.msi</span><span class="sxs-lookup"><span data-stu-id="2eae5-268">appv_client_rds_MSI_x64.msi</span></span></p></td>
    </tr>
    </tbody>
    </table>



4.  <span data-ttu-id="2eae5-269">次の表の情報を使用して、ターゲットコンピューターの目的の言語に基づいて、**インストールする適切**な言語パックを選びます。</span><span class="sxs-lookup"><span data-stu-id="2eae5-269">Using the information in the following table, select the appropriate language pack **.msi** to install, based on the desired language for the target computer.</span></span> <span data-ttu-id="2eae5-270">表の**xxxx**は、言語パックのターゲットロケールを示しています。</span><span class="sxs-lookup"><span data-stu-id="2eae5-270">The **xxxx** in the table refers to the target locale of the language pack.</span></span>

    **<span data-ttu-id="2eae5-271">始める前に知っておくべきこと:</span><span class="sxs-lookup"><span data-stu-id="2eae5-271">What to know before you start:</span></span>**

    -   <span data-ttu-id="2eae5-272">言語パックは、標準の App-v 5.1 クライアントと、App-V 5.1 クライアントのリモートデスクトップサービスバージョンの両方に共通です。</span><span class="sxs-lookup"><span data-stu-id="2eae5-272">The language packs are common to both the standard App-V 5.1 client and the Remote Desktop Services version of the App-V 5.1 client.</span></span>

    -   <span data-ttu-id="2eae5-273">**.Exe**を使って app-v 5.1 クライアントをインストールする場合、インストーラーは、ターゲットコンピューターで実行されているオペレーティングシステムと一致する言語パックのみを展開します。</span><span class="sxs-lookup"><span data-stu-id="2eae5-273">If you install the App-V 5.1 client using the **.exe**, the installer will deploy only the language pack that matches the operating system running on the target computer.</span></span>

    -   <span data-ttu-id="2eae5-274">追加の言語パックをターゲットコンピューターに展開するには、 **Windows Installer (.msi) ファイルを使用して**、この手順に従って app-v 5.1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2eae5-274">To deploy additional language packs on a target computer, use the procedure **To install the App-V 5.1 client by using Windows Installer (.msi) file**.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="2eae5-275">展開の種類</span><span class="sxs-lookup"><span data-stu-id="2eae5-275">Type of deployment</span></span></th>
    <th align="left"><span data-ttu-id="2eae5-276">このファイルを展開</span><span class="sxs-lookup"><span data-stu-id="2eae5-276">Deploy this file</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2eae5-277">コンピューターで32ビットの Microsoft Windows オペレーティングシステムが実行されている</span><span class="sxs-lookup"><span data-stu-id="2eae5-277">Computer is running a 32-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2eae5-278">appv_client_LP_xxxx_ x86.msi</span><span class="sxs-lookup"><span data-stu-id="2eae5-278">appv_client_LP_xxxx_ x86.msi</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2eae5-279">コンピューターで64ビットの Microsoft Windows オペレーティングシステムが実行されている</span><span class="sxs-lookup"><span data-stu-id="2eae5-279">Computer is running a 64-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2eae5-280">appv_client_LP_xxxx_ x64.msi</span><span class="sxs-lookup"><span data-stu-id="2eae5-280">appv_client_LP_xxxx_ x64.msi</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="2eae5-281">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2eae5-281">Related topics</span></span>


[<span data-ttu-id="2eae5-282">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="2eae5-282">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="2eae5-283">Client の構成設定について</span><span class="sxs-lookup"><span data-stu-id="2eae5-283">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

[<span data-ttu-id="2eae5-284">App-V 5.1 Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2eae5-284">How to Uninstall the App-V 5.1 Client</span></span>](how-to-uninstall-the-app-v-51-client.md)









