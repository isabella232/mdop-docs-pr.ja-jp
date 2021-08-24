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
ms.openlocfilehash: 139980fb6712b40685a41bab45610da670803afa
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910622"
---
# <a name="illustrated-features-of-an-mbam-25-deployment"></a>MBAM 2.5 展開の機能の図


このトピックでは、次のトポロジの Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 展開を構成する個々の機能について説明します。

-   MBAM スタンドアロン

-   System Center Configuration Manager統合

**重要**  
これらの機能は、MBAM を展開する推奨アーキテクチャを表すのではありません。 この情報は、MBAM 展開を構成する個々の機能を理解するガイドとしてのみ使用してください。 [MBAM の推奨アーキテクチャについては、「MBAM 2.5](high-level-architecture-for-mbam-25.md)のハイレベル アーキテクチャ」を参照してください。



このトピックで説明するソフトウェアのサポートされているバージョンの一覧については [、「MBAM 2.5 サポートされる構成」を参照してください](mbam-25-supported-configurations.md)。

## <a name="mbam-stand-alone-topology"></a><a href="" id="bkmk-standalone"></a> MBAM スタンドアロン トポロジ


次の図と表では、MBAM スタンドアロン トポロジの機能について説明します。

![mbab2\-5。](images/mbam2-5-standalonecomponents.png)

|機能の種類|説明|Database (データベース)|
|-|-|-|
|回復データベース|このデータベースには、MBAM クライアント コンピューターから収集された回復データが格納されます。|この機能は、サーバーとサポートされているWindowsインスタンスを実行しているサーバー SQL Serverされます。|
|コンプライアンスと監査データベース|このデータベースにはコンプライアンス データが格納されます。このデータは、主にホストを構成するレポートSQL Server Reporting Servicesされます。|この機能は、サーバーとサポートされているWindowsインスタンスを実行しているサーバー SQL Serverされます。|
|コンプライアンスレポートと監査レポート|||
|Reporting Web Service|この Web サービスを使用すると、管理 Web サイトと監視 Web サイトと、レポート データSQL Server格納されているインスタンスとの間の通信が可能になります。|この機能は、サーバーを実行しているサーバー Windowsされます。|
|レポート Web サイト (管理および監視 Web サイト)|[管理と監視] Web サイトからレポートを表示します。 レポートは、企業内のクライアント コンピューターに関する回復監査とコンプライアンス状態データを提供します。|この機能は、サーバーを実行しているサーバー Windowsされます。|
|SQL Server Reporting Services (SSRS)|レポートは SSRS データベース インスタンスで構成されます。 レポートは、SSRS または管理および監視 Web サイトから直接表示できます。|この機能は、サーバーを実行しているサーバー Windows SSRS を実行しているサポートされているSQL Serverで構成されます。|
|Self-Service サーバー|||
|Self-Service Web サービス|この Web サービスは、MBAM クライアントと管理および監視 Web サイト、Self-Serviceデータベースと通信するために使用されます。|この機能は、サーバーを実行しているコンピューター Windowsされます。|
|Self-Service Web サイト (セルフサービス ポータル)|この Web サイトを使用すると、クライアント コンピューター上のエンド ユーザーは、BitLocker パスワードを紛失または忘れた場合に、Web サイトに個別にサインインして回復キーを取得できます。|この機能は、サーバーを実行しているコンピューター Windowsされます。|
|管理および監視サーバー|||
|Web サービスの管理と監視|監視 Web サービスは、MBAM クライアントと Web サイトがデータベースと通信するために使用します。|この機能は、サーバーを実行しているコンピューター Windowsされます。|

**重要**  
Self-Service Web サービスは、MBAM クライアント、管理および監視 Web サイト、および Self-Service ポータルが回復データベースと直接通信する Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 では使用できなくなりました。

**重要**  
MBAM クライアントと Web サイトが回復データベースと直接通信するために、Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 では監視 Web サービスを使用できなくなりました。


## <a name="system-center-configuration-manager-integration-topology"></a><a href="" id="bkmk-cmintegrated"></a>System Center Configuration Manager統合トポロジ

次の図と表は、統合トポロジの機能System Center Configuration Manager説明します。

![mbam2\-5。](images/mbam2-5-cmcomponents.png)

**重要**  
Self-Service Web サービスは、MBAM クライアント、管理および監視 Web サイト、および Self-Service ポータルが回復データベースと直接通信する Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 では使用できなくなりました。

**Warning**  
MBAM クライアントと Web サイトが回復データベースと直接通信するために、Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 では監視 Web サービスを使用できなくなりました。


|                        機能の種類                        |                                                                                                    説明                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Self-Service サーバー                     |                                                                                                                                                                                                                   |
|                  Self-Service Web サービス                  |                                                 この Web サービスは、MBAM クライアントと復旧データベースSelf-Serviceポータルによって使用されます。                                                  |
|                    Self-Service Web サイト                    |                          この Web サイトを使用すると、クライアント コンピューター上のエンド ユーザーは、BitLocker パスワードを紛失または忘れた場合に、Web サイトに個別にサインインして回復キーを取得できます。                          |
| サーバー/回復監査レポートの管理と監視 |                                                                                                                                                                                                                   |
|         Web サービスの管理と監視          |                               この Web サービスでは、管理 Web サイトと監視 Web サイトと、レポート データが格納SQL Serverデータベース間の通信が可能になります。                               |
|           管理と監視の Web サイト            | 回復監査レポートは、管理および監視 Web サイトから表示されます。 Configuration Manager コンソールを使用して、他のすべてのレポートを表示するか、レポートを直接表示SQL Server Reporting Services。 |
|                         データベース                          |                                                                                                                                                                                                                   |
|                     回復データベース                      |                                                                 このデータベースには、MBAM クライアント コンピューターから収集された回復データが格納されます。                                                                  |
|                       監査データベース                       |                                                                   このデータベースには、回復の試行とアクティビティに関する監査情報が格納されます。                                                                    |
|               Configuration Manager の機能               |                                                                                                                                                                                                                   |
|          Configuration Manager 管理コンソール          |                                                                   このコンソールは Configuration Manager に組み込み、レポートの表示に使用されます。                                                                   |
|               Configuration Manager レポート                |                                                             レポートには、エンタープライズ内のクライアント コンピューターのコンプライアンスと回復の監査データが表示されます。                                                              |
|               SQL Server Reporting Services                |                                                SSRS を使用すると、MBAM レポートが有効になります。 レポートは、SSRS または Configuration Manager コンソールから直接表示できます。                                                 |

## <a name="related-topics"></a>関連トピック

[MBAM 2.5 の高レベルのアーキテクチャ](high-level-architecture-for-mbam-25.md)

[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

## <a name="got-a-suggestion-for-mbam"></a>MBAM の提案を受け取った場合
- ここで提案を追加または投票 [します](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- MBAM の問題については [、MBAM TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




