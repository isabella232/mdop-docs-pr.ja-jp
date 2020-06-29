---
title: 仮想化環境内にローカルにインストールされたアプリケーションと仮想化アプリケーションとの連携した実行
description: 仮想化環境内にローカルにインストールされたアプリケーションと仮想化アプリケーションとの連携した実行
author: dansimp
ms.assetid: a8affa46-f1f7-416c-8125-9595cfbfdbc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10c0f3f3c8a1b88cf1a98fd64fe8f7f49b597a91
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813314"
---
# <span data-ttu-id="bee4c-103">仮想化環境内にローカルにインストールされたアプリケーションと仮想化アプリケーションとの連携した実行</span><span class="sxs-lookup"><span data-stu-id="bee4c-103">Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications</span></span>


<span data-ttu-id="bee4c-104">ローカルにインストールされたアプリケーションは、Microsoft Application Virtualization (App-v) を使用して仮想環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-104">You can run a locally installed application in a virtual environment, alongside applications that have been virtualized by using Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="bee4c-105">次のような場合に、この操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-105">You might want to do this if you:</span></span>

-   <span data-ttu-id="bee4c-106">クライアントコンピューターにローカルでアプリケーションをインストールして実行しますが、そのローカルアプリケーションと連携して動作する特定のプラグインを仮想化して実行します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-106">Want to install and run an application locally on client computers, but want to virtualize and run specific plug-ins that work with that local application.</span></span>

-   <span data-ttu-id="bee4c-107">App-v クライアントパッケージのトラブルシューティングを行い、App-v 仮想環境内でローカルアプリケーションを開く場合。</span><span class="sxs-lookup"><span data-stu-id="bee4c-107">Are troubleshooting an App-V client package and want to open a local application within the App-V virtual environment.</span></span>

<span data-ttu-id="bee4c-108">次のいずれかの方法を使って、App-v 仮想環境内のローカルアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-108">Use any of the following methods to open a local application inside the App-V virtual environment:</span></span>

