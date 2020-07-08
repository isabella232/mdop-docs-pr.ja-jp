---
title: MBAM 2.5 Web アプリケーションを構成する方法
description: MBAM 2.5 Web アプリケーションを構成する方法
author: dansimp
ms.assetid: 909bf2d3-028c-4ac1-9247-171532a1eeae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0336d24f51167a00c8565ccd081f4bc5dfb2c4cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824497"
---
# MBAM 2.5 Web アプリケーションを構成する方法


このトピックでは、次のいずれかの方法を使用して、 [mbam 2.5 の推奨される高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)用に Microsoft BitLocker 管理および監視 (mbam) 2.5 web アプリケーションを構成する方法について説明します。

-   Windows PowerShell コマンドレット

-   MBAM サーバー構成ウィザード

Web アプリケーションは、次の web サイトと対応する web サービスを構成します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Web サイト</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理と監視の Web サイト</p></td>
<td align="left"><p>指定したユーザーが自分の PIN またはパスワードを忘れた場合に、エンドユーザーが自分のコンピューターを回復するのに役立つ web サイト</p></td>
</tr>
<tr class="even">
<td align="left"><p>セルフサービスポータル</p></td>
<td align="left"><p>エンドユーザーが PIN またはパスワードを忘れた場合に、自分のコンピューターにアクセスできる個別の web サイト</p></td>
</tr>
</tbody>
</table>



**構成を開始する前に、次の操作を行います。**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">手順を表示する場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM の推奨アーキテクチャを確認します。</p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 のアーキテクチャの概要</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM のサポートされている構成を確認します。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>各サーバーに必要な前提条件を完了します。</p>
<div class="alert">
<strong>注</strong><br/><p>管理と監視の Web サイトを構成する前に、Secure Sockets Layer (SSL) を使用するように SQL ServerReporting Services (SSRS) を構成していることを確認します。 それ以外の場合は、レポート機能で HTTPS の代わりに HTTP が使用されます。</p>
</div>
<div>

</div></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">MBAM 2.5 Server の前提条件構成マネージャーの統合トポロジにのみ適用されます </a> (該当する場合)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Web サイトのアプリケーションプールアカウントのサービスプリンシパル名 (Spn) を登録します。 この手順を実行する必要があるのは、Active Directory ドメインサービス (AD DS) で管理ドメインの権限を持っていない場合のみです。 AD DS でこれらの権限がある場合は、MBAM によって Spn が作成されます。</p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn)">MBAM Web サイトをセキュリティで保護する方法の計画</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</p>
<div class="alert">
<strong>注</strong><br/><p>あるサーバーと web サービスの両方に web サイトをインストールしようとしている場合、その web サイトを構成するには、 <strong> MbamWebApplication の Windows PowerShell コマンドレットを使用する必要があり </strong> ます。 MBAM サーバーの構成ウィザードでは、これらの項目を個別のサーバーで構成することはできません。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>コマンドレットを使用して MBAM Server 機能を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
</tr>
</tbody>
</table>



**Windows PowerShell を使用して web アプリケーションを構成するには**

1.  構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。

2.  Windows PowerShell を使用して web アプリケーションを構成するには、 **MbamWebApplication**コマンドレットを使用します。 このコマンドレットに関する情報を取得するには、「 **get-ヘルプの有効化-MbamWebApplication**」と入力します。

**ウィザードを使用してすべての web アプリケーションの設定を構成するには**

