---
title: MBAM 2.5 から MBAM 2.5 SP1 サービスリリース更新プログラムのアップグレード
author: dansimp
ms.author: ksharma
manager: miaposto
audience: ITPro
ms.topic: article
ms.prod: w10
ms.localizationpriority: Normal
ms.openlocfilehash: 372822e1ec049871c62af9f429290b88bbfac949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812770"
---
# MBAM 2.5 から MBAM 2.5 SP1 サービスリリース更新プログラムをアップグレードする

この記事では、Microsoft BitLocker の管理と監視 (MBAM) 2.5 から MBAM 2.5 Service Pack 1 (SP1) と、 [Microsoft デスクトップ最適化パック (MDOP)](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)を併用して、スタンドアロン構成での2019サービス更新を行う方法について説明します。

このガイドでは、2サーバー構成を使用します。 1つのサーバーは、Microsoft SQL Server 2016 を実行しているデータベースサーバーになります。 このサーバーは、MBAM データベースとレポートをホストします。 他のサーバーは Windows Server 2012 R2 web サーバーになります。 このサーバーは、"管理と監視" と "セルフサービスポータル" をホストします。

## MBAM 2.5 SP1 のアップグレードの準備をする

### 環境内の MBAM サーバーを把握する

1. SQL Server データベースエンジン: MBAM データベースをホストするサーバー。
2. SQL Server Reporting Services: MBAM レポートをホストするサーバー。
3. インターネットインフォメーションサービス (IIS) web サーバー: MBAM Web アプリケーションと MBAM サービスをホストするサーバー。
4. 省略Microsoft System Center Configuration Manager プライマリサイトサーバー: MBAM 構成アプリケーションは、このサーバー上で実行され、MBAM レポートを Configuration Manager に統合します。 これらのレポートは、Configuration Manager SQL Server Reporting Services (SSRS) インスタンスの既存の Configuration Manager レポートにマージされます。

### サービスアカウント、グループ、サーバー名、およびレポート URL を特定する

1. IIS web サーバーで MBAM データベースへのデータの読み取りと書き込みのために使用される MBAM アプリケーションプールサービスアカウントを特定します。
2. MBAM web 機能の構成およびレポート web サービスの URL で使用されるグループを特定します。
3. SQL Server 名とインスタンス名を確認します。 詳細については、このビデオをご覧ください。

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ANP1]

4. コンプライアンスデータおよび監査データベースからコンプライアンスデータを読み取るために使用される SQL Server Reporting Services アカウントを特定します。 詳細については、このビデオをご覧ください。

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALdZ]

## MBAM インフラストラクチャを最新バージョンにアップグレードする

MBAM サーバーインフラストラクチャのインストールまたはアップグレードは、以下に示す順番で実行されます。

- SQL Server データベースエンジン: データベース
- SQL Server Reporting Services: レポート
- Web サーバー: Web アプリケーション
- SCCM サーバー: SCCM 統合レポート (該当する場合)
- クライアント: MBAM エージェントまたはクライアント更新プログラム
- グループポリシーテンプレート: 新しいテンプレートを使用して既存のグループポリシーを更新し、既存の MBAM グループポリシーの新しい設定を有効にします。

> [!NOTE]
> アップグレードを実行する前に、MBAM データベースのデータベース全体のバックアップを作成することをお勧めします。

### MBAM SQL Server をアップグレードする

このビデオでは、MBAM SQL Server をアップグレードする方法について説明します。

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALew]

### MBAM Web サーバーをアップグレードする

このビデオを見て、MBAM Web サーバーをアップグレードする方法を学習してください。

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALex]

## 詳細情報

MBAM 2.5 SP1 の既知の問題の詳細については、「 [mbam 2.5 sp1 のリリースノート](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1)」を参照してください。