-   [<span data-ttu-id="bee4c-109">RunVirtual レジストリキー</span><span class="sxs-lookup"><span data-stu-id="bee4c-109">RunVirtual registry key</span></span>](#bkmk-runvirtual-regkey)

-   [<span data-ttu-id="bee4c-110">AppvClientPackage PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bee4c-110">Get-AppvClientPackage PowerShell cmdlet</span></span>](#bkmk-get-appvclientpackage-posh)

-   [<span data-ttu-id="bee4c-111">コマンドラインスイッチ/appvpid: &lt; PID&gt;</span><span class="sxs-lookup"><span data-stu-id="bee4c-111">Command line switch /appvpid:&lt;PID&gt;</span></span>](#bkmk-cl-switch-appvpid)

-   [<span data-ttu-id="bee4c-112">コマンドラインフックスイッチ/appvve: &lt; GUID&gt;</span><span class="sxs-lookup"><span data-stu-id="bee4c-112">Command line hook switch /appvve:&lt;GUID&gt;</span></span>](#bkmk-cl-hook-switch-appvve)

<span data-ttu-id="bee4c-113">各メソッドは基本的に同じタスクを実行しますが、仮想化されたアプリケーションが既に実行されているかどうかによっては、一部のメソッドが他のアプリケーションに適している場合があります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-113">Each method accomplishes essentially the same task, but some methods may be better suited for some applications than others, depending on whether the virtualized application is already running.</span></span>

## <a href="" id="bkmk-runvirtual-regkey"></a><span data-ttu-id="bee4c-114">RunVirtual レジストリキー</span><span class="sxs-lookup"><span data-stu-id="bee4c-114">RunVirtual registry key</span></span>


<span data-ttu-id="bee4c-115">ローカルにインストールされたアプリケーションをパッケージまたは接続グループの仮想環境に追加するには、次の `RunVirtual` セクションで説明するように、レジストリエディターのレジストリキーにサブキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-115">To add a locally installed application to a package or to a connection group’s virtual environment, you add a subkey to the `RunVirtual` registry key in the Registry Editor, as described in the following sections.</span></span>

<span data-ttu-id="bee4c-116">このレジストリキーを管理するために使用できるグループポリシー設定はありません。そのため、System Center Configuration Manager または別の電子ソフトウェア配布 (ESD) システムを使用するか、手動でレジストリを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-116">There is no Group Policy setting available to manage this registry key, so you have to use System Center Configuration Manager or another electronic software distribution (ESD) system, or manually edit the registry.</span></span>

### <a href="" id="bkmk-"></a><span data-ttu-id="bee4c-117">RunVirtual の使用時にパッケージ発行方法がサポートされています</span><span class="sxs-lookup"><span data-stu-id="bee4c-117">Supported methods of publishing packages when using RunVirtual</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bee4c-118">App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="bee4c-118">App-V version</span></span></th>
<th align="left"><span data-ttu-id="bee4c-119">サポートされている発行方法</span><span class="sxs-lookup"><span data-stu-id="bee4c-119">Supported publishing methods</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bee4c-120">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="bee4c-120">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="bee4c-121">グローバルまたはユーザーに公開されている</span><span class="sxs-lookup"><span data-stu-id="bee4c-121">Published globally or to the user</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bee4c-122">App-V 5.0 ~ app-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="bee4c-122">App-V 5.0 through App-V 5.0 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bee4c-123">グローバルに公開</span><span class="sxs-lookup"><span data-stu-id="bee4c-123">Published globally only</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="bee4c-124">サブキーを作成する手順</span><span class="sxs-lookup"><span data-stu-id="bee4c-124">Steps to create the subkey</span></span>

1.  <span data-ttu-id="bee4c-125">次の表の情報を使用して、 **MyApp.exe**の実行可能ファイルの名前を使用して、新しいレジストリキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-125">Using the information in the following table, create a new registry key using the name of the executable file, for example, **MyApp.exe**.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="bee4c-126">パッケージ発行方法</span><span class="sxs-lookup"><span data-stu-id="bee4c-126">Package publishing method</span></span></th>
    <th align="left"><span data-ttu-id="bee4c-127">レジストリキーを作成する場所</span><span class="sxs-lookup"><span data-stu-id="bee4c-127">Where to create the registry key</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="bee4c-128">グローバルに公開</span><span class="sxs-lookup"><span data-stu-id="bee4c-128">Published globally</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bee4c-129">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\RunVirtual</span><span class="sxs-lookup"><span data-stu-id="bee4c-129">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual</span></span></p>
    <p><strong><span data-ttu-id="bee4c-130">例 </strong> : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span><span class="sxs-lookup"><span data-stu-id="bee4c-130">Example</strong>: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="bee4c-131">ユーザーに公開</span><span class="sxs-lookup"><span data-stu-id="bee4c-131">Published to the user</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bee4c-132">HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual</span><span class="sxs-lookup"><span data-stu-id="bee4c-132">HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</span></span></p>
    <p><strong><span data-ttu-id="bee4c-133">例 </strong> : HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span><span class="sxs-lookup"><span data-stu-id="bee4c-133">Example</strong>: HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="bee4c-134">次のような接続グループがあります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-134">Connection group can contain:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="bee4c-135">グローバルに、または単にユーザーに公開されるパッケージ</span><span class="sxs-lookup"><span data-stu-id="bee4c-135">Packages that are published just globally or just to the user</span></span></p></li>
    <li><p><span data-ttu-id="bee4c-136">グローバルとユーザーに公開されるパッケージ</span><span class="sxs-lookup"><span data-stu-id="bee4c-136">Packages that are published globally and to the user</span></span></p></li>
    </ul></td>
    <td align="left"><p><span data-ttu-id="bee4c-137">HKEY_LOCAL_MACHINE または HKEY_CURRENT_USER キーのいずれかを指定しますが、次のいずれかが満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-137">Either HKEY_LOCAL_MACHINE or HKEY_CURRENT_USER key, but all of the following must be true:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="bee4c-138">仮想環境に複数のパッケージを含める場合は、有効な接続グループに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-138">If you want to include multiple packages in the virtual environment, you must include them in an enabled connection group.</span></span></p></li>
    <li><p><span data-ttu-id="bee4c-139">[接続] グループのパッケージの1つのサブキーのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-139">Create only one subkey for one of the packages in the connection group.</span></span> <span data-ttu-id="bee4c-140">たとえば、グローバルに公開される1つのパッケージと、ユーザーに公開される別のパッケージがある場合は、これらのパッケージのどちらかのサブキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-140">If, for example, you have one package that is published globally, and another package that is published to the user, you create a subkey for either of these packages, but not both.</span></span> <span data-ttu-id="bee4c-141">1つのパッケージのみのサブキーを作成しても、接続グループ内のすべてのパッケージとローカルアプリケーションを仮想環境で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-141">Although you create a subkey for only one of the packages, all of the packages in the connection group, plus the local application, will be available in the virtual environment.</span></span></p></li>
    <li><p><span data-ttu-id="bee4c-142">サブキーを作成するキーは、パッケージで使用した発行方法と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-142">The key under which you create the subkey must match the publishing method you used for the package.</span></span></p>
    <p><span data-ttu-id="bee4c-143">たとえば、ユーザーにパッケージを公開した場合、の下にサブキーを作成する必要があり <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code> ます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-143">For example, if you published the package to the user, you must create the subkey under <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code>.</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

     

2.  <span data-ttu-id="bee4c-144">新しいレジストリサブキーの値をパッケージの PackageId と VersionId に設定します。値はアンダースコアで区切ります。</span><span class="sxs-lookup"><span data-stu-id="bee4c-144">Set the new registry subkey’s value to the PackageId and VersionId of the package, separating the values with an underscore.</span></span>

    <span data-ttu-id="bee4c-145">**書式**: &lt; PackageId &gt; \ _ &lt; VersionId&gt;</span><span class="sxs-lookup"><span data-stu-id="bee4c-145">**Syntax**: &lt;PackageId&gt;\_&lt;VersionId&gt;</span></span>

    <span data-ttu-id="bee4c-146">**例**: 4c909996-afc9-4352-b606-0b74542a09c1 \ _Be463724-Oct1-48f1-8604-c4bd7ca92fa</span><span class="sxs-lookup"><span data-stu-id="bee4c-146">**Example**: 4c909996-afc9-4352-b606-0b74542a09c1\_be463724-Oct1-48f1-8604-c4bd7ca92fa</span></span>

    <span data-ttu-id="bee4c-147">上の例のアプリケーションでは、次のようなレジストリエクスポートファイル (.reg ファイル) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-147">The application in the previous example would produce a registry export file (.reg file) like the following:</span></span>

    ``` syntax
    Windows Registry Editor Version 5.00 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual] 
    @="" 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe] 
    @="aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-555555555
    ```

## <a href="" id="bkmk-get-appvclientpackage-posh"></a><span data-ttu-id="bee4c-148">AppvClientPackage PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bee4c-148">Get-AppvClientPackage PowerShell cmdlet</span></span>


<span data-ttu-id="bee4c-149">**AppVVirtualProcess**コマンドレットを使用してパッケージ名を取得し、指定されたパッケージの仮想環境内でプロセスを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-149">You can use the **Start-AppVVirtualProcess** cmdlet to retrieve the package name and then start a process within the specified package's virtual environment.</span></span> <span data-ttu-id="bee4c-150">このメソッドにより、パッケージが現在実行されているかどうかに関係なく、App-v パッケージのコンテキスト内で任意のコマンドを起動できます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-150">This method lets you launch any command within the context of an App-V package, regardless of whether the package is currently running.</span></span>

<span data-ttu-id="bee4c-151">次の構文の例を使用して \*\*、パッケージの &lt; &gt; \*\*パッケージの名前を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-151">Use the following example syntax, and substitute the name of your package for **&lt;Package&gt;**:</span></span>

`$AppVName = Get-AppvClientPackage <Package>`

`Start-AppvVirtualProcess -AppvClientObject $AppVName cmd.exe`

<span data-ttu-id="bee4c-152">パッケージの正確な名前がわからない場合は、コマンドラインの**AppvClientPackage \ \* executable\ \*\*を使用できます。 <em> ここで、** </em> executable\*は、AppvClientPackage \ \* Word \ \* などのアプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="bee4c-152">If you don’t know the exact name of your package, you can use the command line **Get-AppvClientPackage \*executable\\**<em>, where \**executable</em>* is the name of the application, for example: Get-AppvClientPackage \*Word\*.</span></span>

## <a href="" id="bkmk-cl-switch-appvpid"></a><span data-ttu-id="bee4c-153">コマンドラインスイッチ/appvpid: &lt; PID&gt;</span><span class="sxs-lookup"><span data-stu-id="bee4c-153">Command line switch /appvpid:&lt;PID&gt;</span></span>


<span data-ttu-id="bee4c-154">\*\*/Appvpid: &lt; pid &gt; \*\*スイッチを任意のコマンドに適用することができます。これにより、プロセス ID (pid) を指定して、選択した仮想プロセス内でそのコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-154">You can apply the **/appvpid:&lt;PID&gt;** switch to any command, which enables that command to run within a virtual process that you select by specifying its process ID (PID).</span></span> <span data-ttu-id="bee4c-155">このメソッドを使うと、既に実行されている実行可能ファイルと同じ App-v 環境で、新しい実行可能ファイルが起動します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-155">Using this method launches the new executable in the same App-V environment as an executable that is already running.</span></span>

<span data-ttu-id="bee4c-156">例:</span><span class="sxs-lookup"><span data-stu-id="bee4c-156">Example:</span></span> `cmd.exe /appvpid:8108`

<span data-ttu-id="bee4c-157">App-v プロセスのプロセス ID (PID) を確認するには、管理者特権のコマンドプロンプトからコマンド**tasklist.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-157">To find the process ID (PID) of your App-V process, run the command **tasklist.exe** from an elevated command prompt.</span></span>

## <a href="" id="bkmk-cl-hook-switch-appvve"></a><span data-ttu-id="bee4c-158">コマンドラインフックスイッチ/appvve: &lt; GUID&gt;</span><span class="sxs-lookup"><span data-stu-id="bee4c-158">Command line hook switch /appvve:&lt;GUID&gt;</span></span>


<span data-ttu-id="bee4c-159">このスイッチを使用すると、App-v パッケージの仮想環境内でローカルコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-159">This switch lets you run a local command within the virtual environment of an App-V package.</span></span> <span data-ttu-id="bee4c-160">仮想環境が既に実行されている必要がある **/appvid**スイッチとは異なり、このスイッチを使用すると仮想環境を開始できます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-160">Unlike the **/appvid** switch, where the virtual environment must already be running, this switch enables you to start the virtual environment.</span></span>

<span data-ttu-id="bee4c-161">引数</span><span class="sxs-lookup"><span data-stu-id="bee4c-161">Syntax:</span></span> `cmd.exe /appvve:<PACKAGEGUID_VERSIONGUID>`

<span data-ttu-id="bee4c-162">例:</span><span class="sxs-lookup"><span data-stu-id="bee4c-162">Example:</span></span> `cmd.exe /appvve:aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-55555555`

<span data-ttu-id="bee4c-163">アプリケーションのパッケージ GUID とバージョン GUID を取得するには、 **AppvClientPackage**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-163">To get the package GUID and version GUID of your application, run the **Get-AppvClientPackage** cmdlet.</span></span> <span data-ttu-id="bee4c-164">**/Appvve**スイッチを次のように連結します。</span><span class="sxs-lookup"><span data-stu-id="bee4c-164">Concatenate the **/appvve** switch with the following:</span></span>

-   <span data-ttu-id="bee4c-165">コロン</span><span class="sxs-lookup"><span data-stu-id="bee4c-165">A colon</span></span>

-   <span data-ttu-id="bee4c-166">目的のパッケージのパッケージ GUID</span><span class="sxs-lookup"><span data-stu-id="bee4c-166">Package GUID of the desired package</span></span>

-   <span data-ttu-id="bee4c-167">アンダースコア</span><span class="sxs-lookup"><span data-stu-id="bee4c-167">An underscore</span></span>

-   <span data-ttu-id="bee4c-168">目的のパッケージのバージョン ID</span><span class="sxs-lookup"><span data-stu-id="bee4c-168">Version ID of the desired package</span></span>

<span data-ttu-id="bee4c-169">パッケージの正確な名前がわからない場合は、コマンドラインの**AppvClientPackage \ \* executable\ \** <em> を使用します。ここで、*\* </em> executable\*は、AppvClientPackage \ \* Word \ \* などのアプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="bee4c-169">If you don’t know the exact name of your package, use the command line **Get-AppvClientPackage \*executable\\**<em>, where \**executable</em>* is the name of the application, for example: Get-AppvClientPackage \*Word\*.</span></span>

<span data-ttu-id="bee4c-170">このメソッドにより、パッケージが現在実行されているかどうかに関係なく、App-v パッケージのコンテキスト内で任意のコマンドを起動できます。</span><span class="sxs-lookup"><span data-stu-id="bee4c-170">This method lets you launch any command within the context of an App-V package, regardless of whether the package is currently running.</span></span>






## <span data-ttu-id="bee4c-171">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bee4c-171">Related topics</span></span>


[<span data-ttu-id="bee4c-172">App-V 5.0 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="bee4c-172">Technical Reference for App-V 5.0</span></span>](technical-reference-for-app-v-50.md)

 

 





