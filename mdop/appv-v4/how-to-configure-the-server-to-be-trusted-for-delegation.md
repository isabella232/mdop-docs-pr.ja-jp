---
title: サーバーを委任に対して信頼されるように構成する方法
description: サーバーを委任に対して信頼されるように構成する方法
author: dansimp
ms.assetid: d8d11588-17c0-4bcb-a7e6-86b5e4ba7e1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7164b3046671853216b870d68e651fed4fd84695
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817747"
---
# <span data-ttu-id="c244a-103">サーバーを委任に対して信頼されるように構成する方法</span><span class="sxs-lookup"><span data-stu-id="c244a-103">How to Configure the Server to be Trusted for Delegation</span></span>


<span data-ttu-id="c244a-104">Microsoft Application Virtualization (App-v) Management Server ソフトウェアをインストールするときに、分散システムアーキテクチャを使用してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c244a-104">When you install the Microsoft Application Virtualization (App-V) Management Server software, you can choose to install it by using a distributed system architecture.</span></span> <span data-ttu-id="c244a-105">コンソール、管理 Web サービス、データベースを異なるコンピューターにインストールする場合は、インターネットインフォメーションサービス (IIS) サーバーが委任に対して信頼されるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c244a-105">If you install the console, the Management Web Service, and the database on different computers, you must configure the Internet Information Services (IIS) server to be trusted for delegation.</span></span> <span data-ttu-id="c244a-106">このことが必要になるのは、管理 Web サービスが、コンソールを使用している App-v 管理者の資格情報を使って、App-v データストアに接続しようとしているためです。</span><span class="sxs-lookup"><span data-stu-id="c244a-106">This is necessary because the Management Web Service will attempt to connect to the App-V data store by using the credentials of the App-V administrator who is using the console.</span></span> <span data-ttu-id="c244a-107">データストアがインストールされているデータベースサーバーは、IIS サーバーが委任に対して信頼されるように構成されている場合を除き、IIS サーバーからの管理者の資格情報を受け入れません。そのため、管理 Web サービスは、App-v データストアに接続できません。</span><span class="sxs-lookup"><span data-stu-id="c244a-107">The database server on which the data store is installed will not accept the administrator’s credentials from the IIS server unless the IIS server is configured to be trusted for delegation, and so the Management Web Service will not be able to connect to the App-V data store.</span></span>

<span data-ttu-id="c244a-108">**注** 1台のサーバーに App-v Management Server ソフトウェアをインストールして、データストアを別のサーバーに配置している場合は、管理 Web サービスと管理コンソールが同じサーバー上にある場合でも、委任に対して信頼されるようにサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c244a-108">**Note** If you install the App-V Management Server software on a single server and place the data store on a separate server, there is one situation in which you must still configure the server to be trusted for delegation even though the Management Web Service and Management Console are on the same server.</span></span> <span data-ttu-id="c244a-109">この状況は、[**代替資格情報を使う**] オプションを使って、コンソールで管理 Web サービスに接続する必要がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="c244a-109">This situation occurs if you need to connect to the Management Web Service in the console by using the **Use Alternate Credentials** option.</span></span>

 

