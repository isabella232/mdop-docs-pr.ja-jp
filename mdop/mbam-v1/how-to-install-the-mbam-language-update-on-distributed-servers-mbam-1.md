---
title: 分散サーバーに MBAM Language Update をインストールする方法
description: 分散サーバーに MBAM Language Update をインストールする方法
author: dansimp
ms.assetid: 5ddc64c6-0417-4a04-843e-b5e18d9f1a52
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6758463c6fc038c4d6ea86c0d49804f29bb543d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825697"
---
# 分散サーバーに MBAM Language Update をインストールする方法


Microsoft BitLocker の管理と監視 (MBAM) には、1台以上のコンピューターで実行できる4つのサーバーの役割が含まれます。 ただし、mbam 1.0 言語リリースと MBAM ポリシーテンプレートのインストールをサポートする更新プログラムが必要なのは、MBAM Server の2つの機能だけです。 MBAM Server 機能が複数のコンピューターにインストールされている構成では、次のサーバー機能のみを更新する必要があります。

-   MBAM コンプライアンスと監査レポート

-   MBAM 管理と監視サーバー

**重要** MBAM server 機能は、まずコンプライアンスと監査レポートの順序で更新する必要があります。その後、管理と監視のサーバー。 MBAM グループポリシーテンプレートは、シーケンスを気にすることなくいつでも更新できます。

 

**MBAM コンプライアンスおよび監査レポートサーバー機能に MBAM 言語更新プログラムをインストールするには**

1.  MBAM コンプライアンスと監査レポート機能を実行しているコンピューターで、MBAM 言語更新セットアップウィザード (MBAMsetup.exe) を見つけて実行します。

2.  コンプライアンスおよび監査レポートのためのウィザードを完了して、ウィザードを閉じます。

**MBAM 管理および監視サーバー機能に MBAM 言語更新プログラムをインストールするには**

1.  MBAM 管理と監視機能を実行しているコンピューターで、インターネットインフォメーションサービス (IIS) 管理コンソールを開き、[**サイト**] に移動して、Microsoft BitLocker の管理と監視の web サイトを終了します。

2.  MBAM web サイトのバインドを編集して、サイトのバインドを変更します。 たとえば、ポートを443から9443に変更します。

3.  MBAM 言語更新セットアップウィザード (MBAMsetup.exe) を見つけて実行します。 [管理と監視] サーバー機能のウィザードを完了して、ウィザードを閉じます。

4.  サーバーデータベースをアップグレードしたら、IIS 管理コンソールを開き、Microsoft BitLocker の管理と監視の web サイトのバインドを確認します。

5.  古いバインドを削除して、残りのバインドに、MBAM enterprise 構成の正しいホスト名、証明書、およびポート番号が含まれていることを確認します。

6.  MBAM web サイトを再起動します。

7.  MBAM web サイトの機能をテストします。

    -   MBAM web インターフェイスを開き、クライアントの回復キーを取得できることを確認します。

    -   新規または手動で解読されたクライアントコンピューターの暗号化を強制します。

        **注** MBAM クライアントは、回復およびハードウェアデータベースと通信できる場合にのみ開かれます。

         

## 関連トピック


[MBAM 1.0 Language Release 更新プログラムの展開](deploying-the-mbam-10-language-release-update.md)

 

 





