---
title: Application Virtualization Sequencer のトラブルシューティング
description: Application Virtualization Sequencer のトラブルシューティング
author: dansimp
ms.assetid: 12ea8367-0b84-44e1-a885-e0539486556b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60c47b853c74d90afc21e9ca172c0eec2a2c7a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815184"
---
# Application Virtualization Sequencer のトラブルシューティング


このトピックには、Application Virtualization (App-v) Sequencer の一般的な問題のトラブルシューティングに役立つ情報が含まれています。

## App-v のアプリを使用して SFTD ファイルを作成すると、バージョン番号が予期せず大きくなる


SFTD ファイルに関連付けられているバージョン番号が、予期せず増加します。

**解決策**

コマンドラインを使用して、新しい sft ファイルを生成します。 コマンドラインを使用して、sft ファイルを作成するには、コマンドプロンプトで次のように入力します。

**mkdiffpkg.exe &lt; 基本の sft ファイル名 &gt; &lt; 差分 sft ファイル名&gt;**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a>パッケージのアップグレード後に、OSD ファイルのファイル名が正しくない


既存のパッケージをアップグレードした後、ファイル名が間違っています。

**解決策**

アップグレード用のパッケージを開くときに、パッケージの出力場所としてルート Q:\\ ドライブを指定する必要があります。 出力場所に関連付けられたファイル名を指定しないでください。

## Microsoft Word2003 の既定のインストールでクライアントにストリーム配信するとエラーが発生する


クライアントに Microsoft Word2003 をストリーミングすると、エラーが返されますが、Microsoft Word は引き続き実行されます。

**解決策**

仮想アプリケーションパッケージを再シーケンスして、[**完全インストール**] を選びます。

## 依存パッケージを作成するときに、パッケージのアップグレードが機能しない


パッケージアップグレードを使って依存パッケージを作成し、新しいレジストリエントリを追加すると、正常に機能しているように見えますが、更新されたレジストリエントリは使用できません。

**解決策**

レジストリ設定は、常に元のバージョンのパッケージと共に保存されるため、パッケージの更新は、元のパッケージを修復しなければ利用できないように見えます。

## シーケンス中にエラーが発生しました。NET 2.0


必要なパッケージをシーケンスする場合。NET 2.0 というエラーが発生します。

**解決策**

必要なシーケンスパッケージ。NET 2.0 はサポートされていません。

## 関連トピック


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





