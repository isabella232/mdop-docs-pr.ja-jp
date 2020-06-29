---
title: App-V アップグレードのチェックリスト
description: App-V アップグレードのチェックリスト
author: dansimp
ms.assetid: 64e317d2-d260-4b67-8a49-ba9ac513087a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad856ce3067c327f3e604f9269ee384a66a1675a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819737"
---
# <span data-ttu-id="133c4-103">App-V アップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="133c4-103">App-V Upgrade Checklist</span></span>


<span data-ttu-id="133c4-104">Microsoft Application Virtualization (App-v) 4.5 以降のバージョンにアップグレードする前に、app-v 4.1 より前のバージョンを App-v 4.1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-104">Before trying to upgrade to Microsoft Application Virtualization (App-V) 4.5 or later versions, any version earlier than App-V 4.1 must be upgraded to App-V 4.1.</span></span> <span data-ttu-id="133c4-105">まずクライアントをアップグレードし、次にサーバーコンポーネントをアップグレードすることを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-105">You should plan to upgrade clients first, and then upgrade the server components.</span></span> <span data-ttu-id="133c4-106">App-v 4.5 にアップグレードされた app-v クライアントは、まだアップグレードされていない App-v サーバーで引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="133c4-106">App-V clients that have been upgraded to App-V 4.5 continue to work with App-V servers that have not yet been upgraded.</span></span> <span data-ttu-id="133c4-107">以前のバージョンのクライアントは、App-v 4.5 にアップグレードされたサーバーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="133c4-107">Earlier versions of the client are not supported on servers that have been upgraded to App-V 4.5.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="133c4-108">ステップ</span><span class="sxs-lookup"><span data-stu-id="133c4-108">Step</span></span></th>
<th align="left"><span data-ttu-id="133c4-109">リファレンス</span><span class="sxs-lookup"><span data-stu-id="133c4-109">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-110">App-v クライアントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="133c4-110">Upgrade the App-V clients.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-client.md" data-raw-source="[How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)"><span data-ttu-id="133c4-111">Application Virtualization Client をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="133c4-111">How to Upgrade the Application Virtualization Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-112">App-v のサーバーとデータベースをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="133c4-112">Upgrade the App-V servers and database.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="133c4-113">重要</span><span class="sxs-lookup"><span data-stu-id="133c4-113">Important</span></span></strong><br/><p><span data-ttu-id="133c4-114">App-v データベースへの複数のサーバー共有アクセス権を持っている場合は、データベースのアップグレード中に、これらのすべてのサーバーをオフラインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-114">If you have more than one server sharing access to the App-V database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="133c4-115">データベースのアップグレードについては、通常のビジネス慣行に従う必要がありますが、最初にテストサーバーでデータベースのバックアップコピーを使用してデータベースのアップグレードをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="133c4-115">You should follow your regular business practices for the database upgrade, but we recommend that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="133c4-116">次に、最初のアップグレード用にいずれかのサーバーを選択する必要があります。これにより、データベーススキーマがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="133c4-116">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="133c4-117">運用データベースが正常にアップグレードされた後、他のサーバー上の App-v ソフトウェアをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="133c4-117">After the production database has been successfully upgraded, you can upgrade the App-V software on the other servers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="133c4-118">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="133c4-118">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-119">App-v 管理 Web サービスをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="133c4-119">Upgrade the App-V Management Web Service.</span></span></p>
<p><span data-ttu-id="133c4-120">この手順は、管理 Web サービスが別のサーバー上にある場合にのみ適用されます。そのため、管理 web サービスをアップグレードするには、サーバーインストーラープログラムを別のサーバー上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-120">This step applies only if the Management Web Service is on a separate server, which would require that you run the server installer program on that separate server to upgrade the Management Web service.</span></span> <span data-ttu-id="133c4-121">それ以外の場合は、前のサーバーアップグレード手順によって、自動的に管理 Web サービスがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="133c4-121">Otherwise, the previous server upgrade step will automatically upgrade the Management Web Service.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="133c4-122">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="133c4-122">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-123">App-v 管理コンソールをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="133c4-123">Upgrade the App-V Management Console.</span></span></p>
<p><span data-ttu-id="133c4-124">この手順は、管理コンソールが別のコンピューターにある場合にのみ適用されます。そのため、コンソールをアップグレードするには、別のコンピューターでサーバーインストーラープログラムを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-124">This step applies only if the Management Console is on a separate computer, which would require that you run the server installer program on that separate computer to upgrade the console.</span></span> <span data-ttu-id="133c4-125">それ以外の場合は、前のサーバーアップグレード手順によって管理コンソールがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="133c4-125">Otherwise, the previous server upgrade step will upgrade the Management Console.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="133c4-126">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="133c4-126">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-127">App-v Sequencer をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="133c4-127">Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-sequencer.md" data-raw-source="[How to Upgrade the Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)"><span data-ttu-id="133c4-128">Application Virtualization Sequencer をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="133c4-128">How to Upgrade the Application Virtualization Sequencer</span></span></a></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="133c4-129">アップグレードに関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="133c4-129">Additional Upgrade Considerations</span></span>


