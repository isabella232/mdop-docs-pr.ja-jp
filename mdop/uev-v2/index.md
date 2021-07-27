---
title: Microsoft User Experience Virtualization (UE-V) 2.x
description: Microsoft User Experience Virtualization (UE-V) 2.x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795816"
---
# Microsoft User Experience Virtualization (UE-V) 2.x

>[!NOTE]
>このドキュメントは、Microsoft Desktop Optimization Pack (MDOP) に含まれていた UE-V のバージョンを対象としています。 Windows 10 Enterprise に含まれている UE-V の最新バージョンについては、「[UE-V の開始する](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)」を参照してください。


Microsoft User Experience Virtualization (UE-V) 2.0 または 2.1 を実装することで、ユーザーのアプリケーション設定と Windows OS の設定をキャプチャして一元化します。 次に、これらの設定を、デスクトップ PC、ノート PC、仮想デスクトップ インフラストラクチャ (VDI) セッションなど、企業内でユーザーがアクセスするデバイスに適用します。

**UE-V を使用すると、次のようなことが可能です...**

-   同期するアプリケーションとデスクトップの設定を指定する

-   エンタープライズ規模で、ユーザーが作業する時間や場所を問わず、設定を提供する。

-   サード パーティ製アプリケーションまたは基幹アプリケーション用のカスタム テンプレートを作成する。

-   ハードウェアの交換またはアップグレード後、または仮想マシンを初期状態に再イメージングした後に、設定を回復する。

## UE-V 2.x のコンポーネント


次の図は、展開された UE-V が連携して設定を同期する方法を示しています。

![UEV2 アーキテクチャの図](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンポーネント</th>
<th align="left">関数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V エージェント</strong></p></td>
<td align="left"><p><strong>UE-V エージェント</strong> は、設定の同期が必要なすべてのコンピュータにインストールされ、登録済みのアプリケーションやオペレーティング システムの設定変更を監視し、コンピューター間で設定を同期させます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定パッケージ</strong></p></td>
<td align="left"><p>アプリケーションの設定と Windows 設定は、エージェントによって <strong> 作成された設定 </strong> パッケージUE-Vされます。 構築された設定パッケージはローカル保存され、設定の保存場所にコピーされます。</p>
<ul>
<li><p><strong>デスクトップ アプリケーション</strong>の設定値は、ユーザーがアプリケーションを閉じたときに保存されます。</p></li>
<li><p><strong>Windows 設定</strong>の値は、ユーザーがログオフしたとき、コンピューターがロックされたとき、またはユーザーがコンピューターからリモートで切断したときに保存されます。</p></li>
</ul>
<p>同期プロバイダーは、アプリケーションまたはオペレーティング システムの設定が <strong>[設定パッケージ]</strong> から読み込まれ、同期されるタイミングを決定します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>設定の保存場所</strong></p></td>
<td align="left"><p>これは、ユーザーからアクセスできる標準的なネットワーク共有です。 UE-V エージェントは、この保存場所を確認し、ユーザー設定の保存と取得に使用される隠しシステム フォルダーを作成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定場所テンプレート</strong></p></td>
<td align="left"><p>UE-V は XML ファイルを設定場所のテンプレートとして使用し、デスクトップ アプリケーション設定と Windows デスクトップ設定を監視し、ユーザー コンピューター間で同期します。 既定では、いくつかの設定場所テンプレートが UE-V に含まれています。 また、<a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)">カスタム アプリケーション向け同期の設定の管理</a>により、カスタム設定の場所テンプレートを作成、編集、または検証することができます。</p>
<div class="alert">
<strong>備考</strong><br/><p>Windows アプリには、設定場所テンプレートは必要ありません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows アプリの一覧</strong></p></td>
<td align="left"><p>Windows アプリの設定をキャプチャし、動的に適用します。 アプリ開発者は、アプリごとに同期する設定を指定します。 UE-V は、管理されたアプリの一覧を使用して、どの Windows アプリが設定の同期に対応しているか特定します。 既定では、この一覧にほとんどの Windows アプリが含まれています。</p>
<p>Windows アプリ一覧にアプリケーションを追加または削除するには、<a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)">こちら</a>の手順に従ってください。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a>カスタム アプリケーション同期の設定の管理

