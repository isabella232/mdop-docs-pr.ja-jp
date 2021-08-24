---
title: 単一サーバーに MBAM をインストールして構成する方法
description: 単一サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 45e6a012-6c8c-4d90-902c-d09de9a0cbea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4dffe2e2dcb82866b86a3ac281aca8a0dcaab686
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910662"
---
# <a name="how-to-install-and-configure-mbam-on-a-single-server"></a>単一サーバーに MBAM をインストールして構成する方法


このトピックの手順では、単一サーバー上のスタンドアロン トポロジに Microsoft BitLocker Administration and Monitoring (MBAM) をインストールする方法について説明します。 単一サーバー構成は、テスト環境でのみ使用します。 実稼働環境では、2 つ以上のサーバーを使用します。 Configuration Manager トポロジを使用して Microsoft BitLocker 管理と監視をインストールする場合は、「Deploying MBAM with Configuration [Manager」を参照してください](deploying-mbam-with-configuration-manager-mbam2.md)。

次の図は、単一サーバーアーキテクチャの例を示しています。 データベースと機能の説明については [、「MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md)のハイ レベル アーキテクチャ」を参照してください。

![mbam 2 単一サーバー展開トポロジ。](images/mbam2-1-server.gif)

各サーバー機能には、特定の前提条件があります。 前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには [、「MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations」を参照してください](mbam-20-supported-configurations-mbam-2.md)。 また、一部の機能には、機能を正常に展開するためにインストール プロセス中に提供する必要がある情報もあります。 MBAM 展開を開始 [する前に、「環境を MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md) 用に準備する」も参照してください。

**備考**  
セットアップ ログ ファイルを取得するには、Msiexec パッケージと **/L**場所オプションを使用して &lt; &gt; MBAM をインストールします。 ログ ファイルは、指定した場所に作成されます。

追加のセットアップ ログ ファイルは、MBAM をインストールしているユーザーのサーバー上の %temp% フォルダーに作成されます。



## <a name="to-install-mbam-server-features-on-a-single-server"></a>MBAM Server の機能を 1 つのサーバーにインストールするには


次の手順では、一般的な MBAM 機能をインストールする方法について説明します。

**MBAM Server の機能のインストールを開始するには**

1.  MBAM をインストールするサーバーで、MBAM インストール ウィザード **MBAMSetup.exeを実行 ** します。

2.  [ようこそ **] ページで** 、必要に応じて [カスタマー エクスペリエンス向上プログラム] **を選択**し、[スタート] を **クリックします**。

3.  Microsoft ソフトウェア 使用許諾契約書を読んで同意し、[次へ] をクリック **して** インストールを続行します。

4.  [トポロジ **の選択] ページ** で、スタンドアロン トポロジ **を選択し** 、[次へ] を **クリックします**。

5.  [インストール **する機能の選択] ページ** で、インストールする機能を選択します。 既定では、すべての MBAM 機能がインストール用に選択されています。 同じコンピューターにインストールする機能は、同時に一緒にインストールする必要があります。 他の場所にインストールする機能のチェック ボックスをオフにします。 MBAM 機能は、次の順序でインストールする必要があります。

    -   回復データベース

    -   コンプライアンスと監査データベース

    -   コンプライアンスレポートと監査レポート

    -   Self-Service サーバー

    -   管理および監視サーバー

    -   MBAM グループ ポリシー テンプレート

    **備考**  
    インストール ウィザードは、インストールの前提条件を確認し、不足している前提条件を表示します。 すべての前提条件が満たされている場合、インストールは続行されます。 不足している前提条件が検出された場合は、不足している前提条件を解決し、[前提条件の確認] を再度 **クリックする必要があります**。 この時点ですべての前提条件が満たされている場合は、インストールが再開されます。



6.  [ネットワーク通信 **セキュリティの構成** ] ページで、管理および監視サーバー上の Web サービスとクライアント間の通信を暗号化するかどうかを選択します。 通信を暗号化する場合は、暗号化に使用する証明機関によってプロビジョニングされた証明書を選択します。 このページで証明書を選択するには、この手順の前に証明書を作成する必要があります。

    **備考**  
    このページは、[インストールする機能の選択] ページで Self-Serviceポータルまたは管理および監視サーバー機能を選択した **場合にのみ表示** されます。



7.  [ **次へ**] をクリックし、次の一連の手順に進み、MBAM Server の機能を構成します。

**MBAM Server の機能を構成するには**