1. Web アプリケーションを構成するサーバーで、MBAM サーバー構成ウィザードを起動します。 [**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。

2. [**新しい機能の追加**] をクリックし、[**管理/監視 web サイト**] と [**セルフサービスポータル**] を選択して、[**次へ**] をクリックします。 Web アプリケーションのすべての前提条件が満たされていることがウィザードによってチェックされます。

3. 前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。 それ以外の場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。

4. ウィザードでフィールドの値を入力するには、次の説明を使用します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><strong>フィールド</strong></th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>セキュリティ証明書</strong></p></td>
   <td align="left"><p>以前に作成した証明書を選択して、web サービスと、web サイトを構成しているサーバー間の通信を暗号化することもできます。 [証明書を使用しない] を選択した場合 <strong> </strong> 、web 通信がセキュリティで保護されないことがあります。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>ホスト名</strong></p></td>
   <td align="left"><p>Web サイトを構成するホストコンピューターの名前。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>インストールパス</strong></p></td>
   <td align="left"><p>Web サイトをインストールするパス。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>Port</strong></p></td>
   <td align="left"><p>Web サイトとサービスの通信に使用するポート番号。</p>
   <div class="alert">
   <strong>注</strong><br/><p>指定したポートを介した通信を有効にするには、ファイアウォールの例外を設定する必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>Web サービスアプリケーションプールのドメインアカウントとパスワード</strong></p></td>
   <td align="left"><p>Web サービスアプリケーションプールのドメインユーザーアカウントとパスワード。</p>
   <p>[ <strong> データベースの構成] ページの [読み取り/書き込み権限ドメインユーザーまたはグループ] フィールドにユーザー名を入力した場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</p>
   <p>[ <strong> データベースの構成] ページの [読み取り/書き込みアクセスドメインユーザーまたはグループ] フィールドにグループ名を入力した場合 </strong> <strong> </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</p>
   <p>資格情報を指定しない場合、以前に有効になっていた web アプリケーションに指定された資格情報が使用されます。 すべての web アプリケーションは、同じアプリケーションプールの資格情報を使用する必要があります。 Web アプリケーションごとに異なる資格情報を指定すると、最後に指定された値が使用されます。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>セキュリティを向上させるには、資格情報で指定されているアカウントに、制限付きのユーザー権限を設定します。 また、アカウントのパスワードを無期限に設定します。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



5. 組み込みの IIS \ _IUSRS アカウントまたはアプリケーションプールアカウントが、[**認証後にクライアントを偽装**する] および **[バッチジョブ**のローカルセキュリティ設定] に追加されていることを確認します。

   ローカルセキュリティ設定に追加されているかどうかを確認するには、**ローカルセキュリティポリシーエディター**を開き、[**ローカルポリシー** ] ノードを展開し、[**ユーザー権利の割り当て**] ノードをクリックして、右側のウィンドウで [**認証後にクライアントを偽装**し、**バッチジョブとしてログオンする**] をダブルクリックします。

**ウィザードを使用してデータベースの接続情報を構成するには**

1.  次のフィールドの説明を使用して、コンプライアンスと監査データベース用にウィザードの接続情報を構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">フィールド</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>SQL Server 名</strong></p></td>
    <td align="left"><p>コンプライアンスと監査データベースが構成されているサーバーの名前。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server データベースインスタンス</strong></p></td>
    <td align="left"><p>コンプライアンスと監査データベースが構成されている SQL Server インスタンスの名前。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>データベース名</strong></p></td>
    <td align="left"><p>コンプライアンスおよび監査データベースの名前。</p></td>
    </tr>
    </tbody>
    </table>



2.  次のフィールドの説明を使用して、回復データベースのウィザードで接続情報を構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">フィールド</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>SQL Server 名</strong></p></td>
    <td align="left"><p>回復データベースが構成されているサーバーの名前。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server データベースインスタンス</strong></p></td>
    <td align="left"><p>回復データベースが構成されている SQL Server インスタンスの名前。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>データベース名</strong></p></td>
    <td align="left"><p>回復データベースの名前。</p></td>
    </tr>
    </tbody>
    </table>



**ウィザードを使用して web アプリケーションを構成するには**

1. 次の説明を使用して、管理と監視の Web サイトを構成するためのウィザードのフィールド値を入力します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">フィールド</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>高度なヘルプデスクの役割ドメイングループ</strong></p></td>
   <td align="left"><p>メンバーが [レポート] 領域以外の管理および監視 Web サイトのすべての領域にアクセスできるドメインユーザーグループ。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>ヘルプデスクの役割ドメイングループ</strong></p></td>
   <td align="left"><p><strong> </strong> <strong> </strong> 管理と監視 web サイトの TPM およびドライブの回復領域にアクセスできるメンバーのドメインユーザーグループ。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>System Center Configuration Manager の統合を使用する</strong></p></td>
   <td align="left"><p>Configuration Manager の統合トポロジで MBAM を構成する場合は、このチェックボックスをオンにします。 このチェックボックスをオンにすると、管理と監視の Web サイトではなく、構成マネージャーに表示される回復監査レポートを除くすべてのレポートが作成されます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>レポート役割のドメイングループ</strong></p></td>
   <td align="left"><p>管理と監視の Web サイトの [レポート] 領域に対する読み取り専用アクセス権を持つメンバーのドメインユーザーグループ。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server Reporting Services の URL</strong></p></td>
   <td align="left"><p>MBAM レポートが構成されている SSRS サーバーの URL です。</p>
   <p>レポート Url の例:</p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">ホスト名の種類</th>
   <th align="left">例</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>完全修飾ドメイン名の例</p></td>
   <td align="left"><p><a href="https://MyReportServer.Contoso.com/ReportServer" data-raw-source="https://MyReportServer.Contoso.com/ReportServer">https://MyReportServer.Contoso.com/ReportServer</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>カスタムホスト名を使用した例</p></td>
   <td align="left"><p><a href="https://MyReportServer/ReportServer" data-raw-source="https://MyReportServer/ReportServer">https://MyReportServer/ReportServer</a></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>仮想ディレクトリ</strong></p></td>
   <td align="left"><p>管理と監視の Web サイトの仮想ディレクトリ。 この名前は、サーバー上の web サイトの物理ディレクトリに対応し、web サイトのホスト名に追加されます。たとえば、次のようになります。</p>
   <p>http (s)// &lt; <em> hostname </em> &gt; : &lt; <em> port/ </em> &gt; helpデスク/</p>
   <p>仮想ディレクトリを指定しない場合は、値の <strong> ヘルプデスク </strong> が使用されます。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>データ移行役割ドメイングループ </strong> (オプション)</p></td>
   <td align="left"><p>メンバーが書き込み用の Mbam * Information コマンドレットを使用して、このエンドポイントを介して回復情報を書くためのアクセス権を持つドメインユーザーグループ。</p></td>
   </tr>
   </tbody>
   </table>



2. 次の説明を使用して、セルフサービスポータルを構成するためのウィザードのフィールド値を入力します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">フィールド</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>仮想ディレクトリ</strong></p></td>
   <td align="left"><p>Web アプリケーションの仮想ディレクトリ。 この名前は、サーバー上の web サイトの物理ディレクトリに対応し、web サイトのホスト名に追加されます。たとえば、次のように指定します。</p>
   <p>http (s):// &lt; <em> hostname </em> &gt; : &lt; <em> port </em> &gt; /selfservice/</p>
   <p>仮想ディレクトリを指定しない場合は、値 <strong> selfservice </strong> が使用されます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>会社名</p></td>
   <td align="left"><p>セルフサービスポータルの会社名を指定します。たとえば、次のようにします。</p>
   <p>Contoso IT</p>
   <p>この会社名は、すべてのセルフサービスポータルユーザーによって表示されます。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ヘルプデスクの URL テキスト</p></td>
   <td align="left"><p>組織のヘルプデスクの web サイトにユーザーを誘導するテキストステートメントを指定します。たとえば、次のように指定します。</p>
   <p>ヘルプデスクまたは IT 部門に問い合わせる</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ヘルプデスクの URL</p></td>
   <td align="left"><p>組織のヘルプデスクの web サイトの URL を指定します。例:</p>
   <p>http (s)/会社 &lt; <em> ヘルプの url</em>&gt;/</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>お知らせのテキストファイル</p></td>
   <td align="left"><p>セルフサービスポータルのランディングページで、ユーザーに表示する通知が含まれているファイルを選択します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ユーザーに通知テキストを表示しない</p></td>
   <td align="left"><p>通知テキストがユーザーに表示されないように指定するには、このチェックボックスをオンにします。</p></td>
   </tr>
   </tbody>
   </table>



3. 入力が完了したら、[**次へ**] をクリックします。

   Web アプリケーションのすべての前提条件が満たされていることがウィザードによってチェックされます。

4. **[Next]** をクリックして続行します。

5. [**概要**] ページで、追加される機能を確認します。

   **注**  
   作成したエントリ用に Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。



6. [**追加**] をクリックして web アプリケーションをサーバーに追加し、[**閉じる**] をクリックします。

   ユーザー設定の通知テキスト、会社名、詳細情報へのポインターなどを追加してセルフサービスポータルをカスタマイズする方法については、「[組織のためのセルフサービスポータルのカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)」を参照してください。

**クライアントコンピューターが CDN にアクセスできない場合にセルフサービスポータルを構成するには**

1.  Microsoft BitLocker 管理および監視 (MBAM) 2.5 SP1 を実行しているかどうかを確認します。 その場合は、何も行いません。 セルフサービスポータルの構成が完了しました。

    **注**  
    Microsoft BitLocker 管理と監視 (MBAM) 2.5 SP1 は、セットアップで JavaScript ファイルをインストールするため、Microsoft Ajax コンテンツ配信ネットワークに接続しなくても、セルフサービスポータルを構成する必要はありません。 次の手順は、SP1 より前のバージョンの Microsoft BitLocker 管理および監視 (MBAM) 2.5 を使用している場合にのみ必要です。



2.  クライアントコンピューターが Microsoft Ajax コンテンツ配信ネットワーク (CDN) にアクセスできるかどうかを確認します。

    CDN は、特定の JavaScript ファイルに必要なアクセス権をセルフサービスポータルに提供します。 クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成しないと、会社名とエンドユーザーがサインインしたアカウントは表示されません。 エラーメッセージは表示されません。

3.  次のいずれかの操作を行います。

    -   クライアントコンピューターで CDN にアクセスできる場合は、何も行いません。 セルフサービスポータルの構成が完了しました。

    -   クライアントコンピューターが CDN にアクセスできない場合は、[クライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできないときに、セルフサービスポータルを構成する](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)手順を実行します。


## 関連トピック


[サーバーのイベント ログ](server-event-logs.md)

[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

[クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)

[組織のセルフサービス ポータルのカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)

[MBAM 2.5 サーバー機能の構成の確認](validating-the-mbam-25-server-feature-configuration.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