これらの UE-V コンポーネントを使用して、サード パーティ製アプリケーションまたは基幹アプリケーション用のカスタム テンプレートを作成して管理します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V ジェネレーター</strong></p></td>
<td align="left"><p><strong>UE-V ジェネレーター</strong>を使用してカスタム設定の場所テンプレートを作成し、ユーザー コンピュータに配布することができます。 UE-V ジェネレーターでは、既存のテンプレートを編集したり、他の XM Lエディターで作成したテンプレートを検証することもできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定テンプレート カタログ</strong></p></td>
<td align="left"><p><strong>設定テンプレート カタログ</strong>は、UE-V コンピュータ上のフォルダ パスまたはサーバー メッセージ ブロック (SMB) ネットワーク共有で、カスタム設定の場所テンプレートを保存します。 UE-V エージェントは 1 日 1 回この場所をチェックし、新規または更新されたテンプレートを取得し、同期の動作を更新します。</p>
<p>UE-V の既定の設定の場所テンプレートのみを使用する場合は、設定テンプレート カタログは必要ありません。 設定展開カタログの詳細については、「<a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)">UE-V 設定テンプレート カタログの構成</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>



![UE-V ジェネレーターのプロセス](images/ue-vgeneratorprocess.gif)

## 既定で同期されている設定


UE-V はこれらのアプリケーションの設定を既定で同期します。 完全なリストと詳細情報については、「[UE-V 展開で自動的に同期される設定](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)」を参照してください。

Microsoft Office 2013 アプリケーション (UE-V 2.1 SP1 および 2.1)

Microsoft Office 2010 アプリケーション (UE-V 2.1 SP1、2.1、および 2.0)

Microsoft Office 2007 アプリケーション (UE-V 2.0 のみ)

Internet Explorer 8、9、10

UE-V 2.1 SP1 および 2.1 の Internet Explorer 11

多くの Windows アプリケーション (Xbox など)

多くの Windows デスクトップ アプリケーション (メモ帳など)

多くの Windows 設定 (デスクトップの背景や壁紙など)

**備考**  
既定で同期されたもの以外のアプリケーションに [UE-V をカスタマイズして設定を同期](https://technet.microsoft.com/library/dn458942.aspx)することもできます。



## UE-V と他の Microsoft 製品との比較


このテーブルを使用して、UE-V と Windows 7 のプロファイルの同期、Windows 8 のプロファイルの同期、および Microsoft アカウントの PC 設定の同期機能を比較します。

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
<th align="left">Windows 7 を使用したプロファイルの同期</th>
<th align="left">Windows 8 を使用したプロファイルの同期</th>
<th align="left">Windows 10 を使用したプロファイルの同期</th>
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
<td align="left"><p>Windows アプリ設定を同期する</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>WMI 経由で管理する</p></td>
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
<td align="left"><p>ドメインに参加しないコンピューターのサポート対象</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>プライマリ コンピューターの Active Directory 属性をサポート</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>仮想デスクトップ インフラストラクチャ (VDI)/リモート デスクトップ サービス (RDS) と機能豊富なデスクトップ間の設定を同期します。</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>無制限の設定の記憶域</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同期するアプリ設定の選択</p></td>
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



## UE-V 2.x リリース ノート


詳細情報とドキュメントに記載されていない最新情報については、を参照してください

-   [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## この製品のその他のリソース


-   [UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

-   [UE-V 2.x の展開の準備](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [UE-V 2.x の管理](administering-ue-v-2x-new-uevv2.md)

-   [UE-V 2.x のトラブルシューティング](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)

### 詳細情報

<a href="" id="mdop-techcenter-page"></a>[MDOP TechCenter ページ](https://go.microsoft.com/fwlink/p/?LinkId=225286)最新の MDOP 情報とリソースについて説明します。

<a href="" id="mdop-information-experience"></a>[MDOP 情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032) MDOP テクノロジについての、ドキュメント、ビデオ、その他のリソースがあります。 また、[フィードバックを送信](mailto:MDOPDocs@microsoft.com)したり、[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) または [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447) をフォローして、更新に関する情報を確認したりすることもできます。














