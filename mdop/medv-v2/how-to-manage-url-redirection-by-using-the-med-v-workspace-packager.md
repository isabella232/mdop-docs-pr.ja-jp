---
title: MED-V ワークスペース パッケージ ツールを使用して URL のリダイレクトを管理する方法
description: MED-V ワークスペース パッケージ ツールを使用して URL のリダイレクトを管理する方法
author: dansimp
ms.assetid: 1a8d25af-479f-42d3-bf5f-c7fd974bbf8c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 88167923e3bd47f2a3b0b3ada5e818715740dbe3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824817"
---
# <span data-ttu-id="6c011-103">MED-V ワークスペース パッケージ ツールを使用して URL のリダイレクトを管理する方法</span><span class="sxs-lookup"><span data-stu-id="6c011-103">How to Manage URL Redirection by Using the MED-V Workspace Packager</span></span>


<span data-ttu-id="6c011-104">MED-V ワークスペースパッケージャーを使って、MED-V ワークスペースの URL リダイレクションを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6c011-104">You can use the MED-V Workspace Packager to manage URL redirection in the MED-V workspace.</span></span>

**<span data-ttu-id="6c011-105">MED-V ワークスペースで web アドレスリダイレクションを管理するには</span><span class="sxs-lookup"><span data-stu-id="6c011-105">To manage web address redirection in a MED-V workspace</span></span>**

1.  <span data-ttu-id="6c011-106">**Med-v ワークスペースのパッケージャー**を開くには、 **[スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v workspace パッケージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c011-106">To open the **MED-V Workspace Packager**, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager**.</span></span>

2.  <span data-ttu-id="6c011-107">**Med-v ワークスペースパッケージャー**メインパネルで、[ **Web リダイレクションの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c011-107">On the **MED-V Workspace Packager** main panel, click **Manage Web Redirection**.</span></span>

3.  <span data-ttu-id="6c011-108">[ **Web リダイレクトの管理**] ウィンドウでは、med-v ワークスペースの Internet Explorer にリダイレクトされる url の一覧を入力、貼り付け、またはインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c011-108">In the **Manage Web Redirection** window, you can type, paste, or import a list of the URLs that are redirected to Internet Explorer in the MED-V workspace.</span></span>

    **<span data-ttu-id="6c011-109">注</span><span class="sxs-lookup"><span data-stu-id="6c011-109">Note</span></span>**  
    <span data-ttu-id="6c011-110">MED-V の URL リダイレクションは、プロトコル HTTP と HTTPS のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6c011-110">URL redirection in MED-V only supports the protocols HTTP and HTTPS.</span></span> <span data-ttu-id="6c011-111">MED-V では、FTP やその他のプロトコルのサポートは提供されません。</span><span class="sxs-lookup"><span data-stu-id="6c011-111">MED-V does not provide support for FTP or any other protocols.</span></span>



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



4. <span data-ttu-id="6c011-112">[**名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c011-112">Click **Save as…**</span></span> <span data-ttu-id="6c011-113">指定したフォルダーにある更新された URL リダイレクトファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="6c011-113">to save the updated URL redirection files in the specified folder.</span></span> <span data-ttu-id="6c011-114">MED-V は、更新された URL リダイレクション情報を含むレジストリファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c011-114">MED-V creates a registry file that contains the updated URL redirection information.</span></span> <span data-ttu-id="6c011-115">グループポリシーを使用して、更新されたレジストリキーを展開します。</span><span class="sxs-lookup"><span data-stu-id="6c011-115">Deploy the updated registry key by using Group Policy.</span></span> <span data-ttu-id="6c011-116">グループポリシーの使用方法の詳細については、「[グループポリシーソフトウェアのインストール](https://go.microsoft.com/fwlink/?LinkId=195931)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="6c011-116">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

   <span data-ttu-id="6c011-117">MED-V は、指定されたフォルダーに Windows PowerShell スクリプトを作成します。これは、更新された MED-V ワークスペースパッケージを再作成するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c011-117">MED-V also creates a Windows PowerShell script in the specified folder that you can use to re-create the updated MED-V workspace package.</span></span>

## <span data-ttu-id="6c011-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6c011-118">Related topics</span></span>


[<span data-ttu-id="6c011-119">展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法</span><span class="sxs-lookup"><span data-stu-id="6c011-119">How to Add or Remove URL Redirection Information in a Deployed MED-V Workspace</span></span>](how-to-add-or-remove-url-redirection-information-in-a-deployed-med-v-workspace.md)

[<span data-ttu-id="6c011-120">MED-V の URL リダイレクトの管理</span><span class="sxs-lookup"><span data-stu-id="6c011-120">Manage MED-V URL Redirection</span></span>](manage-med-v-url-redirection.md)









