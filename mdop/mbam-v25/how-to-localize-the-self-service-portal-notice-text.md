---
title: セルフサービス ポータルの通知テキストをローカライズする方法
description: セルフサービス ポータルの通知テキストをローカライズする方法
author: dansimp
ms.assetid: a4c878b7-e5c8-45af-a537-761bb2991659
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a2385f6b00713e7373bd1707b02324b80f300c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826714"
---
# セルフサービス ポータルの通知テキストをローカライズする方法


セルフサービスポータルで既定でエンドユーザーに表示する、ローカライズされた通知テキストを構成することができます。 通知テキストを表示する Notice.txt ファイルは、次のルートディレクトリにあります。

&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

ローカライズされた通知テキストを表示するには、ローカライズされた Notice.txt ファイルを作成し、次の例のディレクトリの特定の言語フォルダーに保存します。

&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

**注** [**アプリケーションの設定**] の**NoticeTextPath**アイテムを使用して、パスを構成できます。

 

MBAM 次のルールに基づいて、通知テキストが表示されます。

-   ローカライズされた**Notice.txt**ファイルを適切な言語フォルダーに作成すると、既定の**Notice.txt**ファイルが存在する場合、mbam にローカライズされた通知テキストが表示されます。 既定の**Notice.txt**ファイルが存在しない場合は、既定のファイルが存在しないことを示すメッセージが表示されます。

-   MBAM でローカライズされたバージョンの Notice.txt ファイルが見つからない場合は、既定の Notice.txt ファイルにテキストが表示されます。

-   MBAM が既定の Notice.txt ファイルを見つけられない場合は、セルフサービスポータルに既定のテキストが表示されます。

**注** エンドユーザーのブラウザーが、対応する言語のサブフォルダーまたは Notice.txt のない言語に設定されている場合、次のルートディレクトリにある Notice.txt ファイルのテキストが表示されます。

&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

 

**ローカライズされた Notice.txt ファイルを作成するには**

1.  セルフサービスポータルを構成したサーバー上で、次のようなディレクトリの例の言語フォルダーを作成し &lt; *Language* &gt; ます。ここでは、language はローカライズされた &lt; *Language* &gt; 言語の名前を表しています。

    &lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

    **注** 一部の言語フォルダーは既に存在するため、フォルダーを作成する必要はありません。 言語フォルダーを作成する必要がある場合は、言語フォルダーに使用できる有効な名前の一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」を参照してください &lt; *Language* &gt; 。

     

2.  ローカライズされた通知テキストを含む Notice.txt ファイルを作成します。

3.  Notice.txt ファイルを [言語] フォルダーに保存し &lt; *Language* &gt; ます。 たとえば、スペイン語でローカライズされた Notice.txt ファイルを作成するには、ローカライズされた Notice.txt ファイルを次の例のディレクトリに保存します。

    &lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\Es-es

    言語フォルダーの名前は、 **es****の代わりに**言語のニュートラル名にすることもできます。 エンドユーザーのブラウザーが**es**に設定されていて、そのフォルダーが存在しない場合、(.net で定義されている) 親ロケールが再帰的に取得されてチェックされ、その &lt; 後、Mbam セルフサービスインストールディレクトリ &gt;\\SelfServiceWebsite\\es\\Notice.txt が、最終的に既定の Notice.txt ファイルになります。 この再帰的フォールバックは、.NET リソース読み込みルールを模倣します。



## 関連トピック


[組織のセルフサービス ポータルのカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





