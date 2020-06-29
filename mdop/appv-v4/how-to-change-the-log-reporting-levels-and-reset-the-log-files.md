---
title: ログ レポート レベルの変更およびログ ファイルのリセットを行う方法
description: ログ レポート レベルの変更およびログ ファイルのリセットを行う方法
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818047"
---
# ログ レポート レベルの変更およびログ ファイルのリセットを行う方法


次の手順を使用して、Application Virtualization 管理コンソールの**Application virtualization**ノードからログレポートレベルを変更できます。 ログファイルが最大サイズ (既定では 256 MB) に達すると、次にログへの書き込みが行われたときにリセットが強制されます。 リセットすると、新しいログファイルが作成され、古いファイルはバックアップとして名前が変更されます。

**ログレポートのレベルを変更するには**

1.  [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**プロパティ**] ダイアログボックスの [全般] タブで、[**ログレベル**] ドロップダウンリストから必要**な**ログレベルを選びます。

    **注** ログレベルとして [**詳細**] を選択した場合、ログファイルは非常に早く大きくなります。 これにより、クライアントのパフォーマンスが妨げられる可能性があります。そのためには、特定の問題を診断する目的でのみこのログレベルを使用することをお勧め

     

3.  [**プロパティ**] ダイアログボックスの [全般] タブで、[**システムログレベル**] ドロップダウンリストから必要**な**ログレベルを選びます。

    **注** システム**ログレベル**設定は、システムイベントログに送信されるメッセージのレベルを制御します。 ログに記録されたメッセージは、クライアントイベントログに記録されるメッセージと同じですが、別の場所に格納されています。

     

4.  [ **OK]** または [**適用**] をクリックして設定を変更します。

**ログファイルをリセットするには**

1.  [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**プロパティ**] ダイアログボックスの [**全般**] タブで、[**ログのリセット**] をクリックして現在のログファイルをバックアップし、新しいログファイルをすぐに開始します。 バックアップログファイルは、同じフォルダーに保存されます。

3.  [ **OK]** または [**適用**] をクリックして設定を変更します。

## 関連トピック


[Application Virtualization Client Management Console でクライアントを構成する方法](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[Application Virtualization Client のユーザー アクセス許可](user-access-permissions-in-application-virtualization-client.md)

 

 





