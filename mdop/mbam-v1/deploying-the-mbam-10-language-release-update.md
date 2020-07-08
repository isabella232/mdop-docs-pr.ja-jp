---
title: MBAM 1.0 Language Release 更新プログラムの展開
description: MBAM 1.0 Language Release 更新プログラムの展開
author: dansimp
ms.assetid: 9dbd85c3-e470-4752-a90f-25754dd46dab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a819be81594efd9349e3f6c0f6559c2b810bdc9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812826"
---
# MBAM 1.0 Language Release 更新プログラムの展開


Microsoft BitLocker の管理と監視 (MBAM) 1.0 言語リリースは、MBAM の更新プログラムで、新しい言語のサポートが含まれています。 新しい言語は次のとおりです。

-   英語 (en-us)

-   フランス語 (fr)

-   イタリア語 (it)

-   ドイツ語 (de)

-   スペイン語 (es)

-   韓国語 (ko)

-   日本語 (ja)

-   ポルトガル語 (ブラジル) (pt-br)

-   ロシア語 (ru)

-   繁体字中国語 (zh-cn&platform)

-   簡体字中国語 (zh-cn&platform)

MBAM 1.0 言語更新プログラムでは、バージョン番号が MBAM 1.0.1237.1 から MBAM 1.0.2001 に変更されます。

追加の言語を追加するために、すべての MBAM 機能を再インストールする必要はありません。 このトピックでは、新しくサポートされる言語を追加するために必要な手順について説明します。

## Mbam international release for MBAM Server 機能を導入する


まず、次の MBAM サーバー機能を更新する必要があります。

-   コンプライアンスと監査レポート

-   管理と監視サーバー

-   ポリシーテンプレート

次に、同じサーバー上で実行されている MBAM 機能を同時にアップグレードするには、 **MbamSetup.exe**を実行する必要があります。

[単一サーバーに MBAM Language Update をインストールする方法](how-to-install-the-mbam-language-update-on-a-single-server-mbam-1.md)

[分散サーバーに MBAM Language Update をインストールする方法](how-to-install-the-mbam-language-update-on-distributed-servers-mbam-1.md)

## グループポリシー用の MBAM 言語更新プログラムをインストールする


MBAM グループポリシーテンプレートは、各管理ワークステーションにインストールすることも、グループポリシーの中央ストアにコピーして、すべてのグループポリシーの管理者が使用できるようにすることもできます。 ポリシーテンプレートは、ドメインコントローラーに直接インストールすることはできません。 グループポリシーの中央ストアを使用していない場合は、MBAM グループポリシーを管理する各ドメインコントローラーにポリシーを手動でコピーする必要があります。

MBAM 言語ポリシーテンプレートを追加するには、"ポリシーテンプレート" ロールがワークステーションコンピューター上の同じ場所にインストールされているコンピューター上の%SystemRoot%\\PolicyDefinitions からグループポリシー言語ファイルをコピーします。 グループポリシーファイルの例をいくつか紹介します。

-   BitLockerManagement の admx

-   BitLockerUserManagement。 admx

-   en-us\\BitLockerManagement.adml

-   en-us\\BitLockerUserManagement.adml

-   fr-fr\\ BitLockerManagement

-   fr-fr\\ BitLockerUserManagement

-   (さらに、サポートされる言語にも同じ)

## MBAM インターナショナルリリースの既知の問題


このトピックでは、Microsoft BitLocker の管理と、国際リリースの監視に関する既知の問題について説明します。

[MBAM International Release の既知の問題](known-issues-in-the-mbam-international-release-mbam-1.md)

## MBAM 1.0 言語更新プログラムの展開に関するその他のリソース


[MBAM 1.0 の展開](deploying-mbam-10.md)

 

 





