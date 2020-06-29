---
title: アプリケーションへのアクセスを拒否する方法
description: アプリケーションへのアクセスを拒否する方法
author: dansimp
ms.assetid: 14f5e201-7265-462c-b738-57938dc3fc30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a89669ea8c6323023b585d6d58620cd203fc00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817517"
---
# <span data-ttu-id="6713b-103">アプリケーションへのアクセスを拒否する方法</span><span class="sxs-lookup"><span data-stu-id="6713b-103">How to Deny Access to an Application</span></span>


<span data-ttu-id="6713b-104">アプリケーションの読み込みと使用を行うには、ユーザーがアプリケーションの**アクセス許可**の一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6713b-104">Users must be in an application's **Access Permissions** list to load and use the application.</span></span> <span data-ttu-id="6713b-105">Application Virtualization Server 管理コンソールは、アプリケーションへのユーザーグループアクセスの明示的な拒否をサポートしていませんが、これを実現するには、アプリケーションのプロパティからユーザーグループを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6713b-105">Although the Application Virtualization Server Management Console does not support explicitly denying a user group access to an application, you can remove the user groups from an application’s properties to achieve this.</span></span>

**<span data-ttu-id="6713b-106">アプリケーションへのアクセスを拒否するには</span><span class="sxs-lookup"><span data-stu-id="6713b-106">To deny access to an application</span></span>**

1.  <span data-ttu-id="6713b-107">既存のアプリケーションの場合は、左側のウィンドウで [**アプリケーション**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6713b-107">For an existing application, click the **Applications** node in the left pane.</span></span>

2.  <span data-ttu-id="6713b-108">右側のウィンドウでアプリケーションを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6713b-108">Right-click an application in the right pane, and choose **Properties**.</span></span> <span data-ttu-id="6713b-109">次に、[**アクセス許可**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6713b-109">Then select the **Access Permissions** tab.</span></span>

3.  <span data-ttu-id="6713b-110">ユーザーグループのアクセスを削除するには、ユーザーグループを強調表示し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6713b-110">To remove access for a user group, highlight the user group and click **Remove**.</span></span>

4.  <span data-ttu-id="6713b-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6713b-111">Click **OK**.</span></span>

    <span data-ttu-id="6713b-112">**注** アプリケーションへのアクセスを制御するために、アプリケーションライセンスを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="6713b-112">**Note** To control access to applications, you can also limit the application licenses.</span></span> <span data-ttu-id="6713b-113">Active Directory ドメインサービスで適切なユーザーグループを設定することで、特定のユーザーのセットへのアクセスを許可したり、拒否したりすることが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="6713b-113">Setting up the proper user groups in Active Directory Domain Services provides the easiest way to grant and deny access to specific sets of users.</span></span>

     

## <span data-ttu-id="6713b-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6713b-114">Related topics</span></span>


[<span data-ttu-id="6713b-115">アプリケーションへのアクセスを許可する方法</span><span class="sxs-lookup"><span data-stu-id="6713b-115">How to Grant Access to an Application</span></span>](how-to-grant-access-to-an-application.md)

[<span data-ttu-id="6713b-116">サーバー管理コンソールでアプリケーション ライセンスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="6713b-116">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="6713b-117">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="6713b-117">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





