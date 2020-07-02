---
title: Microsoft User Experience Virtualization (UE-V) 2. x
description: Microsoft User Experience Virtualization (UE-V) 2. x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795816"
---
# Microsoft User Experience Virtualization (UE-V) 2. x

>[!NOTE]
>このドキュメントは、Microsoft デスクトップ最適化パック (MDOP) に含まれている UE-V のバージョンを示しています。 Windows 10 Enterprise に含まれている最新バージョンの UE-V の詳細については、「 [ue-v の使用を開始](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)する」を参照してください。


Microsoft User Experience Virtualization (UE-V) 2.0 または2.1 を実装して、ユーザーのアプリケーション設定と Windows OS 設定をキャプチャして集中化します。 次に、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、エンタープライズのユーザーアクセスデバイスにこれらの設定を適用します。

**UE-V では...**

-   どのアプリケーションとデスクトップの設定を同期するかを指定する

-   エンタープライズ規模で、ユーザーが作業する時間や場所を問わず、設定を提供する。

-   サード パーティ製アプリケーションまたは基幹アプリケーション用のカスタム テンプレートを作成する。

-   ハードウェアの置き換えまたはアップグレード後、または仮想マシンを初期状態に再イメージした後に設定を回復する

## UE-V 2. x の構成要素


次の図は、展開された UE-V コンポーネントが連携して設定を同期する方法を示しています。

