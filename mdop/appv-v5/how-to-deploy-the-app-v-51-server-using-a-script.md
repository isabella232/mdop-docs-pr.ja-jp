---
title: スクリプトを使用して App-V 5.1 Server を展開する方法
description: スクリプトを使用して App-V 5.1 Server を展開する方法
author: dansimp
ms.assetid: 15c33d7b-9b61-4dbc-8674-399bb33e5f7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/20/2020
ms.openlocfilehash: 579ca685f677aaaa4f5ebb6ac8d2969fdcbe2cd2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814130"
---
# <span data-ttu-id="ea000-103">スクリプトを使用して App-V 5.1 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="ea000-103">How to Deploy the App-V 5.1 Server Using a Script</span></span>

<span data-ttu-id="ea000-104">コマンドラインを正常に実行するために**appv\_server\_setup.exe** Server のセットアップを完了するには、複数のパラメーターを指定して結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea000-104">In order to complete the **appv\_server\_setup.exe** Server setup successfully using the command line, you must specify and combine multiple parameters.</span></span>

## <span data-ttu-id="ea000-105">スクリプトを使用して App-v 5.1 サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-105">Install the App-V 5.1 server using a script</span></span>

- <span data-ttu-id="ea000-106">コマンドラインを使用して App-v 5.1 サーバーをインストールする方法については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea000-106">Use the following information about installing the App-V 5.1 server using the command line.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea000-107">次の表の情報は、コマンドラインを使用して次のコマンドを入力することで、コマンドラインを使用してアクセスすることもできます。 **appv\_server\_setup.exe/?**</span><span class="sxs-lookup"><span data-stu-id="ea000-107">The information in the following tables can also be accessed using the command line by typing the following command: **appv\_server\_setup.exe /?**.</span></span>

### <span data-ttu-id="ea000-108">管理サーバーと管理データベースをローカルコンピューターにインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-108">Install the Management server and Management database on a local machine</span></span>

<span data-ttu-id="ea000-109">次のパラメーターは、Microsoft SQL Server の default インスタンスと custom インスタンスの両方で有効です。</span><span class="sxs-lookup"><span data-stu-id="ea000-109">The following parameters are valid with both the default and custom instance of Microsoft SQL Server:</span></span>

