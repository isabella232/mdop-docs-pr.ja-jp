---
title: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
description: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
author: dansimp
ms.assetid: dbd23b64-dff3-4913-9acd-affe67b9462e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9ea4afd6dd08f2040b9e2bd1e1a8998181d1e60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824614"
---
# 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法


Microsoft BitLocker の管理と監視 (MBAM) を使用して、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を判断できます。 次の手順では、紛失や盗難があった場合に、コンピューター上のボリュームが暗号化されているかどうかを判断する方法について説明します。

**紛失したコンピューターの最後の既知の BitLocker 暗号化の状態を確認するには**

1.  Web ブラウザーを開き、管理と監視の web サイトに移動します。

    **注** 注: 管理および監視 web サイトの既定のアドレスは http://* &lt; computername &gt; *です。 完全修飾サーバー名を使用すると、閲覧の結果が速くなります。

     

2.  ナビゲーションウィンドウで**レポート**ノードを選択し、[コンピューターの**コンプライアンスレポート**] を選択します。

3.  右側のウィンドウのフィルターフィールドを使って検索結果を絞り込んでから、[**検索**] をクリックします。 検索クエリの下に結果が表示されます。

4.  紛失したデバイスのポリシーによって決定される適切な操作を行います。

    **注** デバイスのコンプライアンスは、企業が展開した BitLocker ポリシーによって決定されます。 デバイスの BitLocker 暗号化の状態を確認する前に、展開されたポリシーを確認してください。

     

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





