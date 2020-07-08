---
title: App-V 5.1 容量計画
description: App-V 5.1 容量計画
author: dansimp
ms.assetid: 7a98062f-5a60-49d6-ab40-dc6057e1dd5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b152536b3c61e47f3fda84489b1e102c285e01c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814786"
---
# App-V 5.1 容量計画


以下の推奨事項をベースラインとして使用して、組織の App-v 5.1 インフラストラクチャに適したキャパシティ計画情報を決定することができます。

**重要** このセクションの情報は、アプリ-V 5.1 の展開を計画するための一般的なガイドとしてのみ使用してください。 システム容量の要件は、ハードウェアとアプリケーション環境の具体的な詳細によって異なります。 また、このドキュメントに示されているパフォーマンス数値は例であり、結果は異なる場合があります。

 

## プロジェクトのスコープを決定する


App-v 5.1 インフラストラクチャを設計する前に、プロジェクトのスコープを決定する必要があります。 スコープは、どのアプリケーションを実質的に使用できるか、またターゲットユーザーとその場所を特定するかを決定することで構成されます。 この情報は、実装する必要がある App-v 5.1 インフラストラクチャの種類を決定するのに役立ちます。 プロジェクトの範囲に関する決定は、組織の特定のニーズに基づいて行う必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>アプリケーションの範囲を決定する</p></td>
<td align="left"><p>仮想化するアプリケーションによっては、App-v 5.1 インフラストラクチャはさまざまな方法で設定できます。 最初のタスクは、仮想化するアプリケーションを定義することです。</p></td>
</tr>
<tr class="even">
<td align="left"><p>場所の範囲を決定する</p></td>
<td align="left"><p>場所の範囲は、仮想化されたアプリケーションを実行する予定の物理的な場所 (たとえば、企業全体または特定の地理的な場所) を指します。 仮想アプリケーションを実行するユーザー人口 (単一の部署など) を参照することもできます。 接続パスと、仮想化されたアプリケーションを使用しているユーザーの数および WAN のリンク速度を使用しているユーザーの数について、利用可能な帯域幅を含むネットワークマップを取得する必要があります。</p></td>
</tr>
</tbody>
</table>

 

## 必要な App-v 5.1 インフラストラクチャを決定する


**重要** 次の2つのモデルでは、仮想アプリケーションを実行する予定のコンピューターに App-v 5.1 クライアントがインストールされている必要があります。

また、Microsoft Systems Center Configuration Manager などの電子ソフトウェア配布 (ESD) ソリューションを使用して、App-v 5.1 環境を管理することもできます。 詳細については[、「電子ソフトウェアの配布を使用して app-v 5.1 パッケージを展開する方法」を](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)参照してください。

 

-   **スタンド**アロンモデル-スタンドアロンモデルでは、ストリームを使わずに配布するために仮想アプリケーションを Windows Installer 対応にすることができます。 スタンドアロンモードの App V 5.1 は、sequencer とクライアントで構成されます。追加のコンポーネントは必要ありません。 アプリケーションは、シーケンスと呼ばれるプロセスを使用して仮想化の準備を行います。 詳細については、「 [app-v 5.1 Sequencer とクライアント展開の計画](planning-for-the-app-v-51-sequencer-and-client-deployment.md)」を参照してください。 単体モデルは、次のシナリオでお勧めします。

    -   App-v 5.1 インフラストラクチャに接続できないリモートユーザーが切断されている。

    -   Configuration Manager 2012 などのソフトウェア管理システムを実行している場合。

    -   ネットワーク帯域幅の制限により、電子ソフトウェアの配布が禁止されている場合。

