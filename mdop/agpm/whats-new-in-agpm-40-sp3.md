---
title: AGPM 4.0 SP3 の新機能
description: AGPM 4.0 SP3 の新機能
author: dansimp
ms.assetid: df495d55-9fbf-4f7e-a7af-3905f4f8790e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 44e7dc6c5de75ae3a5e5def638974bae20ad2a1e
ms.sourcegitcommit: 594b6e431af98562e0b806e224d2c5c7e07d2c77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "10895771"
---
# AGPM 4.0 SP3 の新機能


このコンテンツでは、Microsoft Advanced グループポリシー管理 (AGPM) 4.0 Service Pack3 (SP3) の拡張機能とサポートされる構成について説明します。 このコンテンツと他の AGPM ドキュメントの間に違いがある場合は、このコンテンツには権限があることを考慮して、他のドキュメントを置き換えることを前提としています。

## <a href="" id="what-s-new"></a>新機能


AGPM 4.0 SP3 は、次の機能をサポートしています。

### Windows 10 のサポート

AGPM 4.0 SP3 では、Windows 10 と Windows Server 2016 オペレーティングシステムのサポートが追加されています。

### PowerShell のサポート

AGPM 4.0 SP3 では、PowerShell コマンドレットのサポートが追加されています。 説明や構文など、AGPM 4.0 SP3 で利用できるコマンドレットの一覧については、「 [Windows PowerShell による Microsoft デスクトップ最適化パックオートメーション](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps)」を参照してください。

### 顧客のフィードバックと修正プログラムのロールアップ

AGPM 4.0 SP3 には、Microsoft Advanced のグループポリシー管理 4.0 SP2 までのすべての修正プログラムが含まれています。また、AGPM 4.0 SP2 以降で検出された問題に関する修正プログラムも含まれています。

### 構成パラメーターを再入力せずに、AGPM 4.0 SP3 にアップグレードする機能

次の表に示すように、agpm クライアントまたは AGPM サーバーを AGPM 4.0 SP3 にアップグレードすることができます。この場合は、AGPM 4.0 以降の構成パラメーターを再入力する必要があります。 表に示されているように、他のバージョンの AGPM から AGPM 4.0 SP3 にアップグレードする場合は、従来のアップグレードを使用する必要があります。これには、構成パラメーターを再入力する必要があります。 AGPM の各バージョンは特定のオペレーティングシステムに関連付けられているため、「[インストールする agpm のバージョンを選択](https://go.microsoft.com/fwlink/?LinkId=254350)する」を参照して、agpm をアップグレードする前に、適切なオペレーティングシステムにアップグレードしてください。

**AGPM 4.0 SP3 でサポートされているアップグレード**

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
<tbody>
<tr class="odd">
<td align="left"><p><strong>アップグレードできる AGPM バージョン</strong></p></td>
<td align="left"><p><strong>2.5</strong></p></td>
<td align="left"><p><strong>3.0</strong></p></td>
<td align="left"><p><strong>4.0</strong></p></td>
<td align="left"><p><strong>4.0 SP1</strong></p></td>
<td align="left"><p><strong>4.0 SP2</strong></p></td>
<td align="left"><p><strong>4.0 SP3</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>2.5</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>従来のアップグレード</p></td>
<td align="left"><p>インストールがブロックされている</p></td>
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
<td align="left"><p>インストールがブロックされている</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>スマートアップグレード</p></td>
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
<td align="left"><p>スマートアップグレード</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.0 SP2</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>該当なし</p></td>
<td align="left"><p>スマートアップグレード</p></td>
</tr>
</tbody>
</table>

 

## サポートされている構成


AGPM 4.0 SP3 では、次の表の構成がサポートされています。 AGPM では混合構成がサポートされますが、windows Server 2016、windows 8.1 with windows Server 2012 R2 など、同じオペレーティングシステムラインで AGPM クライアントと AGPM サーバーを実行することを強くお勧めします。

**AGPM 4.0 SP3 でサポートされているオペレーティングシステムとポリシーの設定**

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
<td align="left"><p>Windows Server 2019 または Windows 10</p></td>
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2016 または Windows 10</p></td>
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2 または Windows 8.1</p></td>
<td align="left"><p>Windows Server2012 R2 または Windows 8.1</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012、または Windows 8.1</p></td>
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista Service Pack 1 (SP1)</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>サポートされていないアプリ</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や基本設定項目は報告または編集できません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP3 をインストールするための前提条件

次の表では、.NET Framework 4.5.1、PowerShell 3.0、またはリモートサーバー管理ツールの GPMC が見つからない場合の、AGPM 4.0 SP3 クライアントとサーバーインストーラーの動作について説明します。

| AGPM クライアント            |                                                                                                 |                                                                            | AGPM サーバー                                                                     |                                                                                                 |                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| オペレーティング システム       | .NET Framework                                                                                  | PowerShell                                                                 | リモート サーバー管理ツール                                              | .NET Framework                                                                                  | リモート サーバー管理ツール                                              |
| Windows 10             | .NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。 | Powershell 3.0 がインストールされていない場合、インストーラーはインストールをブロックします。 | GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。 | .NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。 | GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。 |
| Windows 8.1            | .NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。 | Powershell 3.0 がインストールされていない場合、インストーラーはインストールをブロックします。 | GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。 | .NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。 | GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。 |
| Windows Server 2012 R2 | .NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。 | Powershell 3.0 がインストールされていない場合、インストーラーはインストールをブロックします。 | GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。   | .NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。 | GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。   |

 

## MDOP 技術の入手方法


AGPM 4.0 SP3 は、MDOP 2015 以降の Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 関連トピック


[高度なグループ ポリシーの管理](index.md)

[Microsoft Advanced Group Policy Management (AGPM) 4.0 SP3 リリース ノート](release-notes-for-microsoft-advanced-group-policy-management-40-sp3.md)

[インストールする AGPM のバージョンの選択](choosing-which-version-of-agpm-to-install.md)

 

 