- <span data-ttu-id="ea000-110">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-110">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="ea000-111">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-111">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="ea000-112">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-112">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-113">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-113">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-114">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="ea000-114">/DB_PREDEPLOY_MANAGEMENT</span></span>
- <span data-ttu-id="ea000-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-115">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>
- <span data-ttu-id="ea000-116">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-116">/MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="ea000-117">例: Microsoft SQL Server のカスタムインスタンスの使用</span><span class="sxs-lookup"><span data-stu-id="ea000-117">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement"
```

### <span data-ttu-id="ea000-118">ローカルコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-118">Install the Management server using an existing Management database on a local machine</span></span>

<span data-ttu-id="ea000-119">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-119">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-120">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-120">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="ea000-121">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-121">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="ea000-122">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-122">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-123">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-123">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-124">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-124">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="ea000-125">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-125">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-126">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-126">/EXISTING_MANAGEMENT_DB_NAME</span></span>

<span data-ttu-id="ea000-127">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-127">To use a custom instance of Microsoft SQL Server, use the following parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-128">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-128">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="ea000-129">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-129">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="ea000-130">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-130">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-131">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-131">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-132">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-132">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="ea000-133">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-133">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-134">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-134">/EXISTING_MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="ea000-135">例: Microsoft SQL Server のカスタムインスタンスの使用</span><span class="sxs-lookup"><span data-stu-id="ea000-135">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### <span data-ttu-id="ea000-136">リモートコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-136">Install the Management server using an existing Management database on a remote machine</span></span>

<span data-ttu-id="ea000-137">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-137">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-138">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-138">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="ea000-139">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-139">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="ea000-140">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-140">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-141">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-141">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-142">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-142">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="ea000-143">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-143">/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-144">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-144">/EXISTING_MANAGEMENT_DB_NAME</span></span>

<span data-ttu-id="ea000-145">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-145">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-146">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-146">/MANAGEMENT_SERVER</span></span>
- <span data-ttu-id="ea000-147">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-147">/MANAGEMENT_ADMINACCOUNT</span></span>
- <span data-ttu-id="ea000-148">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-148">/MANAGEMENT_WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-149">/MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-149">/MANAGEMENT_WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-150">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-150">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="ea000-151">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-151">/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-152">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-152">/EXISTING_MANAGEMENT_DB_NAME</span></span>

**<span data-ttu-id="ea000-153">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-153">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME="SqlServermachine.domainName" /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### <span data-ttu-id="ea000-154">管理データベースと管理サーバーを同じコンピューターにインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-154">Install the Management database and the Management Server on the same computer</span></span>

<span data-ttu-id="ea000-155">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-155">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-156">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="ea000-156">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="ea000-157">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-157">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-158">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-158">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="ea000-159">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-159">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="ea000-160">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-160">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="ea000-161">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-161">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-162">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="ea000-162">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="ea000-163">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-163">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-164">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-164">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="ea000-165">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-165">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="ea000-166">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-166">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="ea000-167">例: Microsoft SQL Server のカスタムインスタンスの使用</span><span class="sxs-lookup"><span data-stu-id="ea000-167">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_SERVER_MACHINE_USE_LOCAL /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="ea000-168">管理データベースを管理サーバーとは異なるコンピューターにインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-168">Install the Management database on a different computer than the Management server</span></span>

<span data-ttu-id="ea000-169">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-169">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-170">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="ea000-170">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="ea000-171">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-171">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-172">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-172">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="ea000-173">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-173">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="ea000-174">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-174">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="ea000-175">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-175">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-176">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="ea000-176">/DB_PREDEPLOY_MANAGEMENT</span></span>
- *<span data-ttu-id="ea000-177">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-177">/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-178">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-178">/MANAGEMENT_DB_NAME</span></span>
- <span data-ttu-id="ea000-179">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-179">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="ea000-180">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-180">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="ea000-181">例: Microsoft SQL Server のカスタムインスタンスの使用</span><span class="sxs-lookup"><span data-stu-id="ea000-181">Example: Using a custom instance of Microsoft SQL Server</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="ea000-182">発行サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-182">Install the publishing server</span></span>

<span data-ttu-id="ea000-183">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea000-183">To use the default instance of Microsoft SQL Server, use the following parameters:</span></span>

- <span data-ttu-id="ea000-184">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-184">/PUBLISHING_SERVER</span></span>
- <span data-ttu-id="ea000-185">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-185">/PUBLISHING_MGT_SERVER</span></span>
- <span data-ttu-id="ea000-186">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-186">/PUBLISHING_WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-187">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-187">/PUBLISHING_WEBSITE_PORT</span></span>

**<span data-ttu-id="ea000-188">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-188">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /PUBLISHING_SERVER /PUBLISHING_MGT_SERVER="http://ManagementServerName:ManagementPort" /PUBLISHING_WEBSITE_NAME="Microsoft AppV Publishing Service" /PUBLISHING_WEBSITE_PORT="8081"
```

### <span data-ttu-id="ea000-189">ローカルコンピューターにレポートサーバーとレポートデータベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-189">Install the Reporting server and Reporting database on a local machine</span></span>

<span data-ttu-id="ea000-190">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-190">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-191">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-191">/REPORTING _SERVER</span></span>
- <span data-ttu-id="ea000-192">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-192">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-193">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-193">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-194">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-194">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="ea000-195">/レポート _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-195">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-196">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-196">/REPORTING _DB_NAME</span></span>

<span data-ttu-id="ea000-197">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-197">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-198">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-198">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="ea000-199">/レポート _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-199">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="ea000-200">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-200">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-201">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-201">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-202">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-202">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="ea000-203">/レポート _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-203">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-204">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-204">/REPORTING _DB_NAME</span></span>

**<span data-ttu-id="ea000-205">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-205">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="ea000-206">レポートサーバーをインストールし、ローカルコンピューター上に既存のレポートデータベースを使用する</span><span class="sxs-lookup"><span data-stu-id="ea000-206">Install the Reporting server and using an existing Reporting database on a local machine</span></span>

<span data-ttu-id="ea000-207">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-207">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-208">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-208">/REPORTING _SERVER</span></span>
- <span data-ttu-id="ea000-209">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-209">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-210">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-210">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-211">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-211">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="ea000-212">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-212">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-213">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-213">/EXISTING_REPORTING _DB_NAME</span></span>

<span data-ttu-id="ea000-214">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-214">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-215">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-215">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="ea000-216">/レポート _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-216">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="ea000-217">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-217">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-218">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-218">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-219">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-219">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span>
- *<span data-ttu-id="ea000-220">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-220">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-221">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-221">/EXISTING_REPORTING _DB_NAME</span></span>

