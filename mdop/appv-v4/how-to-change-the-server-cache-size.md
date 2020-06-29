---
title: サーバーのキャッシュ サイズを変更する方法
description: サーバーのキャッシュ サイズを変更する方法
author: dansimp
ms.assetid: 24e63744-21c3-458e-b137-9592f4fe785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e56a8a28f7a00d71805b497f9e404cca65919d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818027"
---
# サーバーのキャッシュ サイズを変更する方法


次の手順を使用して、Application Virtualization Server 管理コンソールから任意のサーバーのキャッシュサイズを直接変更できます。

**注** キャッシュサイズを変更することはできますが、特に設定でサイズを変更する必要がある場合を除き、キャッシュサイズは既定値に設定しておくことをお勧めします。

 

**サーバーキャッシュのサイズを変更するには**

1.  左側のウィンドウで [**サーバーグループ**] ノードをクリックして、サーバーグループの一覧を展開します。

2.  [**結果**] ウィンドウで、目的のサーバーグループをダブルクリックして、グループ内のサーバーの一覧を表示します。

3.  [**結果**] ウィンドウで、目的のサーバーを右クリックし、[**プロパティ**] を選択します。

4.  [**詳細設定**] タブを選択します。

5.  サーバーキャッシュの [**最大メモリ割り当て**] フィールドに値を入力して、[**メモリ割り当ての警告**] フィールドに値を入力します。

6.  [**最大ブロックサイズ**] フィールドに値を入力します。 この数値は、サーバーからストリーミングされる最大のパッケージの最大ブロックサイズ以上である必要があります。

7.  **[OK]** をクリックします。

## 関連トピック


[サーバー ポートを変更する方法](how-to-change-the-server-port.md)

[サーバー管理コンソールでサーバーを管理する方法](how-to-manage-servers-in-the-server-management-console.md)

 

 





