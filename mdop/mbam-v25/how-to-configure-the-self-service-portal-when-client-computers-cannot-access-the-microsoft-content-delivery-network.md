---
title: クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法
description: クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法
author: dansimp
ms.assetid: 90ee76db-9876-41b5-994a-118556d5ed3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ffce3dd023cb6ff9bd5cdb13ea789b348661de24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824494"
---
# クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法


組織内のクライアントコンピューターが Microsoft Ajax コンテンツ配信ネットワーク (CDN) にアクセスできない場合は、次の手順に従います。

**構成が必要な理由:**

クライアントコンピューターは CDN にアクセスする必要があります。これにより、セルフサービスポータルで、特定の JavaScript ファイルに必要なアクセス権が付与されます。 クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成しないと、会社名とエンドユーザーがログインするアカウントのみが表示されます。 エラーメッセージは表示されません。

**注** MBAM 2.5 SP1 では、JavaScript ファイルは製品に含まれており、このセクションの手順に従って、インターネットにアクセスできないクライアントをサポートするように SSP を構成する必要はありません。

 

**クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成する方法**

1. CDN から次の JavaScript ファイルをダウンロードします。

   -   [jQuery-1.10.2.min.js](https://go.microsoft.com/fwlink/?LinkID=390515)

   -   [jQuery.validate.min.js](https://go.microsoft.com/fwlink/?LinkID=390516)

   -   [jQuery.validate.unobtrusive.min.js](https://go.microsoft.com/fwlink/?LinkID=390517)

2. JavaScript ファイルをセルフサービスポータルの**Scripts**ディレクトリにコピーします。 このディレクトリは、 <em> &lt; mbam セルフサービスインストールディレクトリ &gt; \\ </em> セルフサービス Website\\Scripts. にあります。

3. インターネットインフォメーションサービス (IIS) マネージャーを開きます。

4. **Sites** &gt; **Microsoft BitLocker の管理と監視**を展開し、[ **selfservice**] を強調表示します。

   **注**  
   *Selfservice*は、既定の仮想ディレクトリ名です。 構成時にこのディレクトリに別の名前を選択した場合は、次の手順の*Selfservice*を、選択した名前に置き換えてください。

     

5. 中央のウィンドウで、[アプリケーションの**設定**] をダブルクリックします。

6. 次のリストの各アイテムについて、新しい場所を参照するようにアプリケーションの設定を編集します。これには、/ &lt; *virtual directory* &gt; selfservice/(または構成時に選択した任意の名前) を使用します。 たとえば、仮想ディレクトリのパスは、/Selfservice/スクリプト/jQuery-1.10.2.min.js に似ています。

   -   jQueryPath:/ &lt; *virtual directory*/ &gt; スクリプト/jQuery-1.10.2.min.js

   -   jQueryValidatePath:/ &lt; *virtual directory*/ &gt; スクリプト/jQuery.validate.min.js

   -   jQueryValidateUnobtrusivePath:/ &lt; *virtual directory*/ &gt; スクリプト/jQuery.validate.unobtrusive.min.js



## 関連トピック


[MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





