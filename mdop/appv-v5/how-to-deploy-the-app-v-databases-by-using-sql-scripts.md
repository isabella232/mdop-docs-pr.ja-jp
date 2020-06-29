---
title: SQL スクリプトを使用して APP-V データベースを展開する方法
description: SQL スクリプトを使用して APP-V データベースを展開する方法
author: dansimp
ms.assetid: 23637936-475f-4ca5-adde-76bb27d2372b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 511d1020571eead25af9e9591fe1834a9f97f068
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814114"
---
# <span data-ttu-id="62ebe-103">SQL スクリプトを使用して APP-V データベースを展開する方法</span><span class="sxs-lookup"><span data-stu-id="62ebe-103">How to Deploy the App-V Databases by Using SQL Scripts</span></span>


<span data-ttu-id="62ebe-104">Windows インストーラーではなく SQL スクリプトを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="62ebe-104">Use the following instructions to use SQL scripts, rather than the Windows Installer, to:</span></span>

-   <span data-ttu-id="62ebe-105">App-v 5.0 データベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="62ebe-105">Install the App-V 5.0 databases</span></span>

-   <span data-ttu-id="62ebe-106">5.0 データベースを最新バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="62ebe-106">Upgrade the 5.0 databases to a later version</span></span>

**<span data-ttu-id="62ebe-107">SQL スクリプトを使用して app-v データベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="62ebe-107">How to install the App-V databases by using SQL scripts</span></span>**

1. <span data-ttu-id="62ebe-108">データベーススクリプトをインストールする前に、「App-v ライセンス条項のコピー」を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="62ebe-108">Before you install the database scripts, review and keep a copy of the App-V license terms.</span></span> <span data-ttu-id="62ebe-109">データベーススクリプトを実行すると、ライセンス条項に同意したことになります。</span><span class="sxs-lookup"><span data-stu-id="62ebe-109">By running the database scripts, you are agreeing to the license terms.</span></span> <span data-ttu-id="62ebe-110">同意しない場合は、このソフトウェアを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="62ebe-110">If you do not accept them, you should not use this software.</span></span>

2. <span data-ttu-id="62ebe-111">**appv\_server\_setup.exe**を app-v リリースメディアから一時的な場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="62ebe-111">Copy the **appv\_server\_setup.exe** from the App-V release media to a temporary location.</span></span>

3. <span data-ttu-id="62ebe-112">コマンドプロンプトで**appv\_server\_setup.exe**を実行し、データベーススクリプトを抽出するための一時的な場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="62ebe-112">From a command prompt, run **appv\_server\_setup.exe** and specify a temporary location for extracting the database scripts.</span></span>

   <span data-ttu-id="62ebe-113">例: appv\_server\_setup.exe/layout ¥ &lt; temp location path&gt;</span><span class="sxs-lookup"><span data-stu-id="62ebe-113">Example: appv\_server\_setup.exe /layout c:\\&lt;temporary location path&gt;</span></span>

4. <span data-ttu-id="62ebe-114">作成した一時的な場所を参照し、抽出された [ **Databasescripts** ] フォルダーを開いて、手順について適切な Readme.txt ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="62ebe-114">Browse to the temporary location that you created, open the extracted **DatabaseScripts** folder, and review the appropriate Readme.txt file for instructions:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="62ebe-115">Database (データベース)</span><span class="sxs-lookup"><span data-stu-id="62ebe-115">Database</span></span></th>
   <th align="left"><span data-ttu-id="62ebe-116">使用する Readme.txt ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="62ebe-116">Location of Readme.txt file to use</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="62ebe-117">管理データベース</span><span class="sxs-lookup"><span data-stu-id="62ebe-117">Management database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="62ebe-118">ManagementDatabase サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="62ebe-118">ManagementDatabase subfolder</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="62ebe-119">重要</span><span class="sxs-lookup"><span data-stu-id="62ebe-119">Important</span></span></strong><br/><p><span data-ttu-id="62ebe-120">App-v 5.0 SP3 管理データベースへのアップグレードまたはインストールを行う場合は、「 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 5.0 アプリをインストールまたはアップグレードするための SQL スクリプト」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="62ebe-120">If you are upgrading to or installing the App-V 5.0 SP3 Management database, see <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)">SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="62ebe-121">レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="62ebe-121">Reporting database</span></span></p></td>
   <td align="left"><p><span data-ttu-id="62ebe-122">ReportingDatabase サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="62ebe-122">ReportingDatabase subfolder</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="62ebe-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="62ebe-123">Related topics</span></span>


[<span data-ttu-id="62ebe-124">App-V 5.0 Server の展開</span><span class="sxs-lookup"><span data-stu-id="62ebe-124">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

[<span data-ttu-id="62ebe-125">App-V 5.0 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="62ebe-125">How to Deploy the App-V 5.0 Server</span></span>](how-to-deploy-the-app-v-50-server-50sp3.md)









