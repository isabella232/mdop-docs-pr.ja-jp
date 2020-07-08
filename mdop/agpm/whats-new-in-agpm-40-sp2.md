---
title: AGPM 4.0 SP2 の新機能
description: AGPM 4.0 SP2 の新機能
author: dansimp
ms.assetid: 5c0dcab4-f27d-4153-8b8e-b280b080be51
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56369207780cf0795f16eda91f249a26270c4b47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818147"
---
# AGPM 4.0 SP2 の新機能


このコンテンツでは、Microsoft Advanced グループポリシー管理 (AGPM) 4.0 Service Pack2 (SP2) の拡張機能とサポートされる構成について説明します。 このコンテンツと他の AGPM ドキュメントの間に違いがある場合は、このコンテンツには権限があることを考慮して、他のドキュメントを置き換えることを前提としています。

## <a href="" id="what-s-new"></a>新機能


AGPM 4.0 SP2 では、次の機能がサポートされています。

### Windows 8.1 および Windows Server2012 R2 のサポート

AGPM 4.0 SP2 では、Windows 8.1 および Windows Server2012 R2 オペレーティングシステムのサポートが追加されています。

### クライアント側の新しい拡張子と変更された機能

Windows 8.1 で新しいポリシー設定をサポートするために、AGPM のためにグループポリシークライアント側の拡張機能が追加または変更されています。 これらのポリシー設定を使用すると、グループポリシー管理者は、2つのグループポリシーオブジェクト (Gpo) またはテンプレートの間で変更される特定のポリシー設定を管理および追跡することができます。 クライアント側の拡張機能を表示するには、AGPM クライアントで利用できる設定と差分レポートを使用します。

新しい、または変更されたグループポリシークライアント側拡張機能は次のとおりです。

-   **ワークフォルダーの設定を指定**します。 このポリシー設定を有効にすると、IT 管理者はワークフォルダーを自動的に作成するように構成することができます。 ワークフォルダー機能を使用すると、エンドユーザーは Windows デスクトップデバイスから他のデバイスにファイルを同期することができます。 このポリシー設定を使用して、エンドユーザーのデバイスに同期関係を作成し、ユーザーの作業フォルダーを格納するファイルサーバーの識別方法を構成します。 [**自動プロビジョン**] チェックボックスをオンにすると、ユーザー入力なしで同期パートナーシップが作成され、ユーザーのデバイスへの同期が自動的に開始されます。 [**自動プロビジョン同期**] チェックボックスをオンにしない場合、ユーザーは入力を提供して同期を開始する必要があります。

-   **すべてのユーザーに対して自動セットアップを強制**します。 このポリシー設定を有効にした場合、IT 管理者は、エンドユーザーからの入力を必要とせずに、エンドユーザーのデバイスにワークフォルダーのパートナーシップを自動的に作成するかどうかを決定できます。 このポリシー設定を有効にした場合、同期は、[**ワークフォルダー設定の指定**] ポリシー設定の構成に従って設定されます。 [**自動セットアップをすべてのユーザーに強制**する] ポリシー設定を [**無効**] または [**未構成**] に設定した場合は、[**自動プロビジョニング**] オプションの設定方法に応じ**て、ワーク**フォルダーのパートナーシップが設定されます。

