---
title: MBAM 2.5 展開の機能の図
description: MBAM 2.5 展開の機能の図
author: dansimp
ms.assetid: 7b5eff42-af8c-4bd0-a20a-18cc2e779f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: c3b205d4f0b4b18cf8bdbf51982b5a59e5e1b9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812395"
---
# MBAM 2.5 展開の機能の図


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) 2.5 の展開を構成する、次のトポロジの各機能について説明します。

-   MBAM スタンドアロン

-   System Center Configuration Manager の統合

**重要**  
これらの機能は、MBAM の展開に推奨されるアーキテクチャを示すものではありません。 この情報は、MBAM 展開を構成する個々の機能を理解するためのガイドとしてのみ使用してください。 MBAM の推奨アーキテクチャについては、「 [mbam 2.5 の高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)」を参照してください。



このトピックで説明しているソフトウェアのサポートされているバージョンの一覧については、「 [Mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。

## <a href="" id="bkmk-standalone"></a> MBAM スタンドアロントポロジ


次の画像と表では、MBAM スタンドアロントポロジの機能について説明します。

![mbab2\-5](images/mbam2-5-standalonecomponents.png)

|機能の種類|説明|Database (データベース)|
|-|-|-|
|回復用データベース|このデータベースには、MBAM クライアントコンピューターから収集された回復データが格納されます。|この機能は、Windows Server を実行しているサーバーとサポートされている SQL Server インスタンスで構成されています。|
|コンプライアンスと監査データベース|このデータベースには、主に SQL Server Reporting Services ホストのレポートに使用されるコンプライアンスデータが格納されます。|この機能は、Windows Server を実行しているサーバーとサポートされている SQL Server インスタンスで構成されています。|
|コンプライアンスと監査レポート|||
|レポート Web サービス|この web サービスにより、管理と監視の Web サイトと、レポートデータが保存されている SQL Server インスタンスの間の通信が可能になります。|この機能は、Windows Server が実行されているサーバーにインストールされています。|
|レポート Web サイト (管理と監視の Web サイト)|管理と監視の Web サイトからレポートを表示します。 レポートは、企業内のクライアントコンピューターに関する回復監査およびコンプライアンスステータスのデータを提供します。|この機能は、Windows Server が実行されているサーバーで構成されています。|
|SQL Server Reporting Services (SSRS)|レポートは、SSRS データベースインスタンスで構成されます。 レポートは、SSRS から直接表示することも、管理と監視の Web サイトから表示することもできます。|この機能は、Windows Server を実行しているサーバーと、SSRS を実行しているサポートされている SQL Server インスタンスで構成されています。|
|セルフサービスサーバー|||
|セルフサービス Web サービス|この web サービスは、MBAM クライアントと、管理/モニタリング Web サイトとセルフサービスポータルで、回復用データベースと通信するために使用されます。|この機能は、Windows Server が実行されているコンピューターにインストールされています。|
|セルフサービス Web サイト (セルフサービスポータル)|この web サイトでは、クライアントコンピューターのエンドユーザーが、自分の BitLocker パスワードを紛失または忘れた場合に、回復キーを取得するために、web サイトに個別にサインインすることを可能にします。|この機能は、Windows Server が実行されているコンピューターで構成されます。|
|管理と監視サーバー|||
|管理と監視 Web サービス|この監視 Web サービスは、MBAM クライアントと web サイトでデータベースと通信するために使用されます。|この機能は、Windows Server が実行されているコンピューターにインストールされています。|

**重要**  
このセルフサービス Web サービスは、Microsoft BitLocker の管理と監視 (MBAM) 2.5 SP1 では利用できなくなりました。 MBAM クライアント、管理と監視の Web サイト、セルフサービスポータルが回復用データベースと直接通信します。

**重要**  
MBAM クライアントと web サイトが回復データベースと直接通信しているため、監視 Web サービスは Microsoft BitLocker 管理および監視 (MBAM) 2.5 SP1 では利用できなくなりました。


## <a href="" id="bkmk-cmintegrated"></a>System Center Configuration Manager の統合トポロジ

次の画像と表では、System Center Configuration Manager の統合トポロジの機能について説明します。

![mbam2\-5](images/mbam2-5-cmcomponents.png)

**重要**  
このセルフサービス Web サービスは、Microsoft BitLocker の管理と監視 (MBAM) 2.5 SP1 では利用できなくなりました。 MBAM クライアント、管理と監視の Web サイト、セルフサービスポータルが回復用データベースと直接通信します。

**Warning**  
MBAM クライアントと web サイトが回復データベースと直接通信しているため、監視 Web サービスは Microsoft BitLocker 管理および監視 (MBAM) 2.5 SP1 では利用できなくなりました。


|                        機能の種類                        |                                                                                                    説明                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    セルフサービスサーバー                     |                                                                                                                                                                                                                   |
|                  セルフサービス Web サービス                  |                                                 この web サービスは、MBAM クライアントとセルフサービスポータルで、回復用データベースと通信するために使用されます。                                                  |
|                    セルフサービス Web サイト                    |                          この web サイトでは、クライアントコンピューターのエンドユーザーが、自分の BitLocker パスワードを紛失または忘れた場合に、回復キーを取得するために、web サイトに個別にサインインすることを可能にします。                          |
| 管理と監視サーバー/回復監査レポート |                                                                                                                                                                                                                   |
|         管理と監視 Web サービス          |                               この web サービスにより、管理と監視の Web サイトと、レポートデータが保存されている SQL Server データベースの間の通信が可能になります。                               |
|           管理と監視の Web サイト            | 回復監査レポートは、管理と監視の Web サイトから表示されます。 Configuration Manager コンソールを使用して、他のすべてのレポートを表示したり、SQL Server Reporting Services から直接レポートを表示したりします。 |
|                         データベース                          |                                                                                                                                                                                                                   |
|                     回復用データベース                      |                                                                 このデータベースには、MBAM クライアントコンピューターから収集された回復データが格納されます。                                                                  |
|                       監査データベース                       |                                                                   このデータベースには、回復の試行とアクティビティに関する監査情報が格納されます。                                                                    |
|               Configuration Manager の機能               |                                                                                                                                                                                                                   |
|          Configuration Manager の管理コンソール          |                                                                   この本体は構成マネージャーに組み込まれており、レポートの表示に使用されます。                                                                   |
|               Configuration Manager のレポート                |                                                             レポートには、企業内のクライアントコンピューターのコンプライアンスと回復の監査データが表示されます。                                                              |
|               SQL Server Reporting Services                |                                                SSRS は、MBAM レポートを有効にします。 レポートは、SSRS から直接表示することも、Configuration Manager コンソールから直接表示することもできます。                                                 |

## 関連トピック

[MBAM 2.5 のアーキテクチャの概要](high-level-architecture-for-mbam-25.md)

[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