**<span data-ttu-id="ea000-222">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-222">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="ea000-223">リモートコンピューター上の既存のレポートデータベースを使用して、レポートサーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-223">Install the Reporting server using an existing Reporting database on a remote machine</span></span>

<span data-ttu-id="ea000-224">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-224">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-225">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-225">/REPORTING _SERVER</span></span>
- <span data-ttu-id="ea000-226">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-226">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-227">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-227">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-228">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-228">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="ea000-229">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-229">/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-230">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-230">/EXISTING_REPORTING _DB_NAME</span></span>

<span data-ttu-id="ea000-231">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-231">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-232">/レポート _SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-232">/REPORTING _SERVER</span></span>
- *<span data-ttu-id="ea000-233">/レポート _ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-233">/REPORTING _ADMINACCOUNT</span></span>*
- <span data-ttu-id="ea000-234">/レポート _WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-234">/REPORTING _WEBSITE_NAME</span></span>
- <span data-ttu-id="ea000-235">/レポート _WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-235">/REPORTING _WEBSITE_PORT</span></span>
- <span data-ttu-id="ea000-236">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-236">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span>
- *<span data-ttu-id="ea000-237">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-237">/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-238">/EXISTING_REPORTING _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-238">/EXISTING_REPORTING _DB_NAME</span></span>

**<span data-ttu-id="ea000-239">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-239">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME="SqlServerMachine.DomainName" /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### <span data-ttu-id="ea000-240">レポートサーバーと同じコンピューターにレポートデータベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-240">Install the Reporting database on the same computer as the Reporting server</span></span>

<span data-ttu-id="ea000-241">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-241">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-242">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-242">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="ea000-243">/レポート _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-243">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>*
- <span data-ttu-id="ea000-244">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-244">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="ea000-245">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-245">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="ea000-246">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-246">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="ea000-247">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-247">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-248">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-248">/DB_PREDEPLOY_REPORTING</span></span>
- *<span data-ttu-id="ea000-249">/レポート _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-249">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>*
- <span data-ttu-id="ea000-250">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-250">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="ea000-251">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-251">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span>
- <span data-ttu-id="ea000-252">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-252">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="ea000-253">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-253">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_SERVER_MACHINE_USE_LOCAL /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="ea000-254">レポートデータベースをレポートサーバーとは異なるコンピューターにインストールする</span><span class="sxs-lookup"><span data-stu-id="ea000-254">Install the Reporting database on a different computer than the Reporting server</span></span>

<span data-ttu-id="ea000-255">Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-255">To use the default instance of Microsoft SQL Server, use the following parameters (difference from custom instance in *italic*):</span></span>

- <span data-ttu-id="ea000-256">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-256">/DB_PREDEPLOY_REPORTING</span></span>
- <span data-ttu-id="ea000-257">/レポート _DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-257">/REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span>
- <span data-ttu-id="ea000-258">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-258">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="ea000-259">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-259">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="ea000-260">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-260">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

<span data-ttu-id="ea000-261">Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。</span><span class="sxs-lookup"><span data-stu-id="ea000-261">To use a custom instance of Microsoft SQL Server, use these parameters (difference from default instance in *italic*):</span></span>

- <span data-ttu-id="ea000-262">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-262">/DB_PREDEPLOY_REPORTING</span></span>
- <span data-ttu-id="ea000-263">/レポート _DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-263">/REPORTING _DB_CUSTOM_SQLINSTANCE</span></span>
- <span data-ttu-id="ea000-264">/レポート _DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-264">/REPORTING _DB_NAME</span></span>
- <span data-ttu-id="ea000-265">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-265">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span>
- <span data-ttu-id="ea000-266">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-266">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span>

**<span data-ttu-id="ea000-267">例: Microsoft SQL Server のカスタムインスタンスの使用:</span><span class="sxs-lookup"><span data-stu-id="ea000-267">Example: Using a custom instance of Microsoft SQL Server:</span></span>**

