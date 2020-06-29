---
title: ショートカットとファイルの種類の関連付け動作を構成する方法
description: ショートカットとファイルの種類の関連付け動作を構成する方法
author: dansimp
ms.assetid: d6fd1728-4de6-4066-b36b-d4837d593d40
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84e3e0cdd43cfc26cf56f1b5ac72560b1c702ae6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817914"
---
# <span data-ttu-id="5fe82-103">ショートカットとファイルの種類の関連付け動作を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5fe82-103">How to Configure Shortcut and File Type Association Behavior</span></span>


<span data-ttu-id="5fe82-104">ショートカットとファイルの種類の関連付け (FTA) 発行ポリシーは、発行用の XML ファイルによって定義および制御されます。このファイルは発行サーバーによって公開されます。</span><span class="sxs-lookup"><span data-stu-id="5fe82-104">Shortcut and File Type Association (FTA) publishing policy is defined and controlled by the publishing XML file, which is sent to clients by a publishing server during a publishing refresh operation.</span></span> <span data-ttu-id="5fe82-105">クライアントはこの情報を受け取ると、アイコンや FTAs などのアプリケーションに関する新たに公開されたデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fe82-105">When the client receives this information, it adds any newly published data about applications such as the icons and FTAs.</span></span> <span data-ttu-id="5fe82-106">次に、古い発行データを削除します。</span><span class="sxs-lookup"><span data-stu-id="5fe82-106">Then, it removes any outdated publishing data.</span></span>

<span data-ttu-id="5fe82-107">App-v バージョン4.6 では、管理者がこの動作を制御できるように、2つのレジストリキー値が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fe82-107">In App-V version 4.6, two registry key values have been defined to enable administrators to control this behavior.</span></span> <span data-ttu-id="5fe82-108">既定では、クライアントコンソールを使用してローカルで作成されたショートカットは保持されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5fe82-108">By default, shortcuts that are created locally by using the client console are now retained.</span></span>

## <span data-ttu-id="5fe82-109">ショートカットと FTA の動作を変更する方法</span><span class="sxs-lookup"><span data-stu-id="5fe82-109">How to Change Shortcut and FTA Behavior</span></span>


<span data-ttu-id="5fe82-110">クライアント構成レジストリキー "FileTypePolicy" と "ShortcutPolicy" には、2つの新しい DWORD レジストリ値が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5fe82-110">Two new DWORD registry values have been defined for the client Configuration registry key, “FileTypePolicy” and “ShortcutPolicy”.</span></span> <span data-ttu-id="5fe82-111">これらの DWORD レジストリ値は既定では存在しませんが、手動で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5fe82-111">These DWORD registry values are not present by default, but they can be added manually.</span></span> <span data-ttu-id="5fe82-112">構成レジストリキーは、HKEY \ _LOCAL \ _MACHINE ¥¥¥ \ [Wow6432Node\\\] の [\] にあります (\\ 4)。</span><span class="sxs-lookup"><span data-stu-id="5fe82-112">The Configuration registry key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\[Wow6432Node\\\]Microsoft\\SoftGrid\\4.5\\Client\\Configuration.</span></span>

