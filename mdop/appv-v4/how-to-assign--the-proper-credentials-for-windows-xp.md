---
title: Windows XP の適切な資格情報を割り当てる方法
description: Windows XP の適切な資格情報を割り当てる方法
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819324"
---
# <span data-ttu-id="8f1f6-103">Windows XP の適切な資格情報を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="8f1f6-103">How to Assign the Proper Credentials for Windows XP</span></span>


<span data-ttu-id="8f1f6-104">次の手順を使用して、適切な WindowsXP の資格情報を持つように App-v デスクトップクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsXP credentials.</span></span>

<span data-ttu-id="8f1f6-105">**注** この手順を完了すると、ドメインに参加していないクライアントは、ドメインに参加しなくても公開更新を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-105">**Note** After finishing this procedure, the non-domain joined client can perform a publishing refresh without being joined to a domain.</span></span>

 

**<span data-ttu-id="8f1f6-106">WindowsXP を実行している App-v クライアントに適切な資格情報を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8f1f6-106">To assign the proper credentials for App-V clients running WindowsXP</span></span>**

1.  <span data-ttu-id="8f1f6-107">WindowsXP を実行している App-v クライアントの管理者権限がある場合は、[**ユーザーアカウント**] コントロールパネル (クラシックコントロールパネル) を開きます。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-107">With administrator privileges on the App-V Client running WindowsXP, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="8f1f6-108">[**詳細設定] タブ**をクリックし、[**パスワードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-108">Click the **Advanced Tab**, and select **Manage Passwords**.</span></span>

3.  <span data-ttu-id="8f1f6-109">[**ユーザー名とパスワードの保存**] 画面で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-109">On the **Stored User Names and Passwords** screen, click **Add**.</span></span>

4.  <span data-ttu-id="8f1f6-110">[**ログオン情報のプロパティ**] 画面で、次のフィールドに app-v インフラストラクチャからの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-110">On the **Logon Information Properties** screen, fill out the following fields with information from the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="8f1f6-111">**サーバー:** 発行サーバーの外部名の名前。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-111">**Server:** Name of publishing server external name.</span></span>

    2.  <span data-ttu-id="8f1f6-112">**ユーザー名:** フォーム Domain\\username. の外部ユーザーのユーザー名</span><span class="sxs-lookup"><span data-stu-id="8f1f6-112">**User name:** User name for external user in the form Domain\\username.</span></span>

    3.  <span data-ttu-id="8f1f6-113">**パスワード:**[**ユーザー名**] フィールドに入力されたユーザーアカウントのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-113">**Password:** Password for the user account entered in the **User name** field.</span></span>

5.  <span data-ttu-id="8f1f6-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-114">Click **OK**.</span></span> <span data-ttu-id="8f1f6-115">資格情報はクライアントに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8f1f6-115">The credentials will be stored on the client.</span></span>

## <span data-ttu-id="8f1f6-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8f1f6-116">Related topics</span></span>


[<span data-ttu-id="8f1f6-117">ドメインに参加しているクライアントとドメインに参加していないクライアント</span><span class="sxs-lookup"><span data-stu-id="8f1f6-117">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="8f1f6-118">Windows Vista の適切な資格情報を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="8f1f6-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





