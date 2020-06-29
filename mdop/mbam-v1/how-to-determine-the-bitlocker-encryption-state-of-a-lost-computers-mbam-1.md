---
title: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
description: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
author: dansimp
ms.assetid: 9440890a-9c63-463b-9113-f46071446388
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9b977b20ecf219830609c3b1f646a29e6678448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824294"
---
# 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法


Microsoft BitLocker 管理と監視 (MBAM) を使用すると、紛失または盗難されたコンピューターの最後の既知の BitLocker 暗号化の状態を判断できます。 所有していないコンピューターでボリュームが暗号化されているかどうかを確認するには、次の手順を使用します。

**コンピューターの最後の既知の BitLocker 暗号化の状態を確認する**

1.  MBAM web サイトを開きます。

    **注** MBAM web サイトの既定のアドレスは http://* &lt; computername &gt; *です。 検索結果をすばやく表示するには、完全修飾サーバー名を使います。

     

2.  ナビゲーションウィンドウから [**レポート**] ノードを選択し、[**コンピューターのコンプライアンスレポート**] を選択します。

3.  右側のウィンドウのフィルターフィールドを使って検索結果を絞り込んでから、[**検索**] をクリックします。 検索クエリの下に結果が表示されます。

4.  紛失したデバイスのポリシーによって決定された適切なアクションを実行します。

    **注** デバイスのコンプライアンスは、展開された BitLocker ポリシーによって決まります。 デバイスの BitLocker 暗号化の状態を確認しようとしている場合は、これらの展開されたポリシーを確認する必要があります。

     

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam.md)

 

 





