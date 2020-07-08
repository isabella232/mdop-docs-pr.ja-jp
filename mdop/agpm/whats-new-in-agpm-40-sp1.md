---
title: AGPM 4.0 SP1 の新機能
description: AGPM 4.0 SP1 の新機能
author: dansimp
ms.assetid: c6a3d94a-13c3-44e6-a466-c3011879999e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca1ee4a1c2eb943a25246dc31b127eaf72ff5fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818154"
---
# AGPM 4.0 SP1 の新機能


この "最新情報" のコンテンツでは、Microsoft Advanced グループポリシー管理 (AGPM) 4.0 SP1 の拡張機能とサポートされる構成について説明します。 このコンテンツと他の AGPM ドキュメントの間に違いがある場合、このコンテンツは、権限があると見なされ、この製品に含まれているコンテンツを置き換える必要があります。

## <a href="" id="what-s-new"></a>新機能


AGPM 4.0 SP1 では、次の機能強化がサポートされています。

### クライアント側の新しい拡張子と変更された機能

Windows 8 および Windows Server 2012 で新しいグループポリシーをサポートするために、AGPM のためにグループポリシークライアント側の拡張機能 (CSEs) が追加または変更されています。 これらのグループポリシーを使用すると、グループポリシー管理者は、2つのグループポリシーオブジェクト (Gpo) とテンプレートの間で変更される Windows 8 固有のグループポリシー設定を管理および追跡することができます。 また、Windows 8 固有の設定を使用してカスタム Gpo を作成し、Gpo をテンプレートとして構成して保存することもできます。 CSEs を表示するには、AGPM 4.0 SP1 クライアントで利用可能な設定と差分レポートを使用します。

新しい、または変更されたグループポリシークライアント側拡張機能は次のとおりです。

-   **集約型アクセスポリシー:** グループポリシー管理者が、[ファイルサーバー] などのグループポリシーサーバーに対して集約型アクセスポリシーを指定できるようにします。 集約型アクセスポリシーは、GPO 項目によって指定され、ポリシーのターゲットに適用され、リソースの集中アクセスと制御を容易にするための承認ポリシーです。 これらの中央アクセスポリシーは、Active Directory 内のグループポリシークライアントコンピューターで構成する必要があります。 グループポリシーは、適用する必要があるコンピューターに対して、適用可能な集約型アクセスポリシーの知識を配布します。

-   **名前解決ポリシーの変更:** グループポリシー管理者が dns クライアントコンピューター上の DNS セキュリティと DirectAccess の設定を構成できるようにします。 標準 DNS サーバー設定とエンコード設定を構成するための新しいタブが追加されました。

-   **グループポリシーの基本設定の変更:** Windows 8 用に追加された Internet Explorer 10 設定の構成と管理のサポートを追加します。

-   **リモートアプリケーションとデスクトップ接続:** グループポリシー管理者は、リモートアプリケーションとデスクトップ接続に使用する既定の接続 URL を指定することができます。

-   **Windows To Go スタートアップオプション:** グループポリシー管理者は、Windows to Go ワークスペースを含む USB デバイスが接続されている場合に、コンピューターが Windows を起動するかどうかを構成できます。

-   **Windows To Go Hibernate のオプション:** グループポリシー管理者は、コンピューターが Windows To Go ワークスペースから開始されたときに、コンピューターが休止状態のスリープ状態 (S4) を使用できるかどうかを構成できます。

### 顧客のフィードバックと修正プログラムのロールアップ

AGPM 4.0 SP1 には、AGPM 4.0 リリース以降で検出された問題に対処するための修正プログラムが含まれています。 AGPM 4.0 SP1 には、Microsoft Advanced Group Policy Management 4.0 Hotfix 1 までの最新の修正プログラムが含まれています。

### 設定と差分レポートで、新しいグループポリシーの拡張機能が表示される

[設定] と [差分] レポートに新しいグループポリシー拡張機能が追加されました。

### インストーラーの変更とサポート

AGPM 4.0 SP1 インストーラーの変更とサポートは、次のとおりです。

