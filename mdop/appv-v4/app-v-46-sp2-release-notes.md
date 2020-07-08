---
title: App-V 4.6 SP2 リリース ノート
description: App-V 4.6 SP2 リリース ノート
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822344"
---
# App-V 4.6 SP2 リリース ノート


**これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。**

Microsoft Application Virtualization (App-v) 4.6 SP2 をインストールする前に、これらのリリースノートをよくお読みください。

これらのリリースノートには、Application Virtualization 4.6 SP2 を正常にインストールするために必要な情報が含まれています。 リリースノートには、製品ドキュメントに記載されていない情報も含まれています。 これらのリリースノートと他の App-v 4.6 SP2 ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## 製品ドキュメントについて


App-v のドキュメントの詳細については、Microsoft TechNet の[Application Virtualization](https://go.microsoft.com/fwlink/?LinkID=232982)ページを参照してください。

## フィードバックの提供


弊社では、App-v 4.6 SP2 についてご意見をお寄せしています。 にフィードバックを送信でき <mdopdocs@microsoft.com> ます。

**注** このメールアドレスはサポートチャネルではありませんが、お客様からのフィードバックは、弊社のドキュメントと製品リリースの将来の変更を計画するのに役立ちます。

 

MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。

新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a>App-v 4.6 SP2 の既知の問題


### シーケンスの際に、システム以外の物理ドライブの短いファイル名のサポートは無効になります

Windows 8 または Windows Server 2012 でシーケンスを行うと、システム以外の物理ドライブの場合、短いファイル名 (8.3) のサポートは既定で無効になります。

シーケンスステーションのプライマリ仮想アプリケーションディレクトリ (たとえば、"Q:\\appname") に関連付けられた基になる物理ドライブは、仮想アプリケーションパッケージを作成するときに短いファイル名を生成するために、短いファイル名 (8.3) のサポートを提供する必要があります。 短いファイル名 (8.3) Windows 8 または Windows Server 2012 のシステム以外の物理ドライブでは、既定でサポートが無効になっています。

**回避策:** システム以外の物理ドライブで短いファイル名 (8.3) のサポートを有効にします。 Windows 8 または Windows Server 2012 で短いファイル名のサポートを有効にするには、次のコマンドを使用します。

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

たとえば、ドライブ文字が "Q:" の場合は、次のコマンドを使用します。

``` syntax
fsutil 8dot3name set Q: 0
```

**注** App-v ファイルシステムでは、Windows 8 または Windows Server 2012 上の短いパスが適切に処理されるため、App-v クライアントでこの設定を変更する必要はありません。

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> Windows 8 でのファイルの種類またはプロトコルの関連付けの既定のハンドラーを、app-v が上書きしない

Windows 8 の**コントロールパネル**の [**既定のプログラム**] を使って既定のアプリケーションを選択した場合、そのアプリケーションに関連付けられているファイルの種類の関連付けは、app-v によって上書きされません。

**回避策:**-.

### 仮想化された Outlook 2010 は、Windows 8 の mailto クリックリンクのオプションとして提供されていません。

Mailto シェル拡張機能では、Windows 8 で仮想化された Outlook 2010 は提供されません。 たとえば、Windows 8 で実行されている仮想化された Outlook 2010 から mailto: リンクをクリックした場合、新しいメールウィンドウは作成されません。 このオプションは、windows 7 およびそれ以前のバージョンの Windows オペレーティングシステムで正しく動作します。

**回避策:**-.

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> Microsoft Update を使用するすべてのロケールで Application Virtualization 4.6 SP2 更新プログラムが提供されない

Microsoft Update を使用している場合、以下の言語ロケールでは、App-v 4.6 SP2 の更新プログラムは使用できません。

-   カザフ語

-   ヒンディー語

-   セルビア語-キリル

**回避策:** Microsoft Windows Server Update Services (WSUS) を使用している場合は、英語版の更新プログラムを使用するか、Microsoft Update カタログから更新プログラムをダウンロードしてください。

## リリースノートの著作権情報


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。 その他のすべての商標は、該当する所有者に帰属します。



## 関連トピック


[Microsoft Application Virtualization 4.6 SP2 について](about-microsoft-application-virtualization-46-sp2.md)

 

 





