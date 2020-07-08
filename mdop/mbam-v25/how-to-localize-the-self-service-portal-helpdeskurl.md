---
title: セルフサービス ポータルの "HelpdeskURL" をローカライズする方法
description: セルフサービス ポータルの "HelpdeskURL" をローカライズする方法
author: dansimp
ms.assetid: 86798460-077b-459b-8d54-4b605e07d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0d7ec4ce87bbe5aab56e9fa877ced5f51625a5dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826707"
---
# セルフサービス ポータルの "HelpdeskURL" をローカライズする方法


既定でエンドユーザーに表示するセルフサービスポータル URL のローカライズされたバージョンを構成することができます。 セルフサービスポータル URL は、パラメーター **Helpデスク url**で表されます。

次の手順で説明するように、ローカライズされたバージョンを作成すると、Microsoft BitLocker の管理と監視 (MBAM) でローカライズされたバージョンが検索されて表示されます。 MBAM でローカライズされたバージョンが見つからない場合は、パラメーター **Helpデスク url**に対して構成されている url が表示されます。

**注** 次の手順では、 *selfservice*がセルフサービスポータルの既定の仮想ディレクトリ名です。 セルフサービスポータルを構成したときに、別の名前が使用されている可能性があります。

 

**セルフサービスポータル URL をローカライズするには**

1.  セルフサービスポータルを構成したサーバーで、[**サイト**の管理]、[ &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **サービス** &gt; **アプリケーション設定**の監視] の各サイトに移動します。

2.  [**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。

3.  [**名前**] フィールドに「**ヘルプ**」と入力し &lt; *Language* &gt; ます。ここで、 &lt; *言語* &gt; は url の適切な言語コードです。

    たとえば、スペイン語でローカライズされた値のローカライズされたバージョンを作成するには、 `HelpdeskURL` パラメーターに「**ヘルプデスク url \ _es**という名前を指定します。

    言語フォルダーの名前は、 **es****の代わりに**言語のニュートラル名にすることもできます。 エンドユーザーのブラウザーが**es**に設定されていて、そのフォルダーが存在しない場合、(.net で定義されている) 親ロケールが再帰的に取得されてチェックされ、その &lt; 後、Mbam セルフサービスインストールディレクトリ &gt;\\SelfServiceWebsite\\es\\Notice.txt が、最終的に既定の Notice.txt ファイルになります。 この再帰的フォールバックは、.NET リソース読み込みルールを模倣します。

    使用できる有効な言語コードの一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。

4.  [**値**] フィールドに、エンドユーザーに対して表示するローカライズされたバージョンの値を入力し `HelpdeskURL` ます。



## 関連トピック


[組織のセルフサービス ポータルのカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)

 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




