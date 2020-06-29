---
title: MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード
description: MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 2/16/2018
ms.openlocfilehash: 19da3df0976b51700e0d10c302a31421a88d17e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812746"
---
# MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード
このトピックでは、Microsoft BitLocker 管理および監視 (MBAM) サーバー2.5 と MBAM クライアントを2.5 から MBAM 2.5 SP1 にアップグレードするプロセスについて説明します。

### 始める前に
#### 2019年5月のサービスリリースをダウンロードする
[デスクトップ最適化パック](https://www.microsoft.com/download/details.aspx?id=58345)

#### インストールドキュメントを確認する
すべてのサーバー名、データベース名、サービスアカウント、パスワードなど、MBAM 環境の最新ドキュメントがあることを確認します。

### アップグレード手順
#### MBAM データベースのアップグレード手順 (SQL Server)
1. MBAM コンフィギュレーターの使用SQL server または SSRS データベースがホストされている場所からレポートロールを削除します。 使用している環境に応じて、同じサーバーまたは別のサーバーにすることができます。
  > [!NOTE]
  > データベースを削除するオプションは表示されません。これは想定されています。  
2. 2.5 SP1 をインストールします (次に、ボリュームライセンスサービスセンターサイトから、MDOP-Microsoft デスクトップ最適化パック2015にあります)。  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. この時点で構成しない 
4. MBAM コンフィギュレーターの使用レポートロールをもう一度追加する
5. MBAM コンフィギュレーターの使用sql Server の sql データベースロールを再追加する
6. 最後に、Db は既に存在し、作成されていないという警告が表示されますが、これは予期されています。
7. このプロセスにより、既存のデータベースがインストールされている現在のバージョンに更新されます。              

#### MBAM サーバーをアップグレードする手順 (MBAM と IIS を実行している場合)
1. MBAM コンフィギュレーターの使用IIS サーバーから管理者とセルフサービスポータルを削除する
2. MBAM 2.5 SP1 をインストールする
3. この時点で構成しない  
4. MBAM コンフィギュレーターの使用管理者とセルフサービスポータルを IIS サーバーに再追加する 
5. 管理者特権でコマンドプロンプトを開き、「 **IISRESET**」と入力して、Enter キーを押します。
 
#### MBAM クライアント/エンドポイントのアップグレード手順
1. クライアントエンドポイントから2.5 エージェントをアンインストールする
2. クライアントエンドポイントに 2.5 SP1 エージェントをインストールする
3. 2.5 SP1 エージェントを実行しているクライアントに2019年5月のロールアップクライアント更新プログラムをプッシュする 
4. 2019年5月のロールアップをインストールする前に、既存のクライアントをアンインストールする必要はありません。  