-   **完全**なインフラストラクチャモデル-完全なインフラストラクチャモデルでは、ソフトウェアの配布、管理、レポート機能が提供されます。また、ネットワーク経由のアプリケーションのストリーミングも含まれます。 App-v 5.1 の完全なインフラストラクチャモデルは、1つ以上の App-v 5.1 management サーバーで構成されます。 管理サーバーを使用して、アプリケーションをすべてのクライアントに公開することができます。 公開プロセスでは、仮想アプリケーションのアイコンとショートカットがターゲットコンピューターに配置されます。 また、ローカルユーザーにアプリケーションをストリームすることもできます。 管理サーバーのインストールの詳細については、「 [app-v 5.1 サーバー展開の計画](planning-for-the-app-v-51-server-deployment.md)」を参照してください。 次のシナリオでは、完全なインフラストラクチャモデルをお勧めします。

    **重要** アプリ-V 5.1 の完全なインフラストラクチャモデルでは、構成データを保存するために Microsoft SQL Server が必要です。 詳細については[、「app-v 5.1 でサポートされている構成](app-v-51-supported-configurations.md)」を参照してください。

     

    -   管理サーバーを使用して、アプリケーションをターゲットコンピューターに発行する場合。

    -   ターゲットコンピューターへのアプリケーションの迅速なプロビジョニング。

    -   App-v 5.1 レポートを使用する場合。

## エンドツーエンドサーバーのサイズ変更のガイダンス


以下のセクションでは、エンドツーエンドの App-v 5.1 のサイズと計画について説明します。 詳細については、後続のセクションを参照してください。

**注** クライアントでのラウンドトリップの応答時間は、アプリ-V 5.1 クライアントを実行しているコンピューターが、発行サーバーから正常な通知を受信するまでにかかった時間です。 発行サーバーのラウンドトリップ応答時間は、発行サーバーを実行しているコンピューターが管理サーバーから正常なパッケージメタデータ更新を受信するまでの時間です。

 

-   2万クライアントは、1つのパブリッシングサーバーをターゲットとして、適切なラウンドトリップ時間でパッケージの更新を取得することができます。 ( &lt; 3 秒)

-   1つの管理サーバーでは、許容可能なラウンドトリップ時間内のパッケージのメタデータの更新について、最大50の発行サーバーをサポートできます。 ( &lt; 5 秒)

## <a href="" id="---------app-v-5-1-management-server-capacity-planning-recommendations"></a> App-v 5.1 Management Server キャパシティ計画の推奨事項


App-v 5.1 公開サーバーでは、パッケージの更新要求とパッケージ更新の応答に管理サーバーが必要です。 その後、管理サーバーはその情報を管理データベースに送信して情報を取得します。 App-v 5.1 management server でサポートされている構成の詳細については[、「app-v 5.1 でサポートされている構成](app-v-51-supported-configurations.md)」を参照してください。

**注** App-v 5.1 公開サーバーの既定の更新時刻は、10分です。

 

複数の同時発行サーバーから1つの管理サーバーに連絡してパッケージのメタデータを更新すると、次の3つの要因が、発行サーバーのラウンドトリップ応答時間に影響します。

1.  同時要求を行っている発行サーバーの数です。

2.  管理サーバーで構成されている接続グループの数。

3.  管理サーバーで構成されているアクセスグループの数。

次の表は、往復時間に影響を与える各要素についての詳細を示しています。

**注** ラウンドトリップの応答時間は、管理サーバーから正常にパッケージのメタデータ更新を受信するために、App-v 5.1 発行サーバーを実行しているコンピューターによって行われた時間です。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ラウンドトリップの応答時間に影響を与える要因</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージのメタデータの更新を同時に要求する発行サーバーの数です。</p></td>
<td align="left"><p></p>
<ul>
<li><p>1つの管理サーバーは、同時に公開するために、最大320の発行サーバーに応答できます。</p></li>
<li><p>320 pub サーバーのラウンドトリップ応答時間は、最大40秒です。</p></li>
<li><p>&lt;50 パブリッシングサーバーでメタデータを同時に要求する場合、ラウンドトリップの応答時間は &lt; 5 秒です。</p></li>
<li><p>50から320発行サーバーへの応答時間は直線的に増加します (約 2x)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>管理サーバーで構成されている接続グループの数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>最大100の接続グループについては、パブリッシングサーバーのラウンドトリップ応答時間に大幅な変更はありません。</p></li>
<li><p>100-400 接続グループの場合、ラウンドトリップ応答時間のわずかな線形増加が発生します。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>管理サーバーで構成されているアクセスグループの数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>最大40のアクセスグループについては、パブリッシングサーバーのラウンドトリップ応答時間が直線的 (約3倍) 増加しています。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

