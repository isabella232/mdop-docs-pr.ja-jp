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
# Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法


より安全な App-v のインストールをサポートするには、次の手順を使用して、Windows Server2003 または Windows Server2008 のいずれかで秘密キーを変更します。 秘密キーのアクセス許可を変更するには、Windows Server2003 リソースキットツールを使用でき `WinHttpCertCfg.exe` ます。

Windows Server2003 の場合、このドキュメントに記載されている前提条件を満たしている証明書が、App-v 管理またはストリーミングサーバーをインストールするコンピューターまたはコンピューターにインストールされている必要があります。 このツールの使用に関する追加情報 `WinHttpCertCfg.exe` は、で入手でき <https://go.microsoft.com/fwlink/?LinkId=151981> ます。

Windows Server2008 では、秘密キーの Acl を変更するプロセスが非常に簡単になりました。 証明書のユーザーインターフェイスを使って、秘密キーのアクセス許可を管理することができます。

**注** 既定のセキュリティコンテキストはネットワークサービスです。ただし、代わりにドメインアカウントを使うことができます。

 

**Windows Server2003 で秘密キーを管理するには**

1.  App-v 管理またはストリーミングサーバーになるコンピューターでは、コマンドプロンプトに次のコマンドを入力して、特定の証明書に割り当てられている現在のアクセス許可を一覧表示します。

    `winhttpcertcfg -l -c LOCAL_MACHINE\My -s Name_of_cert`

2.  必要に応じて、管理またはストリーミングサービスに使用されるセキュリティコンテキストへの読み取りアクセスを提供するために、証明書のアクセス許可を変更します。

    `winhttpcertcfg -g -c LOCAL_MACHINE\My -s Name_of_cert -a NetworkService`

3.  証明書のアクセス許可の一覧によって、セキュリティコンテキストが適切に追加されていることを確認します。

    `winhttpcertcfg –l –c LOCAL_MACHINE\My –s Name_of_cert`

**Windows Server2008 で秘密キーを管理するには**

1.  *ローカルコンピューター*の証明書ストアを対象とする*証明書*スナップインを使用して、MICROSOFT 管理コンソール (MMC) を作成します。

2.  MMC を展開し、[**秘密キーの管理**] を選択します。

3.  [**セキュリティ**] タブで、**読み取り**アクセス権を持つ**ネットワークサービス**アカウントを追加します。

## 関連トピック


[APP-V Management Server または Streaming Server をサポートするための証明書の構成](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)

[安全なストリーミングをサポートするための証明書の構成](configuring-certificates-to-support-secure-streaming.md)

 

 