ワークフォルダー機能の詳細については、「[ワークフォルダーの概要](https://go.microsoft.com/fwlink/?LinkId=330444)」を参照してください。

### 顧客のフィードバックと修正プログラムのロールアップ

AGPM 4.0 SP2 には、AGPM 4.0 Service Pack1 (SP1) 以降で検出された問題に対処するための修正プログラムのロールアップが含まれています。 AGPM 4.0 SP2 には、Microsoft Advanced Group Policy Management 4.0 SP1 Hotfix1 を含む最新の修正プログラムが含まれています。 詳細については、サポート技術情報の記事[2873472](https://go.microsoft.com/fwlink/?LinkId=325400)) を参照してください。

### 設定と差分レポートの新しいグループポリシーの拡張機能

[設定] と [差分] レポートに新しいグループポリシー拡張機能が追加されました。

### インストーラーの変更とサポート

AGPM 4.0 SP2 インストーラーの変更とサポートは、次のとおりです。

-   Windows 8 または Windows Server 2012 オペレーティングシステムまたはそれ以降のオペレーティングシステムに AGPM 4.0 SP2 をインストールした場合、AGPM インストーラーは、必要な必須ソフトウェア (グループポリシー管理コンソール (GPMC) と Microsoft .NET Framework 3.5) がインストールされていることを確認します。 この必須ソフトウェアがインストールされていない場合は、AGPM 4.0 SP2 インストールがブロックされます。

-   AGPM サーバーをインストールすると、WCF のアクティブ化、非 HTTP アクティベーション、Windows プロセスのアクティブ化サービスが自動的に有効になります。

-   Windows Vista クライアントオペレーティングシステム以降のオペレーティングシステムでは、AGPM 4.0 SP2 をインストールする前に、使用しているオペレーティングシステムに対応したバージョンのリモートシステム管理ツールをダウンロードします。

-   AGPM 4.0 SP2 は、サポートされている以前のオペレーティングシステムとの下位互換性をサポートしています。

### 指定した構成パラメーターを指定せずに AGPM 4.0 SP2 にアップグレードする機能

次の表に示すように、AGPM クライアントまたは AGPM サーバーを AGPM 4.0 SP2 にアップグレードすることができます。この場合は、次の表に示すように、agpm 4.0 以降の構成パラメーターを再入力する必要があります。 表に示すように、他のバージョンの AGPM から AGPM 4.0 SP2 にアップグレードする場合は、従来のアップグレードを使用する必要があります。これには、構成パラメーターを再入力する必要があります。 AGPM の各バージョンは特定のオペレーティングシステムに関連付けられているため、「[インストールする agpm のバージョンを選択](https://go.microsoft.com/fwlink/?LinkId=254350)する」を参照して、agpm をアップグレードする前に、適切なオペレーティングシステムにアップグレードしてください。

**AGPM 4.0 SP2 でサポートされているアップグレード**

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>アップグレードできる AGPM バージョン</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
<td align="left"><p><strong>4.0 SP2</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3.0</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>スマートアップグレード</p></td>
<td align="left"><p>スマートアップグレード</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.0 SP1</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>スマートアップグレード</p></td>
</tr>
</tbody>
</table>

 

## サポートされている構成


AGPM 4.0 SP2 では、次の表に示す構成がサポートされています。 AGPM では混合構成がサポートされていますが、windows 8.1 と windows Server2012 R2、windows 8、windows Server 2012 など、同じオペレーティングシステム行で AGPM クライアントと AGPM サーバーを実行することを強くお勧めします。

**AGPM 4.0 SP2 でサポートされているオペレーティングシステムとポリシー設定**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>AGPM サーバーでサポートされている構成</strong></th>
<th align="left"><strong>AGPM クライアントでサポートされている構成</strong></th>
<th align="left"><strong>AGPM のサポート</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2 または Windows 8.1</p></td>
<td align="left"><p>Windows Server2012 R2 または Windows 8.1</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012、Windows 8.1、または Windows 8</p></td>
<td align="left"><p>Windows Server 2012 または Windows 8</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 または Windows 8 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8、または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista Service Pack 1 (SP1)</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、windows 8.1、Windows 8、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8、または Windows7</p></td>
<td align="left"><p>サポートされていないアプリ</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、windows 8.1、Windows 8、または Windows7 でのみ存在するポリシー設定または設定項目をレポートまたは編集することはできません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP2 をインストールするための前提条件


次の表では、リモートサーバー管理ツールで .NET Framework 3.5 または GPMC が見つからない場合の Windows 8.1 の AGPM 4.0 SP2 クライアントとサーバーインストーラーの動作について説明します。

**AGPM クライアント**

**AGPM サーバー**

**オペレーティング システム**

**.NET Framework**

**リモート サーバー管理ツール**

**.NET Framework**

**リモート サーバー管理ツール**

**Windows 8.1**

.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。

.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。

**Windows Server2012 R2**

.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。

.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。

GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。

 

## MDOP 技術の入手方法


AGPM 4.0 SP2 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 関連トピック


[高度なグループ ポリシーの管理](index.md)

[Microsoft Advanced Group Policy Management (AGPM) 4.0 SP2 リリース ノート](release-notes-for-microsoft-advanced-group-policy-management-40-sp2.md)

[インストールする AGPM のバージョンの選択](choosing-which-version-of-agpm-to-install.md)

 

 