1.  [回復**データベースの構成**] ページで、復旧SQL Server格納するデータベースの名前を指定します。 また、データベース ファイルの場所とログ情報の場所の両方を指定する必要があります。

2.  **[Next]** をクリックして続行します。

3.  [コンプライアンス**と監査データベース**の構成] ページで、SQL Serverのインスタンス名と、コンプライアンスと監査データを格納するデータベースの名前を指定します。 また、データベース ファイルの場所とログ情報の場所を指定する必要があります。

4.  **[Next]** をクリックして続行します。

5.  [コンプライアンス**と**監査レポートの構成] ページで、コンプライアンスレポートと監査レポートをインストールする SQL Server Reporting Services インスタンスを指定し、コンプライアンスと監査データベースにアクセスするドメイン ユーザー アカウントとパスワードを指定します。 このアカウントのパスワードを有効期限が切れることはありません。 ユーザー アカウントは、MBAM Reports Users グループで使用できるすべてのデータにアクセスできる必要があります。

6.  **[Next]** をクリックして続行します。

7.  [ポータル **の構成Self-Service]** ページで、ポータルのポート番号、ホスト名、仮想ディレクトリ名、インストール パスをSelf-Serviceします。

    **備考**  
    一意のホスト ヘッダー名を指定しない限り、指定するポート番号は、管理サーバーと監視サーバーの未使用のポート番号である必要があります。 ファイアウォールを使用しているWindowsポートが自動的に開きます。



8.  **[Next]** をクリックして続行します。

9.  Microsoft Updates を使用してコンピューターのセキュリティを維持するかどうかを指定し、[次へ] を **クリックします**。 これにより、自動更新プログラムが有効Windows。

10. [管理 **と監視サーバーの構成** ] ページで、ヘルプ デスク Web サイトのポート番号、ホスト名、仮想ディレクトリ名、およびインストール パスを入力します。

    **備考**  
    一意のホスト ヘッダー名を指定しない限り、指定するポート番号は、管理サーバーと監視サーバーの未使用のポート番号である必要があります。 ファイアウォールを使用しているWindowsポートが自動的に開きます。



11. [インストール**の概要] ページ**で、インストールする機能の一覧を確認し、[**** インストール] をクリックして MBAM 機能のインストールを開始します。 インストール **設定を** 確認または変更する必要がある場合は、[戻る] をクリックしてウィザードに戻ります。または [キャンセル] をクリックして **セットアップを終了** します。 セットアップでは、MBAM 機能がインストールされ、インストールが完了したという通知が表示されます。

12. [ **完了] を** クリックしてウィザードを終了します。 Microsoft BitLocker Administration and Monitoring Server の機能がインストールされた後、次のセクションに進み、Microsoft BitLocker の管理と監視の役割にユーザーを追加する手順を完了します。 役割の詳細については [、「Planning for MBAM 2.0 Administrator Roles」を参照してください](planning-for-mbam-20-administrator-roles-mbam-2.md)。

**インストール後の構成を実行するには**

1.  管理および監視サーバーで、次のローカル グループにユーザーを追加して、MBAM ヘルプ デスク Web サイトの機能にアクセスできます。

    -   **MBAM ヘルプデスク ユーザー**: このローカル グループのメンバーは、MBAM 管理および監視 Web サイトでドライブの回復および TPM 機能の管理にアクセスできます。 ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスク ユーザーに必要なフィールドです。

    -   **MBAM Advanced Helpdesk Users**: このローカル グループのメンバーは、MBAM 管理および監視 Web サイトのドライブの回復機能と TPM の管理機能に高度にアクセスできます。 Advanced Helpdesk Users の場合、ドライブの回復には [ **キー ID]** フィールドだけが必要です。 [TPM の管理] で、[ **コンピューター ドメイン]** フィールドと [ **コンピューター名]** フィールドだけが必要です。

2.  管理および監視サーバーで、次のローカル グループにユーザーを追加して、MBAM 管理および監視 Web サイトのレポート機能にアクセスできます。

    -   **MBAM レポート ユーザー**: このローカル グループのメンバーは、MBAM 管理および監視 Web サイトのレポート機能にアクセスできます。

    -   会社名Self-Service通知テキスト、その他の会社固有の情報を使用して、ポータルポータルをブランド化します。 手順については、「How [to Brand the Self-Service ポータル」を参照してください](how-to-brand-the-self-service-portal.md)。

    **備考**  
    MBAM レポート ユーザー ローカル グループの同一のユーザーまたはグループ メンバーシップは **、MBAM** Administration and Monitoring Server の機能、コンプライアンスと監査データベース、コンプライアンスレポートと監査レポートがインストールされているすべてのコンピューターで維持する必要があります。 これを行う推奨される方法は、ドメイン セキュリティ グループを作成し、そのドメイン グループを各ローカル MBAM レポート ユーザー グループに追加する方法です。 このプロセスを使用する場合は、ドメイン グループを使用してグループ メンバーシップを管理します。