次の表は、前の各要素のサンプル値を示しています。 各バリエーションで、120パッケージは、app-v 5.1 management サーバーから更新されます。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">バリエーション</th>
<th align="left">接続グループの数</th>
<th align="left">アクセスグループの数</th>
<th align="left">発行サーバーの数</th>
<th align="left">ネットワーク接続の種類発行サーバー/管理サーバー</th>
<th align="left">パブリッシングサーバーのラウンドトリップ応答時間 (秒単位)</th>
<th align="left">管理サーバーの CPU 使用率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サーバーを公開して、メタデータを公開するために管理サーバーに同時に接続します。</p></td>
<td align="left"><p>発行サーバーの数</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>50</p></li>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>300</p></li>
<li><p>315</p></li>
<li><p>320</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>個</p></li>
<li><p>常用</p></li>
<li><p>#</p></li>
<li><p>32</p></li>
<li><p>求める</p></li>
<li><p>37</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>17</p></li>
<li><p>17</p></li>
<li><p>17</p></li>
<li><p>マート</p></li>
<li><p>17</p></li>
<li><p>マート</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>発行メタデータに接続グループが含まれている</p></td>
<td align="left"><p>接続グループの数</p></td>
<td align="left"><p></p>
<ul>
<li><p>常用</p></li>
<li><p>50</p></li>
<li><p>100</p></li>
<li><p>150</p></li>
<li><p>300</p></li>
<li><p>400</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
<li><p>件</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>常用</p></li>
<li><p>折り</p></li>
<li><p>折り</p></li>
<li><p>16</p></li>
<li><p>22</p></li>
<li><p>50</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>17</p></li>
<li><p>#</p></li>
<li><p>22</p></li>
<li><p>#</p></li>
<li><p>超える</p></li>
<li><p>超える</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>公開メタデータにアクセスグループが含まれている</p></td>
<td align="left"><p>アクセスグループの数</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>常用</p></li>
<li><p>超える</p></li>
<li><p>40</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>常用</p></li>
<li><p>43</p></li>
<li><p>153</p></li>
<li><p>535</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>17</p></li>
<li><p>#</p></li>
<li><p>24</p></li>
<li><p>24</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

管理サーバーを実行しているコンピューターの CPU 使用率は、ターゲットに設定されている発行サーバーの数に関係なく、約25% になります。 Microsoft SQL Server データベーストランザクション/sec、バッチ要求/秒、およびユーザー接続は、発行サーバーの数に関係なく同一になります。 たとえば、トランザクション/sec は ~ 30、バッチ要求 ~ 200、ユーザーは ~ 6 を接続します。

地理的に分散した展開を使用している場合、管理サーバー & 発行サーバーは、それらの間の低速リンクネットワークを利用します。発行サーバーのラウンドトリップ応答時間は、 &lt; 1 つの管理サーバーで同時に100を要求する場合でも、許容時間制限 (5 秒) になります。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">バリエーション</th>
<th align="left">接続グループの数</th>
<th align="left">アクセスグループの数</th>
<th align="left">発行サーバーの数</th>
<th align="left">ネットワーク接続の種類発行サーバー/管理サーバー</th>
<th align="left">パブリッシングサーバーのラウンドトリップ応答時間 (秒単位)</th>
<th align="left">管理サーバーの CPU 使用率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>発行サーバーと管理サーバーの間のネットワーク接続</p></td>
<td align="left"><p>1.5 Mbps 低速リンクネットワーク</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>件</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>50</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 mbps ケーブルの DSL</p></li>
<li><p>1.5 mbps ケーブルの DSL</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>4d</p></li>
<li><p>個</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>両面</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>発行サーバーと管理サーバーの間のネットワーク接続</p></td>
<td align="left"><p>LAN/WIFI ネットワーク</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>件</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>Wifi</p></li>
<li><p>Wifi</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>折り</p></li>
<li><p>超える</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>マート</p></li>
<li><p>17</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

管理サーバーと発行サーバーが低速リンクネットワークまたは高速ネットワーク経由で接続されているかどうかにかかわらず、管理サーバーは約15000パッケージ更新要求を30分で処理できます。

## <a href="" id="---------app-v-5-1-reporting-server-capacity-planning-recommendations"></a> App-v 5.1 レポートサーバーキャパシティ計画の推奨事項


