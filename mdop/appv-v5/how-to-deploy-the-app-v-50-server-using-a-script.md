---
title: スクリプトを使用して APP-V 5.0 Server を展開する方法
description: スクリプトを使用して APP-V 5.0 Server を展開する方法
author: dansimp
ms.assetid: b91a35c8-df9e-4065-9187-abafbe565b84
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: aeb16d166fe7b1c4bb418c212024c49f6b151b94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814170"
---
# <span data-ttu-id="a1568-103">スクリプトを使用して APP-V 5.0 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="a1568-103">How to Deploy the App-V 5.0 Server Using a Script</span></span>


<span data-ttu-id="a1568-104">コマンドラインを正常に実行するために**appv\_server\_setup.exe** Server のセットアップを完了するには、複数のパラメーターを指定して結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1568-104">In order to complete the **appv\_server\_setup.exe** Server setup successfully using the command line, you must specify and combine multiple parameters.</span></span>

<span data-ttu-id="a1568-105">コマンドラインを使用した App-v 5.0 サーバーのインストールの詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1568-105">Use the following tables for more information about installing the App-V 5.0 server using the command line.</span></span>

>[!NOTE]
> <span data-ttu-id="a1568-106">次の表の情報は、次のコマンドを入力してコマンドラインを使用してアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a1568-106">The information in the following tables can also be accessed using the command line by typing the following command:</span></span>
>```
> appv\_server\_setup.exe /?
>```

