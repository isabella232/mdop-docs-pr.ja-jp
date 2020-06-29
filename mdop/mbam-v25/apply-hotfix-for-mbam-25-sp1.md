---
title: MBAM 2.5 SP1 への修正プログラムの適用
description: MBAM 2.5 SP1 への修正プログラムの適用
ms.author: ppriya-msft
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: 71f840ce4d57a0698289128f92b9d760ca14ddfc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824187"
---
# MBAM 2.5 SP1 への修正プログラムの適用
このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) Server 2.5 SP1 の修正プログラムを適用するためのプロセスについて説明します。

### 作業を始める前に、Microsoft BitLocker 管理と監視 (MBAM) Server 2.5 SP1 の最新の修正プログラムをダウンロードしてください。
[デスクトップ最適化パック](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> 修正プログラムのリリースの詳細については、「 [Mbam バージョングラフ](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)」を参照してください。

#### 既存の MBAM 環境用の MBAM サーバーを更新する手順 
1. MBAM サーバー機能を削除します (これを行うには、MBAM Server 構成ツールを開いてから、[機能の削除] を選びます)。
2. コントロールパネルから MDOP MBAM を削除します。[プログラムと機能] を選びます。
3. MBAM 2.5 SP1 RTM サーバーコンポーネントをインストールします。
4. 映像 MBAM 2.5 SP1 修正プログラムのロールアップをインストールします。
5. MBAM Server Configurator を使用して MBAM 機能を構成します。

#### 新しい MBAM 2.5 SP1 サーバーの修正プログラムをインストールする手順
[新しいサーバーインストール](deploying-the-mbam-25-server-infrastructure.md)のドキュメントを参照してください。