-   Windows 8 または Windows Server 2012 で AGPM 4.0 SP1 をインストールする場合、AGPM インストーラーは、必須の必須ソフトウェア (グループポリシー管理コンソールと .NET 3.5 フレームワーク) がインストールされていることを確認します。 これらの前提条件がインストールされていない場合、AGPM 4.0 SP1 のインストールはブロックされます。

-   AGPM 4.0 SP1 をインストールすると、WCF のアクティブ化、非 HTTP アクティベーション、Windows プロセスのアクティブ化サービスが自動的に有効になります。

-   Windows Vista、Windows 7、Windows 8 クライアントオペレーティングシステムでは、AGPM 4.0 SP1 をインストールする前に、使用しているオペレーティングシステム用の適切なバージョンのリモートシステム管理ツールキットをダウンロードします。

-   サポートされている以前のオペレーティングシステムとの下位互換性がサポートされています。

### 構成パラメーターを再入力せずに、AGPM 4.0 SP1 にアップグレードまたは更新する機能

次の表に示すように、AGPM クライアントまたはサーバーは、AGPM 4.0 からのみ agpm 4.0 SP1 にアップグレードできます ("スマートアップグレード" と呼ばれます)。 表に示されているように、他のバージョンの AGPM から AGPM 4.0 SP1 にアップグレードする場合は、構成パラメーターを再入力する必要がある "クラシックアップグレード" を使用する必要があります。 AGPM の各バージョンは特定のオペレーティングシステムに関連付けられているため、[インストールする agpm のバージョンを選択](https://go.microsoft.com/fwlink/?LinkId=254350)する方法を参照して、アップグレードを実行する前に、必要に応じてオペレーティングシステムをアップグレードしてください。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>アップグレードできる AGPM バージョン</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>適用不可能</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3.0</p></td>
<td align="left"><p>適用不可能</p></td>
<td align="left"><p>適用不可能</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>適用不可能</p></td>
<td align="left"><p>適用不可能</p></td>
<td align="left"><p>適用不可能</p></td>
<td align="left"><p>スマートアップグレード</p></td>
</tr>
</tbody>
</table>

 

## サポートされている構成


AGPM では、次の表に示す構成がサポートされています。 AGPM では混合構成がサポートされていますが、AGPM クライアントとサーバーは同じオペレーティングシステムファミリで実行することを強くお勧めします。たとえば、windows 8 では windows Server 2012、windows 7 は windows Server 2008 R2 などです。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AGPM 4.0 SP1 サーバーでサポートされている構成</strong></p></td>
<td align="left"><p><strong>AGPM 4.0 SP1 クライアントでサポートされている構成</strong></p></td>
<td align="left"><p><strong>AGPM 4.0 SP1 のサポート</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8 または Windows Server 2012</p></td>
<td align="left"><p>Windows 8 または Windows Server 2012</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2 または Windows 7</p></td>
<td align="left"><p>Windows Server 2008 R2 または Windows 7</p></td>
<td align="left"><p>サポートされますが、Windows 8 にのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2 または windows 7 または windows 8 または windows Server 2012</p></td>
<td align="left"><p>Windows Server 2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、Windows Server 2008 R2 または Windows 7 または windows 8 でのみ存在するポリシー設定や基本設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2008 R2 または windows 7 または windows 8 または windows Server 2012</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、Windows Server 2008 R2 または Windows 7 または windows 8 でのみ存在するポリシー設定または設定項目を報告または編集することはできません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP1 をインストールするための前提条件


次の表では、.NET 3.5 またはリモートサーバー管理ツール (RSAT) 内のグループポリシー管理コンソールが見つからない場合の、AGPM 4.0 SP1 クライアントとサーバーインストーラーでの動作について説明します。

**AGPM クライアント 4.0 SP1**

**AGPM サーバー 4.0 SP1**

**オペレーティング システム**

**.NET**

**RSAT**

**.NET**

**RSAT**

**Windows 8**

.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていないか、システムにインストールされていない場合は、インストーラーによってインストールがブロックされます。

.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていないか、システムにインストールされていない場合は、インストーラーによってインストールがブロックされます。

**Windows Server 2012**

.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。

.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。

 

## 関連トピック


[高度なグループ ポリシーの管理](index.md)

[Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート](release-notes-for-microsoft-advanced-group-policy-management-40-sp1.md)

 

 





