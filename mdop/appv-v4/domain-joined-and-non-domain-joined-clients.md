---
title: ドメインに参加しているクライアントとドメインに参加していないクライアント
description: ドメインに参加しているクライアントとドメインに参加していないクライアント
author: dansimp
ms.assetid: a935dc98-de60-45f3-ab74-2444ce082e88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4385ab3f26bb867dd649fe768e1500c9d015ffa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821634"
---
# <span data-ttu-id="32ce5-103">ドメインに参加しているクライアントとドメインに参加していないクライアント</span><span class="sxs-lookup"><span data-stu-id="32ce5-103">Domain-Joined and Non-Domain-Joined Clients</span></span>


<span data-ttu-id="32ce5-104">クライアントがドメインに参加しているか、ドメイン以外の参加であるかに関係なく、ネットワークへの接続を許可するように App-v デスクトップクライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="32ce5-104">The App-V Desktop Client can be configured to allow connection to a network regardless of whether the client is domain joined or non-domain joined.</span></span>

## <span data-ttu-id="32ce5-105">ドメインに参加しているクライアント</span><span class="sxs-lookup"><span data-stu-id="32ce5-105">Domain-Joined Clients</span></span>


<span data-ttu-id="32ce5-106">ドメインに参加しているが内部ネットワーク以外のクライアントは、VPN 接続を使って App-v インフラストラクチャと通信できます。</span><span class="sxs-lookup"><span data-stu-id="32ce5-106">Clients that are domain joined, but outside the internal network, can communicate with the App-V infrastructure by using a VPN connection.</span></span> <span data-ttu-id="32ce5-107">ユーザーが内部ネットワークを離れても、App-v インフラストラクチャで通信できるようにする場合、環境には非常に小さな設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="32ce5-107">When you want to provide users the ability to leave the internal network but still communicate in an App-V infrastructure, your environment requires very little setup.</span></span> <span data-ttu-id="32ce5-108">ユーザーは既にドメインに含まれているため、キャッシュされた資格情報がクライアントでサポートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ce5-108">Because the users are already part of the domain, you simply need to ensure that Cached Credentials are supported on the client.</span></span> <span data-ttu-id="32ce5-109">これは既定の構成であり、この設定の変更はグループポリシーから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="32ce5-109">This is the default configuration, and any changes to this setting can be accomplished from Group Policies.</span></span>

<span data-ttu-id="32ce5-110">App-v セキュリティのベストプラクティスガイドで説明したように、ユーザーはユーザーチケットを App-v インフラストラクチャに送信して認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="32ce5-110">As mentioned in the App-V Security Best Practices Guide, the user will attempt to send their user ticket to the App-V infrastructure for authentication.</span></span> <span data-ttu-id="32ce5-111">チケットの有効期限が切れている場合は、NTLM と、コンピューター上のキャッシュされた資格情報の使用に戻ります。</span><span class="sxs-lookup"><span data-stu-id="32ce5-111">If the ticket is expired, it will revert to using NTLM and the cached credentials on the computer.</span></span> <span data-ttu-id="32ce5-112">ローミングを許可するには、管理者は、内部でアクセスされる発行サーバーを、名前が正しく解決されるように、外部と同じ名前で使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ce5-112">To allow roaming, administrators must ensure that the publishing server being accessed internally is available at the same name externally for the names to resolve properly.</span></span>

## <span data-ttu-id="32ce5-113">ドメインに参加していないクライアント</span><span class="sxs-lookup"><span data-stu-id="32ce5-113">Non-Domain-Joined Clients</span></span>


<span data-ttu-id="32ce5-114">ドメインに参加していないが、app-v インフラストラクチャで通信する必要があるクライアントは、app-v インフラストラクチャへの認証が正常に行われるように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ce5-114">Clients that are non-domain joined but need to communicate in the App-V infrastructure must be configured to ensure that authentication to the App-V infrastructure is successful.</span></span> <span data-ttu-id="32ce5-115">App-v デスクトップクライアントでは、公開の更新プロセスの入力を要求することはできません。そのため、クライアントは、適切な資格情報をアプリの Hyper-v 管理サーバーに提示するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ce5-115">The App-V Desktop Client does not permit prompting for the publishing refresh process, so the client must be configured to present the proper credentials to the App-V Management Server.</span></span>

<span data-ttu-id="32ce5-116">公開サーバーは、非ドメイン参加クライアントからの更新を公開するように構成されています。そのためには、クライアントアクセスの外部名が、発行サーバーの証明書の共通名またはサブジェクトの代替名 (SAN) として構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ce5-116">The publishing server, which is configured for publishing refresh from the non-domain joined client, requires that the external name that clients access is configured as the common name or a subject alternate name (SAN) on the publishing server’s certificate.</span></span>

## <span data-ttu-id="32ce5-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="32ce5-117">Related topics</span></span>


[<span data-ttu-id="32ce5-118">Windows Vista の適切な資格情報を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="32ce5-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

[<span data-ttu-id="32ce5-119">Windows XP の適切な資格情報を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="32ce5-119">How to Assign the Proper Credentials for Windows XP</span></span>](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