App-v 5.1 クライアントは、レポートデータをレポートサーバーに送信します。 その後、レポートサーバーでは、Microsoft SQL Server データベースに情報が記録され、App-v 5.1 クライアントを実行しているコンピューターに正常に通知が返されます。 App-v 5.1 Reporting Server でサポートされている構成の詳細については[、「app-v 5.1 でサポートされている構成](app-v-51-supported-configurations.md)」を参照してください。

**注** ラウンドトリップの応答時間は、レポート情報をレポートサーバーに送信して、レポートサーバーから正常に通知を受信するために、App-v 5.1 クライアントを実行しているコンピューターにかかる時間です。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">まとめ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複数の App-v 5.1 クライアントは、レポート情報を同時にレポートサーバーに送信します。</p></td>
<td align="left"><p></p>
<ul>
<li><p>レポートサーバーからのラウンドトリップ応答時間は、500クライアントでは2.6 秒です。</p></li>
<li><p>レポートサーバーからのラウンドトリップ応答時間は、1000クライアントでは5.65 秒です。</p></li>
<li><p>ラウンドトリップの応答時間は、クライアント数に応じて直線的に増加します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>レポートサーバーによって処理された1秒あたりの要求数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>1つのレポートサーバーと1つのデータベースは、1秒あたり最大139要求を処理できます。 平均は121要求数/秒です。</p></li>
<li><p>同じ Microsoft SQL Server データベースにレポートされた2つのレポートサーバーを使用する場合、average requests/秒は1つのレポートサーバー = ~ 127 に似ていますが、最大278要求数は1秒です。</p></li>
<li><p>1つのレポートサーバーで、500の同時接続とアクティブな接続を処理できます。</p></li>
<li><p>1つのレポートサーバーで、最大1500の同時接続を処理できます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>レポートデータベース。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>Microsoft SQL Server を実行しているコンピューターのロックの競合は、要求/秒の制限要素です。</p></li>
<li><p>スループットと応答時間はデータベースのサイズに依存しません。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**ランダム遅延の計算**:

ランダムな遅延は、レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。 スケジュールされたタスクが開始されると、クライアントは**0**と**ReportingRandomDelay**の間のランダムな遅延を生成し、データを送信する前に指定された期間待機します。

ランダム遅延 = 4 \ * クライアント数/秒あたりの平均要求数。

例: 500 クライアントで、1秒あたりの120要求があった場合、ランダム遅延は、4 \ * 500/120 = ~ 17 分です。

## <a href="" id="---------app-v-5-1-publishing-server-capacity-planning-recommendations"></a> App-v 5.1 発行サーバーのキャパシティ計画に関する推奨事項


App-v 5.1 クライアントを実行しているコンピューターは、app-v 5.1 発行サーバーに接続して、公開更新要求を送信し、応答を受信します。 ラウンドトリップの応答時間は、App-v 5.1 クライアントを実行しているコンピューターで測定されます。 プロセッサ時間は発行サーバーで測定されます。 App-v 5.1 Publishing Server でサポートされている構成の詳細については[、「app-v 5.1 でサポートされている構成](app-v-51-supported-configurations.md)」を参照してください。

**重要** 次の一覧は、App-v 5.1 発行サーバーのセットアップ時に考慮する主な要素を示しています。

-   1つのパブリッシングサーバーに同時に接続しているクライアントの数。

-   各更新のパッケージ数。

