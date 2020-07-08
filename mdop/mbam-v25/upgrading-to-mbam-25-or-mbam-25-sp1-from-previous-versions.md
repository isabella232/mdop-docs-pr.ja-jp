---
title: 以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード
description: 以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812754"
---
# 以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) サーバーと MBAM クライアントを以前のバージョンの MBAM からアップグレードするプロセスについて説明します。

**注** 以前のバージョンの MBAM から MBAM 2.5 または MBAM 2.5 SP1 に直接アップグレードすることができます。

 

## アップグレードを開始する前に


アップグレードを開始する前に、次の情報を確認してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">始める前に知っておくべきこと</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM web サイトを1つのサーバーと別のサーバー上の web サービスにインストールする場合は、Windows PowerShell コマンドレットを使用して構成する必要があります。</p></td>
<td align="left"><p>MBAM サーバーの構成ウィザードでは、1つのサーバーと別のサーバー上の web サービスで web サイトを構成することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 の MBAM 2.0 または 2.0 SP1 から MBAM 2.5 または 2.5 SP1 にアップグレードする場合は、次の操作を実行します。</p>
<p>インターネットインフォメーションサービス (IIS) がすでにインストールされている場合は、管理と監視の Web サイトとセルフサービスポータルは使用できません。</p>
<p>この問題が発生するのは、IIS をインストールした後で .NET Framework がインストールされた場合に、ASP.NET を IIS に正しく登録できないためです。</p></td>
<td align="left"><p><strong>この問題を解決するには、次の操作を行います。</strong></p>
<p><strong> </strong> 次の場所から aspnet_regiis – i を実行します。</p>
<p>C:\windows\microsoft.net\Framework\v4.0.30319</p>
<p>詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET IIS 登録ツール」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>次の条件がすべて満たされている場合は、アプリケーションプールアカウントに SPN を登録します。</p>
<ul>
<li><p>以前のバージョンの MBAM からアップグレードしようとしています。</p></li>
<li><p>現時点では、ロードバランスまたは分散構成で MBAM web サイトを実行していませんが、MBAM 2.5 または 2.5 SP1 にアップグレードした場合は、このようにします。</p></li>
</ul></td>
<td align="left"><p>手順については、「 <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> MBAM Web サイトをセキュリティで保護する方法を計画する」を参照してください </a> 。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>推奨事項</strong></p></td>
<td align="left"><p>コンピューターアカウントの Spn が既に登録されている場合でも、アプリケーションプールアカウントのサービスプリンシパル名 (SPN) を登録します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>推奨される理由</strong></p></td>
<td align="left"><p>負荷分散または分散構成で web サイトを構成するには、アプリケーションプールアカウントに SPN を登録する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>コンピューターアカウントで Spn が既に構成されている場合はどうなりますか?</strong></p></td>
<td align="left"><p>MBAM は、既に登録済みの Spn を使用します。追加の Spn を構成する必要はありませんが、負荷分散または分散構成で web サイトを構成することはできません。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## MBAM サーバーインフラストラクチャのアップグレード手順


スタンドアロントポロジまたは System Center Configuration Manager の統合トポロジ用に MBAM をアップグレードするには、次のセクションの手順を実行します。

**スタンドアロントポロジのために MBAM サーバーインフラストラクチャをアップグレードするには**

1.  以前のバージョンの MBAM を**プログラムと機能**および web サーバーからアンインストールして、情報が mbam クライアントから mbam インフラストラクチャに書き込まれないようにします。 手順について[は、「MBAM サーバーの機能またはソフトウェアの削除](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)」を参照してください。

2.  データベースをバックアップします。

3.  SQL server Reporting Services を使用して MBAM レポートをホストしている SQL Server など、**プログラムと機能**を使って、sql server から以前のバージョンの mbam をアンインストールします。 残りのすべての MBAM サーバーの一時ファイルまたはフォルダーをデータベースサーバーと reporting services から削除します。

    **注** データベースは削除されず、すべてのコンプライアンスデータと回復データはデータベースに保持されます。

     