<span data-ttu-id="5fe82-113">次の表では、次の4つのポリシー値が定義されています。これらはどちらのレジストリキー値にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="5fe82-113">There are four policy values defined in the following table and these apply to both registry key values.</span></span> <span data-ttu-id="5fe82-114">次の一覧は、レジストリ設定の数値と、発行更新操作のファイルの種類またはショートカットに適用される動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fe82-114">The following list shows the numeric values for the registry settings, and the behavior applied to file types or shortcuts on a publishing refresh operation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5fe82-115">名前</span><span class="sxs-lookup"><span data-stu-id="5fe82-115">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-116">型</span><span class="sxs-lookup"><span data-stu-id="5fe82-116">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-117">データ (例)</span><span class="sxs-lookup"><span data-stu-id="5fe82-117">Data (Examples)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-118">説明</span><span class="sxs-lookup"><span data-stu-id="5fe82-118">Description</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5fe82-119">FileTypePolicy</span><span class="sxs-lookup"><span data-stu-id="5fe82-119">FileTypePolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-120">DWORD</span><span class="sxs-lookup"><span data-stu-id="5fe82-120">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-121">Default = 0x2 (App-v 4.6)</span><span class="sxs-lookup"><span data-stu-id="5fe82-121">Default=0x2 (App-V 4.6)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-122">(0x0) – "ClientOnly"-同じ公開情報ソースから既存のアイテムを削除し、ローカルに追加されたアイテムのみを残します。</span><span class="sxs-lookup"><span data-stu-id="5fe82-122">(0x0) – “ClientOnly”- remove any existing items from the same publishing information source, and keep only items that are added locally</span></span></p>
<p><span data-ttu-id="5fe82-123">(0x1) – "ServerOnly"-同じ公開情報ソースとローカルに追加されたすべてのアイテムから古いアイテムを削除し、新しいアイテムを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fe82-123">(0x1) – “ServerOnly” - remove any outdated items from the same publishing information source and any items that are added locally, and add the new items</span></span></p>
<p><span data-ttu-id="5fe82-124">(0x2) – "ClientAndServer"-同じ公開情報ソースから古いアイテムを削除し、アイテムをローカルに追加したままにして、新しいアイテムを追加します (App-v 4.6 の場合は既定値になります)。</span><span class="sxs-lookup"><span data-stu-id="5fe82-124">(0x2) – “ClientAndServer”- remove any outdated items from the same publishing information source, keep items added locally, and add the new items (default if not present for App-V 4.6)</span></span></p>
<p><span data-ttu-id="5fe82-125">(0x3) – "NoChange"-ファイルの種類またはショートカットに変更を加えない</span><span class="sxs-lookup"><span data-stu-id="5fe82-125">(0x3) – “NoChange” - make no changes to file types or shortcuts</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5fe82-126">ShortcutPolicy</span><span class="sxs-lookup"><span data-stu-id="5fe82-126">ShortcutPolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-127">DWORD</span><span class="sxs-lookup"><span data-stu-id="5fe82-127">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-128">Default = 0x2</span><span class="sxs-lookup"><span data-stu-id="5fe82-128">Default=0x2</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fe82-129">(0x0) – "ClientOnly"-同じ公開情報ソースから既存のアイテムを削除し、アイテムをローカルに追加したままにします。</span><span class="sxs-lookup"><span data-stu-id="5fe82-129">(0x0) – “ClientOnly”- remove any existing items from the same publishing information source, and keep only items added locally</span></span></p>
<p><span data-ttu-id="5fe82-130">(0x1) – "ServerOnly"-同じ公開情報ソースとローカルに追加されたすべてのアイテムから古いアイテムを削除し、新しいアイテムを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fe82-130">(0x1) – “ServerOnly” - remove any outdated items from the same publishing information source and any items added locally, and add the new items</span></span></p>
<p><span data-ttu-id="5fe82-131">(0x2) – "ClientAndServer"-同じ公開情報ソースから古いアイテムを削除し、アイテムをローカルに追加したままにして、新しいアイテムを追加します (存在しない場合は既定値)。</span><span class="sxs-lookup"><span data-stu-id="5fe82-131">(0x2) – “ClientAndServer”- remove any outdated items from the same publishing information source, keep items added locally, and add the new items (default if not present)</span></span></p>
<p><span data-ttu-id="5fe82-132">(0x3) – "NoChange"-ファイルの種類またはショートカットに変更を加えない</span><span class="sxs-lookup"><span data-stu-id="5fe82-132">(0x3) – “NoChange” - make no changes to file types or shortcuts</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="5fe82-133">**注** テキスト値は、発行 XML ファイルの XML 属性の値を参照します。</span><span class="sxs-lookup"><span data-stu-id="5fe82-133">**Note** The text values refer to the values for the XML attributes in the publishing XML file.</span></span><span data-ttu-id="5fe82-134">カスタム HTTP 発行ソリューションを実装している場合は、これらの値を手動で設定できます。</span><span class="sxs-lookup"><span data-stu-id="5fe82-134"> You can set these values manually if you have implemented a custom HTTP publishing solution.</span></span>

 

 

 





