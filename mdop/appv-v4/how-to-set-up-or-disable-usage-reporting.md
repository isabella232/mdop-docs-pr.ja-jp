---
title: 使用状況レポートをセットアップまたは無効にする方法
description: 使用状況レポートをセットアップまたは無効にする方法
author: dansimp
ms.assetid: 8587003a-128d-4b5d-ac70-5b9eddddd3dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f8f6c44d4060581f1ebe435875bc2f105cb93d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816547"
---
# 使用状況レポートをセットアップまたは無効にする方法


Application Virtualization Server 管理コンソールで次の手順を使用して、データベースに格納するアプリケーションの仮想化システムの利用状況情報の期間 (月数) を指定できます。

**注** 使用状況の情報を保存するには、[**プロバイダーパイプライン**] タブの [**ログの使用情報**] チェックボックスをオンにする必要があります。このタブを表示するには、[**プロバイダーポリシーの結果**] ウィンドウでプロバイダーポリシーを右クリックし、[**プロパティ**] を選びます。

 

**利用状況レポートを設定するには**

1.  左側のウィンドウで [Application Virtualization System] ノードを右クリックし、[**システムオプション**] を選択します。

2.  [**データベース**] タブを選択します。

3.  [**使用を継続する (月数)** ] または [**すべての使用を維持**] ラジオボタンを選択します。

4.  使用期間を月単位で指定する場合は、1 ~ 120 の数値を入力します (既定値は6か月)。 [すべての**使用を保持**] を選択すると、指定したサイズ制限に達するまでデータベースが拡張されます。

5.  [**適用**] または [ **OK]** をクリックします。

**使用状況レポートを無効にするには**

1.  [**プロバイダーポリシー** ] ノードをクリックします。

2.  [**プロバイダーポリシー** ] を右クリックし、[**プロパティ**] を選択します。

3.  [**プロバイダーパイプライン**] タブを選択します。

4.  [**ログの使用情報**] チェックボックスをオフにします。

5.  [**適用**] または [ **OK]** をクリックします。

## 関連トピック


[サーバー管理コンソールで Application Virtualization システムをカスタマイズする方法](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[データベース サイズをセットアップまたは無効にする方法](how-to-set-up-or-disable-database-size.md)

 

 