-   <span data-ttu-id="133c4-130">バージョン4.2 でシーケンスされた仮想アプリケーションパッケージは、バージョン4.5 で使用するために再度順序付けする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="133c4-130">Any virtual application packages sequenced in version 4.2 will not have to be sequenced again for use with version 4.5.</span></span> <span data-ttu-id="133c4-131">ただし、既定のアクセス制御リスト (Acl) を適用したり、Windows インストーラーファイルを生成したりする場合は、仮想パッケージを Microsoft Application Virtualization 4.5 形式にアップグレードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="133c4-131">However, you should consider upgrading the virtual packages to the Microsoft Application Virtualization 4.5 format if you want to apply default access control lists (ACLs) or generate a Windows Installer file.</span></span> <span data-ttu-id="133c4-132">これは単純なプロセスであり、既存の仮想アプリケーションパッケージを開いて、App-v 4.5 Sequencer と共に保存するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="133c4-132">This is a simple process and requires only that the existing virtual application package be opened and saved with the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="133c4-133">これは、アプリの VSequencer コマンドラインインターフェイスを使って自動化できます。</span><span class="sxs-lookup"><span data-stu-id="133c4-133">This can be automated by using the App-VSequencer command-line interface.</span></span> <span data-ttu-id="133c4-134">詳細については、「 [App-v を使用して仮想アプリケーションを作成またはアップグレードする方法](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="133c4-134">For more information, see [How to Create or Upgrade Virtual Applications Using the App-V Sequencer](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)</span></span>

-   <span data-ttu-id="133c4-135">4.5 Sequencer の1つの機能は、Windows Installer (.msi) ファイルを、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布 (ESD) システムとの制御ポイントとして作成できる機能です。</span><span class="sxs-lookup"><span data-stu-id="133c4-135">One of the features of the 4.5 Sequencer is the ability to create Windows Installer (.msi) files as control points for virtual application package interoperability with electronic software distribution (ESD) systems, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="133c4-136">アプリの仮想化のために MSI ツールを使って作成された、Application Virtualization 用の MSI ツールで作成された、アプリの仮想 4.2 4.1 化のための MSI ツールを使って作成された以前の Windows インストーラーファイルは、アプリの hyper-v 4.5 に4.5 インストールされることはありませんが、その後も引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="133c4-136">Previous Windows Installer files created with the MSI tool for Application Virtualization that were installed on a App-V 4.1 or 4.2 client that is subsequently upgraded to App-V 4.5 will continue to work, although they cannot be installed on the App-V 4.5 client.</span></span> <span data-ttu-id="133c4-137">ただし、アプリ-V 4.5 Sequencer でアップグレードしない限り、削除またはアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="133c4-137">However, they cannot be removed or upgraded unless they are upgraded in the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="133c4-138">4.5 より前の元の App-v パッケージは、App-v 4.5 Sequencer で開いて、Windows Installer ファイルとして保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-138">The original App-V package earlier than 4.5 has to be opened in the App-V 4.5 Sequencer and then saved as a Windows Installer File.</span></span>

    **<span data-ttu-id="133c4-139">注</span><span class="sxs-lookup"><span data-stu-id="133c4-139">Note</span></span>**  
    <span data-ttu-id="133c4-140">App-v 4.2 クライアントが既に app-v 4.5 にアップグレードされている場合は、回避策をスクリプト化して、バージョンの4.5 クライアント上のバージョン4.2 パッケージを保存し、それらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="133c4-140">If the App-V 4.2 Client has already been upgraded to App-V 4.5, it is possible to script a workaround to preserve the version 4.2 packages on version 4.5 clients and allow them to be managed.</span></span> <span data-ttu-id="133c4-141">このスクリプトでは、msvcp71.dll と msvcr71.dll の2つのファイルを App-v のインストールフォルダーにコピーし、レジストリキーの下に次のレジストリキーの値を設定する必要があります。 \ [HKEY \ _LOCAL \ _MACHINE ¥ [HKEY \ \]</span><span class="sxs-lookup"><span data-stu-id="133c4-141">This script must copy two files, msvcp71.dll and msvcr71.dll, to the App-V installation folder and set the following registry key values under the registry key:\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:</span></span>

    <span data-ttu-id="133c4-142">"ClientVersion" = "4.2.1.20"</span><span class="sxs-lookup"><span data-stu-id="133c4-142">"ClientVersion"="4.2.1.20"</span></span>

    <span data-ttu-id="133c4-143">"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (グローバルに書き込み可能な場所)</span><span class="sxs-lookup"><span data-stu-id="133c4-143">"GlobalDataDirectory"="C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (a globally writeable location)</span></span>



-   <span data-ttu-id="133c4-144">App-v 4.5 Sequencer によって生成された Windows Installer ファイルは、App-v 4.6 クライアントで実行しようとすると、"このパッケージは Microsoft Application Virtualization Client 4.5 以降を必要とします" というエラーメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="133c4-144">Windows Installer files generated by the App-V 4.5 Sequencer display the error message "This package requires Microsoft Application Virtualization Client 4.5 or later" when trying to run them on an App-V 4.6 Client.</span></span> <span data-ttu-id="133c4-145">App-v 4.5 SP1 Sequencer または App-v 4.6 Sequencer のいずれかを使用して、古いパッケージを開き、パッケージの新しい .msi ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="133c4-145">Open the old package with either the App-V 4.5 SP1 Sequencer or the App-V 4.6 Sequencer and generate a new .msi file for the package.</span></span>

-   <span data-ttu-id="133c4-146">作成および保存されたバージョン4.2 のレポートは、サーバーがバージョン4.5 にアップグレードされると上書きされます。</span><span class="sxs-lookup"><span data-stu-id="133c4-146">Any version 4.2 reports that were created and saved will be overwritten when the server is upgraded to version 4.5.</span></span> <span data-ttu-id="133c4-147">これらのレポートを保持する必要がある場合は、サーバー上の SoftGrid 管理コンソールフォルダーにある SftMMC ファイルのバックアップコピーを保存し、そのコピーを使用してアップグレード中にインストールされた新しい SftMMC を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="133c4-147">If you have to keep these reports, you must save a backup copy of the SftMMC.msc file located in the SoftGrid Management Console folder on the server and use that copy to replace the new SftMMC.msc that is installed during the upgrade.</span></span>

-   <span data-ttu-id="133c4-148">以前のバージョンからのアップグレードの詳細については、「 [Microsoft Application Virtualization 4.5 へのアップグレード](https://go.microsoft.com/fwlink/?LinkId=120358)に関する FAQ (」を参照してください https://go.microsoft.com/fwlink/?LinkId=120358) 。</span><span class="sxs-lookup"><span data-stu-id="133c4-148">For additional information about upgrading from previous versions, see [Upgrading to Microsoft Application Virtualization 4.5 FAQ](https://go.microsoft.com/fwlink/?LinkId=120358) (https://go.microsoft.com/fwlink/?LinkId=120358).</span></span>

## <a href="" id="app-v-4-6-client-package-support-"></a><span data-ttu-id="133c4-149">App-v 4.6 クライアントパッケージのサポート</span><span class="sxs-lookup"><span data-stu-id="133c4-149">App-V 4.6 Client Package Support</span></span>


<span data-ttu-id="133c4-150">以前のバージョンの App-v で作成されたパッケージを、app-v 4.6 クライアントに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="133c4-150">You can deploy packages created in previous versions of App-V to App-V 4.6 clients.</span></span> <span data-ttu-id="133c4-151">ただし、適切なオペレーティングシステムとチップアーキテクチャの情報が含まれるように、関連する .osd ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-151">However, you must modify the associated .osd file so that it includes the appropriate operating system and chip architecture information.</span></span> <span data-ttu-id="133c4-152">次の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="133c4-152">The following values can be used:</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="133c4-153">OS 値</span><span class="sxs-lookup"><span data-stu-id="133c4-153">OS Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-154">&lt;OS 値 = "Win2003TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-154">&lt;OS VALUE=”Win2003TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-155">&lt;OS 値 = "Win2003TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-155">&lt;OS VALUE=”Win2003TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-156">&lt;OS 値 = "Win2008TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-156">&lt;OS VALUE=”Win2008TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-157">&lt;OS 値 = "Win2008TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-157">&lt;OS VALUE=”Win2008TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-158">&lt;OS 値 = "Win2008R2TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-158">&lt;OS VALUE=”Win2008R2TS64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-159">&lt;OS 値 = "Win7"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-159">&lt;OS VALUE=”Win7”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-160">&lt;OS 値 = "Win764"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-160">&lt;OS VALUE=”Win764”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-161">&lt;OS 値 = "WinVista"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-161">&lt;OS VALUE=”WinVista”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-162">&lt;OS 値 = "WinVista64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-162">&lt;OS VALUE=”WinVista64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-163">&lt;OS 値 = "WinXP"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-163">&lt;OS VALUE=”WinXP”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-164">&lt;OS 値 = "WinXP64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="133c4-164">&lt;OS VALUE=”WinXP64”/&gt;</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="133c4-165">新しく作成された32ビットパッケージを実行するには、App-v 4.6 Sequencer がインストールされた32ビットオペレーティングシステムを実行しているコンピューターでアプリケーションをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-165">To run a newly created 32-bit package, you must sequence the application on a computer running a 32-bit operating system with the App-V 4.6 Sequencer installed.</span></span> <span data-ttu-id="133c4-166">アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブをクリックし、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="133c4-166">After you have sequenced the application, in the Sequencer console, click the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

**<span data-ttu-id="133c4-167">重要</span><span class="sxs-lookup"><span data-stu-id="133c4-167">Important</span></span>**  
<span data-ttu-id="133c4-168">64ビットオペレーティングシステムを実行しているコンピューターでシーケンスされたアプリケーションは、64ビットオペレーティングシステムを実行しているコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-168">Applications sequenced on a computer running a 64-bit operating system must be deployed to computers running a 64-bit operating system.</span></span> <span data-ttu-id="133c4-169">App-v 4.6 Sequencer を使用して作成された新しい32ビットパッケージは、App-v 4.5 クライアントを実行しているコンピューターでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="133c4-169">New 32-bit packages created by using the App-V 4.6 Sequencer do not run on computers running the App-V 4.5 client.</span></span>



<span data-ttu-id="133c4-170">新しい64ビットパッケージを App-v 4.6 クライアントで実行するには、App-v 4.6 Sequencer を実行していて、64ビットオペレーティングシステムを実行しているコンピューターでアプリケーションをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="133c4-170">To run new 64-bit packages on the App-V 4.6 Client, you must sequence the application on a computer running the App-V 4.6 Sequencer and that is running a 64-bit operating system.</span></span> <span data-ttu-id="133c4-171">アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブをクリックし、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="133c4-171">After you have sequenced the application, in the Sequencer console, click the **Deployment** tab, and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="133c4-172">次の表は、さまざまなバージョンの sequencer を使用して作成されたパッケージを実行するクライアントバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="133c4-172">The following table lists which client versions will run packages created by using the various versions of the sequencer.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="133c4-173">App-v 4.2 Sequencer を使用したシーケンス</span><span class="sxs-lookup"><span data-stu-id="133c4-173">Sequenced by using the App-V 4.2 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="133c4-174">App-v 4.5 Sequencer を使用したシーケンス</span><span class="sxs-lookup"><span data-stu-id="133c4-174">Sequenced by using the App-V 4.5 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="133c4-175">32ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</span><span class="sxs-lookup"><span data-stu-id="133c4-175">Sequenced by using the 32-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="133c4-176">64ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</span><span class="sxs-lookup"><span data-stu-id="133c4-176">Sequenced by using the 64-bit App-V 4.6 Sequencer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-177">4.2 クライアント</span><span class="sxs-lookup"><span data-stu-id="133c4-177">4.2 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-178">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-178">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-179">×</span><span class="sxs-lookup"><span data-stu-id="133c4-179">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-180">なし</span><span class="sxs-lookup"><span data-stu-id="133c4-180">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-181">なし</span><span class="sxs-lookup"><span data-stu-id="133c4-181">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-182">4.5 クライアント¹</span><span class="sxs-lookup"><span data-stu-id="133c4-182">4.5 Client ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-183">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-183">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-184">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-184">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-185">×</span><span class="sxs-lookup"><span data-stu-id="133c4-185">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-186">なし</span><span class="sxs-lookup"><span data-stu-id="133c4-186">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="133c4-187">4.6 クライアント (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="133c4-187">4.6 Client (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-188">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-188">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-189">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-189">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-190">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-191">×</span><span class="sxs-lookup"><span data-stu-id="133c4-191">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="133c4-192">4.6 クライアント (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="133c4-192">4.6 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-193">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-194">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-194">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-195">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-195">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="133c4-196">あり</span><span class="sxs-lookup"><span data-stu-id="133c4-196">Yes</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="133c4-197">¹は、app-v 4.5 クライアントのすべてのバージョン (アプリ-V 4.5、App-v 4.5 CU1、App-v 4.5 SP1 など) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="133c4-197">¹Applies to all versions of the App-V 4.5 client, including App-V 4.5, App-V 4.5 CU1, and App-V 4.5 SP1.</span></span>









