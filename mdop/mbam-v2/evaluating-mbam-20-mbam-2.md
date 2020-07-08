---
title: MBAM 2.0 の評価
description: MBAM 2.0 の評価
author: dansimp
ms.assetid: bfc77eec-0fd7-4fec-9c78-6870afa87152
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7be883f44f5f09a904f619972ae3e7c35261d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824737"
---
# MBAM 2.0 の評価


Microsoft BitLocker の管理と監視 (MBAM) を運用環境に展開する前に、テスト環境で評価する必要があります。 このトピックに記載されている情報を使用して、評価目的のみを対象とした単一サーバーのテスト環境で、スタンドアロンのトポロジを使用して Microsoft BitLocker の管理と監視を設定することができます。 運用環境では、単一サーバートポロジは推奨されません。

テスト環境に MBAM を導入する方法については、「 [MBAM を1台のサーバーにインストールして構成する方法](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)」を参照してください。

## テスト環境のセットアップ


テスト環境で評価するために MBAM の非運用インスタンスを設定する場合でも、前提条件とハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。 インストールを開始する前に、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)、 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」、「 [Mbam 2.0 用の環境の準備](preparing-your-environment-for-mbam-20-mbam-2.md)」を参照してください。

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
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)">MBAM 2.0 をお使いになる前に</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM 2.0 の展開前提条件を計画し、コンピューティング環境を準備します。</p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)">MBAM 2.0 展開の前提条件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM グループポリシー要件を計画して構成します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)">MBAM 2.0 グループ ポリシー要件の計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な ActiveDirectoryDomainServices セキュリティグループの計画と作成を行い、MBAM ローカルセキュリティグループメンバーシップの要件を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">MBAM 2.0 管理者ロールの計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM サーバー機能の展開を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)">MBAM 2.0 サーバーの展開計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアント展開の展開を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)">MBAM 2.0 クライアントの展開計画</a></p></td>
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
<td align="left"><p>MBAM でサポートされている構成情報を確認して、使用しているクライアントコンピューターおよびサーバーコンピューターで MBAM 機能のインストールがサポートされていることを確認します。</p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 がサポートされる構成</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM セットアップを実行して、評価目的で MBAM Server 機能を1台のサーバーに展開します。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)">単一サーバーに MBAM をインストールして構成する方法</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>計画段階で作成した ActiveDirectoryDomainServices セキュリティグループを、新しい MBAM サーバー上の適切なローカルの MBAM サーバー機能ローカルグループに追加します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">MBAM 2.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> Mbam 管理者ロールの管理方法</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な MBAM グループポリシーオブジェクトを作成して展開します。</p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)">MBAM 2.0 グループ ポリシー オブジェクトの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアントソフトウェアを展開します。</p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)">MBAM 2.0 クライアントの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## MBAM 評価用にラボコンピューターを構成する


このセクションには、MBAM クライアントステータスレポートの速度を向上させるために使用できる情報が含まれています。 ただし、これらの変更はテスト目的でのみ使用してください。

**注** 以下のセクションでは、Windows レジストリの変更方法について説明します。 レジストリエディターを誤って使用すると、Windows の再インストールが必要になる深刻な問題が発生する可能性があります。 Microsoft は、レジストリエディターの不正使用によって発生した問題を解決できないことを保証できません。 レジストリエディターは、各自の責任において使用してください。

 

### MBAM クライアントステータスレポートの頻度の設定を変更する

MBAM クライアントのスリープ解除とステータスレポートの頻度は、グループポリシーを使用して設定した場合、最小値で90分に設定されます。 Windows レジストリを使用して、MBAM クライアントコンピューターでこれらの頻度を小さい値に変更して、テスト速度を向上させることができます。

MBAM クライアントステータスレポートの頻度の設定を変更するには、次の操作を行います。

1.  レジストリエディターを使用して**HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**に移動します。

2.  最小クライアントサポート値として、 **ClientWakeupFrequency**と**statusreportingfrequency**の値を**1**に変更します。 この変更により、MBAM クライアントは分ごとに報告されます。

3.  **BitLocker 管理クライアントサービス**を再起動します。

**注** この低い値を設定するには、レジストリで手動で設定する必要があります。

 

### MBAM クライアントサービスの起動遅延を変更する

MBAM クライアントのスリープとステータスレポートの頻度に加えて、MBAM クライアントエージェントサービスがクライアントコンピューターで開始されると、最大90分のランダムな遅延が発生します。 ランダム遅延を発生させたくない場合は、 **DWORD**値 " **nostartupdelay** of **HKLM\\Software\\Microsoft\\MBAM**" を作成し、その値を**1**に設定してから、 **BitLocker 管理クライアントサービス**を再起動します。

## 関連トピック


[MBAM 2.0 をお使いになる前に](getting-started-with-mbam-20-mbam-2.md)

 

 





