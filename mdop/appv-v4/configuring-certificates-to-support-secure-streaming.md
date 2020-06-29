---
title: 安全なストリーミングをサポートするための証明書の構成
description: 安全なストリーミングをサポートするための証明書の構成
author: dansimp
ms.assetid: 88dc76d8-7745-4729-92a1-af089c921244
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9376634a1b9843f46dba4cd452e672cc9e535226
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821894"
---
# 安全なストリーミングをサポートするための証明書の構成


既定では、App-v サービスは Network Service アカウントで実行されます。 ただし、Active Directory ドメインサービスでサービスアカウントを作成し、ネットワークサービスアカウントを Active Directory ドメインアカウントに置き換えることができます。

サービスが実行されるセキュリティコンテキストは、強化されたセキュリティで保護された通信を構成するために重要です。 このセキュリティコンテキストは、証明書の秘密キーの読み取りアクセス許可を持っている必要があります。 アプリ-V server で PKCS \ #10*証明書署名要求*(CSR) が生成されると、Windows*暗号化サービスプロバイダー*が呼び出され、秘密キーが生成されます。 秘密鍵は、システムアカウントと管理者アカウントに付与された権限によって保護されます。

TLS でセキュリティ保護された通信を成功させるために必要な秘密キーにアクセスするには、秘密キーのアクセス制御リスト (Acl) を変更する必要があります。

## 証明書の入手とインストール


App-v 用の証明書を取得してインストールするシナリオは、次のとおりです。

-   内部公開キー基盤 (PKI)。

-   サードパーティ証明書の発行証明機関 (CA)。

    **注** サードパーティ CA から証明書を取得する必要がある場合は、その CA の Web サイトで利用可能なドキュメントに従ってください。

     

PKI インフラストラクチャが展開されている場合は、PKI 管理者に問い合わせて、このトピックで説明されている要件に準拠する証明書を取得してください。 PKI インフラストラクチャが利用できない場合は、サードパーティ CA を使って有効な証明書を取得してください。

証明書を入手してインストールするための詳しいガイダンスについては、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151969> 。

## 関連トピック


セキュリティで保護されたストリーミングをサポートするための証明書の構成[管理サーバーまたはストリーミングサーバーをサポートするための秘密キーのアクセス許可を変更する方法](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