## <span data-ttu-id="a1568-107">一般的なパラメーターと例</span><span class="sxs-lookup"><span data-stu-id="a1568-107">Common parameters and Examples</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-108">管理サーバーと管理データベースをローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-108">To Install the Management server and Management database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-109">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-109">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-110">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-110">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-111">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-111">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-112">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-112">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-113">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-113">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-114">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-114">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-116">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-116">/MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-117">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-117">To use a custom instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-118">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-118">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-119">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-119">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-120">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-120">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-121">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-121">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-122">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-122">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-123">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-123">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-124">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-124">/MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-125">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-125">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-126">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-126">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-127">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-127">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="a1568-128">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="a1568-128">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="a1568-129">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理サービス"</span><span class="sxs-lookup"><span data-stu-id="a1568-129">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="a1568-130">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="a1568-130">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="a1568-131">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-131">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="a1568-132">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-132">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-133">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="a1568-133">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>
     
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-134">ローカルコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-134">To Install the Management server using an existing Management database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-135">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-135">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-136">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-136">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-137">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-137">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-138">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-138">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-139">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-139">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-140">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-140">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-141">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-141">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-142">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-142">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-143">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-143">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-144">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-144">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-145">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-145">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-146">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-146">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-147">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-147">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-148">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-148">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-149">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-149">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-150">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-150">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-151">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-151">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-152">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-152">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-153">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-153">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="a1568-154">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="a1568-154">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="a1568-155">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理サービス"</span><span class="sxs-lookup"><span data-stu-id="a1568-155">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="a1568-156">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="a1568-156">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="a1568-157">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-157">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="a1568-158">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-158">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE =”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-159">/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="a1568-159">/EXISTING_MANAGEMENT_DB_NAME =”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>  

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-160">リモートコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-160">To install the Management server using an existing Management database on a remote machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-161">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-161">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-162">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-162">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-163">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-163">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-164">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-164">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-165">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-165">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-166">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-166">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-167">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-167">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-168">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-168">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-169">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-169">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-170">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-170">/MANAGEMENT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-171">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-171">/MANAGEMENT_ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-172">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-172">/MANAGEMENT_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-173">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-173">/MANAGEMENT_WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-174">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-174">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-175">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-175">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-176">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-176">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-177">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-177">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-178">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-178">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-179">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-179">/MANAGEMENT_SERVER</span></span></p>
    <p><span data-ttu-id="a1568-180">/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</span><span class="sxs-lookup"><span data-stu-id="a1568-180">/MANAGEMENT_ADMINACCOUNT=”Domain\AdminGroup”</span></span></p>
    <p><span data-ttu-id="a1568-181">/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理サービス"</span><span class="sxs-lookup"><span data-stu-id="a1568-181">/MANAGEMENT_WEBSITE_NAME=”Microsoft AppV Management Service”</span></span></p>
    <p><span data-ttu-id="a1568-182">/MANAGEMENT_WEBSITE_PORT = "8080"</span><span class="sxs-lookup"><span data-stu-id="a1568-182">/MANAGEMENT_WEBSITE_PORT=”8080”</span></span></p>
    <p><span data-ttu-id="a1568-183">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME = "SqlServermachine"</span><span class="sxs-lookup"><span data-stu-id="a1568-183">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME=”SqlServermachine.domainName”</span></span></p>
    <p><span data-ttu-id="a1568-184">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-184">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE =”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-185">/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="a1568-185">/EXISTING_MANAGEMENT_DB_NAME =”AppVManagement”</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-186">管理データベースと管理サーバーを同じコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-186">To Install the Management database and the Management Server on the same computer.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-187">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-187">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-188">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-188">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-189">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-189">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-190">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-190">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-191">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-191">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-192">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-192">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-193">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-193">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-194">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-194">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-195">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-195">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-196">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-196">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-197">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-197">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-198">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-198">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-199">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-199">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-200">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-200">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-201">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-201">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="a1568-202">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-202">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-203">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="a1568-203">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p>
    <p><span data-ttu-id="a1568-204">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-204">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="a1568-205">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</span><span class="sxs-lookup"><span data-stu-id="a1568-205">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-206">管理データベースを管理サーバーとは異なるコンピューターにインストールするには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="a1568-206">To install the Management database on a different computer than the Management server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-207">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-207">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-208">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-208">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-209">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-209">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-210">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-210">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-211">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-211">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-212">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-212">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-213">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-213">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-214">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-214">/DB_PREDEPLOY_MANAGEMENT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-215">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-215">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-216">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-216">/MANAGEMENT_DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-217">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-217">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-218">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-218">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-219">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-219">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-220">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-220">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-221">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-221">/DB_PREDEPLOY_MANAGEMENT</span></span></p>
    <p><span data-ttu-id="a1568-222">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-222">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-223">/MANAGEMENT_DB_NAME = "AppVManagement"</span><span class="sxs-lookup"><span data-stu-id="a1568-223">/MANAGEMENT_DB_NAME=”AppVManagement”</span></span></p>
    <p><span data-ttu-id="a1568-224">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "\ アカウントアカウント"</span><span class="sxs-lookup"><span data-stu-id="a1568-224">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT=”Domain\MachineAccount”</span></span></p>
    <p><span data-ttu-id="a1568-225">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</span><span class="sxs-lookup"><span data-stu-id="a1568-225">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-226">を選び、発行サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-226">To Install the publishing server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-227">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-227">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-228">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-228">/PUBLISHING_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-229">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-229">/PUBLISHING_MGT_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-230">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-230">/PUBLISHING_WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-231">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-231">/PUBLISHING_WEBSITE_PORT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-232">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-232">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-233">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-233">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-234">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-234">/PUBLISHING_SERVER</span></span></p>
    <p><span data-ttu-id="a1568-235">/PUBLISHING_MGT_SERVER = " http://ManagementServerName:ManagementPort "</span><span class="sxs-lookup"><span data-stu-id="a1568-235">/PUBLISHING_MGT_SERVER=”http://ManagementServerName:ManagementPort”</span></span></p>
    <p><span data-ttu-id="a1568-236">/PUBLISHING_WEBSITE_NAME = "Microsoft AppV 公開サービス"</span><span class="sxs-lookup"><span data-stu-id="a1568-236">/PUBLISHING_WEBSITE_NAME=”Microsoft AppV Publishing Service”</span></span></p>
    <p><span data-ttu-id="a1568-237">/PUBLISHING_WEBSITE_PORT = "8081"</span><span class="sxs-lookup"><span data-stu-id="a1568-237">/PUBLISHING_WEBSITE_PORT=”8081”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-238">レポートサーバーとレポートデータベースをローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-238">To Install the Reporting server and Reporting database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-239">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-239">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-240">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-240">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-241">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-241">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-242">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-242">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-243">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-243">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-244">/レポート _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-244">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-245">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-245">/REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-246">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-246">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-247">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-247">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-248">/レポート _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-248">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-249">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-249">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-250">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-250">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-251">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-251">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-252">/レポート _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-252">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-253">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-253">/REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-254">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-254">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-255">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-255">/appv_server_setup.exe /QUIET</span></span></p></li>
    <li><p><span data-ttu-id="a1568-256">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-256">/REPORTING_SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-257">/REPORTING_WEBSITE_NAME = "Microsoft AppV Reporting Service"</span><span class="sxs-lookup"><span data-stu-id="a1568-257">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p></li>
    <li><p><span data-ttu-id="a1568-258">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="a1568-258">/REPORTING_WEBSITE_PORT=”8082”</span></span></p></li>
    <li><p><span data-ttu-id="a1568-259">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-259">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-260">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-260">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p></li>
    <li><p><span data-ttu-id="a1568-261">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="a1568-261">/REPORTING_DB_NAME=”AppVReporting”</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-262">レポートサーバーをインストールして、ローカルコンピューターに既存のレポートデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-262">To Install the Reporting server and using an existing Reporting database on a local machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-263">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-263">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-264">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-264">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-265">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-265">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-266">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-266">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-267">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-267">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-268">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-268">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-269">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-269">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-270">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-270">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-271">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-271">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-272">/レポート _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-272">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-273">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-273">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-274">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-274">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-275">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-275">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-276">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-276">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-277">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-277">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-278">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-278">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-279">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-279">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-280">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-280">/REPORTING_SERVER</span></span></p>
    <p><span data-ttu-id="a1568-281">/REPORTING_WEBSITE_NAME = "Microsoft AppV Reporting Service"</span><span class="sxs-lookup"><span data-stu-id="a1568-281">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p>
    <p><span data-ttu-id="a1568-282">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="a1568-282">/REPORTING_WEBSITE_PORT=”8082”</span></span></p>
    <p><span data-ttu-id="a1568-283">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-283">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="a1568-284">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-284">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-285">/EXITING_REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="a1568-285">/EXITING_REPORTING_DB_NAME=”AppVReporting”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-286">リモートコンピューター上の既存のレポートデータベースを使用して、レポートサーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1568-286">To Install the Reporting server using an existing Reporting database on a remote machine.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-287">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-287">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-288">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-288">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-289">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-289">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-290">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-290">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-291">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-291">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-292">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-292">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-293">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-293">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-294">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-294">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-295">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-295">/REPORTING _SERVER</span></span></p></li>
    <li><p><span data-ttu-id="a1568-296">/レポート _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-296">/REPORTING _ADMINACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-297">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-297">/REPORTING _WEBSITE_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-298">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-298">/REPORTING _WEBSITE_PORT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-299">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-299">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-300">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-300">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-301">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-301">/EXISTING_REPORTING _DB_NAME</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-302">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-302">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-303">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-303">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-304">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-304">/REPORTING_SERVER</span></span></p>
    <p><span data-ttu-id="a1568-305">/REPORTING_WEBSITE_NAME = "Microsoft AppV Reporting Service"</span><span class="sxs-lookup"><span data-stu-id="a1568-305">/REPORTING_WEBSITE_NAME=”Microsoft AppV Reporting Service”</span></span></p>
    <p><span data-ttu-id="a1568-306">/REPORTING_WEBSITE_PORT = "8082"</span><span class="sxs-lookup"><span data-stu-id="a1568-306">/REPORTING_WEBSITE_PORT=”8082”</span></span></p>
    <p><span data-ttu-id="a1568-307">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME = "SqlServerMachine"</span><span class="sxs-lookup"><span data-stu-id="a1568-307">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME=”SqlServerMachine.DomainName”</span></span></p>
    <p><span data-ttu-id="a1568-308">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-308">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-309">/EXITING_REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="a1568-309">/EXITING_REPORTING_DB_NAME=”AppVReporting”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-310">レポートサーバーと同じコンピューターにレポートデータベースをインストールする。</span><span class="sxs-lookup"><span data-stu-id="a1568-310">To install the Reporting database on the same computer as the Reporting server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-311">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-311">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-312">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-312">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-313">/レポート _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-313">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-314">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-314">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-315">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-315">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-316">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-316">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-317">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-317">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-318">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-318">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-319">/レポート _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-319">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-320">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-320">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-321">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-321">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></li>
    <li><p><span data-ttu-id="a1568-322">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-322">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-323">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-323">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-324">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-324">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-325">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-325">/DB_PREDEPLOY_REPORTING</span></span></p>
    <p><span data-ttu-id="a1568-326">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-326">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-327">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="a1568-327">/REPORTING_DB_NAME=”AppVReporting”</span></span></p>
    <p><span data-ttu-id="a1568-328">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-328">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p>
    <p><span data-ttu-id="a1568-329">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</span><span class="sxs-lookup"><span data-stu-id="a1568-329">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-330">レポートデータベースをレポートサーバーとは別のコンピューターにインストールする。</span><span class="sxs-lookup"><span data-stu-id="a1568-330">To install the Reporting database on a different computer than the Reporting server.</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-331">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-331">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-332">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-332">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-333">/レポート _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-333">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-334">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-334">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-335">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-335">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-336">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-336">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-337">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1568-337">To use a custom instance of Microsoft SQL Server, use these parameters:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="a1568-338">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-338">/DB_PREDEPLOY_REPORTING</span></span></p></li>
    <li><p><span data-ttu-id="a1568-339">/レポート _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-339">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span></p></li>
    <li><p><span data-ttu-id="a1568-340">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-340">/REPORTING _DB_NAME</span></span></p></li>
    <li><p><span data-ttu-id="a1568-341">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-341">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></li>
    <li><p><span data-ttu-id="a1568-342">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-342">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></li>
    </ul>
    <p><span data-ttu-id="a1568-343">Microsoft SQL Server のカスタムインスタンスの使用例:</span><span class="sxs-lookup"><span data-stu-id="a1568-343">Using a custom instance of Microsoft SQL Server example:</span></span></p>
    <p><span data-ttu-id="a1568-344">/appv_server_setup.exe/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-344">/appv_server_setup.exe /QUIET</span></span></p>
    <p><span data-ttu-id="a1568-345">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-345">/DB_PREDEPLOY_REPORTING</span></span></p>
    <p><span data-ttu-id="a1568-346">/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</span><span class="sxs-lookup"><span data-stu-id="a1568-346">/REPORTING_DB_CUSTOM_SQLINSTANCE=”SqlInstanceName”</span></span></p>
    <p><span data-ttu-id="a1568-347">/REPORTING_DB_NAME = "AppVReporting"</span><span class="sxs-lookup"><span data-stu-id="a1568-347">/REPORTING_DB_NAME=”AppVReporting”</span></span></p>
    <p><span data-ttu-id="a1568-348">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "\ アカウントアカウント"</span><span class="sxs-lookup"><span data-stu-id="a1568-348">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT=”Domain\MachineAccount”</span></span></p>
    <p><span data-ttu-id="a1568-349">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</span><span class="sxs-lookup"><span data-stu-id="a1568-349">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT=”Domain\InstallAdminAccount”</span></span></p></td>
    </tr>
    </tbody>
    </table>

