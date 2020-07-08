---
title: AGPM のアップグレードのトラブルシューティング
description: AGPM のアップグレードのトラブルシューティング
author: dansimp
ms.assetid: 1abbf0c1-fd32-46a8-a3ba-c005f066523d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2089eac51803dca60da51f61ebdb112fbf0bda08
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818247"
---
# AGPM のアップグレードのトラブルシューティング

このセクションでは、高度なグループポリシー管理 (AGPM) サーバーを新しいバージョン (AGPM 4.0 から AGPM 4.3) にアップグレードするときに発生する可能性がある一般的な問題について説明します。 ここに記載されていない問題を診断するには、[トラブルシューティング](troubleshooting-agpm-agpm40.md)のヒントを表示するか、Agpm 管理者 (フルコントロール) でログとトレースを使用することができます。 詳細については、「[ログとトレースを構成する](configure-logging-and-tracing-agpm40.md)」を参照してください。

## どのような問題が発生していますか?

-   [HTML GPO の相違レポートを生成できませんでした (エラーコード 80004003)](#bkmk-error-80004003)

### <a href="" id="bkmk-error-80004003"></a>HTML GPO の相違レポートを生成できませんでした (エラーコード 80004003)

-   **原因**: 不適切なアカウントで AGPM アップグレードパッケージをインストールしている。

-   **解決策**: この問題を解決するには、AGPM 管理者である必要があります。
    
    -   **AGPM サービスアカウント**のユーザー名 & パスワードがわかっていることを確認します。

    -   Agpm サービスアカウントとして、AGPM サーバーに対話的にログオンします。
        
        -   別のアカウントを使用するとインストールが失敗するため、これは非常に重要です。

    -   AGPM サービスをシャットダウンします。
    
    -   必要な修正プログラムをインストールします。
    
    -   AGPM クライアントを使って AGPM に接続し、差異レポートが機能していることをテストします。
    
## Microsoft Advanced グループポリシー管理 4.0 SP3 の修正プログラムパッケージ1をインストールする
    
**この修正プログラムで修正**された問題: AGPM で、新しいグループポリシーオブジェクト (gpo) を制御または管理するときに、差分レポートを生成できません。

**この更新プログラムの入手方法**: 最新バージョンの Microsoft デスクトップ最適化パック ([2017 年3月のサービスリリース](https://www.microsoft.com/download/details.aspx?id=54967)) をインストールします。 詳細については、 [KB 4014009](https://support.microsoft.com/help/4014009/)を参照してください。

具体的には、[ `AGPM4.0SP1_Server_X64_KB4014009.exe` ダウンロード] ボタンを押した後に表示されるリストから、最初のファイルのみをダウンロードすることを選択できます。
      
Microsoft デスクトップ最適化パック (2017 年3月のサービスリリース) へのダウンロードリンクは、[ここ](https://www.microsoft.com/download/details.aspx?id=54967)にあります。
      
      
## 参照リンク
https://support.microsoft.com/help/3127165/hotfix-package-1-for-microsoft-advanced-group-policy-management-4-0-sp
      