4.  MBAM 2.5 または 2.5 SP1 のデータベース、レポート、および web アプリケーションをその順序でインストールして構成します。 データベースが適切にアップグレードされます。

5.  MBAM 2.5 テンプレートを使用してグループポリシーオブジェクト (Gpo) を更新し、暗号化の強制などの MBAM の新機能を利用します。 Gpo と MBAM クライアントを MBAM 2.5 に更新しない場合、以前のバージョンの MBAM クライアントは、機能が制限された現在の Gpo に対して引き続き報告されます。 最新の ADMX テンプレートをダウンロードするために、 [MDOP グループポリシー (admx) テンプレートを取得する方法](https://www.microsoft.com/download/details.aspx?id=41183)について説明します。

    MBAM サーバーインフラストラクチャをアップグレードした後、既存のクライアントコンピューターは、MBAM 2.5 または 2.5 SP1 サーバーに引き続き正常に報告し、回復データは保存されたままになります。

6.  最新の MBAM 2.5 または 2.5 SP1 クライアントをインストールします。 クライアントコンピューターは、展開後に再起動する必要はありません。

**System Center Configuration Manager の統合トポロジ用の MBAM インフラストラクチャをアップグレードするには**

1.  以前のバージョンの MBAM を**プログラムと機能**および web サーバーからアンインストールして、情報が mbam クライアントから mbam インフラストラクチャに書き込まれないようにします。 手順について[は、「MBAM サーバーの機能またはソフトウェアの削除](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)」を参照してください。

2.  データベースをバックアップします。

3.  SQL server Reporting Services を使用して MBAM レポートをホストしている SQL Server など、**プログラムと機能**を使って、sql server から以前のバージョンの mbam をアンインストールします。 残りのすべての MBAM サーバーの一時ファイルまたはフォルダーをデータベースサーバーと reporting services から削除します。

4.  Configuration Manager サーバーから MBAM をアンインストールします。

    **注** データベースと Configuration Manager オブジェクト (baseline、MBAM サポートされているコンピューターのコレクション、およびレポート) は削除されず、すべてのコンプライアンスデータと回復データはデータベースに保持されます。

     

5.  .Mof ファイルを更新します。

6.  MBAM 2.5 または 2.5 SP1 データベース、レポート、web アプリケーション、構成マネージャーの統合をその順序でインストールして構成します。 データベースと構成マネージャーのオブジェクトが適切にアップグレードされます。

7.  必要に応じて、[暗号化の強制] などの新しい機能を MBAM に実装する場合は、グループポリシーオブジェクト (Gpo) を更新し、設定を編集します。 Gpo を更新しない場合、MBAM は現在の Gpo に対して引き続き報告します。 最新の ADMX テンプレートをダウンロードするために、 [MDOP グループポリシー (admx) テンプレートを取得する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)について説明します。

    MBAM サーバーインフラストラクチャをアップグレードした後、既存のクライアントコンピューターは、MBAM 2.5 または 2.5 SP1 サーバーに引き続き正常に報告し、回復データは保存されたままになります。

8.  最新の MBAM 2.5 または 2.5 SP1 クライアントをインストールします。 クライアントコンピューターは、展開後に再起動する必要はありません。

## MBAM クライアントのアップグレードのサポート


MBAM は、以前のバージョンの MBAM クライアントから MBAM 2.5 クライアントへのアップグレードをサポートしています。

**MBAM クライアントをインストールする方法:**

-   Mbam クライアントを実行しているコンピューターを一度にすべて、または MBAM 2.5 Server インフラストラクチャのインストール後に段階的にアップグレードします。

-   電子ソフトウェア配布システムまたは Active Directory Domain Services または System Center Configuration Manager などのツールを使用して、MBAM クライアントをインストールします。



## 関連トピック


[MBAM 2.5 の展開](deploying-mbam-25.md)

[MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)

[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