## <span data-ttu-id="a1568-350">パラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="a1568-350">Parameter Definitions</span></span>

### <span data-ttu-id="a1568-351">一般的なパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-351">General Parameters</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-352">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-352">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-353">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-353">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-354">/QUIET</span><span class="sxs-lookup"><span data-stu-id="a1568-354">/QUIET</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-355">サイレントインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-355">Specifies silent install.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-356">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="a1568-356">/UNINSTALL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-357">アンインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-357">Specifies an uninstall.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-358">/レイアウト</span><span class="sxs-lookup"><span data-stu-id="a1568-358">/LAYOUT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-359">レイアウトアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-359">Specifies layout action.</span></span> <span data-ttu-id="a1568-360">これにより、実際には製品をインストールせずに、MSIs ファイルとスクリプトファイルがフォルダーに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-360">This extracts the MSIs and script files to a folder without actually installing the product.</span></span> <span data-ttu-id="a1568-361">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-361">No value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-362">/Layoutdir</span><span class="sxs-lookup"><span data-stu-id="a1568-362">/LAYOUTDIR</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-363">レイアウトディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-363">Specifies the layout directory.</span></span> <span data-ttu-id="a1568-364">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-364">Takes a string.</span></span> <span data-ttu-id="a1568-365">たとえば、/layoutdir = "C:\ Application Virtualization Server"</span><span class="sxs-lookup"><span data-stu-id="a1568-365">For example, /LAYOUTDIR=”C:\Application Virtualization Server”</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-366">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="a1568-366">/INSTALLDIR</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-367">インストールディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-367">Specifies the installation directory.</span></span> <span data-ttu-id="a1568-368">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-368">Takes a string.</span></span> <span data-ttu-id="a1568-369">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-369">E.g.</span></span> <span data-ttu-id="a1568-370">/INSTALLDIR = "C:\Program Files\Application Virtualization\Server"</span><span class="sxs-lookup"><span data-stu-id="a1568-370">/INSTALLDIR=”C:\Program Files\Application Virtualization\Server”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-371">/Muoptin</span><span class="sxs-lookup"><span data-stu-id="a1568-371">/MUOPTIN</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-372">Microsoft Update を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1568-372">Enables Microsoft Update.</span></span> <span data-ttu-id="a1568-373">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-373">No value is expected</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-374">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="a1568-374">/ACCEPTEULA</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-375">ライセンス契約を承諾します。</span><span class="sxs-lookup"><span data-stu-id="a1568-375">Accepts the license agreement.</span></span> <span data-ttu-id="a1568-376">これは、無人インストールの場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="a1568-376">This is required for an unattended installation.</span></span> <span data-ttu-id="a1568-377">使用例: <strong> /ACCEPTEULA </strong> または <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a1568-377">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="a1568-378">管理サーバーのインストールパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-378">Management Server Installation Parameters</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-379">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-379">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-380">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-380">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-381">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-381">/MANAGEMENT_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-382">管理サーバーをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-382">Specifies that the management server will be installed.</span></span> <span data-ttu-id="a1568-383">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-383">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-384">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-384">/MANAGEMENT_ADMINACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-385">管理サーバーへの管理者アクセス許可を持つことができるアカウントを指定します。このアカウントは、個々のユーザーアカウントまたはグループにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1568-385">Specifies the account that will be allowed to Administrator access to the management server This account can be an individual user account or a group.</span></span> <span data-ttu-id="a1568-386">使用例: <strong> /MANAGEMENT_ADMINACCOUNT = "my" 管理者 " </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a1568-386">Example usage: <strong>/MANAGEMENT_ADMINACCOUNT=”mydomain\admin”</strong>.</span></span> <span data-ttu-id="a1568-387"><strong>/MANAGEMENT_SERVER </strong> が指定されていない場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-387">If <strong>/MANAGEMENT_SERVER</strong> is not specified, this will be ignored.</span></span> <span data-ttu-id="a1568-388">管理サーバーへの管理者アクセスが許可されるアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-388">Specifies the account that will be allowed to Administrator access to the management server.</span></span> <span data-ttu-id="a1568-389">これは、ユーザーアカウントまたはグループのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="a1568-389">This can be a user account or a group.</span></span> <span data-ttu-id="a1568-390">たとえば、 <strong> /MANAGEMENT_ADMINACCOUNT = &quot; myの管理者 &quot; </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a1568-390">For example, <strong>/MANAGEMENT_ADMINACCOUNT=&quot;mydomain\admin&quot;</strong>.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-391">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-391">/MANAGEMENT_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-392">管理サービス用に作成される web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-392">Specifies name of the website that will be created for the management service.</span></span> <span data-ttu-id="a1568-393">たとえば、/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V Management Service"</span><span class="sxs-lookup"><span data-stu-id="a1568-393">For example, /MANAGEMENT_WEBSITE_NAME=”Microsoft App-V Management Service”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-394">MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-394">MANAGEMENT_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-395">管理サービスが使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-395">Specifies the port number that will be used by the management service will use.</span></span> <span data-ttu-id="a1568-396">たとえば、/MANAGEMENT_WEBSITE_PORT = 82 とします。</span><span class="sxs-lookup"><span data-stu-id="a1568-396">For example, /MANAGEMENT_WEBSITE_PORT=82.</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="a1568-397">管理サーバーデータベースのパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-397">Parameters for the Management Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-398">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-398">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-399">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-399">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-400">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="a1568-400">/DB_PREDEPLOY_MANAGEMENT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-401">管理データベースをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-401">Specifies that the management database will be installed.</span></span> <span data-ttu-id="a1568-402">このインストールを完了するには、十分なデータベース権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="a1568-402">You must have sufficient database permissions to complete this installation.</span></span> <span data-ttu-id="a1568-403">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-403">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-404">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-404">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-405">既定の SQL インスタンスを使用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-405">Indicates that the default SQL instance should be used.</span></span> <span data-ttu-id="a1568-406">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-406">No value is expected.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-407">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-407">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-408">新しいデータベースの作成に使用するカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-408">Specifies the name of the custom SQL instance that should be used to create a new database.</span></span> <span data-ttu-id="a1568-409">使用例: <strong> /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a1568-409">Example usage: <strong>/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE=”MYSQLSERVER”</strong>.</span></span> <span data-ttu-id="a1568-410">/DB_PREDEPLOY_MANAGEMENT が指定されていない場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-410">If /DB_PREDEPLOY_MANAGEMENT is not specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-411">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-411">/MANAGEMENT_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-412">作成する新しい管理データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-412">Specifies the name of the new management database that should be created.</span></span> <span data-ttu-id="a1568-413">使用例: <strong> /MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong></span><span class="sxs-lookup"><span data-stu-id="a1568-413">Example usage: <strong>/MANAGEMENT_DB_NAME=”AppVMgmtDB”</strong>.</span></span> <span data-ttu-id="a1568-414">/DB_PREDEPLOY_MANAGEMENT が指定されていない場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-414">If /DB_PREDEPLOY_MANAGEMENT is not specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-415">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-415">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-416">データベースにアクセスする管理サーバーがローカルサーバーにインストールされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-416">Indicates if the management server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="a1568-417">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-417">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-418">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-418">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-419">管理サーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-419">Specifies the machine account of the remote machine that the management server will be installed on.</span></span> <span data-ttu-id="a1568-420">使用例: <strong> /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"</span><span class="sxs-lookup"><span data-stu-id="a1568-420">Example usage: <strong>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT=”domain\computername”</span></span></strong></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-421">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-421">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-422">管理サーバーをインストールするために使用される管理者アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-422">Indicates the Administrator account that will be used to install the management server.</span></span> <span data-ttu-id="a1568-423">使用例: <strong> /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\alias"</span><span class="sxs-lookup"><span data-stu-id="a1568-423">Example usage: <strong>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT =”domain\alias”</span></span></strong></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="a1568-424">発行サーバーをインストールするためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-424">Parameters for Installing Publishing Server</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-425">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-425">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-426">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-426">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-427">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-427">/PUBLISHING_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-428">発行サーバーをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-428">Specifies that the Publishing Server will be installed.</span></span> <span data-ttu-id="a1568-429">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-429">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-430">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-430">/PUBLISHING_MGT_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-431">発行サーバーが接続する管理サービスの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-431">Specifies the URL to Management Service the Publishing server will connect to.</span></span> <span data-ttu-id="a1568-432">使用例: <strong> http:// &lt; management server name &gt; : &lt; 管理サーバーのポート番号 &gt; </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a1568-432">Example usage: <strong>http://&lt;management server name&gt;:&lt;Management server port number&gt;</strong>.</span></span> <span data-ttu-id="a1568-433">/PUBLISHING_SERVER が使用されていない場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-433">If /PUBLISHING_SERVER is not used, this parameter will be ignored</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-434">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-434">/PUBLISHING_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-435">発行サービス用に作成される web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-435">Specifies name of the website that will be created for the publishing service.</span></span> <span data-ttu-id="a1568-436">たとえば、/PUBLISHING_WEBSITE_NAME = "Microsoft App-V Publishing Service"</span><span class="sxs-lookup"><span data-stu-id="a1568-436">For example, /PUBLISHING_WEBSITE_NAME=”Microsoft App-V Publishing Service”</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-437">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-437">/PUBLISHING_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-438">発行サービスによって使用されるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-438">Specifies the port number used by the publishing service.</span></span> <span data-ttu-id="a1568-439">たとえば、/PUBLISHING_WEBSITE_PORT = 83</span><span class="sxs-lookup"><span data-stu-id="a1568-439">For example, /PUBLISHING_WEBSITE_PORT=83</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="a1568-440">レポートサーバーのパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-440">Parameters for Reporting Server</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-441">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-441">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-442">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-442">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-443">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="a1568-443">/REPORTING_SERVER</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-444">レポートサーバーをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-444">Specifies that the Reporting Server will be installed.</span></span> <span data-ttu-id="a1568-445">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-445">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-446">/REPORTING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-446">/REPORTING_WEBSITE_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-447">レポートサービス用に作成される web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-447">Specifies name of the website that will be created for the Reporting Service.</span></span> <span data-ttu-id="a1568-448">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-448">E.g.</span></span> <span data-ttu-id="a1568-449">/REPORTING_WEBSITE_NAME = &quot; Microsoft App-V ReportingService&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-449">/REPORTING_WEBSITE_NAME=&quot;Microsoft App-V ReportingService&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-450">/REPORTING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="a1568-450">/REPORTING_WEBSITE_PORT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-451">レポートサービスが使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-451">Specifies the port number that the Reporting Service will use.</span></span> <span data-ttu-id="a1568-452">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-452">E.g.</span></span> <span data-ttu-id="a1568-453">/REPORTING_WEBSITE_PORT = 82</span><span class="sxs-lookup"><span data-stu-id="a1568-453">/REPORTING_WEBSITE_PORT=82</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

