---
title: Streaming Server のインストール後のセキュリティを構成する方法
description: Streaming Server のインストール後のセキュリティを構成する方法
author: dansimp
ms.assetid: 9bde3677-d1aa-4dcc-904e-bb49a268d748
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1945b38da5dd50c0bd2fb0c741bd92012e78586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817904"
---
# <span data-ttu-id="081bb-103">Streaming Server のインストール後のセキュリティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="081bb-103">How to Configure Streaming Server Security Post-Installation</span></span>


<span data-ttu-id="081bb-104">レジストリを使用してセキュリティを強化するように、App-v ストリーミングサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="081bb-104">Configure the App-V Streaming Server for enhanced security through the registry.</span></span> <span data-ttu-id="081bb-105">App-v 管理サーバーの場合と同様に、証明書は、次のインストール後の手順を完了する前に、サーバー認証用の正しい EKU 識別子を使用して適切にプロビジョニングされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="081bb-105">As with the App-V Management Server, a certificate must be correctly provisioned with the correct EKU identifier for Server Authentication before you complete the following post-installation procedure.</span></span>

**<span data-ttu-id="081bb-106">ストリーミングサーバーのセキュリティのインストール後に構成するには</span><span class="sxs-lookup"><span data-stu-id="081bb-106">To configure Streaming Server security post-installation</span></span>**

1.  <span data-ttu-id="081bb-107">MMC を作成して、**証明書**スナップインを追加し、[**ローカルコンピューター証明書ストア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="081bb-107">Create an MMC, add the **Certificates** snap-in, and select **Local Machine certificate store**.</span></span>

2.  <span data-ttu-id="081bb-108">コンピューターの**個人**証明書を開き、app-v 用にプロビジョニングされた証明書を開きます。</span><span class="sxs-lookup"><span data-stu-id="081bb-108">Open the **Personal** certificates for the computer, and open the certificate provisioned for App-V.</span></span>

3.  <span data-ttu-id="081bb-109">[**詳細**] タブで、拇印までスクロールダウンし、[詳細] ウィンドウでハッシュをコピーします。</span><span class="sxs-lookup"><span data-stu-id="081bb-109">On the **Details** tab, scroll down to the thumbprint and copy the hash in the details pane.</span></span>

4.  <span data-ttu-id="081bb-110">レジストリエディターを開き、に移動し `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server` ます。</span><span class="sxs-lookup"><span data-stu-id="081bb-110">Open the registry editor, and navigate to `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server`.</span></span>

5.  <span data-ttu-id="081bb-111">`X509CertHash`値を編集し、[値] フィールドに拇印ハッシュを貼り付けて、すべてのスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="081bb-111">Edit the `X509CertHash` value, paste the thumbprint hash in the value field, and remove all spaces.</span></span> <span data-ttu-id="081bb-112">[ **OK]** をクリックして編集を承諾します。</span><span class="sxs-lookup"><span data-stu-id="081bb-112">Click **OK** to accept the edit.</span></span>

6.  <span data-ttu-id="081bb-113">レジストリエディターで、に移動 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts` します。</span><span class="sxs-lookup"><span data-stu-id="081bb-113">In the registry editor, navigate to `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts`.</span></span>

7.  <span data-ttu-id="081bb-114">"322" という名前の新しい**DWORD**値を作成し、その10進数を322または142として16進数値として入力します。</span><span class="sxs-lookup"><span data-stu-id="081bb-114">Create a new **DWORD** value named "322," and then enter the decimal value as 322 or the hexadecimal value as 142.</span></span>

8.  <span data-ttu-id="081bb-115">ストリーミングサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="081bb-115">Restart the streaming service.</span></span>

## <span data-ttu-id="081bb-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="081bb-116">Related topics</span></span>


[<span data-ttu-id="081bb-117">Management Server のインストール後のセキュリティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="081bb-117">How to Configure Management Server Security Post-Installation</span></span>](how-to-configure-management-server-security-post-installation.md)

[<span data-ttu-id="081bb-118">証明書のアクセス許可の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="081bb-118">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)

 

 