<span data-ttu-id="c244a-110">使用できる委任の種類は、Active Directory ドメインサービス (ADDS) インフラストラクチャで構成したドメインの機能レベルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c244a-110">The type of delegation that you can use depends on the Domain Functional Level that you have configured in your Active Directory Domain Services (ADDS) infrastructure.</span></span> <span data-ttu-id="c244a-111">次の表に、App-v の各ドメインの機能レベルに対して構成できる委任の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c244a-111">The following table lists the types of delegation that can be configured for each Domain Functional Level for App-V.</span></span> <span data-ttu-id="c244a-112">詳しい手順については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c244a-112">Detailed instructions follow the table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c244a-113">ドメインの機能レベル</span><span class="sxs-lookup"><span data-stu-id="c244a-113">Domain Functional Level</span></span></th>
<th align="left"><span data-ttu-id="c244a-114">利用可能な委任レベル</span><span class="sxs-lookup"><span data-stu-id="c244a-114">Delegation Levels Available</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c244a-115">Windows 2000 ネイティブ</span><span class="sxs-lookup"><span data-stu-id="c244a-115">Windows 2000 native</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c244a-116">委任なし (既定)</span><span class="sxs-lookup"><span data-stu-id="c244a-116">No delegation (default)</span></span></p></li>
<li><p><span data-ttu-id="c244a-117">無制限の委任</span><span class="sxs-lookup"><span data-stu-id="c244a-117">Unconstrained delegation</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c244a-118">Windows Server 2003、Windows Server 2008、または Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c244a-118">Windows Server 2003, Windows Server 2008, or Windows Server 2008 R2</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="c244a-119">委任なし (既定)</span><span class="sxs-lookup"><span data-stu-id="c244a-119">No delegation (default)</span></span></p></li>
<li><p><span data-ttu-id="c244a-120">無制限の委任¹</span><span class="sxs-lookup"><span data-stu-id="c244a-120">Unconstrained delegation¹</span></span></p></li>
<li><p><span data-ttu-id="c244a-121">制約付き委任 (Kerberos のみのプロトコルを使用)</span><span class="sxs-lookup"><span data-stu-id="c244a-121">Constrained delegation (Use Kerberos Only Protocols)</span></span></p></li>
<li><p><span data-ttu-id="c244a-122">制約付き委任 (任意の認証プロトコルを使用) ¹</span><span class="sxs-lookup"><span data-stu-id="c244a-122">Constrained delegation (Use any authentication protocol) ¹</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c244a-123">¹おすすめのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c244a-123">¹ Not recommended.</span></span>

## <span data-ttu-id="c244a-124">ドメインの機能レベルが Windows 2000 ネイティブの場合に、制約なし委任を構成するには</span><span class="sxs-lookup"><span data-stu-id="c244a-124">To configure unconstrained delegation when the Domain Functional Level is Windows 2000 native</span></span>


<span data-ttu-id="c244a-125">Web サーバーのドメインのドメインコントローラーで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c244a-125">On the domain controller for your Web server’s domain, complete the following steps.</span></span>

****

1.  <span data-ttu-id="c244a-126">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-126">Click **Start**, **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

2.  <span data-ttu-id="c244a-127">[Domain] を展開し、[コンピューター] フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c244a-127">Expand domain, and then expand the Computers folder.</span></span>

3.  <span data-ttu-id="c244a-128">右側のウィンドウで、Web サーバーのコンピューター名を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-128">In the right pane, right-click the computer name for the Web server, and then click **Properties**.</span></span>

