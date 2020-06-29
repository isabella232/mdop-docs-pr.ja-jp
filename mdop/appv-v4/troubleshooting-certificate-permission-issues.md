---
title: 証明書のアクセス許可の問題のトラブルシューティング
description: 証明書のアクセス許可の問題のトラブルシューティング
author: dansimp
ms.assetid: 06b8cbbc-93fd-44aa-af39-2d780792d3c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 728c35b9f51c8f2e18db8acd63708c70bb5d3100
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815207"
---
# <span data-ttu-id="67ca6-103">証明書のアクセス許可の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="67ca6-103">Troubleshooting Certificate Permission Issues</span></span>


<span data-ttu-id="67ca6-104">App-v 4.5 をインストールした後、秘密キーがネットワークサービス用の適切な ACL で構成されていない場合、イベントが NT イベントログに記録され、エントリがファイルに格納され `Sft-server.log` ます。</span><span class="sxs-lookup"><span data-stu-id="67ca6-104">After the installation of App-V4.5, if the private key has not been configured with the proper ACL for the Network Service, an event is logged in the NT Event Log and an entry is placed in the `Sft-server.log` file.</span></span>

## <span data-ttu-id="67ca6-105">エラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="67ca6-105">Error Messages</span></span>


### <span data-ttu-id="67ca6-106">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="67ca6-106">Windows Server2003</span></span>

<span data-ttu-id="67ca6-107">イベント ID 36870 — SSL サーバー資格情報の秘密キーにアクセスしようとしたときに重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="67ca6-107">Event ID 36870—A fatal error occurred when attempting to access the SSL server credential private key.</span></span> <span data-ttu-id="67ca6-108">暗号化モジュールから返されるエラーコードは0x80090016 です。</span><span class="sxs-lookup"><span data-stu-id="67ca6-108">The error code returned from the cryptographic module is 0x80090016.</span></span>

### <span data-ttu-id="67ca6-109">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="67ca6-109">Windows Server2008</span></span>

<span data-ttu-id="67ca6-110">イベント ID 36870 — SSL サーバー資格情報の秘密キーにアクセスしようとしたときに重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="67ca6-110">Event ID 36870—A fatal error occurred when attempting to access the SSL server credential private key.</span></span> <span data-ttu-id="67ca6-111">暗号化モジュールから返されるエラーコードは0x8009030d です。</span><span class="sxs-lookup"><span data-stu-id="67ca6-111">The error code returned from the cryptographic module is 0x8009030d.</span></span>

## <span data-ttu-id="67ca6-112">Sft-server</span><span class="sxs-lookup"><span data-stu-id="67ca6-112">Sft-server.log</span></span>


<span data-ttu-id="67ca6-113">ディレクトリにあるファイルには、次のエラーが表示され `sft-server.log` `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` ます。</span><span class="sxs-lookup"><span data-stu-id="67ca6-113">The following error is placed in the `sft-server.log` file located in the `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` directory:</span></span>

<span data-ttu-id="67ca6-114">証明書を読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="67ca6-114">Certificate could not be loaded.</span></span> <span data-ttu-id="67ca6-115">エラーコード \ [-2146893043 \]。</span><span class="sxs-lookup"><span data-stu-id="67ca6-115">Error code \[-2146893043\].</span></span> <span data-ttu-id="67ca6-116">ネットワークサービスアカウントに、証明書とそれに対応する秘密キーファイルへの適切なアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67ca6-116">Make sure that the Network Service account has proper access to the certificate and its corresponding private key file.</span></span>

 

 





