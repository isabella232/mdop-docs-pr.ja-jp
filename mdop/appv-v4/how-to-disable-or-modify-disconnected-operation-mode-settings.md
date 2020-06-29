---
title: 非接続操作モード設定を無効化または変更する方法
description: 非接続操作モード設定を無効化または変更する方法
author: dansimp
ms.assetid: 39f166d7-2d25-4899-8405-b45f051facb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 288c35c8d43352037c8514b4c060e847b456267c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817484"
---
# 非接続操作モード設定を無効化または変更する方法


切断された操作モードの設定を無効または変更するには、Application Virtualization クライアントで次の手順を実行します。

**切断操作を無効にするには**

1.  コンソールで [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**接続**] タブをクリックし、[切断された**操作を許可する**] チェックボックスをオフにします。

3.  [ **OK]** をクリックして変更を確定します。

**タイムアウトを変更するには**

1.  コンソールで [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**接続**] タブをクリックし、[**切断操作を制限する**] チェックボックスをオンにします。

3.  フィールドに、1 ~ 999999 (日数を表す) の値を入力します。 既定値は90日です。

4.  [ **OK]** をクリックして変更を確定します。

**オフラインで作業するには**

1.  コンソールで [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。

2.  [**接続**] タブをクリックし、[**オフライン作業**] チェックボックスをオンにします。

3.  [ **OK]** をクリックして変更を確定します。

## 関連トピック


[非接続操作モード](disconnected-operation-mode.md)

[Application Virtualization をオフラインまたはオンラインで作業する方法](how-to-work-offline-or-online-with-application-virtualization.md)

 

 