4.  <span data-ttu-id="c244a-129">[**全般**] タブで、[**コンピューターを委任用に信頼**する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c244a-129">On the **General** tab, ensure that the **Trust computer for delegation** check box is selected.</span></span>

5.  <span data-ttu-id="c244a-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-130">Click **OK**.</span></span>

## <span data-ttu-id="c244a-131">ドメインの機能レベルが Windows Server 2003、windows Server 2008、または Windows Server 2008 R2 の場合に、制約のない委任を構成するには</span><span class="sxs-lookup"><span data-stu-id="c244a-131">To configure unconstrained delegation when the Domain Functional Level is Windows Server 2003, Windows Server 2008, or Windows Server 2008 R2</span></span>


<span data-ttu-id="c244a-132">Web サーバーのドメインのドメインコントローラーで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c244a-132">On the domain controller for your Web server’s domain, complete the following steps.</span></span>

****

1.  <span data-ttu-id="c244a-133">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-133">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

2.  <span data-ttu-id="c244a-134">[Domain] を展開し、[コンピューター] フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c244a-134">Expand domain, and expand the Computers folder.</span></span>

3.  <span data-ttu-id="c244a-135">右側のウィンドウで、Web サーバーのコンピューター名を右クリックし、[**プロパティ**] を選択して、[**委任**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-135">In the right pane, right-click the computer name for the Web server, select **Properties**, and then click the **Delegation** tab.</span></span>

4.  <span data-ttu-id="c244a-136">[**すべてのサービスに対する委任に対してこのコンピューターを信頼する (Kerberos のみ)**] をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="c244a-136">Click to select **Trust this computer for delegation to any service (Kerberos only)**.</span></span>

5.  <span data-ttu-id="c244a-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-137">Click **OK**.</span></span>

## <span data-ttu-id="c244a-138">ドメインの機能レベルが Windows Server 2003、Windows Server 2008、または Windows Server 2008 R2 の場合に、制約付き委任を構成するには</span><span class="sxs-lookup"><span data-stu-id="c244a-138">To configure constrained delegation when the Domain Functional Level is Windows Server 2003, Windows Server 2008, or Windows Server 2008 R2</span></span>


<span data-ttu-id="c244a-139">Web サーバーのドメインのドメインコントローラーで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c244a-139">On the domain controller for your Web server’s domain, complete the following steps.</span></span>

****

1.  <span data-ttu-id="c244a-140">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-140">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

2.  <span data-ttu-id="c244a-141">[Domain] を展開し、[コンピューター] フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c244a-141">Expand domain, and then expand the Computers folder.</span></span>

3.  <span data-ttu-id="c244a-142">右側のウィンドウで、Web サーバーのコンピューター名を右クリックし、[**プロパティ**] を選択して、[**委任**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-142">In the right pane, right-click the computer name for the Web server, select **Properties**, and then click the **Delegation** tab.</span></span>

4.  <span data-ttu-id="c244a-143">[指定し**たサービスに対する委任に対してこのコンピューターを信頼**する] をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="c244a-143">Click to select **Trust this computer for delegation to specified services only**.</span></span>

5.  <span data-ttu-id="c244a-144">[ **Kerberos のみを使用**] が選択されていることを確認し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-144">Ensure that **Use Kerberos only** is selected, and then click **OK**.</span></span>

6.  <span data-ttu-id="c244a-145">**[追加]** ボタンをクリックします </span><span class="sxs-lookup"><span data-stu-id="c244a-145">Click the **Add** button.</span></span> <span data-ttu-id="c244a-146">[**サービスの追加**] ダイアログボックスで、[**ユーザーまたはコンピューター**] をクリックし、app-v データストアがある Microsoft SQL server の名前を参照または入力して、IIS からユーザー資格情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c244a-146">In the **Add Services** dialog box, click **Users or Computers**, and then browse to or type the name of the Microsoft SQL server that has the App-V data store and is to receive the users credentials from IIS.</span></span> <span data-ttu-id="c244a-147">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-147">Click **OK**.</span></span>

7.  <span data-ttu-id="c244a-148">[**使用可能なサービス**] ボックスの一覧で、Microsoft SQL Server が app-v データベースへの接続を許可しているポート番号を一覧表示する MSSQLSvc サービスを選択します (既定のポートは 1433)。</span><span class="sxs-lookup"><span data-stu-id="c244a-148">In the **Available Services** list, select the MSSQLSvc service that lists port number on which the Microsoft SQL Server is accepting connections for the App-V database (the default port is 1433).</span></span> <span data-ttu-id="c244a-149">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-149">Click **OK**.</span></span>

### <span data-ttu-id="c244a-150">制約付き委任用に IIS 7 を構成するための追加の手順</span><span class="sxs-lookup"><span data-stu-id="c244a-150">Additional steps to configure IIS 7 for constrained delegation</span></span>

<span data-ttu-id="c244a-151">IIS 7 サーバーで管理 Web サービスを実行している場合は、次の手順を実行して、IIS 7 *useAppPoolCredentials*変数を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c244a-151">If you are running the Management Web Service on an IIS 7 server, you must complete the following steps to set the IIS 7 *useAppPoolCredentials* variable to True.</span></span>

1.  <span data-ttu-id="c244a-152">昇格したコマンドプロンプトウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="c244a-152">Open an elevated Command Prompt window.</span></span> <span data-ttu-id="c244a-153">昇格したコマンドプロンプトウィンドウを開くには、[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c244a-153">To open an elevated Command Prompt window, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="c244a-154">%Windir%\\system32\\inetsrv. に移動する</span><span class="sxs-lookup"><span data-stu-id="c244a-154">Navigate to %windir%\\system32\\inetsrv.</span></span>

3.  <span data-ttu-id="c244a-155">「appcmd.exe 設定」と入力します。 **「system.webserver/security/authentication/windowsAuthentication-useAppPoolCredentials: true**」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c244a-155">Type **appcmd.exe set config -section:system.webServer/security/authentication/windowsAuthentication -useAppPoolCredentials:true**, and then press ENTER.</span></span>

 

 





