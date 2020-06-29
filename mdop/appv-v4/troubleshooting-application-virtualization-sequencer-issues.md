---
title: Application Virtualization Sequencer の問題のトラブルシューティング
description: Application Virtualization Sequencer の問題のトラブルシューティング
author: dansimp
ms.assetid: 2712094b-a0bc-4643-aced-5415535f3fec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8b84f37217f29ff2c08a2254d7f54ce74348d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815244"
---
# Application Virtualization Sequencer の問題のトラブルシューティング


このトピックには、Application Virtualization (App-v) Sequencer の一般的な問題のトラブルシューティングに役立つ情報が含まれています。

## App-v のアプリを使用して SFTD ファイルを作成すると、バージョン番号が予期せず大きくなる


コマンドラインを使用して、新しい sft ファイルを生成します。 コマンドラインを使用して、sft ファイルを作成するには、コマンドプロンプトで次のように入力します。

**mkdiffpkg.exe &lt; 基本の sft ファイル名 &gt; &lt; 差分 sft ファイル名&gt;**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a>パッケージのアップグレード後に、OSD ファイルのファイル名が正しくない


アップグレード用のパッケージを開くときに、パッケージの出力場所としてルート Q:\\ ドライブを指定する必要があります。 出力場所に関連付けられたファイル名を指定しないでください。

## Microsoft Word2003 の既定のインストールでクライアントにストリーム配信するとエラーが発生する


クライアントに Microsoft Word2003 をストリーミングすると、エラーが返されますが、Microsoft Word は引き続き実行されます。

**解決策**

仮想アプリケーションパッケージを再シーケンスして、[**完全インストール**] を選びます。

## 依存パッケージを作成すると、アクティブなアップグレードが機能しない


アクティブなアップグレードを使用して、新しいレジストリエントリを追加して、依存パッケージを作成すると、正常に機能しているように見えますが、更新されたレジストリエントリは使用できません。

**解決策**

レジストリ設定は、常に元のバージョンのパッケージと共に保存されるため、パッケージの更新は、元のパッケージを修復しなければ利用できないように見えます。

## [プロパティ] ページを使用して、Microsoft Office2007 ドキュメントの詳細情報が表示されない


[プロパティ] ページを使用して、Microsoft Office2007 ドキュメントに関連付けられている詳細情報を表示しようとすると、詳細情報は表示されません。

**解決策**

これらのプロパティページに必要なシェルの拡張子は、app-v でサポートされていません。

## 16ビットアプリケーションをシーケンスするときに一部のレジストリキーがキャプチャされない


App-v 4.5 では、レジストリフックはカーネルモードからユーザーモードに移動されました。 16ビットアプリケーションまたは16ビットインストーラーを使用するアプリケーションをシーケンスする場合は、まず、Windows NT 仮想 DOS コンピューター (NTVDM) でプロセスを実行するように sequencer コンピューターを構成する必要があります。

**解決策**

優先順位のコンピューターでは、アプリケーションをシーケンスする前に、次のグローバル REGSZ レジストリキー値を [はい] に設定します。

HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM

この機能を有効にするには、コンピューターを再起動する必要があります。

## 関連トピック


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





