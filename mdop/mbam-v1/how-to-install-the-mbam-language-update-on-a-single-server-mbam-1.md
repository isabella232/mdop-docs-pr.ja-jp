---
title: 単一サーバーに MBAM Language Update をインストールする方法
description: 単一サーバーに MBAM Language Update をインストールする方法
author: dansimp
ms.assetid: e6fe59a3-a3e1-455c-a059-1f23ee083cf6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94814158335430aba433c180cdba83d0cf15b760
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824754"
---
# 単一サーバーに MBAM Language Update をインストールする方法


Microsoft BitLocker の管理と監視 (MBAM) には、1台以上のコンピューターで実行できる4つのサーバーの役割が含まれます。 ただし、mbam 1.0 言語リリースと MBAM ポリシーテンプレートのインストールをサポートするには、MBAM Server の2つの機能のみを更新する必要があります。 1台のコンピューターにインストールされる必要がある3つのすべての MBAM 機能を更新するには、このトピックで説明する手順を実行します。

**1台のサーバーに MBAM 言語更新プログラムをインストールするには**

1.  インターネットインフォメーションサービス (IIS) 管理コンソールを開き、[**サイト**] に移動して、Microsoft BitLocker の管理と監視の web サイトを終了します。

2.  MBAM web サイトのバインドを編集してから、サイトのバインドを一時的に変更します。 たとえば、ポートを443から9443に変更します。

3.  MBAM セットアップウィザード (MBAMsetup.exe) を見つけて実行し、次の3つの機能を選びます。

    1.  コンプライアンスと監査レポート

    2.  管理と監視サーバー

    3.  グループポリシーテンプレート

    **重要** MBAM server 機能は、次の順序で更新する必要があります: 最初にコンプライアンスと監査レポート、次に管理と監視サーバー。 グループポリシーテンプレートは、シーケンスを気にすることなくいつでも更新できます。

     

4.  サーバーデータベースをアップグレードしたら、IIS 管理コンソールを開いて、Microsoft BitLocker の管理と監視の web サイトのバインドを確認します。

5.  バインドの1つを削除して、残りのバインドに MBAM enterprise 構成の正しいホスト名、証明書、およびポート番号が含まれていることを確認します。

6.  MBAM web サイトを再起動します。

7.  MBAM web サイトの機能をテストします。

    -   MBAM web インターフェイスを開き、クライアントの回復キーを取得できることを確認します。

    -   新規または手動で解読されたクライアントコンピューターの暗号化を強制します。

        **注** MBAM クライアントは、回復およびハードウェアデータベースと通信できる場合にのみ開かれます。

         

## 関連トピック


[MBAM 1.0 Language Release 更新プログラムの展開](deploying-the-mbam-10-language-release-update.md)

 

 





