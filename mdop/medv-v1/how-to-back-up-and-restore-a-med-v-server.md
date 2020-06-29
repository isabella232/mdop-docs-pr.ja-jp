---
title: MED-V サーバーをバックアップおよび復元する方法
description: MED-V サーバーをバックアップおよび復元する方法
author: dansimp
ms.assetid: 8d05e3a4-279b-4ce6-a319-8a09e7a30c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51cfe3727896ed68a1fd67441174a294a1073cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823087"
---
# <span data-ttu-id="a5fc3-103">MED-V サーバーをバックアップおよび復元する方法</span><span class="sxs-lookup"><span data-stu-id="a5fc3-103">How to Back Up and Restore a MED-V Server</span></span>


<span data-ttu-id="a5fc3-104">サーバー上にある XML ファイルをバックアップして、サーバー上のデータが失われた場合に復元することができます。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-104">XML files located on the server can be backed up and then restored in case of loss of data on the server.</span></span>

**<span data-ttu-id="a5fc3-105">MED-V サーバーのバックアップを作成するには</span><span class="sxs-lookup"><span data-stu-id="a5fc3-105">To back up a MED-V server</span></span>**

-   <span data-ttu-id="a5fc3-106">\* &lt; InstallDir &gt; \\Servers\\ConfigurationServer\*にある次のファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-106">Back up the following files, located in *&lt;InstallDir&gt;\\Servers\\ConfigurationServer*:</span></span>

    <span data-ttu-id="a5fc3-107">**注** 構成が既定の設定から変更されている場合は、ファイルが別の場所に保存されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-107">**Note** If the configuration has been changed from the default, the files might be stored in a different location.</span></span>

     

    -   <span data-ttu-id="a5fc3-108">ClientPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="a5fc3-108">ClientPolicy.xml</span></span>

    -   <span data-ttu-id="a5fc3-109">ClientSettings.xml</span><span class="sxs-lookup"><span data-stu-id="a5fc3-109">ClientSettings.xml</span></span>

    -   <span data-ttu-id="a5fc3-110">ConfigurationFiles.xml</span><span class="sxs-lookup"><span data-stu-id="a5fc3-110">ConfigurationFiles.xml</span></span>

    -   <span data-ttu-id="a5fc3-111">OrganizationPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="a5fc3-111">OrganizationPolicy.xml</span></span>

    -   <span data-ttu-id="a5fc3-112">WorkspaceKeys.xml</span><span class="sxs-lookup"><span data-stu-id="a5fc3-112">WorkspaceKeys.xml</span></span>

    <span data-ttu-id="a5fc3-113">**注** ServerSettings.xml ファイルもバックアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-113">**Note** The ServerSettings.xml file can be backed up as well.</span></span> <span data-ttu-id="a5fc3-114">ただし、特定の構成が変更されている場合 (たとえば、元のサーバーでは、MED-V の VM ディレクトリは "*C:\\Vms*" にあり、そのようなディレクトリは新しいサーバーに存在しません)、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-114">However, if a specific configuration has been changed (for example, on the original server, the MED-V VMS directory is located in "*C:\\Vms*" and such a directory does not exist on the new server), it can cause an error.</span></span>

     

**<span data-ttu-id="a5fc3-115">MED-V サーバーを復元するには</span><span class="sxs-lookup"><span data-stu-id="a5fc3-115">To restore a MED-V server</span></span>**

1.  <span data-ttu-id="a5fc3-116">新しい MED-V サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-116">Install a new MED-V server.</span></span>

2.  <span data-ttu-id="a5fc3-117">バックアップファイルを次のディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-117">Copy the backup files to the following directory:</span></span>

    *<span data-ttu-id="a5fc3-118">&lt;InstallDir &gt; \\Servers\\ConfigurationServer</span><span class="sxs-lookup"><span data-stu-id="a5fc3-118">&lt;InstallDir&gt;\\Servers\\ConfigurationServer</span></span>*

3.  <span data-ttu-id="a5fc3-119">MED-V サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5fc3-119">Restart the MED-V service.</span></span>

 

 





