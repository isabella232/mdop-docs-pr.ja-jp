---
title: スクリプトのアクションを設定する方法
description: スクリプトのアクションを設定する方法
author: dansimp
ms.assetid: 367e28f1-d8c2-4845-a01b-2fff9128ccfd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bfa264be447a0a8560e4af16ccaadc2ec1db3f6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812387"
---
# <span data-ttu-id="200f6-103">スクリプトのアクションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="200f6-103">How to Set Up Script Actions</span></span>


<span data-ttu-id="200f6-104">スクリプトアクションエディターを使用すると、管理者は、MED-V workspace のセットアップ中に実行される操作を作成できるだけでなく、実行する順序を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="200f6-104">The script actions editor allows the administrator to create actions to be performed during MED-V workspace setup, as well as to define the order in which they are performed.</span></span>

<span data-ttu-id="200f6-105">ドメイン設定スクリプトに追加できる操作の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="200f6-105">The following is a list of actions that can be added to the domain setup script:</span></span>

-   <span data-ttu-id="200f6-106">**Windows を再起動**します。 windows を再起動します。</span><span class="sxs-lookup"><span data-stu-id="200f6-106">**Restart Windows**—Restart Windows.</span></span>

-   <span data-ttu-id="200f6-107">[**ドメインに参加**]: ドメインに参加している場合、この操作を行い、ユーザー名、パスワード、完全修飾ドメイン名、NetBIOS ドメイン名、および組織単位 (省略可能) を構成します。</span><span class="sxs-lookup"><span data-stu-id="200f6-107">**Join Domain**—If joining a domain, include this action and configure the user name, password, fully qualified domain name, NetBIOS domain name, and organization unit (optional).</span></span>

-   <span data-ttu-id="200f6-108">[**接続の確認**] —接続するサーバーを構成し、med-v ワークスペースがネットワークリソース (ドメインサーバーなど) に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="200f6-108">**Check Connectivity**—Configure a server to connect to and verify that the MED-V workspace can connect to a network resource (such as the domain server).</span></span>

-   <span data-ttu-id="200f6-109">**コマンドライン**-med-v ワークスペースのスクリプトを構成し、スクリプトのパスとスクリプトの引数を含むコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="200f6-109">**Command Line**—Configure a script in the MED-V workspace, and enter a command line that includes the path of the script and the script arguments.</span></span>

-   <span data-ttu-id="200f6-110">[**コンピューター名の変更**] —定義された設定に基づいて仮想マシンコンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="200f6-110">**Rename Computer**—Rename the virtual machine computer based on the defined settings.</span></span>

-   <span data-ttu-id="200f6-111">**自動ログオンを無効に**する-Windows 自動ログオンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="200f6-111">**Disable Auto-Logon**—Disable Windows Auto-Logon.</span></span> <span data-ttu-id="200f6-112">この操作は、コンピューターをドメインに追加するスクリプトの最後に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="200f6-112">This action should be added at the end of scripts that add the computer to the domain.</span></span>

## <a href="" id="how-to-set-up-script-actions-"></a><span data-ttu-id="200f6-113">スクリプトのアクションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="200f6-113">How to Set Up Script Actions</span></span>


**<span data-ttu-id="200f6-114">スクリプトアクションを設定するには</span><span class="sxs-lookup"><span data-stu-id="200f6-114">To set up script actions</span></span>**

