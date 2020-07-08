---
title: MBAM 1.0 の評価
description: MBAM 1.0 の評価
author: dansimp
ms.assetid: a1e2b674-eda9-4e1c-9b4c-e748470c71f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f09b06af52f5738fd50bfe727987b760d98552d9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825254"
---
# MBAM 1.0 の評価


Microsoft BitLocker の管理と監視 (MBAM) を運用環境に展開する前に、ラボ環境で評価する必要があります。 このトピックの情報を使用して、評価目的に限って、1つのサーバーラボ環境で MBAM を設定することができます。

実際の展開手順は、「 [1 台のサーバーに MBAM をインストールして構成する方法](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)」で説明されているシナリオと非常に似ていますが、このトピックには、mbam 評価環境を最小限に設定できるようにするための追加情報が含まれています。

## ラボ環境のセットアップ


テスト環境で評価するために MBAM の非運用インスタンスを設定する場合でも、展開の前提条件とハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。 詳細については、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。 MBAM 評価版の展開を始める前に、 [mbam 1.0 の環境の準備](preparing-your-environment-for-mbam-10.md)も確認しておく必要があります。

### MBAM 評価版の展開を計画する

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">タスク</th>
<th align="left">参照先</th>
<th align="left">備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>展開計画を開始する前に、MBAM の概要情報を確認して、製品について基本的な理解を深めてください。</p></td>
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)">MBAM 1.0 をお使いになる前に</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p></p>
<p>MBAM インストール用にコンピューティング環境を準備します。 これを行うには、MBAM データベースをホストする SQL Server インスタンスで、透過データ暗号化 (TDE) を有効にする必要があります。 ラボ環境で TDE を有効にするには、MBAM が使用する SQL Server のインスタンスでホストされている master データベースに対して実行する .sql ファイルを作成できます。</p>
<div class="alert">
<strong>注</strong><br/><p>次の例を使用して、使用しているラボ環境の .sql ファイルを作成して、MBAM データベースをホストする SQL Server インスタンスの TDE をすばやく有効にすることができます。 これらの SQL Server コマンドは、ローカルに署名された SQL Server 証明書を使用して、TDE を有効にします。 TDE 証明書とそれに関連付けられた暗号化キーを、C:\Backup のローカルバックアップパスの例にバックアップしてください <em> </em> 。 データベースを復元する場合、または、証明書とキーを TDE 暗号化が設定されている別のサーバーに移動する場合は、TDE 証明書とキーが必要です。</p>
</div>
<div>

</div>
<pre class="syntax" space="preserve"><code>USE master;
GO
CREATE MASTER KEY ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;;
GO
CREATE CERTIFICATE tdeCert WITH SUBJECT = &#39;TDE Certificate&#39;;
GO
BACKUP CERTIFICATE tdeCert TO FILE = &#39;C:\Backup\TDECertificate.cer&#39;
   WITH PRIVATE KEY (
         FILE = &#39;C:\Backup\TDECertificateKey.pvk&#39;,
         ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;);
GO</code></pre></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)">MBAM 1.0 展開の前提条件</a></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=269703" data-raw-source="[Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703)">SQL Server 2008 Enterprise Edition のデータベース暗号化</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM グループポリシー要件を計画して構成します。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)">MBAM 1.0 グループ ポリシー要件の計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な Active Directory ドメインサービスセキュリティグループを計画して作成し、MBAM ローカルセキュリティグループのメンバーシップ要件を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">MBAM 1.0 管理者ロールの計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM サーバー機能の展開を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)">MBAM 1.0 サーバーの展開計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアントの展開を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)">MBAM 1.0 クライアントの展開計画</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### MBAM 評価版の展開を実行する

MBAM のインストールのために、必要な計画とソフトウェアの前提条件のインストールが完了したら、MBAM 評価の展開を開始できます。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM でサポートされている構成情報を確認して、使用しているクライアントとサーバーコンピューターが MBAM 機能のインストールでサポートされていることを確認します。</p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)">MBAM 1.0 がサポートされる構成</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM セットアップを実行して、評価目的で MBAM Server 機能を1台のサーバーに展開します。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)">単一サーバーに MBAM をインストールして構成する方法</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>計画フェーズで作成した Active Directory ドメインサービスセキュリティグループを、新しい MBAM サーバー上の適切なローカルの MBAM サーバー機能ローカルグループに追加します。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">MBAM 1.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> Mbam 管理者ロールの管理方法</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な MBAM グループポリシーオブジェクトを作成して展開します。</p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)">MBAM 1.0 グループ ポリシー オブジェクトの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアントソフトウェアを展開します。</p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)">MBAM 1.0 クライアントの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## MBAM 評価用にラボコンピューターを構成する


MBAM クライアントステータスレポートの頻度設定は、レジストリエディターを使って変更できます。 ただし、これらの変更はテスト目的でのみ使用してください。

**Warning**  
このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。 Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。 レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。 Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。 レジストリは、自分の責任において変更してください。



### <a href="" id="modify-the-frequency-settings-on-mbam-client-status-reporting-"></a>MBAM クライアントステータスレポートの頻度の設定を変更する

MBAM クライアントのスリープ解除とステータスレポートの頻度は、グループポリシーを使用するように設定されている場合、最小値で90分の値になります。 MBAM クライアントコンピューターでは、これらの頻度を変更することができます。これは、テストを高速化するのに役立ちます。 MBAM クライアントステータスレポートの頻度の設定を変更するには、レジストリエディターを使用して**HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**に移動し、クライアントでサポートされている最小値として**ClientWakeupFrequency**と**statusreportingfrequency**の値を**1**に変更してから、BitLocker 管理クライアントサービスを再起動します。 この変更を行うと、MBAM クライアントでは1分ごとに報告されます。 レジストリで手動で設定する場合は、値を低に設定することができます。

### <a href="" id="modify-the-startup-delay-on-mbam-client-service-"></a>MBAM クライアントサービスの起動遅延を変更する

MBAM クライアントのスリープとステータスレポートの頻度に加えて、MBAM クライアントエージェントサービスがクライアントコンピューターで開始されると、最大90分のランダムな遅延が発生します。 ランダム遅延を発生させたくない場合は、 **DWORD**値 " **nostartupdelay** of **HKLM\\Software\\Microsoft\\MBAM**" を作成し、その値を**1**に設定してから、BitLocker 管理クライアントサービスを再起動します。

## 関連トピック


[MBAM 1.0 をお使いになる前に](getting-started-with-mbam-10.md)









