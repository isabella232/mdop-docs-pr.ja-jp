---
title: キャッシュ サイズおよびドライブ文字の指定を変更する方法
description: キャッシュ サイズおよびドライブ文字の指定を変更する方法
author: dansimp
ms.assetid: e7d7b635-079e-41aa-a5e6-655f33b4e317
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf972f114845064ecf3027cf52d1a038dc6a5118
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818037"
---
# キャッシュ サイズおよびドライブ文字の指定を変更する方法


キャッシュサイズとドライブ文字の指定は、Application Virtualization クライアント管理コンソールの**アプリケーション仮想化**ノードから直接変更できます。

**注**  
キャッシュサイズを設定した後は、サイズを小さくすることはできません。



**キャッシュサイズを変更するには**

1.  [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**プロパティ**] ダイアログボックスの [**ファイルシステム**] タブを選択します。 [**クライアントキャッシュ構成の設定**] セクションで、次のいずれかのラジオボタンをクリックして、キャッシュ領域の管理方法を選択します。

    **重要**  
    [**空きディスク領域のしきい値を使用**する] 設定を選択した場合、入力した値によってキャッシュサイズは、ディスクの合計サイズから、入力した空きディスク領域のしきい値を差し引いた値に設定されます。 [**最大キャッシュサイズの使用**] 設定を [元に戻す] を使用したい場合は、既存のキャッシュサイズよりも大きい値を指定する必要があります。 そうしないと、"新しいサイズは既存のキャッシュサイズより大きくなければなりません" というエラーが表示されます。



~~~
-   **Use maximum cache size**

    Enter a numeric value from 100 to 1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache. The value shown in **Reserved Cache Size** indicates the amount of cache in use.

-   **Use free disk space threshold**

    Enter a numeric value to specify the amount of free disk space, in MB, that the cache must leave available on the disk. This allows the cache to grow until the amount of free disk space reaches this limit. The value shown in **Free disk space remaining** indicates how much disk space is unused.
~~~

3. [ **OK]** または [**適用**] をクリックして設定を変更します。

**ドライブ文字の指定を変更するには**

1.  [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**プロパティ**] ダイアログボックスの [**ファイルシステム**] タブの [**使用するドライブ**] フィールドで、使用可能なドライブ文字のドロップダウンリストから目的のドライブ文字を選びます。 この設定は、コンピューターを再起動すると有効になります。

3.  [ **OK]** または [**適用**] をクリックして設定を変更します。

## 関連トピック


[Application Virtualization Client Management Console でクライアントを構成する方法](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)









