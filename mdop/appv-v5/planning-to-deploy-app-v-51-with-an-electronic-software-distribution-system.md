---
title: 電子ソフトウェア配布システムを使った App-V 5.1 の展開計画
description: 電子ソフトウェア配布システムを使った App-V 5.1 の展開計画
author: dansimp
ms.assetid: c26602c2-5e8d-44e6-90df-adacc593607e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fde3f0ea4f1dec72b97143b4b27dd0b32a503b15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813402"
---
# <span data-ttu-id="11c6f-103">電子ソフトウェア配布システムを使った App-V 5.1 の展開計画</span><span class="sxs-lookup"><span data-stu-id="11c6f-103">Planning to Deploy App-V 5.1 with an Electronic Software Distribution System</span></span>


<span data-ttu-id="11c6f-104">App-v パッケージを展開するために電子ソフトウェア配布システムを使用している場合は、次の計画の考慮事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11c6f-104">If you are using an electronic software distribution system to deploy App-V packages, review the following planning considerations.</span></span> <span data-ttu-id="11c6f-105">System Center Configuration Manager を使用した App-v の展開の詳細については、「[構成マネージャーでのアプリケーション管理の概要](https://go.microsoft.com/fwlink/?LinkId=281816)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c6f-105">For information about using System Center Configuration Manager to deploy App-V, see [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816).</span></span>

<span data-ttu-id="11c6f-106">ESD を使って App-v パッケージを展開するときに適用される、次のコンポーネントとアーキテクチャの要件のオプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="11c6f-106">Review the following component and architecture requirements options that apply when you use an ESD to deploy App-V packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="11c6f-107">展開の要件またはオプション</span><span class="sxs-lookup"><span data-stu-id="11c6f-107">Deployment requirement or option</span></span></th>
<th align="left"><span data-ttu-id="11c6f-108">説明</span><span class="sxs-lookup"><span data-stu-id="11c6f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11c6f-109">App-v Management server、管理データベース、およびパブリッシングサーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="11c6f-109">The App-V Management server, Management database, and Publishing server are not required.</span></span></p></td>
<td align="left"><p><span data-ttu-id="11c6f-110">これらの関数は、実装された ESD ソリューションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="11c6f-110">These functions are handled by the implemented ESD solution.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11c6f-111">アプリ V レポートサーバーとレポートデータベースを ESD と並行して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="11c6f-111">You can deploy the App-V Reporting server and Reporting database side by side with the ESD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="11c6f-112">サイドバイサイド展開では、データを収集し、レポートを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="11c6f-112">The side-by-side deployment lets you to collect data and generate reports.</span></span></p>
<p><span data-ttu-id="11c6f-113">レポート情報を送信するように App-v クライアントを有効にしていて、App-v レポートサーバーを使っていない場合、レポートデータは関連付けられた .xml ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="11c6f-113">If you enable the App-V client to send report information, and you are not using the App-V Reporting server, the reporting data is stored in associated .xml files.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="11c6f-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="11c6f-114">Related topics</span></span>


[<span data-ttu-id="11c6f-115">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="11c6f-115">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





