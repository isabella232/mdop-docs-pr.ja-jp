---
title: DaRT 8.0 のリリース ノート
description: DaRT 8.0 のリリース ノート
author: dansimp
ms.assetid: e8b373c8-7aa5-4930-a8f9-743d26145dad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 894708585ff4006c37085e71f365690b8424d43e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824787"
---
# DaRT 8.0 のリリース ノート


**これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。**

Microsoft 診断/回復ツールセット (DaRT) 8.0 をインストールする前に、これらのリリースノートをよくお読みください。

これらのリリースノートには、DaRT 8.0 を正常にインストールするために必要な情報が記載されています。 リリースノートには、製品ドキュメントに記載されていない情報も含まれています。 これらのリリースノートとその他の DaRT ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

DaRT ソフトウェアの入手方法については、「 [MDOP の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」をご覧ください。

## 製品ドキュメントについて


DaRT のマニュアルについては、Microsoft TechNet の[DaRT のホームページ](https://go.microsoft.com/fwlink/?LinkID=252096)をご覧ください。

DaRT ドキュメントのダウンロード可能なコピーを入手するには、 <https://go.microsoft.com/fwlink/?LinkID=267420> Microsoft ダウンロードセンターを参照してください。

## フィードバックの提供


DaRT 8.0 についてご意見をお寄せしております。 にフィードバックを送信でき <mdopdocs@microsoft.com> ます。

**注** このメールアドレスはサポートチャネルではありませんが、お客様からのフィードバックは、弊社のドキュメントと製品リリースの将来の変更を計画するのに役立ちます。

 

MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。

新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。

## DaRT 8.0 の既知の問題


### Locksmith またはレジストリエディターを実行すると、システムの復元に失敗する

Locksmith、Registry Editor、その他のツールを実行した場合、システムの復元は失敗します。

**回避策:** DaRT を閉じてから再起動してから、システムの復元を開始します。

### Locksmith またはコンピューターの管理を起動して閉じると、SFC スキャンが実行されない

Locksmith またはコンピューター管理ツールを起動して閉じた場合、システムファイルチェッカーは実行できません。

**回避策:** DaRT を閉じてから再起動し、SFC を起動します。

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> ADK がインストールされていないと DaRT インストーラーが失敗しない

コマンドラインを使って MSI を実行して DaRT 8.0 をインストールした場合に、ADK がインストールされていないと、DaRT のインストールは失敗します。 現時点では、dart 8.0 installer は DaRT 8.0 リカバリ画像を除くすべてのコンポーネントをインストールします。

**回避策:**-.

### Locksmith、RegEdit、Crash Analyzer、およびコンピューター管理を起動した後、Defender を起動できない

Locksmith、RegEdit、Crash Analyzer、コンピューター管理を既に起動している場合、Defender は起動しません。

**回避策:** DaRT を閉じてから再起動してから、Defender を起動します。

### Defender の起動に時間がかかる場合がある

Defender の起動には数分かかることがあります。 進行状況バーは、現在の読み込みの状態を示します。

**回避策:**-.

## リリースノートの著作権情報


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。 その他のすべての商標は、該当する所有者に帰属します。



## 関連トピック


[DaRT 8.0 について](about-dart-80-dart-8.md)

 

 





