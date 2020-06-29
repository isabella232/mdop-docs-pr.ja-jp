---
title: 接続グループの管理
description: 接続グループの管理
author: dansimp
ms.assetid: 1a9c8f26-f421-4b70-b7e2-da8118e8198c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2e57b9dbe56072e6049e8fabef5705c374d022c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813579"
---
# <span data-ttu-id="75501-103">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="75501-103">Managing Connection Groups</span></span>


<span data-ttu-id="75501-104">接続グループによって、パッケージ内のアプリケーションが仮想環境で相互にやり取りできるようになりますが、システムの他の部分から分離することができます。</span><span class="sxs-lookup"><span data-stu-id="75501-104">Connection groups enable the applications within a package to interact with each other in the virtual environment, while remaining isolated from the rest of the system.</span></span> <span data-ttu-id="75501-105">接続グループを使うと、管理者はパッケージを個別に管理できます。また、同じアプリケーションをクライアントコンピューターに複数回追加しなくても済むようになります。</span><span class="sxs-lookup"><span data-stu-id="75501-105">By using connection groups, administrators can manage packages independently and can avoid having to add the same application multiple times to a client computer.</span></span>

<span data-ttu-id="75501-106">**注** 以前のバージョンの App-v 5.0 では、接続グループは動的 Suite コンポジションと呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="75501-106">**Note** In previous versions of App-V 5.0, connection groups were referred to as Dynamic Suite Composition.</span></span>

 

**<span data-ttu-id="75501-107">このトピックの内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75501-107">In this topic:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md)"><span data-ttu-id="75501-108">接続グループの仮想環境について</span><span class="sxs-lookup"><span data-stu-id="75501-108">About the Connection Group Virtual Environment</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75501-109">接続グループの仮想環境について説明します。</span><span class="sxs-lookup"><span data-stu-id="75501-109">Describes the connection group virtual environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="about-the-connection-group-file.md" data-raw-source="[About the Connection Group File](about-the-connection-group-file.md)"><span data-ttu-id="75501-110">接続グループ ファイルについて</span><span class="sxs-lookup"><span data-stu-id="75501-110">About the Connection Group File</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75501-111">接続グループファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75501-111">Describes the connection group file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-create-a-connection-group.md" data-raw-source="[How to Create a Connection Group](how-to-create-a-connection-group.md)"><span data-ttu-id="75501-112">接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="75501-112">How to Create a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75501-113">新しい接続グループを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="75501-113">Explains how to create a new connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)"><span data-ttu-id="75501-114">ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="75501-114">How to Create a Connection Group with User-Published and Globally Published Packages</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75501-115">ユーザーに公開されグローバルに公開されるパッケージの混在を含む、新しい接続グループを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="75501-115">Explains how to create a new connection group that contains a mix of packages that are published to the user and published globally.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-delete-a-connection-group.md" data-raw-source="[How to Delete a Connection Group](how-to-delete-a-connection-group.md)"><span data-ttu-id="75501-116">接続グループを削除する方法</span><span class="sxs-lookup"><span data-stu-id="75501-116">How to Delete a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75501-117">接続グループを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="75501-117">Explains how to delete a connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-publish-a-connection-group.md" data-raw-source="[How to Publish a Connection Group](how-to-publish-a-connection-group.md)"><span data-ttu-id="75501-118">接続グループを公開する方法</span><span class="sxs-lookup"><span data-stu-id="75501-118">How to Publish a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75501-119">接続グループを公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="75501-119">Explains how to publish a connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="75501-120">App-v 5.0 接続グループのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="75501-120">Other resources for App-V 5.0 connection groups</span></span>


-   [<span data-ttu-id="75501-121">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="75501-121">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