![uev2 のアーキテクチャ図](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンポーネント</th>
<th align="left">機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V Agent</strong></p></td>
<td align="left"><p>設定を同期する必要があるすべてのコンピューターにインストールされている <strong> Ue-v agent は、 </strong> 登録済みアプリケーションとオペレーティングシステムを監視して、すべての設定を変更し、コンピューター間でこれらの設定を同期します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定パッケージ</strong></p></td>
<td align="left"><p>アプリケーション設定と Windows 設定は <strong> </strong> 、ue-v agent によって作成された設定パッケージに保存されます。 構築された設定パッケージはローカル保存され、設定の保存場所にコピーされます。</p>
<ul>
<li><p>デスクトップアプリケーションの設定値 <strong> </strong> は、ユーザーがアプリケーションを閉じると保存されます。</p></li>
<li><p><strong>Windows 設定の値 </strong> は、ユーザーがログオフしたとき、コンピューターがロックされているとき、またはユーザーがコンピューターからリモートで切断したときに保存されます。</p></li>
</ul>
<p>同期プロバイダーは、アプリケーションまたはオペレーティングシステムの設定が設定パッケージから読み取られるタイミングを決定し、 <strong> </strong> 同期されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>設定の保存場所</strong></p></td>
<td align="left"><p>これは、ユーザーがアクセスできる標準のネットワーク共有です。 UE-V Agent は、その場所を確認し、ユーザー設定を保存して取得する非表示のシステムフォルダーを作成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定場所テンプレート</strong></p></td>
<td align="left"><p>UE-V は、設定場所テンプレートとして XML ファイルを使用して、デスクトップアプリケーションの設定と、ユーザーのコンピューター間の Windows デスクトップの設定を監視および同期します。 既定では、一部の設定場所テンプレートは UE-V に含まれています。 カスタムアプリケーションの設定の同期を管理することによって、カスタム設定の場所テンプレートを作成、編集、または検証することもでき <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> </a> ます。</p>
<div class="alert">
<strong>注</strong><br/><p>設定場所テンプレートは、Windows アプリでは必要ありません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows アプリの一覧</strong></p></td>
<td align="left"><p>Windows アプリの設定は、動的にキャプチャおよび適用されます。 アプリの開発者は、アプリごとに同期される設定を指定します。 UE-V は、アプリの管理リストを使用して、設定の同期にどの Windows アプリを有効にするかを決定します。 既定では、この一覧にはほとんどの Windows アプリが含まれています。</p>
<p>次に示す手順に従って、Windows アプリリストのアプリケーションを追加または削除することができ <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> </a> ます。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a>カスタムアプリケーションの設定の同期を管理する

これらの UE-V コンポーネントを使用して、サードパーティまたは基幹業務アプリケーションのカスタムテンプレートを作成し、管理します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V Generator</strong></p></td>
<td align="left"><p><strong>Ue-v Generator を使って、 </strong> ユーザー設定の場所テンプレートを作成し、ユーザーコンピューターに配布することができます。 UE-V Generator を使うと、既存のテンプレートを編集したり、別の XML エディターを使って作成されたテンプレートを検証したりすることもできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定テンプレートカタログ</strong></p></td>
<td align="left"><p><strong>設定テンプレートカタログ </strong> は、カスタム設定の場所テンプレートが保存されている ue-v (ue-v) コンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有です。 UE-V Agent は、この場所を1日に1回チェックし、新規または更新されたテンプレートを取得し、その同期動作を更新します。</p>
<p>UE-V の既定の設定の場所テンプレートのみを使用している場合、設定テンプレートカタログは不要です。 設定展開カタログの詳細については、「 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> ue-v 設定テンプレートカタログを構成する」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>



![ue-v generator プロセス](images/ue-vgeneratorprocess.gif)

## 既定で同期されている設定


UE-V は、既定でこれらのアプリケーションの設定を同期します。 完全なリストと詳細情報については、「 [ue-v 展開で自動的に同期される設定](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)」を参照してください。

Microsoft Office 2013 アプリケーション (UE-V 2.1 SP1 および 2.1)

Microsoft Office 2010 アプリケーション (UE-V 2.1 SP1、2.1、2.0)

Microsoft Office 2007 アプリケーション (UE-V 2.0 のみ)

Internet Explorer 8、9、10

Internet Explorer 11 (UE-V 2.1 SP1 および 2.1)

多くの Windows アプリケーション (Xbox など)

メモ帳などの多くの Windows デスクトップアプリケーション

デスクトップの背景や壁紙など、多くの Windows 設定

**注**  
また、UE-V をカスタマイズして、既定で同期されていないアプリケーションの[設定を同期する](https://technet.microsoft.com/library/dn458942.aspx)こともできます。



## UE-V を他の Microsoft 製品と比較する


この表を使用して、UE-V と Windows 7 のプロファイルの同期、Windows 8 でのプロファイルの同期、Microsoft アカウントの同期 PC 設定機能の比較を行います。

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">機能</th>
<th align="left">Windows 7 を使用してプロファイルを同期する</th>
<th align="left">Windows 8 を使用してプロファイルを同期する</th>
<th align="left">Windows 10 を使用してプロファイルを同期する</th>
<th align="left">Microsoft アカウント</th>
<th align="left">UE-V 2.0</th>
<th align="left">UE-V 2.1 および 2.1 SP1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複数のコンピューター間で設定を同期する</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>物理アプリと仮想アプリの間で設定を同期する</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows アプリの設定を同期する</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>WMI を使用して管理する</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定の変更を定期的に同期する</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>セットアップの最小構成</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドメインに参加していないコンピューターでのサポート</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>プライマリコンピューターの Active Directory 属性をサポートしています</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>仮想デスクトップインフラストラクチャ (VDI)/デスクトップサービス (RDS) とリッチデスクトップの間で設定を同期します。</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>無制限のストレージスペースの設定</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同期するアプリの設定の選択</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>IT プロフェッショナル向けのバックアップ/復元</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>一部</p></td>
<td align="left"><p>●</p></td>
</tr>
</tbody>
</table>



## UE-V 2. x のリリースノート


詳細と最新ニュースについては、このドキュメントを参照してください。

-   [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## この製品のその他のリソース


-   [UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

-   [UE-V の展開を準備する](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

-   [UE-V 2. x のトラブルシューティング](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)

### 詳細情報

<a href="" id="mdop-techcenter-page"></a>[MDOP TechCenter ページ](https://go.microsoft.com/fwlink/p/?LinkId=225286)最新の MDOP 情報とリソースについて説明します。

<a href="" id="mdop-information-experience"></a>[MDOP 情報の操作](https://go.microsoft.com/fwlink/p/?LinkId=236032)MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。 また、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をフォローして、[フィードバックを送信](mailto:MDOPDocs@microsoft.com)したり、更新プログラムに関する情報を確認したりすることもできます。