1.  <span data-ttu-id="200f6-115">[ **VM のセットアップ**] タブで、[**スクリプトエディター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="200f6-115">On the **VM Setup** tab, click **Script Editor**.</span></span>

2.  <span data-ttu-id="200f6-116">[**スクリプト操作**] ダイアログボックスの [**追加**] をクリックし、サブメニューで目的の操作をクリックします。</span><span class="sxs-lookup"><span data-stu-id="200f6-116">In the **Script Actions** dialog box, click **Add**, and on the submenu, click the desired actions.</span></span>

3.  <span data-ttu-id="200f6-117">次の表で説明するように、アクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="200f6-117">Configure the actions as described in the following tables.</span></span>

    <span data-ttu-id="200f6-118">**注** 
    [**コンピューター名の変更**] が [ **VM の設定**] タブで構成されています。詳細については、「 [VM コンピューター名パターンプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="200f6-118">**Note**
**Rename Computer** is configured in the **VM Settings** tab. For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

     

~~~
**Note**  
To rename a computer, Windows must be restarted. It is recommended to add a Restart Windows action following a Rename Computer action.
~~~



4. <span data-ttu-id="200f6-119">アクションの順序を設定するには、アクションを選んで、[**上**] または [**下**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="200f6-119">Set the order of the actions by selecting an action and clicking **Up** or **Down**.</span></span>

5. <span data-ttu-id="200f6-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="200f6-120">Click **OK**.</span></span>

**<span data-ttu-id="200f6-121">注</span><span class="sxs-lookup"><span data-stu-id="200f6-121">Note</span></span>**  
<span data-ttu-id="200f6-122">スクリプトを動作させるために、Join ドメインスクリプトを実行している場合、MED-V ワークスペース仮想マシンにログインしているユーザーは、ローカル管理者の権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="200f6-122">When running the Join Domain script, for the script to work, the user logged into the MED-V workspace virtual machine must have local administrator rights.</span></span>



**<span data-ttu-id="200f6-123">注</span><span class="sxs-lookup"><span data-stu-id="200f6-123">Note</span></span>**  
<span data-ttu-id="200f6-124">自動ログオンスクリプトを無効にする場合は、最初のセットアップが完了したら、自動ログオンで使用されるローカルゲストアカウントを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="200f6-124">When running the Disable Auto-Logon script, it is recommended to disable the local guest account used for the auto-logon once the initial setup is complete.</span></span>



### <a href="" id="bkmk-joindomainproperties"></a>

**<span data-ttu-id="200f6-125">ドメインのプロパティに参加する</span><span class="sxs-lookup"><span data-stu-id="200f6-125">Join Domain Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="200f6-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="200f6-126">Property</span></span></th>
<th align="left"><span data-ttu-id="200f6-127">説明</span><span class="sxs-lookup"><span data-stu-id="200f6-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-128">VM をドメインに参加させるときに使用する資格情報</span><span class="sxs-lookup"><span data-stu-id="200f6-128">Credentials to use when joining the VM to the domain</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-129">VM をドメインに参加させるときに使用する資格情報のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="200f6-129">Select one of the following credentials to use when joining the VM to the domain:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="200f6-130">MED-V の資格情報を使っ </strong> て、エンドユーザーの資格情報を使います。</span><span class="sxs-lookup"><span data-stu-id="200f6-130">Use MED-V credentials</strong>—The end-user credentials.</span></span></p></li>
<li><p><strong><span data-ttu-id="200f6-131">次の資格情報を使用します </strong> 。指定された資格情報は、対応するフィールドにユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="200f6-131">Use the following credentials</strong>—The credentials specified; enter a user name and password in the corresponding fields.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="200f6-132">注</span><span class="sxs-lookup"><span data-stu-id="200f6-132">Note</span></span></strong><br/><p><span data-ttu-id="200f6-133">入力した資格情報は、すべての MED-V ワークスペースユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="200f6-133">The credentials you enter are visible to all MED-V workspace users.</span></span> <span data-ttu-id="200f6-134">ドメイン管理者の資格情報を提供することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="200f6-134">It is not recommended to provide domain administrator credentials.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-135">参加するドメイン</span><span class="sxs-lookup"><span data-stu-id="200f6-135">Domain to join</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-136">次のいずれかのオプションを選択してください:</span><span class="sxs-lookup"><span data-stu-id="200f6-136">Select one of the following:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="200f6-137">ワークスペースの開始で使用されていたドメイン名を使用し </strong> ます。 med-v クライアントにログインするときに、エンドユーザーによって入力されたドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="200f6-137">Use the domain name utilized in starting the Workspace</strong>—Join the domain entered by the end user when logging into the MED-V client.</span></span></p>
<p><span data-ttu-id="200f6-138">NetBIOS から完全修飾ドメイン名へのマッピングを定義するには、[ <strong> グローバルドメインマッピングテーブル] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="200f6-138">To define the mapping from NetBIOS to fully qualified domain names, click <strong>Global domain mapping table</strong>.</span></span> <span data-ttu-id="200f6-139">グローバルドメインマッピングテーブルで [追加] <strong> をクリックし </strong> 、 <strong> NetBIOS ドメイン名 </strong> と <strong> 完全修飾ドメイン名を入力 </strong> して、[OK] をクリックし <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="200f6-139">In the global domain mapping table, click <strong>Add</strong>, enter a <strong>NetBIOS domain name</strong> and a <strong>Fully qualified domain name</strong>, and click <strong>OK</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="200f6-140">次のドメイン名を使用します </strong> 。指定したドメインに参加します。対応するフィールドにドメイン名と NetBIOS ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="200f6-140">Use the following domain name</strong>—Join the domain specified; enter a domain name and NetBIOS domain name in the corresponding fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-141">組織単位</span><span class="sxs-lookup"><span data-stu-id="200f6-141">Organization Unit</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-142">組織単位 (OU) を指定して、コンピューターを特定の OU に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="200f6-142">An organization unit (OU) may be specified to join the computer to a specific OU.</span></span> <span data-ttu-id="200f6-143">この形式は、ou 識別名の後に指定する必要があります。 OU = &lt; 組織単位 &gt; 、 &lt; ドメインコントローラー &gt; (例: OU = QATest、dc = IL、dc = MED、dc =、dc = com)。</span><span class="sxs-lookup"><span data-stu-id="200f6-143">The format must follow an OU distinguished name: OU=&lt;Organization Unit&gt;,&lt;Domain Controller&gt; (for example, OU=QATest, DC=il, DC=MED-V, DC=com).</span></span></p>
<div class="alert">
<strong><span data-ttu-id="200f6-144">Warning</span><span class="sxs-lookup"><span data-stu-id="200f6-144">Warning</span></span></strong><br/><p><span data-ttu-id="200f6-145">上の例のように、1レベルの OU のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="200f6-145">Only a single level OU is supported as is shown in the example above.</span></span></p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-checkconnectivityproperties"></a>

**<span data-ttu-id="200f6-146">接続のプロパティを確認する</span><span class="sxs-lookup"><span data-stu-id="200f6-146">Check Connectivity Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="200f6-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="200f6-147">Property</span></span></th>
<th align="left"><span data-ttu-id="200f6-148">説明</span><span class="sxs-lookup"><span data-stu-id="200f6-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-149">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="200f6-149">IP Address</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-150">接続を確認するサーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="200f6-150">The IP Address of the server that you are verifying connection to.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-151">Port</span><span class="sxs-lookup"><span data-stu-id="200f6-151">Port</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-152">接続を確認しようとしているサーバーのポート。</span><span class="sxs-lookup"><span data-stu-id="200f6-152">The port of the server that you are verifying connection to.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-153">タイムアウト</span><span class="sxs-lookup"><span data-stu-id="200f6-153">Timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-154">応答を待つまでの待機時間 (秒数)。</span><span class="sxs-lookup"><span data-stu-id="200f6-154">The number of seconds to wait for a response before timing out.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-commandlineproperties"></a>

**<span data-ttu-id="200f6-155">コマンドラインのプロパティ</span><span class="sxs-lookup"><span data-stu-id="200f6-155">Command-Line Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="200f6-156">プロパティ</span><span class="sxs-lookup"><span data-stu-id="200f6-156">Property</span></span></th>
<th align="left"><span data-ttu-id="200f6-157">説明</span><span class="sxs-lookup"><span data-stu-id="200f6-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-158">Path</span><span class="sxs-lookup"><span data-stu-id="200f6-158">Path</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-159">コマンドラインのパス。</span><span class="sxs-lookup"><span data-stu-id="200f6-159">The path of the command line.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-160">Arguments</span><span class="sxs-lookup"><span data-stu-id="200f6-160">Arguments</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-161">コマンドライン引数。</span><span class="sxs-lookup"><span data-stu-id="200f6-161">Command-line arguments.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-162">終了を待つ</span><span class="sxs-lookup"><span data-stu-id="200f6-162">Wait for exit</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-163">このチェックボックスをオンにすると、スクリプトの操作が続行されます。</span><span class="sxs-lookup"><span data-stu-id="200f6-163">Select the check box to wait for a return before continuing with the script actions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-164">エラー発生時</span><span class="sxs-lookup"><span data-stu-id="200f6-164">Fail on error</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-165">戻り値が指定された値以外の場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="200f6-165">Select this check box if the return is anything but the value specified.</span></span></p>
<p><span data-ttu-id="200f6-166">コマンドを正常に実行するための値を入力します。</span><span class="sxs-lookup"><span data-stu-id="200f6-166">Enter the value that will indicate the command as a success.</span></span></p>
<p><span data-ttu-id="200f6-167">既定値: <strong> 0</span><span class="sxs-lookup"><span data-stu-id="200f6-167">Default: <strong>0</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-168">一度だけ実行する</span><span class="sxs-lookup"><span data-stu-id="200f6-168">Perform only once</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-169">コマンドラインを1回だけ実行する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="200f6-169">Select this check box to run the command line only once.</span></span> <span data-ttu-id="200f6-170">スクリプトが失敗するかキャンセルされた場合は、このコマンドは再実行されません。</span><span class="sxs-lookup"><span data-stu-id="200f6-170">If the script fails or is canceled, this command will not be performed again.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-171">このコマンドラインは、ワークスペースの Windows を再起動します</span><span class="sxs-lookup"><span data-stu-id="200f6-171">This command line causes a restart of Windows in the Workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-172">コマンドラインで完了後に再起動する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="200f6-172">Select this check box if the command line causes a restart after completion.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-173">操作の許可</span><span class="sxs-lookup"><span data-stu-id="200f6-173">Allow interaction</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-174">コマンドでユーザーの操作が必要な場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="200f6-174">Select this check box if the command will require user interaction.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-175">進行状況メッセージ</span><span class="sxs-lookup"><span data-stu-id="200f6-175">Progress message</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-176">コマンドの実行中にユーザーに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="200f6-176">Message to be displayed to the user while the command is running.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-177">エラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="200f6-177">Failure message</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-178">コマンドが失敗した場合にユーザーに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="200f6-178">Message to be displayed to the user if the command fails.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="200f6-179">コマンドライン操作を構成するときに、次の表で定義されているように、いくつかの変数を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="200f6-179">When configuring the command-line action, several variables can be used as defined in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="200f6-180">パラメーター</span><span class="sxs-lookup"><span data-stu-id="200f6-180">Parameter</span></span></th>
<th align="left"><span data-ttu-id="200f6-181">値</span><span class="sxs-lookup"><span data-stu-id="200f6-181">Value</span></span></th>
<th align="left"><span data-ttu-id="200f6-182">説明</span><span class="sxs-lookup"><span data-stu-id="200f6-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-183">% MEDVUser%</span><span class="sxs-lookup"><span data-stu-id="200f6-183">%MEDVUser%</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-184">認証されたユーザー名。</span><span class="sxs-lookup"><span data-stu-id="200f6-184">An authenticated user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-185">MED-V で認証されたユーザー名。</span><span class="sxs-lookup"><span data-stu-id="200f6-185">MED-V authenticated user name.</span></span> <span data-ttu-id="200f6-186">ユーザー名とパスワードは、[ドメインの参加] セットアップスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="200f6-186">The user name and password can be used in the join domain VM setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-187">% MEDVPassword%</span><span class="sxs-lookup"><span data-stu-id="200f6-187">%MEDVPassword%</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-188">認証されたパスワード。</span><span class="sxs-lookup"><span data-stu-id="200f6-188">An authenticated password.</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-189">MED-V で認証されたパスワード。</span><span class="sxs-lookup"><span data-stu-id="200f6-189">MED-V authenticated password.</span></span> <span data-ttu-id="200f6-190">ユーザー名とパスワードは、[ドメインの参加] セットアップスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="200f6-190">The user name and password can be used in the join domain VM setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="200f6-191">% MEDVDomain%</span><span class="sxs-lookup"><span data-stu-id="200f6-191">%MEDVDomain%</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-192">構成済みドメイン。</span><span class="sxs-lookup"><span data-stu-id="200f6-192">Configured domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-193">MED-V 認証で構成されているドメイン。</span><span class="sxs-lookup"><span data-stu-id="200f6-193">The domain configured in the MED-V authentication.</span></span> <span data-ttu-id="200f6-194">VM のセットアップスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="200f6-194">It can be used on the VM setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="200f6-195">%DesiredMachineName%</span><span class="sxs-lookup"><span data-stu-id="200f6-195">%DesiredMachineName%</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-196">コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="200f6-196">Computer name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="200f6-197">管理アプリケーションで構成されている一意のコンピューター名。</span><span class="sxs-lookup"><span data-stu-id="200f6-197">The unique computer name configured in the management application.</span></span> <span data-ttu-id="200f6-198">これは、VM のセットアップスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="200f6-198">It can be used in the VM setup script.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="200f6-199">関連トピック</span><span class="sxs-lookup"><span data-stu-id="200f6-199">Related topics</span></span>


[<span data-ttu-id="200f6-200">MED-V ワークスペースの仮想マシンのセットアップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="200f6-200">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[<span data-ttu-id="200f6-201">VM のコンピューター名パターンのプロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="200f6-201">How to Configure VM Computer Name Pattern Properties</span></span>](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

 

 





