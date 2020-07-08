---
title: MBAM 2.5 Web サイトを移動する方法
description: MBAM 2.5 Web サイトを移動する方法
author: dansimp
ms.assetid: 71af9a54-c27b-408f-9d75-37c0d02e730e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa5bd8156810b3dccc1588b4dfd4cadd96fd22fb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825747"
---
# MBAM 2.5 Web サイトを移動する方法


次の手順を使用して、次の MBAM web サイトを1台のコンピューターから別のコンピューターに移動します。つまり、サーバー A からサーバー B に次の機能を移動します。

-   管理と監視の Web サイト

-   セルフサービスポータル

**重要** 両方の web サイトの構成中に、現在使用しているものと同じ接続文字列、レポート URL、グループアカウント、および web サービスアプリケーションプールドメインアカウントを指定する必要があります。 同じ値を使用しないと、一部のサーバーにアクセスできません。 現在の値を取得する**には、Windows PowerShell**コマンドレットを使用します。

 

**管理と監視の Web サイトを別のサーバーに移動するには**

1.  サーバー B で、MBAM 2.5 サーバーソフトウェアをインストールします。 手順については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](installing-the-mbam-25-server-software.md)」を参照してください。

2.  サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**管理と監視の web サイト**] 機能のみを選択します。

    または、 **MbamWebApplication** Windows PowerShell コマンドレットを使用して、管理と監視の web サイトを構成することもできます。

    管理と監視の web サイトを構成する方法については、「 [MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)」を参照してください。

**セルフサービスポータルを別のサーバーに移動するには**

1.  サーバー B で、MBAM 2.5 サーバーソフトウェアをインストールします。 手順については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](installing-the-mbam-25-server-software.md)」を参照してください。

2.  サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**セルフサービスポータル**機能のみ] を選択します。

    または、 **MbamWebApplication** Windows PowerShell コマンドレットを使用して、セルフサービスポータルを構成することもできます。

    管理と監視の web サイトを構成する方法については、「 [MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)」を参照してください。

3.  組織内のクライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできない場合は、JavaScript ファイルも移動する必要があります。 [クライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできない場合に、セルフサービスポータルを構成する方法](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)について説明します。詳細については、こちらを参照してください。

4.  組織のセルフサービスポータルをカスタマイズします。 「[組織のためにセルフサービスポータルをカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)する」の手順に従って、現在のカスタマイズ内容を確認し、サーバー B のセルフサーバーポータルでカスタム設定を構成します。



## 関連トピック


[MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)

[Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[他のサーバーへの MBAM 2.5 機能の移行](moving-mbam-25-features-to-another-server.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





