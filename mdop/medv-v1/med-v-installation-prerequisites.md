---
title: MED-V のインストールの前提条件
description: MED-V のインストールの前提条件
author: dansimp
ms.assetid: cf3c0906-23eb-4c4a-8951-a65741720f95
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2b432b8c2b06e171eb339aab6c7b15efb20d5919
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824967"
---
# MED-V のインストールの前提条件


次に、MED-V をインストールするための前提条件を示します。

[Active Directory の要件](#bkmk-activedirectoryrequirements)

[レポートデータベース](#bkmk-howtoinstallthereportdatabase)

[ウイルス対策/バックアップソフトウェアの構成](#bkmk-antivirusbackupsoftwareconfiguration)

[Microsoft Virtual PC 2007 SP1](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1)

## <a href="" id="bkmk-activedirectoryrequirements"></a>Active Directory の要件


ユーザーがサーバーが属しているドメインと同じドメインに属していない場合は、MED-V サーバーを構成するときに、ドメイン間に信頼を設定する必要があります。

## <a href="" id="bkmk-howtoinstallthereportdatabase"></a>レポートデータベースのインストール方法


すべての MED-V ワークスペースログを保存するには、レポートデータベースが必要です。 ログデータベースは、MED-V レポートを生成するために使用されます。 レポートの詳細については、「 [Med-v レポート](med-v-reporting.md)」を参照してください。

SQL Server は、MED-V サーバーまたはリモートサーバーと同じサーバーにインストールできます。 リモートサーバーにインストールする場合は、「[リモートサーバーに SQL server をインストール](#bkmk-installingsqlserveronaremoteserver)する」を参照してください。

### <a href="" id="bkmk-installingsqlserveronaremoteserver"></a>リモートサーバーへの SQL Server のインストール

**リモートサーバーに SQL Server をインストールするには**

1.  リモートサーバーで次のように構成します。

    -   インスタンス名—既定のインスタンス

    -   認証モード (混在モード)

    -   ユーザー: 作成された既定のユーザーは "sa" です。

    -   パスワード: 目的のパスワード

    -   照合順序の設定—既定

    -   利用状況レポートの設定でエラーが発生した場合 (既定)

2.  MED-V サーバーに次のファイルをインストールします。

    -   Microsoft SQL Server2008 の管理パックオブジェクトコレクションの前提条件をインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server2008 Native Client](https://go.microsoft.com/fwlink/?LinkId=164039)をダウンロードしてください。

    -   Microsoft SQL Server2005 の管理パックオブジェクトコレクションの前提条件をインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server2005 Native Client](https://go.microsoft.com/fwlink/?LinkId=164038)をダウンロードしてください。

    -   Microsoft SQL Server2008 に必要な dll ファイルをインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server 2008 管理オブジェクトコレクション](https://go.microsoft.com/fwlink/?LinkId=164041)をダウンロードします。

    -   Microsoft SQL Server2005 に必要な dll ファイルをインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server2005 管理オブジェクト](https://go.microsoft.com/fwlink/?LinkId=164040)をダウンロードします。

    -   SQL Server2008 の追加の値を提供する単体インストールパッケージをインストールするには、microsoft ダウンロードセンターから[MICROSOFT SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960)をダウンロードしてください。

    -   SQL Server2005 の追加の値を提供する単体インストールパッケージをインストールするには、Microsoft ダウンロードセンターから[MICROSOFT SQL Server2005 の Feature Pack]( https://go.microsoft.com/fwlink/?LinkId=163961)をダウンロードしてください。

    これらのファイルの詳細について[Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960)は、Microsoft ダウンロードセンター ( https://go.microsoft.com/fwlink/?LinkId=163960) または microsoft ダウンロードセンターの[機能パック Server2008 の feature](https://go.microsoft.com/fwlink/?LinkId=163961) pack () を参照してください https://go.microsoft.com/fwlink/?LinkId=163961) 。

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a>ウイルス対策/バックアップソフトウェアの構成


ウイルス対策によって仮想デスクトップのパフォーマンスが影響を受けないようにするには、ホストで実行されているすべてのウイルス対策またはバックアップ処理から、次の仮想マシンのファイルの種類を除外することをお勧めします。

-   \*..VMC

-   \*.VUD

-   \*.VSV

-   \*.CKM

-   \*.EVHD

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1"></a>Microsoft Virtual PC2007 SP1 をインストールして構成する方法


**重要** Windows 用仮想 PC がホストコンピューターに存在する場合は、Virtual PC2007 SP1 をインストールする前にアンインストールします。

 

**Microsoft Virtual PC2007 SP1 をインストールするには**

1.  Microsoft ダウンロードセンター [VIRTUAL PC 2007 sp1](https://go.microsoft.com/fwlink/?LinkId=142994)から VIRTUAL PC2007 SP1 をダウンロードします。

2.  ホストコンピューターでインストールファイルを実行し、ウィザードの指示に従います。

3.  昇格モードでホストコンピューターに Virtual PC2007 SP1 更新プログラムをインストールします。

    詳細については、「 [VIRTUAL PC 2007 SP1 の修正プログラムパッケージの説明](https://go.microsoft.com/fwlink/?LinkId=150575)」を参照してください。

    **注** Virtual PC2007 SP1 を実行するには、Virtual PC2007 SP1 更新プログラムが必要です。

     

## 関連トピック


[サポートされる構成](supported-configurationsmedv-orientation.md)

 

 





