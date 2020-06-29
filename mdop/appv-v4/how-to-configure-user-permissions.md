---
title: ユーザーのアクセス許可を構成する方法
description: ユーザーのアクセス許可を構成する方法
author: dansimp
ms.assetid: 54e69f46-b028-4ad1-9b80-f06ef5c8f559
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3c2581a9f9dddcbc63682d356c777a24222dd62f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817734"
---
# <span data-ttu-id="0e748-103">ユーザーのアクセス許可を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0e748-103">How to Configure User Permissions</span></span>


<span data-ttu-id="0e748-104">権限を持っていないユーザーに対して、管理者権限を持たない操作を有効または無効にするには、 **Permissions**レジストリキー (HKEY \ _LOCAL \ _MACHINE ¥) でキー値を編集します。</span><span class="sxs-lookup"><span data-stu-id="0e748-104">You can enable and disable some actions for users who do not have administrative rights by editing the key values under the **Permissions** registry key (HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions).</span></span> <span data-ttu-id="0e748-105">このキーは主に、管理者権限を持つユーザーがこれらのいずれかのキー値を編集できるようにすることで、特別なセキュリティを提供するのではなく、ユーザーによるミスを防ぐために設計されています。</span><span class="sxs-lookup"><span data-stu-id="0e748-105">This key is primarily designed to help prevent users from making mistakes rather than to provide any special security, because users with administrative rights can edit any of these key values.</span></span> <span data-ttu-id="0e748-106">次の手順は、キーの値を変更する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="0e748-106">The following procedures are examples of how to change the key values.</span></span> <span data-ttu-id="0e748-107">Application Virtualization (App-v) クライアントのレジストリキーと値の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=121528> 。</span><span class="sxs-lookup"><span data-stu-id="0e748-107">For more information about the Application Virtualization (App-V) Client registry keys and values, see <https://go.microsoft.com/fwlink/?LinkId=121528>.</span></span>

**<span data-ttu-id="0e748-108">ユーザー権限を変更するには</span><span class="sxs-lookup"><span data-stu-id="0e748-108">To change user permissions</span></span>**

1.  <span data-ttu-id="0e748-109">ユーザーがオフラインモードでクライアントを実行することを選択できるようにするには、次のキー値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e748-109">To enable the users to choose to run the client in offline mode, set the following key value to 1:</span></span>

    <span data-ttu-id="0e748-110">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode</span><span class="sxs-lookup"><span data-stu-id="0e748-110">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode</span></span>

2.  <span data-ttu-id="0e748-111">ユーザーがユーザーインターフェイスを使用してすべてのアプリケーションを表示できるようにするには、次のキー値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e748-111">To enable the users to view all applications through the user interface, set the following key value to 1.</span></span> <span data-ttu-id="0e748-112">この値を 0 (ゼロ) に設定すると、ユーザーが利用できるアプリケーションのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0e748-112">Setting the value to 0 (zero) allows the users to see only the applications that are available to them.</span></span>

    <span data-ttu-id="0e748-113">HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \ 一般法人向け \ すべてのアプリについて (英語)</span><span class="sxs-lookup"><span data-stu-id="0e748-113">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ViewAllApplications</span></span>

## <span data-ttu-id="0e748-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0e748-114">Related topics</span></span>


[<span data-ttu-id="0e748-115">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0e748-115">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

[<span data-ttu-id="0e748-116">Application Virtualization Client のユーザー アクセス許可</span><span class="sxs-lookup"><span data-stu-id="0e748-116">User Access Permissions in Application Virtualization Client</span></span>](user-access-permissions-in-application-virtualization-client.md)

 

 





