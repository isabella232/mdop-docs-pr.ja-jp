---
title: Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法
description: Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法
author: dansimp
ms.assetid: 1ebe86fa-0fbc-4512-aebc-0a5da991cd43
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e35c2df518f22ba81a070d2c40ad3862f376a6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817027"
---
# <span data-ttu-id="61b88-103">Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法</span><span class="sxs-lookup"><span data-stu-id="61b88-103">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>


<span data-ttu-id="61b88-104">より安全な App-v のインストールをサポートするには、次の手順を使用して、Windows Server2003 または Windows Server2008 のいずれかで秘密キーを変更します。</span><span class="sxs-lookup"><span data-stu-id="61b88-104">To support a more secure App-V installation, you can use the following procedures to modify private keys in either Windows Server2003 or Windows Server2008.</span></span> <span data-ttu-id="61b88-105">秘密キーのアクセス許可を変更するには、Windows Server2003 リソースキットツールを使用でき `WinHttpCertCfg.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="61b88-105">To modify the permissions of the private key, you can use the Windows Server2003 Resource Kit tool `WinHttpCertCfg.exe`.</span></span>

<span data-ttu-id="61b88-106">Windows Server2003 の場合、このドキュメントに記載されている前提条件を満たしている証明書が、App-v 管理またはストリーミングサーバーをインストールするコンピューターまたはコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b88-106">For Windows Server2003, the procedure requires that a certificate that meets the prerequisites listed in this document is installed on the computer or computers on which you will install the App-V Management or Streaming Server.</span></span> <span data-ttu-id="61b88-107">このツールの使用に関する追加情報 `WinHttpCertCfg.exe` は、で入手でき <https://go.microsoft.com/fwlink/?LinkId=151981> ます。</span><span class="sxs-lookup"><span data-stu-id="61b88-107">Additional information about using the `WinHttpCertCfg.exe` tool is available at <https://go.microsoft.com/fwlink/?LinkId=151981>.</span></span>

<span data-ttu-id="61b88-108">Windows Server2008 では、秘密キーの Acl を変更するプロセスが非常に簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="61b88-108">In Windows Server2008, the process of changing the ACLs on the private key is much simpler.</span></span> <span data-ttu-id="61b88-109">証明書のユーザーインターフェイスを使って、秘密キーのアクセス許可を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="61b88-109">The certificate’s user interface can be used to manage private key permissions.</span></span>

<span data-ttu-id="61b88-110">**注** 既定のセキュリティコンテキストはネットワークサービスです。ただし、代わりにドメインアカウントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="61b88-110">**Note** The default security context is Network Service; however, a domain account can be used instead.</span></span>

 

**<span data-ttu-id="61b88-111">Windows Server2003 で秘密キーを管理するには</span><span class="sxs-lookup"><span data-stu-id="61b88-111">To manage private keys in Windows Server2003</span></span>**

1.  <span data-ttu-id="61b88-112">App-v 管理またはストリーミングサーバーになるコンピューターでは、コマンドプロンプトに次のコマンドを入力して、特定の証明書に割り当てられている現在のアクセス許可を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="61b88-112">On the computer that will become the App-V Management or Streaming Server, type the following command in a command prompt to list the current permissions assigned to a specific certificate:</span></span>

    `winhttpcertcfg -l -c LOCAL_MACHINE\My -s Name_of_cert`

2.  <span data-ttu-id="61b88-113">必要に応じて、管理またはストリーミングサービスに使用されるセキュリティコンテキストへの読み取りアクセスを提供するために、証明書のアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="61b88-113">If necessary, modify the permissions of the certificate to provide read access to the security context that will be used for Management or Streaming Service:</span></span>

    `winhttpcertcfg -g -c LOCAL_MACHINE\My -s Name_of_cert -a NetworkService`

3.  <span data-ttu-id="61b88-114">証明書のアクセス許可の一覧によって、セキュリティコンテキストが適切に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61b88-114">Verify that the security context was properly added by listing the permissions on the certificate:</span></span>

    `winhttpcertcfg –l –c LOCAL_MACHINE\My –s Name_of_cert`

**<span data-ttu-id="61b88-115">Windows Server2008 で秘密キーを管理するには</span><span class="sxs-lookup"><span data-stu-id="61b88-115">To manage private keys in Windows Server2008</span></span>**

1.  <span data-ttu-id="61b88-116">*ローカルコンピューター*の証明書ストアを対象とする*証明書*スナップインを使用して、MICROSOFT 管理コンソール (MMC) を作成します。</span><span class="sxs-lookup"><span data-stu-id="61b88-116">Create a Microsoft Management Console (MMC) with the *Certificates* snap-in that targets the *Local Machine* certificate store.</span></span>

2.  <span data-ttu-id="61b88-117">MMC を展開し、[**秘密キーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61b88-117">Expand the MMC and select **Manage Private Keys**.</span></span>

3.  <span data-ttu-id="61b88-118">[**セキュリティ**] タブで、**読み取り**アクセス権を持つ**ネットワークサービス**アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="61b88-118">On the **Security** tab, add the **Network Service** account with **Read** access.</span></span>

## <span data-ttu-id="61b88-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="61b88-119">Related topics</span></span>


[<span data-ttu-id="61b88-120">APP-V Management Server または Streaming Server をサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="61b88-120">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)

[<span data-ttu-id="61b88-121">安全なストリーミングをサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="61b88-121">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)

 

 