## <a name="validating-the-mbam-server-feature-installation"></a>MBAM Server 機能のインストールの検証


Microsoft BitLocker 管理と監視のインストールが完了したら、BitLocker 管理に必要なすべての MBAM 機能がインストールで正常にセットアップされたことを検証します。 MBAM サービスが機能しているのを確認するには、次の手順を実行します。

**MBAM Server 機能のインストールを検証するには**

1. MBAM 機能が展開されている各サーバーで、[コントロール パネル] **を開きます**。 [プログラム **] を**選択し、[プログラム] **をプログラムと機能**します。 Microsoft **BitLocker 管理と監視が** [管理] **リストに表示** プログラムと機能します。

   **備考**  
   インストールを検証するには、各サーバーにローカル コンピューターの管理資格情報を持つドメイン アカウントを使用する必要があります。



2. 回復データベースがインストールされているサーバーで、データベースを開SQL Server Management Studio **MBAM Recovery and Hardware**データベースがインストールされていることを確認します。

3. コンプライアンス データベースと監査データベースがインストールされているサーバーで、データベースを開SQL Server Management Studio **MBAM コンプライアンス**状態データベースがインストールされていることを確認します。

4. コンプライアンスレポートと監査レポートがインストールされているサーバーで、管理資格情報を使用して Web ブラウザーを開き、サイトの "ホーム" をSQL Server Reporting Servicesします。

   サイト インスタンスの既定のホームSQL Server Reporting Services <em> &lt; NameofMBAMReportsServer /Reports の http:// 場所 &gt; </em> にあります。 実際の URL を見つけるには、Reporting Services Configuration Manager ツールを使用し、セットアップ中に指定されたインスタンスを選択します。

   Microsoft BitLocker Administration and Monitoring という名前の Reports フォルダーに **、マルタDataSource** というデータ ソースが含まれており **、en-us** フォルダーに 4 つのレポートが含まれているか確認します。

   **備考**  
   名前付SQL Server Reporting Servicesとして構成されている場合、URL は次のようになります* &lt; 。nameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; * http://



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 管理と監視機能がインストールされているサーバーで、サーバー マネージャーを実行し **、[役割** ] を **参照します**。 [Web**サーバー (IIS)]** を選択し、[管理者] **(IIS) インターネット インフォメーション サービスをクリックします。**

6. [**接続] で、*** &lt; コンピューター &gt; 名を参照し*、[**サイト]** を選択し **、[Microsoft BitLocker の管理と監視] を選択します**。 **MBAMAdministrationService** **、MBAMUserSupportService、MBAMComplianceStatusService、** および**MBAMRecoveryAndHardwareService**が一覧表示されます。 ****

7. 管理と監視機能と Self-Service ポータルがインストールされているサーバーで、管理資格情報を使用して Web ブラウザーを開き、次の場所を参照して、正常に読み込まれます。

   -   *http:// &lt; &gt; /HelpDesk/default.aspx を* 選択し、ナビゲーションとレポートの各リンクを確認する

   -   *http:// &lt; &gt; /SelfService&gt;/*

   -   *http:// &lt; &gt; /MBAMAdministrationService/AdministrationService.svc*

   -   *http:// &lt; &gt; /MBAMUserSupportService/UserSupportService.svc*

   -   *http:// &lt; &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *http:// &lt; &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **備考**  
   サーバー機能は、ネットワーク暗号化なしで既定のポートにインストールされたと想定されます。 サーバー機能を別のポートまたは仮想ディレクトリにインストールした場合は、URL を変更して、適切なポート *(http:// ホスト名 &lt; : port &gt; &lt; &gt; /HelpDesk/default.asp*x または http:// ホスト名 : port* &lt; &gt; &lt; &gt; / &lt; virtualdirectory &gt; /default.aspx*など) を含める必要があります。

   サーバーの機能がネットワーク暗号化と一緒にインストールされている場合は、サーバーの http:// に https://。



## <a name="related-topics"></a>関連トピック


[MBAM 2.0 サーバー インフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