### <span data-ttu-id="a1568-454">既存のレポートサーバーデータベースを使用するためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-454">Parameters for using an Existing Reporting Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-455">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-455">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-456">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-456">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-457">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-457">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-458">Microsoft SQL Server がローカルサーバーにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-458">Indicates that the Microsoft SQL Server is installed on the local server.</span></span> <span data-ttu-id="a1568-459">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-459">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-460">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-460">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-461">SQL Server がインストールされているリモートコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-461">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="a1568-462">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-462">Takes a string.</span></span> <span data-ttu-id="a1568-463">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-463">E.g.</span></span> <span data-ttu-id="a1568-464">/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-464">/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME=&quot;mycomputer1&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-465">レポート DB_SQLINSTANCE_USE_DEFAULT の EXISTING_ <em></span><span class="sxs-lookup"><span data-stu-id="a1568-465">/EXISTING_ REPORTING <em>DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-466">既定の SQL インスタンスが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-466">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="a1568-467">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-467">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-468">既存の </em> REPORTING_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-468">/EXISTING</em> REPORTING_DB_CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-469">使用するカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-469">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="a1568-470">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-470">Takes a string.</span></span> <span data-ttu-id="a1568-471">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-471">E.g.</span></span> <span data-ttu-id="a1568-472">/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-472">/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE=&quot;MYSQLSERVER&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-473">レポート _DB_NAME の EXISTING_</span><span class="sxs-lookup"><span data-stu-id="a1568-473">/EXISTING_ REPORTING _DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-474">使用する既存のレポートデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-474">Specifies the name of the existing Reporting database that should be used.</span></span> <span data-ttu-id="a1568-475">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-475">Takes a string.</span></span> <span data-ttu-id="a1568-476">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-476">E.g.</span></span> <span data-ttu-id="a1568-477">/EXISTING_REPORTING_DB_NAME = &quot; AppVReporting&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-477">/EXISTING_REPORTING_DB_NAME=&quot;AppVReporting&quot;</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="a1568-478">レポートサーバーデータベースをインストールするためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-478">Parameters for installing Reporting Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-479">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-479">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-480">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-480">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-481">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="a1568-481">/DB_PREDEPLOY_REPORTING</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-482">レポートデータベースがインストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-482">Specifies that the Reporting Database will be installed.</span></span> <span data-ttu-id="a1568-483">このインストールには、DBA 権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="a1568-483">DBA permissions are required for this installation.</span></span> <span data-ttu-id="a1568-484">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-484">No value is expected</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-485">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-485">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-486">使用するカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-486">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="a1568-487">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-487">Takes a string.</span></span> <span data-ttu-id="a1568-488">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-488">E.g.</span></span> <span data-ttu-id="a1568-489">/REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-489">/REPORTING_DB_ CUSTOM_SQLINSTANCE=&quot;MYSQLSERVER&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-490">/REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-490">/REPORTING_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-491">作成する新しいレポートデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-491">Specifies the name of the new Reporting database that should be created.</span></span> <span data-ttu-id="a1568-492">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-492">Takes a string.</span></span> <span data-ttu-id="a1568-493">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-493">E.g.</span></span> <span data-ttu-id="a1568-494">/REPORTING_DB_NAME = &quot; AppVMgmtDB&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-494">/REPORTING_DB_NAME=&quot;AppVMgmtDB&quot;</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-495">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-495">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-496">データベースにアクセスするレポートサーバーがローカルサーバーにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-496">Indicates that the Reporting server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="a1568-497">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-497">Switch parameter so no value is expected.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-498">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-498">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-499">レポートサーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-499">Specifies the machine account of the remote machine that the Reporting server will be installed on.</span></span> <span data-ttu-id="a1568-500">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-500">Takes a string.</span></span> <span data-ttu-id="a1568-501">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-501">E.g.</span></span> <span data-ttu-id="a1568-502">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot; domain\computername&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-502">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot;domain\computername&quot;</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-503">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="a1568-503">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-504">App-v レポートサーバーをインストールするために使用される管理者アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-504">Indicates the Administrator account that will be used to install the App-V Reporting Server.</span></span> <span data-ttu-id="a1568-505">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-505">Takes a string.</span></span> <span data-ttu-id="a1568-506">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-506">E.g.</span></span> <span data-ttu-id="a1568-507">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot; domain\alias&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-507">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot;domain\alias&quot;</span></span></p></td>
    </tr>
    </tbody>
    </table>