-   クライアントと App-v 5.1 発行サーバーとの間の環境で利用可能なネットワーク帯域幅。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">まとめ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複数の App-v 5.1 クライアントは、1つのパブリッシングサーバーに同時に接続します。</p></td>
<td align="left"><p></p>
<ul>
<li><p>デュアルコアプロセッサを実行している発行サーバーでは、ほとんどの5000クライアントで同時に更新を要求することができます。</p></li>
<li><p>5000-10000 クライアントの場合、発行サーバーに最低限の4コアが必要です。</p></li>
<li><p>10000-20000 クライアントの場合、応答時間をより効率的にするために、発行サーバーには2つのクワッドコアが必要です。</p></li>
<li><p>4コアの発行サーバーは、3秒以内に最大1万パッケージを更新することができます。 (1万の同時クライアントのサポート)</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>各更新のパッケージ数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>パッケージの数を増やすと 40% (最大1000パッケージ) の応答時間が増加します。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.1 クライアントと発行サーバー間のネットワーク。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>低速ネットワーク (1.5 Mbps の帯域幅) では、LAN と比較した場合の応答時間が97% 増加しています (最大1000ユーザー)。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**注** 発行サーバーの CPU 使用率は、同時要求を処理する必要がある時間間隔内に常に高くなり &gt; ます (ほとんどの場合、90% です)。 発行サーバーは、1秒で1500クライアント要求を処理できます。

 

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">バリエーション</th>
<th align="left">App-v 5.1 クライアントの数</th>
<th align="left">パッケージ数</th>
<th align="left">パブリッシングサーバー上のプロセッサ構成</th>
<th align="left">ネットワーク接続の種類発行サーバー/App-v 5.1 クライアント</th>
<th align="left">App-v 5.1 クライアントでのラウンドトリップ時間 (秒単位)</th>
<th align="left">パブリッシングサーバーの CPU 使用率 (%)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.1 クライアントは、発行の更新要求 &amp; を受信し、120パッケージを含む各要求を送信します。</p></td>
<td align="left"><p>クライアント数</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>1000</p></li>
<li><p>5000</p></li>
<li><p>1万</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>デュアルコア</p></li>
<li><p>デュアルコア</p></li>
<li><p>クアッドコア</p></li>
<li><p>クアッドコア</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>件</p></li>
<li><p>両面</p></li>
<li><p>両面</p></li>
<li><p>-</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>99</p></li>
<li><p>89</p></li>
<li><p>77</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>更新ごとに複数のパッケージ</p></td>
<td align="left"><p>パッケージ数</p></td>
<td align="left"><p></p>
<ul>
<li><p>1000</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>500</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>クアッドコア</p></li>
<li><p>クアッドコア</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>両面</p></li>
<li><p>-</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>92</p></li>
<li><p>91</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>クライアントと発行サーバー間のネットワーク</p></td>
<td align="left"><p>1.5 Mbps 低速リンクネットワーク</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>500</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>クアッドコア</p></li>
<li><p>クアッドコア</p></li>
<li><p>クアッドコア</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 Mbps の大陸内ネットワーク</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>-</p></li>
<li><p>10 (0.2% の故障率)</p></li>
<li><p>17 (1% の故障率)</p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------app-v-5-1-streaming-capacity-planning-recommendations"></a> App-v 5.1 ストリーミングキャパシティ計画の推奨事項


App-v 5.1 クライアントを実行しているコンピューターは、ストリーミングサーバーから仮想アプリケーションパッケージをストリームします。 ラウンドトリップの応答時間は、App-v 5.1 クライアントを実行しているコンピューターで測定され、パッケージ全体をストリーミングするのにかかった時間です。

**重要** 次のリストは、App-v 5.1 ストリーミングサーバーのセットアップ時に考慮する主な要素を示しています。

-   1つのストリーミングサーバーから同時にアプリケーションパッケージをストリーミングするクライアントの数です。

-   ストリーミングされるパッケージのサイズ。

-   クライアントとストリーミングサーバー間の環境で利用可能なネットワーク帯域幅。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">まとめ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複数の App-v 5.1 クライアントは、単一のストリーミングサーバーからアプリケーションを同時にストリーミングします。</p></td>
<td align="left"><p></p>
<ul>
<li><p>同じサーバーから同時にストリーミングしているクライアントの数が増加すると、パッケージのダウンロード/ストリーミング時間との間に線形関係があります。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ストリーミングされるパッケージのサイズ。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>パッケージサイズは、サイズが 1 GB の大きなパッケージのストリーミング/ダウンロード時間に大きな影響を与えます。 3 MB から 100 MB までのパッケージサイズの場合、ストリーミングの時間範囲は20秒から100秒までで、100の同時クライアントがあります。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.1 クライアントとストリーミングサーバー間のネットワーク。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>低速ネットワーク (1.5 Mbps の帯域幅) では、LAN と比較した場合の応答時間が70-80% 増加しています (最大100ユーザー)。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

