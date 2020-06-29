---
title: Application Virtualization サーバーのトラブルシューティング情報
description: Application Virtualization サーバーのトラブルシューティング情報
author: dansimp
ms.assetid: e9d43d9b-84f2-4d1b-bb90-a13740151e0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c98ad42a00e20900263d0598822a6381e2df1ef
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815187"
---
# <span data-ttu-id="2a0bd-103">Application Virtualization サーバーのトラブルシューティング情報</span><span class="sxs-lookup"><span data-stu-id="2a0bd-103">Troubleshooting Information for the Application Virtualization Server</span></span>


<span data-ttu-id="2a0bd-104">このトピックには、Application Virtualization (App-v) サーバーのさまざまな問題のトラブルシューティングに使用できる情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-104">This topic includes information that you can use to troubleshoot various issues on the Application Virtualization (App-V) Servers.</span></span>

## <span data-ttu-id="2a0bd-105">サーバーをインストールした後のセットアップログの警告メッセージ25017</span><span class="sxs-lookup"><span data-stu-id="2a0bd-105">Warning Message 25017 in Setup Log After Installing the Server</span></span>


<span data-ttu-id="2a0bd-106">インストール後、サーバーのセットアップログに次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-106">You might find the following message in the server setup log after installation.</span></span>

*<span data-ttu-id="2a0bd-107">警告25017。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-107">Warning 25017.</span></span> <span data-ttu-id="2a0bd-108">インストールプログラムで、サーバーの Active Directory マーカーオブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-108">The installation Program could not create the Active Directory marker object for the server.</span></span> <span data-ttu-id="2a0bd-109">インストールに使用したアカウントに、Active Directory または Active Directory への書き込みに必要な権限がない。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-109">The account used to install did not have the sufficient rights to write to Active Directory or Active Directory was unavailable.</span></span>*

<span data-ttu-id="2a0bd-110">App-v 管理またはストリーミングサーバーのインストーラーは、インストーラーを実行するために使用されたアカウントに適切な権限がある場合、サーバーがインストールされているコンピューターに対応する [Active Directory ドメインサービス (ADDS)] のコンピューターオブジェクトの下に、サービス接続ポイントエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-110">The App-V Management or Streaming Server installer creates a Service Connection Point entry under the Computer object in Active Directory Domain Services (ADDS) that corresponds to the computer on which the server is installed if the account used to run the installer has the appropriate rights.</span></span> <span data-ttu-id="2a0bd-111">このエントリの作成に失敗しても、インストールが失敗することはありません。これは、製品の機能に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-111">Failure to create this entry will not cause the install to fail and this should not otherwise affect the functioning of the product.</span></span> <span data-ttu-id="2a0bd-112">エラーの原因としては、インストールの実行に使用されたユーザーアカウントに、追加の書き込みに必要な権限がないことが考えられます。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-112">The likely cause of any failure is that the user account used to run the install did not have sufficient rights to write to ADDS.</span></span> <span data-ttu-id="2a0bd-113">アプリの追加には、ADDS でのアプリの登録は任意ですが、一元管理ツールを使用して、在庫や管理の目的でアプリ-V サーバーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-113">Although registering the App-V server in ADDS is optional, one benefit of doing so enables centralized management tools to locate the App-V server for inventory and management purposes.</span></span>

## <span data-ttu-id="2a0bd-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2a0bd-114">Related topics</span></span>


[<span data-ttu-id="2a0bd-115">Application Virtualization サーバー</span><span class="sxs-lookup"><span data-stu-id="2a0bd-115">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





