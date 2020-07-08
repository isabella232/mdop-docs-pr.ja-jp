---
title: APP-V Management Server または Streaming Server を安全にインストールする
description: APP-V Management Server または Streaming Server を安全にインストールする
author: dansimp
ms.assetid: d2a51a81-a80f-427c-a727-611e1eb74f02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0150f4dc7f489731c4a818fed9780ebb25dbd24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816327"
---
# APP-V Management Server または Streaming Server を安全にインストールする


このセクションのトピックでは、強化されたセキュリティバージョンの App-v Management Server または App-v ストリーミングサーバーのインストールに関する情報を提供します。

**注** 強化されたセキュリティ (トランスポート層セキュリティ、TLS など) を使用するためにアプリをインストールまたは構成するには、x.509 V3 証明書が App-v サーバーにプロビジョニングされている必要があります。

 

セキュリティで保護された管理サーバーまたはストリーミングサーバーをインストールまたは構成するための準備として、次の技術要件を考慮してください。

-   証明書は有効である必要があります。 証明書が有効でない場合、クライアントは接続を終了します。

-   証明書には、適切な*拡張キー使用法*(EKU)、サーバー認証 (OID 1.3.6.1.5.5.7.3.1) が含まれている必要があります。 証明書にこの EKU が含まれていない場合、クライアントは接続を終了します。

-   証明書の完全修飾ドメイン名 (FQDN) は、それがインストールされているサーバーと一致している必要があります。 たとえば、クライアントが通話を発信していて `RTSPS://Myserver.mycompany.com/content/MyApp.sft` 、[**発行先**] フィールドがに設定されている場合、 `Server1.mycompany.com` クライアントはサーバーに接続せず、セッションは終了します。 このエラーはユーザーに報告されます。

    **注** ネットワーク負荷分散クラスターで App-v を使用している場合は、RTSPS をサポートするようにサブジェクト代替名 (San) を使用する証明書を構成する必要があります。 証明機関 (CA) を構成し、San で証明書を作成する方法については、「」を参照してください <https://go.microsoft.com/fwlink/?LinkId=133228> 。

     

-   クライアントとサーバーは、ルート CA を信頼する必要があります。 CA は、サーバーに接続しているクライアントによって信頼されている必要があります。 それ以外の場合、クライアントは接続を終了します。

-   アプリ-V サービスアカウントが証明書にアクセスできるようにするには、証明書の秘密キーにアクセス許可が変更されている必要があります。 既定では、App-v は Network Service アカウントを使用します。既定では、ネットワークサービスアカウントには秘密キーへのアクセス許可が与えられていないため、安全な接続はできません。

## このセクションの内容


<a href="" id="configuring-certificates-to-support-secure-streaming"></a>[安全なストリーミングをサポートするための証明書の構成](configuring-certificates-to-support-secure-streaming.md)  
セキュリティで保護されたストリーミングをサポートするための証明書の取得、構成、インストールについて説明します。

<a href="" id="how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server"></a>[Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)  
Windows Server2003 および Windows Server2008 でキーを変更するための手順について説明します。

<a href="" id="configuring-certificates-to-support-app-v-management-server-or-streaming-server"></a>[APP-V Management Server または Streaming Server をサポートするための証明書の構成](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)  
ネットワーク負荷分散環境用の証明書の構成に関する情報を含む、App-v 管理またはストリーミングサーバー用の証明書の構成について説明します。

 

 