次の表は、前の一覧の各要素のサンプル値を示しています。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">バリエーション</th>
<th align="left">App-v 5.1 クライアントの数</th>
<th align="left">各パッケージのサイズ</th>
<th align="left">ネットワーク接続の種類のストリーミングサーバー/App-v 5.1 クライアント</th>
<th align="left">App-v 5.1 クライアントでのラウンドトリップ時間 (秒単位)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複数の App-v 5.1 クライアントが、ストリーミングサーバーから仮想アプリケーションパッケージをストリーミングします。</p></td>
<td align="left"><p>クライアント数。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>1000</p></li>
<li><p></p></li>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3.5 MB</p></li>
<li><p>3.5 MB</p></li>
<li><p>3.5 MB</p></li>
<li><p></p></li>
<li><p>5 MB</p></li>
<li><p>5 MB</p></li>
<li><p>5 MB</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p></p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>29</p></li>
<li><p>39</p></li>
<li><p>391</p></li>
<li><p></p></li>
<li><p>35</p></li>
<li><p>68</p></li>
<li><p>461</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ストリーミングされる各パッケージのサイズ。</p></td>
<td align="left"><p>各パッケージのサイズ。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p></p></li>
<li><p>100</p></li>
<li><p>200</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>21 MB</p></li>
<li><p>21 MB</p></li>
<li><p></p></li>
<li><p>109</p></li>
<li><p>109</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p></p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<p>33</p>
<p>83</p>
<p></p>
<p>100</p>
<p>160</p></td>
</tr>
<tr class="odd">
<td align="left"><p>クライアントと App-v 5.1 ストリーミングサーバー間のネットワーク接続。</p></td>
<td align="left"><p>1.5 Mbps 低速リンクネットワーク。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p></p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3.5 MB</p></li>
<li><p></p></li>
<li><p>5 MB</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 Mbps の大陸内ネットワーク</p></li>
</ul></td>
<td align="left"><p></p>
<p>102</p>
<p></p>
<p>121</p></td>
</tr>
</tbody>
</table>

 

各 App-v 5.1 ストリーミングサーバーは、仮想化されたアプリケーションを同時にストリーミングする少なくとも200クライアントを処理できる必要があります。

**注** ストリームにかかる実際の時間は、主に、同時にストリーミングしているクライアント数、パッケージ数、パッケージサイズ、サーバーのネットワークアクティビティ、ネットワークの状態によって決まります。

 

たとえば、平均ユーザーは 100 MB のパッケージを2分未満でストリーミングできます。これは、100の同時クライアントがサーバーからストリーミングしている場合です。 ただし、サイズが 1 GB のパッケージは、最大30分かかることがあります。 ほとんどの実際の環境では、ストリーミング需要は一律配布されていません。必要なストリーミングサーバの数を正しくサイズ指定するために、お客様の環境に存在するおおよそのピークストリーミング要件を理解しておく必要があります。

アプリケーションを事前にキャッシュしておくと、ストリーミングサーバーがサポートできるクライアントの数が大きくなり、ピークストリーミングの要件が小さくなります。 オンデマンドストリーミング配信とストリーム最適化されたパッケージを使用して、ストリーミングサーバーがサポートできるクライアントの数を増やすこともできます。

## App-v 5.1 サーバーロールの組み合わせ


割引のスケーリングとフォールトトレランスの要件: Active Directory への接続がある場所に必要なサーバーの最小数は1です。 このサーバーは、管理サーバー、管理サーバーサービス、Microsoft SQL Server の役割をホストします。 したがって、サーバーの役割は、互いに競合しないため、任意の組み合わせで配置することができます。

スケーリング要件を無視すると、フォールトトレラントな実装を提供するために必要なサーバーの最小数は4です。 管理サーバーと Microsoft SQL Server の役割は、フォールトトレラント構成に配置されています。 管理サーバーサービスは、いずれのロールとも組み合わせることができますが、単一点障害のままです。

フォールトトレランスの戦略とテクノロジはいくつでも提供されていますが、特定のサービスに適用することはできません。 さらに、App-v 5.1 ロールが結合されている場合、非互換性のために一部のフォールトトレランスオプションが適用されないことがあります。






## 関連トピック


[App-V 5.1 でサポートされる構成](app-v-51-supported-configurations.md)

[App-V 5.1 の高可用性の計画](planning-for-high-availability-with-app-v-51.md)

[App-V の展開計画](planning-to-deploy-app-v51.md)

 

 