```dos
 appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### <span data-ttu-id="ea000-268">パラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="ea000-268">Parameter Definitions</span></span>

#### <span data-ttu-id="ea000-269">一般的なパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-269">General Parameters</span></span>

| <span data-ttu-id="ea000-270">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-270">Parameter</span></span> | <span data-ttu-id="ea000-271">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-271">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-272">/QUIET</span><span class="sxs-lookup"><span data-stu-id="ea000-272">/QUIET</span></span> | <span data-ttu-id="ea000-273">サイレントインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-273">Specifies silent install.</span></span> |
| <span data-ttu-id="ea000-274">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="ea000-274">/UNINSTALL</span></span> | <span data-ttu-id="ea000-275">アンインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-275">Specifies an uninstall.</span></span> |
| <span data-ttu-id="ea000-276">/レイアウト</span><span class="sxs-lookup"><span data-stu-id="ea000-276">/LAYOUT</span></span> | <span data-ttu-id="ea000-277">レイアウトアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-277">Specifies layout action.</span></span> <span data-ttu-id="ea000-278">これにより、実際には製品をインストールせずに、MSIs ファイルとスクリプトファイルがフォルダーに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-278">This extracts the MSIs and script files to a folder without actually installing the product.</span></span> <span data-ttu-id="ea000-279">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-279">No value is expected.</span></span> |
| <span data-ttu-id="ea000-280">/Layoutdir</span><span class="sxs-lookup"><span data-stu-id="ea000-280">/LAYOUTDIR</span></span> | <span data-ttu-id="ea000-281">レイアウトディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-281">Specifies the layout directory.</span></span> <span data-ttu-id="ea000-282">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-282">Takes a string.</span></span> <span data-ttu-id="ea000-283">使用例: **/layoutdir = "C:\\Application Virtualization Server"**</span><span class="sxs-lookup"><span data-stu-id="ea000-283">Example usage: **/LAYOUTDIR="C:\\Application Virtualization Server"**</span></span> |
| <span data-ttu-id="ea000-284">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="ea000-284">/INSTALLDIR</span></span> | <span data-ttu-id="ea000-285">インストールディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-285">Specifies the installation directory.</span></span> <span data-ttu-id="ea000-286">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-286">Takes a string.</span></span> <span data-ttu-id="ea000-287">使用例: **/INSTALLDIR = "c/ファイル \\ アプリケーション Virtualization\\Server"**</span><span class="sxs-lookup"><span data-stu-id="ea000-287">Example usage: **/INSTALLDIR="C:\\Program Files\\Application Virtualization\\Server"**</span></span> |
| <span data-ttu-id="ea000-288">/Muoptin</span><span class="sxs-lookup"><span data-stu-id="ea000-288">/MUOPTIN</span></span> | <span data-ttu-id="ea000-289">Microsoft Update を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ea000-289">Enables Microsoft Update.</span></span> <span data-ttu-id="ea000-290">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-290">No value is expected.</span></span> |
| <span data-ttu-id="ea000-291">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="ea000-291">/ACCEPTEULA</span></span> | <span data-ttu-id="ea000-292">ライセンス契約を承諾します。</span><span class="sxs-lookup"><span data-stu-id="ea000-292">Accepts the license agreement.</span></span> <span data-ttu-id="ea000-293">これは、無人インストールの場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="ea000-293">This is required for an unattended installation.</span></span> <span data-ttu-id="ea000-294">使用例: **/ACCEPTEULA**または **/ACCEPTEULA = 1**</span><span class="sxs-lookup"><span data-stu-id="ea000-294">Example usage: **/ACCEPTEULA** or **/ACCEPTEULA=1**</span></span> |

#### <span data-ttu-id="ea000-295">管理サーバーのインストールパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-295">Management Server Installation Parameters</span></span>

|<span data-ttu-id="ea000-296">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-296">Parameter</span></span> |<span data-ttu-id="ea000-297">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-297">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-298">/MANAGEMENT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-298">/MANAGEMENT_SERVER</span></span> | <span data-ttu-id="ea000-299">管理サーバーをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-299">Specifies that the management server will be installed.</span></span> <span data-ttu-id="ea000-300">値は期待されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-300">No value is expected</span></span> |
| <span data-ttu-id="ea000-301">/MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-301">/MANAGEMENT_ADMINACCOUNT</span></span> | <span data-ttu-id="ea000-302">管理サーバーへの管理者アクセスが許可されるアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-302">Specifies the account that will be allowed Administrator access to the management server.</span></span> <span data-ttu-id="ea000-303">これは、ユーザーアカウントまたはグループのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="ea000-303">This can be a user account or a group.</span></span> <span data-ttu-id="ea000-304">使用例: **/MANAGEMENT_ADMINACCOUNT = "mydomain\\admin"**</span><span class="sxs-lookup"><span data-stu-id="ea000-304">Example usage: **/MANAGEMENT_ADMINACCOUNT="mydomain\\admin"**.</span></span> <span data-ttu-id="ea000-305">**/MANAGEMENT_SERVER**が指定されていない場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-305">If **/MANAGEMENT_SERVER** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="ea000-306">/MANAGEMENT_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-306">/MANAGEMENT_WEBSITE_NAME</span></span> | <span data-ttu-id="ea000-307">管理サービス用に作成される web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-307">Specifies name of the website that will be created for the management service.</span></span> <span data-ttu-id="ea000-308">使用例: **/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V MANAGEMENT Service"**</span><span class="sxs-lookup"><span data-stu-id="ea000-308">Example usage: **/MANAGEMENT_WEBSITE_NAME="Microsoft App-V Management Service"**</span></span> |
| <span data-ttu-id="ea000-309">MANAGEMENT_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-309">MANAGEMENT_WEBSITE_PORT</span></span> | <span data-ttu-id="ea000-310">管理サービスが使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-310">Specifies the port number that will be used by the management service will use.</span></span> <span data-ttu-id="ea000-311">使用例: **/MANAGEMENT_WEBSITE_PORT = 82**</span><span class="sxs-lookup"><span data-stu-id="ea000-311">Example usage: **/MANAGEMENT_WEBSITE_PORT=82**</span></span> |

#### <span data-ttu-id="ea000-312">管理サーバーデータベースのパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-312">Parameters for the Management Server Database</span></span>

| <span data-ttu-id="ea000-313">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-313">Parameter</span></span> | <span data-ttu-id="ea000-314">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-314">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-315">/DB_PREDEPLOY_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="ea000-315">/DB_PREDEPLOY_MANAGEMENT</span></span> | <span data-ttu-id="ea000-316">管理データベースをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-316">Specifies that the management database will be installed.</span></span> <span data-ttu-id="ea000-317">このインストールを完了するには、十分なデータベース権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea000-317">You must have sufficient database permissions to complete this installation.</span></span> <span data-ttu-id="ea000-318">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-318">No value is expected.</span></span> |
| <span data-ttu-id="ea000-319">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-319">/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="ea000-320">既定の SQL インスタンスを使用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-320">Indicates that the default SQL instance should be used.</span></span> <span data-ttu-id="ea000-321">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-321">No value is expected.</span></span> |
| <span data-ttu-id="ea000-322">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-322">/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="ea000-323">新しいデータベースの作成に使用するカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-323">Specifies the name of the custom SQL instance that should be used to create a new database.</span></span> <span data-ttu-id="ea000-324">使用例: **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**。</span><span class="sxs-lookup"><span data-stu-id="ea000-324">Example usage: **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**.</span></span> <span data-ttu-id="ea000-325">**/DB_PREDEPLOY_MANAGEMENT**が指定されていない場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-325">If **/DB_PREDEPLOY_MANAGEMENT** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="ea000-326">/MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-326">/MANAGEMENT_DB_NAME</span></span> | <span data-ttu-id="ea000-327">作成する新しい管理データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-327">Specifies the name of the new management database that should be created.</span></span> <span data-ttu-id="ea000-328">使用例: **/MANAGEMENT_DB_NAME = "AppVMgmtDB"**</span><span class="sxs-lookup"><span data-stu-id="ea000-328">Example usage: **/MANAGEMENT_DB_NAME="AppVMgmtDB"**.</span></span> <span data-ttu-id="ea000-329">**/DB_PREDEPLOY_MANAGEMENT**が指定されていない場合は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-329">If **/DB_PREDEPLOY_MANAGEMENT** is not specified, this will be ignored.</span></span> |
| <span data-ttu-id="ea000-330">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-330">/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span> | <span data-ttu-id="ea000-331">データベースにアクセスする管理サーバーがローカルサーバーにインストールされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-331">Indicates if the management server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="ea000-332">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-332">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="ea000-333">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-333">/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span> | <span data-ttu-id="ea000-334">管理サーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-334">Specifies the machine account of the remote machine that the management server will be installed on.</span></span> <span data-ttu-id="ea000-335">使用例: **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\\computername ドメイン \"**</span><span class="sxs-lookup"><span data-stu-id="ea000-335">Example usage: **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="domain\\computername"**</span></span> |
| <span data-ttu-id="ea000-336">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-336">/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span> | <span data-ttu-id="ea000-337">管理サーバーをインストールするために使用される管理者アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-337">Indicates the Administrator account that will be used to install the management server.</span></span> <span data-ttu-id="ea000-338">使用例: **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"**</span><span class="sxs-lookup"><span data-stu-id="ea000-338">Example usage: **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT ="domain\\alias"**</span></span> |

#### <span data-ttu-id="ea000-339">発行サーバーをインストールするためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-339">Parameters for Installing Publishing Server</span></span>

| <span data-ttu-id="ea000-340">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-340">Parameter</span></span> | <span data-ttu-id="ea000-341">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-341">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-342">/PUBLISHING_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-342">/PUBLISHING_SERVER</span></span> | <span data-ttu-id="ea000-343">発行サーバーをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-343">Specifies that the Publishing Server will be installed.</span></span> <span data-ttu-id="ea000-344">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-344">No value is expected.</span></span> |
| <span data-ttu-id="ea000-345">/PUBLISHING_MGT_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-345">/PUBLISHING_MGT_SERVER</span></span> | <span data-ttu-id="ea000-346">発行サーバーが接続する管理サービスの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-346">Specifies the URL to Management Service the Publishing server will connect to.</span></span> <span data-ttu-id="ea000-347">使用例: **http:// &lt; management server name &gt; : &lt; 管理サーバーのポート &gt; 番号**。</span><span class="sxs-lookup"><span data-stu-id="ea000-347">Example usage: **http://&lt;management server name&gt;:&lt;Management server port number&gt;**.</span></span> <span data-ttu-id="ea000-348">**/PUBLISHING_SERVER**が使用されていない場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-348">If **/PUBLISHING_SERVER** is not used, this parameter will be ignored.</span></span> |
| <span data-ttu-id="ea000-349">/PUBLISHING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-349">/PUBLISHING_WEBSITE_NAME</span></span> | <span data-ttu-id="ea000-350">発行サービス用に作成される web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-350">Specifies name of the website that will be created for the publishing service.</span></span> <span data-ttu-id="ea000-351">使用例: **/PUBLISHING_WEBSITE_NAME = "Microsoft App-V PUBLISHING Service"**</span><span class="sxs-lookup"><span data-stu-id="ea000-351">Example usage: **/PUBLISHING_WEBSITE_NAME="Microsoft App-V Publishing Service"**</span></span> |
| <span data-ttu-id="ea000-352">/PUBLISHING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-352">/PUBLISHING_WEBSITE_PORT</span></span> | <span data-ttu-id="ea000-353">発行サービスによって使用されるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-353">Specifies the port number used by the publishing service.</span></span> <span data-ttu-id="ea000-354">使用例: **/PUBLISHING_WEBSITE_PORT = 83**</span><span class="sxs-lookup"><span data-stu-id="ea000-354">Example usage: **/PUBLISHING_WEBSITE_PORT=83**</span></span> |

#### <span data-ttu-id="ea000-355">レポートサーバーのパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-355">Parameters for Reporting Server</span></span>

| <span data-ttu-id="ea000-356">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-356">Parameter</span></span> | <span data-ttu-id="ea000-357">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-357">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-358">/REPORTING_SERVER</span><span class="sxs-lookup"><span data-stu-id="ea000-358">/REPORTING_SERVER</span></span> | <span data-ttu-id="ea000-359">レポートサーバーをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-359">Specifies that the Reporting Server will be installed.</span></span> <span data-ttu-id="ea000-360">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-360">No value is expected.</span></span> |
| <span data-ttu-id="ea000-361">/REPORTING_WEBSITE_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-361">/REPORTING_WEBSITE_NAME</span></span> | <span data-ttu-id="ea000-362">レポートサービス用に作成される web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-362">Specifies name of the website that will be created for the Reporting Service.</span></span> <span data-ttu-id="ea000-363">使用例: **/REPORTING_WEBSITE_NAME = "Microsoft App-V ReportingService"**</span><span class="sxs-lookup"><span data-stu-id="ea000-363">Example usage: **/REPORTING_WEBSITE_NAME="Microsoft App-V ReportingService"**</span></span> |
| <span data-ttu-id="ea000-364">/REPORTING_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="ea000-364">/REPORTING_WEBSITE_PORT</span></span> | <span data-ttu-id="ea000-365">レポートサービスが使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-365">Specifies the port number that the Reporting Service will use.</span></span> <span data-ttu-id="ea000-366">使用例: **/REPORTING_WEBSITE_PORT = 82**</span><span class="sxs-lookup"><span data-stu-id="ea000-366">Example usage: **/REPORTING_WEBSITE_PORT=82**</span></span> |

#### <span data-ttu-id="ea000-367">既存のレポートサーバーデータベースを使用するためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-367">Parameters for using an Existing Reporting Server Database</span></span>

| <span data-ttu-id="ea000-368">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-368">Parameter</span></span> | <span data-ttu-id="ea000-369">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-369">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-370">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-370">/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</span></span> | <span data-ttu-id="ea000-371">Microsoft SQL Server がローカルサーバーにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-371">Indicates that the Microsoft SQL Server is installed on the local server.</span></span> <span data-ttu-id="ea000-372">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-372">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="ea000-373">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-373">/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</span></span> | <span data-ttu-id="ea000-374">SQL Server がインストールされているリモートコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-374">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="ea000-375">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-375">Takes a string.</span></span> <span data-ttu-id="ea000-376">使用例: **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"**</span><span class="sxs-lookup"><span data-stu-id="ea000-376">Example usage: **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME="mycomputer1"**</span></span> |
| <span data-ttu-id="ea000-377">レポート _DB_SQLINSTANCE_USE_DEFAULT の EXISTING_</span><span class="sxs-lookup"><span data-stu-id="ea000-377">/EXISTING_ REPORTING _DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="ea000-378">既定の SQL インスタンスが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-378">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="ea000-379">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-379">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="ea000-380">/EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-380">/EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="ea000-381">使用するカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-381">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="ea000-382">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-382">Takes a string.</span></span> <span data-ttu-id="ea000-383">使用例: **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**</span><span class="sxs-lookup"><span data-stu-id="ea000-383">Example usage: **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**</span></span> |
| <span data-ttu-id="ea000-384">レポート _DB_NAME の EXISTING_</span><span class="sxs-lookup"><span data-stu-id="ea000-384">/EXISTING_ REPORTING _DB_NAME</span></span> | <span data-ttu-id="ea000-385">使用する既存のレポートデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-385">Specifies the name of the existing Reporting database that should be used.</span></span> <span data-ttu-id="ea000-386">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-386">Takes a string.</span></span> <span data-ttu-id="ea000-387">使用例: **/EXISTING_REPORTING_DB_NAME = "AppVReporting"**</span><span class="sxs-lookup"><span data-stu-id="ea000-387">Example usage: **/EXISTING_REPORTING_DB_NAME="AppVReporting"**</span></span> |

#### <span data-ttu-id="ea000-388">レポートサーバーデータベースをインストールするためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-388">Parameters for installing Reporting Server Database</span></span>

| <span data-ttu-id="ea000-389">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-389">Parameter</span></span> | <span data-ttu-id="ea000-390">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-390">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-391">/DB_PREDEPLOY_REPORTING</span><span class="sxs-lookup"><span data-stu-id="ea000-391">/DB_PREDEPLOY_REPORTING</span></span> | <span data-ttu-id="ea000-392">レポートデータベースがインストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-392">Specifies that the Reporting Database will be installed.</span></span> <span data-ttu-id="ea000-393">このインストールには、DBA 権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea000-393">DBA permissions are required for this installation.</span></span> <span data-ttu-id="ea000-394">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-394">No value is expected.</span></span> |
| <span data-ttu-id="ea000-395">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-395">/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="ea000-396">使用するカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-396">Specifies the name of the custom SQL instance that should be used.</span></span> <span data-ttu-id="ea000-397">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-397">Takes a string.</span></span> <span data-ttu-id="ea000-398">使用例: **/REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**</span><span class="sxs-lookup"><span data-stu-id="ea000-398">Example usage: **/REPORTING_DB_ CUSTOM_SQLINSTANCE="MYSQLSERVER"**</span></span> |
| <span data-ttu-id="ea000-399">/REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-399">/REPORTING_DB_NAME</span></span> | <span data-ttu-id="ea000-400">作成する新しいレポートデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-400">Specifies the name of the new Reporting database that should be created.</span></span> <span data-ttu-id="ea000-401">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-401">Takes a string.</span></span> <span data-ttu-id="ea000-402">使用例: **/REPORTING_DB_NAME = "AppVMgmtDB"**</span><span class="sxs-lookup"><span data-stu-id="ea000-402">Example usage: **/REPORTING_DB_NAME="AppVMgmtDB"**</span></span> |
| <span data-ttu-id="ea000-403">/REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-403">/REPORTING_SERVER_MACHINE_USE_LOCAL</span></span> | <span data-ttu-id="ea000-404">データベースにアクセスするレポートサーバーがローカルサーバーにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-404">Indicates that the Reporting server that will be accessing the database is installed on the local server.</span></span> <span data-ttu-id="ea000-405">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-405">Switch parameter so no value is expected.</span></span> |
| <span data-ttu-id="ea000-406">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-406">/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span> | <span data-ttu-id="ea000-407">レポートサーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-407">Specifies the machine account of the remote machine that the Reporting server will be installed on.</span></span> <span data-ttu-id="ea000-408">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-408">Takes a string.</span></span> <span data-ttu-id="ea000-409">使用例: **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"**</span><span class="sxs-lookup"><span data-stu-id="ea000-409">Example usage: **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="domain\computername"**</span></span> |
| <span data-ttu-id="ea000-410">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="ea000-410">/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span> | <span data-ttu-id="ea000-411">App-v レポートサーバーをインストールするために使用される管理者アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-411">Indicates the Administrator account that will be used to install the App-V Reporting Server.</span></span> <span data-ttu-id="ea000-412">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-412">Takes a string.</span></span> <span data-ttu-id="ea000-413">使用例: **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"**</span><span class="sxs-lookup"><span data-stu-id="ea000-413">Example usage: **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="domain\\alias"**</span></span> |

#### <span data-ttu-id="ea000-414">既存の管理サーバーデータベースを使用するためのパラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-414">Parameters for using an existing Management Server Database</span></span>

| <span data-ttu-id="ea000-415">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea000-415">Parameter</span></span> | <span data-ttu-id="ea000-416">情報</span><span class="sxs-lookup"><span data-stu-id="ea000-416">Information</span></span> |
|--|--|
| <span data-ttu-id="ea000-417">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="ea000-417">/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</span></span> | <span data-ttu-id="ea000-418">SQL Server がローカルサーバーにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-418">Indicates that the SQL Server is installed on the local server.</span></span> <span data-ttu-id="ea000-419">スイッチパラメーター。値は予期されません。**/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-419">Switch parameter so no value is expected.If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="ea000-420">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-420">/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</span></span> | <span data-ttu-id="ea000-421">SQL Server がインストールされているリモートコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-421">Specifies the name of the remote computer that SQL Server is installed on.</span></span> <span data-ttu-id="ea000-422">文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea000-422">Takes a string.</span></span> <span data-ttu-id="ea000-423">使用例: **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"**</span><span class="sxs-lookup"><span data-stu-id="ea000-423">Example usage: **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME="mycomputer1"**</span></span> |
| <span data-ttu-id="ea000-424">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ea000-424">/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</span></span> | <span data-ttu-id="ea000-425">既定の SQL インスタンスが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="ea000-425">Indicates that the default SQL instance is to be used.</span></span> <span data-ttu-id="ea000-426">スイッチパラメーター。値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="ea000-426">Switch parameter so no value is expected.</span></span> <span data-ttu-id="ea000-427">**/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-427">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="ea000-428">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="ea000-428">/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</span></span> | <span data-ttu-id="ea000-429">使用されるカスタム SQL インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-429">Specifies the name of the custom SQL instance that will be used.</span></span> <span data-ttu-id="ea000-430">使用例 **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement"**。</span><span class="sxs-lookup"><span data-stu-id="ea000-430">Example usage **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE="AppVManagement"**.</span></span> <span data-ttu-id="ea000-431">**/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-431">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |
| <span data-ttu-id="ea000-432">/EXISTING_MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="ea000-432">/EXISTING_MANAGEMENT_DB_NAME</span></span> | <span data-ttu-id="ea000-433">使用する既存の管理データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea000-433">Specifies the name of the existing management database that should be used.</span></span> <span data-ttu-id="ea000-434">使用例: **/EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB"**</span><span class="sxs-lookup"><span data-stu-id="ea000-434">Example usage: **/EXISTING_MANAGEMENT_DB_NAME="AppVMgmtDB"**.</span></span> <span data-ttu-id="ea000-435">**/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ea000-435">If **/DB_PREDEPLOY_MANAGEMENT** is specified, this will be ignored.</span></span> |

<span data-ttu-id="ea000-436">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="ea000-436">Got an App-V issue?</span></span> <span data-ttu-id="ea000-437">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea000-437">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ea000-438">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ea000-438">Related topics</span></span>

[<span data-ttu-id="ea000-439">App-V 5.1 Server の展開</span><span class="sxs-lookup"><span data-stu-id="ea000-439">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)
