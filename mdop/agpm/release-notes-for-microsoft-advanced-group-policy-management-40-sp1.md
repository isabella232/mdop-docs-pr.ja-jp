---
title: Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート
description: Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート
author: dansimp
ms.assetid: 91835bf8-e53c-4202-986e-8d37050d1267
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff9ce0405df766aef9b30e67d07ceb579c4fa89f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818534"
---
# Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート


これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

Microsoft Advanced グループポリシー管理 (AGPM) 4.0 SP1 をインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、AGPM 4.0 SP1 を正常にインストールするために必要な情報が含まれており、製品のドキュメントでは提供されていない情報が含まれています。 これらのリリースノートとその他の AGPM ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。

## AGPM 4.0 SP1 の既知の問題


このセクションには、AGPM 4.0 SP1 のリリースノートが含まれています。

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a>AGPM サーバー設定を変更しようとすると、コントロールパネルの "アンインストール" ツールが機能しないことがある

コントロールパネルのツールで、AGPM サーバーの設定を変更しようとしても、プログラムをアンインストールまたは変更できないことがあります。

対応策: コントロールパネルを使用して AGPM サーバーの設定を変更する前に、AGPM アーカイブフォルダーのコピーを作成してください。 次に、Setup.exe を使って AGPM サーバーを再インストールし、必要な構成パラメーターを選びます。

### グループポリシーオブジェクトに追加されたリンクはレポートに表示されない

AGPM 設定と差分レポートには、グループポリシーオブジェクト (GPO) に追加されたリンクは表示されません。

対応策: レポート内のリンクを表示するには、グループポリシー管理コンソール (GPMC) で GPO を選んで、右側のウィンドウで [**設定**] タブをクリックします。

### <a href="" id="reports-do-not-display-all--choice-options-properties--settings"></a>レポートにすべての [選択肢オプションプロパティ] の設定が表示されない

AGPM 設定と差分レポートでは、グループポリシーオブジェクトエディターの [オプションの選択] ダイアログボックスで選択されたすべての設定が表示されません。

回避策: GPMC を使用して、レポートで選択した選択オプションのプロパティの設定を表示します。

### 特定のブラウザーで [表示] と [非表示] のタブが表示されないレポート

AGPM 設定と差分レポートの右側に表示される [表示] タブと [非表示] タブは、Google Chrome または Mozilla Firefox でレポートを表示するときには表示されません。

回避策: Internet Explorer を使用してレポートを表示します。

### AGPM の設定と差分レポートでは、GPMC レポートのさまざまなコンテンツが表示される場合がある

AGPM 設定と差分レポートでは、グループポリシー管理コンソール (GPMC) のレポートと同じコンテンツが表示されない場合があります。

回避策: GPMC を使って AGPM レポートを表示します。

### ドメインコントローラーがオンラインでない場合、AGPM サービスが開始されない

Windows 8 のドメインコントローラーに AGPM サービスがインストールされている場合、そのドメインコントローラーがオンラインでない場合はサービスが開始されません。

回避策: ドメインコントローラーがオンラインになったら、AGPM サービスを手動で開始します。

### Agpm 4.0 リリースと修正プログラムのどちらからアップグレードしても、agpm サーバーから AGPM 4.0 SP1 へのアップグレードがブロックされます。

AGPM サーバーを AGPM 4.0 にアップグレードしようとした場合。 [SP1] AGPM 4.0 をインストールしてから AGPM ホットフィックスをインストールする (「サポート技術情報の記事[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)」を参照)、アップグレードは失敗し、完了することができません。

回避策: AGPM 4.0 サーバーをアンインストールしてから、AGPM 4.0 SP1 をインストールします。

### レポートに組織単位のリンクが表示されない

制御されていない GPO を組織単位にリンクして、AGPM を使ってその GPO を制御した場合、AGPM 設定と差分レポートには組織単位のリンクは表示されません。

回避策: [**設定の変更**] ノードの [**コントロール**] タブで、gpo を右クリックして [**設定**] をクリックし、[ **gpo リンク**] をクリックして組織リンクを表示します。 または、GPMC を使用して、[**スコープ**] タブから GPO へのリンクを表示することもできます。

## 関連トピック


[高度なグループ ポリシーの管理](index.md)

[AGPM 4.0 SP1 の新機能](whats-new-in-agpm-40-sp1.md)

 

 