### <span data-ttu-id="a1568-508">既存の管理サーバーデータベースを使用するためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-508">Parameters for using an existing Management Server Database</span></span>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a1568-509">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1568-509">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="a1568-510">情報</span><span class="sxs-lookup"><span data-stu-id="a1568-510">Information</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-511">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="a1568-511">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-512">SQL Server がローカルサーバーにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-512">Indicates that the SQL Server is installed on the local server.</span></span> <span data-ttu-id="a1568-513">スイッチパラメーター。値は予期されません。/DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-513">Switch parameter so no value is expected.If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-514">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-514">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-515">SQL Server がインストールされているリモートコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-515">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="a1568-516">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a1568-516">Takes a string.</span></span> <span data-ttu-id="a1568-517">例:</span><span class="sxs-lookup"><span data-stu-id="a1568-517">E.g.</span></span> <span data-ttu-id="a1568-518">/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</span><span class="sxs-lookup"><span data-stu-id="a1568-518">/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME=&quot;mycomputer1&quot;</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-519">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a1568-519">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-520">既定の SQL インスタンスが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a1568-520">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="a1568-521">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="a1568-521">Switch parameter so no value is expected.</span></span> <span data-ttu-id="a1568-522">/DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-522">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a1568-523">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="a1568-523">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-524">使用されるカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-524">Specifies the name of the custom SQL instance that will be used.</span></span> <span data-ttu-id="a1568-525">使用例 <strong> /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a1568-525">Example usage <strong>/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE=”AppVManagement”</strong>.</span></span> <span data-ttu-id="a1568-526">/DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-526">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a1568-527">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="a1568-527">/EXISTING_MANAGEMENT_DB_NAME</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a1568-528">使用する既存の管理データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1568-528">Specifies the name of the existing management database that should be used.</span></span> <span data-ttu-id="a1568-529">使用例: <strong> /EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong></span><span class="sxs-lookup"><span data-stu-id="a1568-529">Example usage: <strong>/EXISTING_MANAGEMENT_DB_NAME=”AppVMgmtDB”</strong>.</span></span> <span data-ttu-id="a1568-530">/DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a1568-530">If /DB_PREDEPLOY_MANAGEMENT is specified, this will be ignored.</span></span></p>
    <p></p>
    <p><strong><span data-ttu-id="a1568-531">App-v の提案をお寄せ </strong> ください。</span><span class="sxs-lookup"><span data-stu-id="a1568-531">Got a suggestion for App-V</strong>?</span></span> <span data-ttu-id="a1568-532">ここで候補を追加または投票 <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)"> </a> してください。</span><span class="sxs-lookup"><span data-stu-id="a1568-532">Add or vote on suggestions <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)">here</a>.</span></span> <strong><span data-ttu-id="a1568-533">App-v issu e をお持ち </strong> ですか?</span><span class="sxs-lookup"><span data-stu-id="a1568-533">Got an App-V issu</strong>e?</span></span> <span data-ttu-id="a1568-534">App-v の <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)"> TechNet フォーラムを使用し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="a1568-534">Use the <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)">App-V TechNet Forum</a>.</span></span></p></td>
</tr>
</tbody>
</table>
  

## <span data-ttu-id="a1568-535">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a1568-535">Related topics</span></span>

[<span data-ttu-id="a1568-536">App-V 5.0 Server の展開</span><span class="sxs-lookup"><span data-stu-id="a1568-536">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

 

 





