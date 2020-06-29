---
title: App-V 5.0 のリリース ノート
description: App-V 5.0 のリリース ノート
author: dansimp
ms.assetid: 68a6a5a1-4b3c-4c09-b00c-9ca4237695d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e49f6072d738b45afe25de24f2ee9a2d09d64a2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813322"
---
# App-V 5.0 のリリース ノート


**これらのリリースノートで特定の問題を検索するには、CTRL キーを押しながら F キーを押します。**

App-v 5.0 をインストールする前に、これらのリリースノートをよくお読みください。

これらのリリースノートには、App-v 5.0 を正常にインストールするために必要な情報が含まれています。 リリースノートには、製品ドキュメントに記載されていない情報も含まれています。 これらのリリースノートと他の App-v 5.0 ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## 製品ドキュメントについて


App-v 5.0 ドキュメントの詳細については、Microsoft TechNet の「App-v 5.0 のホームページ」を参照してください。

## フィードバックの提供


弊社では、App-v 5.0 についてご意見をお寄せしています。 にフィードバックを送信でき <mdopdocs@microsoft.com> ます。

**注** このメールアドレスはサポートチャネルではありませんが、お客様のフィードバックは、今後のドキュメントや製品リリースの将来の変更を計画するのに役立ちます。

 

MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。

新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。

## App-v 5.0 の既知の問題


このセクションには、App-v 5.0 の既知の問題に関するリリースノートが含まれています。

### サーバー PowerShell コマンドレットを使用すると、パッケージの追加を終了できない

PowerShell を使用してパッケージを追加する場合、新しいパッケージの追加を終了する方法はありません。

対応策: パッケージの追加を停止するには、最終的なパッケージを追加した後で**enter**キーを押します。

### <a href="" id="-------------app-v-5-0-client-rejects-packages-from-servers-whose-ssl-certificate-has-been-revoked"></a> App-v 5.0 クライアントは、SSL 証明書が失効しているサーバーからパッケージを拒否します。

HTTPS プロトコルを使用している場合、App-v 5.0 クライアントは、SSL 証明書が失効しているサーバーからのパッケージを既定で拒否します。 この動作を無効にするには、 **VerifyCertificateRevocationList**設定を変更します。 この設定の新しい構成の適用は、App-v 5.0 サービスが再開されるまで有効になりません。

対応策: App-v 5.0 サービスを再起動してください。

## リリースノートの著作権情報


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。 その他のすべての商標は、該当する所有者に帰属します。








## 関連トピック


[App-V 5.0 について](about-app-v-50.md)

 

 





