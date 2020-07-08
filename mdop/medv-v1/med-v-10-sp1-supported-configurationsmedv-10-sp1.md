---
title: MED-V 1.0 SP1 でサポートされる構成
description: MED-V 1.0 SP1 でサポートされる構成
author: dansimp
ms.assetid: 4dcf37c4-a061-43d2-878c-28efc87c3cdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5a707e8a3d59a423308f9f735ff38df9e235fbf5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824167"
---
# MED-V 1.0 SP1 でサポートされる構成


このトピックでは、環境に Microsoft Enterprise デスクトップ仮想化 (MED-V) 1.0 Service Pack 1 (SP1) をインストールして実行するために必要な要件を示します。

## MED-V 1.0 SP1 クライアントシステム要件


### MED-V クライアントオペレーティングシステム要件

次の表は、MED-V 1.0 SP1 クライアントのインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインを確認するには、[ライフサイクルでサポートされているサービスパック](https://go.microsoft.com/fwlink/?LinkId=31975)() をご覧ください https://go.microsoft.com/fwlink/?LinkId=31975) 。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/?LinkId=31976)に関する FAQ (を参照してください https://go.microsoft.com/fwlink/?LinkId=31976) 。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows XP</p></td>
<td align="left"><p>プロフェッショナルエディション</p></td>
<td align="left"><p>SP2 または SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>ビジネス、エンタープライズ、または究極</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
</tbody>
</table>



**注**  
MED-V クライアントは、ネイティブ x64 モードでは実行されません。 代わりに、MED-V は、64ビットコンピューター上の windows 64 ビット (WOW64) モードの Windows で実行されます。



次の表は、MED-V 1.0 SP1 でサポートされている各オペレーティングシステムに必要な最小限の RAM を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">必要最小限の RAM</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows XP Professional</p></td>
<td align="left"><p>1 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 x86</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7 x64</p></td>
<td align="left"><p>3 GB</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-client-configuration-"></a>MED-V 1.0 SP1 クライアントの構成

**.NET Framework のバージョン**

以下のバージョンの Microsoft .NET Framework は、MED-V 1.0 SP1 クライアントをインストールする場合にサポートされています。

-   .NET Framework 2.0 または .NET Framework 2.0 SP1

-   .NET Framework 3.0 または .NET Framework 3.0 SP1

-   .NET Framework 3.5 または .NET Framework 3.5 SP1

**仮想化エンジン**

Microsoft サポート技術情報の記事974918で説明されている修正プログラムを含む microsoft Virtual PC 2007 SP1 は、次の構成で、MED-V 1.0 SP1 クライアントのインストールでサポートされています。

-   静的仮想ハードディスク (VHD) ファイル

-   同じディレクトリ内にある複数の VHD ファイル

-   動的 VHD ファイル

**インターネット ブラウザー**

Windows Internet Explorer 7 と Windows Internet Explorer 8 は、MED-V 1.0 SP1 クライアントをインストールする場合にサポートされています。

**Microsoft Hyper-V Server**

MED-V クライアントは、Microsoft Hyper-v Server 環境ではサポートされていません。

## MED-V 1.0 SP1 ワークスペースシステム要件


MED-V 1.0 SP1 は、システム要件の変更について、MED-V 1.0 用のものから行っています。

### MED-V ワークスペースのオペレーティングシステム要件

次の表は、MED-V 1.0 SP1 ワークスペースでサポートされているオペレーティングシステムの一覧です。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインを確認するには、[ライフサイクルでサポートされているサービスパック](https://go.microsoft.com/fwlink/?LinkId=31975)() をご覧ください https://go.microsoft.com/fwlink/?LinkId=31975) 。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/?LinkId=31976)に関する FAQ (を参照してください https://go.microsoft.com/fwlink/?LinkId=31976) 。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 2000</p></td>
<td align="left"><p>Professional</p></td>
<td align="left"><p>SP4</p></td>
<td align="left"><p>X86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows XP</p></td>
<td align="left"><p>プロフェッショナルエディション</p></td>
<td align="left"><p>SP2 または SP3</p>
<div class="alert">
<strong>注</strong><br/><p>MED-V ワークスペースが将来のバージョンの MED-V と互換性があることを確認するには、SP3 をお勧めします。</p>
</div>
<div>

</div></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-workspace-configuration-"></a>MED-V 1.0 SP1 ワークスペースの構成

**.NET Framework のバージョン**

MED-V を使用するには、MED-V 1.0 SP1 ワークスペースのインストールでサポートされている次のいずれかのバージョンの Microsoft .NET Framework が必要です。

-   .NET Framework 2.0 SP1

-   .NET Framework 3.0 SP1

-   .NET Framework 3.5 または .NET Framework 3.5 SP1

**注**  
MED-V ワークスペースが将来のバージョンの MED-V と互換性があることを確認するために、.NET Framework 3.5 SP1 をお勧めします。



**インターネット ブラウザー**

Windows Internet Explorer 6 SP2 と Windows Internet Explorer 7 は、MED-V 1.0 SP1 ワークスペースのインストールでサポートされています。

### <a href="" id="med-v-workspace-images-"></a>MED-V ワークスペースのイメージ

MED-V ワークスペースの画像は、Virtual PC 2007 SP1 を使用して作成する必要があります。

## MED-V 1.0 SP1 サーバーシステム要件


MED-V 1.0 SP1 は、システム要件の変更について、MED-V 1.0 用のものから行っています。

### MED-V 1.0 サーバーオペレーティングシステム要件

次の表は、MED-V 1.0 SP1 server インストールでサポートされているオペレーティングシステムの一覧です。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインを確認するには、[ライフサイクルでサポートされているサービスパック](https://go.microsoft.com/fwlink/?LinkId=31975)() をご覧ください https://go.microsoft.com/fwlink/?LinkId=31975) 。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/?LinkId=31976)に関する FAQ (を参照してください https://go.microsoft.com/fwlink/?LinkId=31976) 。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 2008</p></td>
<td align="left"><p>Standard または Enterprise</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>X86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>Standard または Enterprise</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-server-configuration-"></a>MED-V 1.0 SP1 サーバーの構成

**.NET Framework のバージョン**

MED-V を使用するには、MED-V 1.0 SP1 ワークスペースのインストールでサポートされている次のいずれかのバージョンの Microsoft .NET Framework が必要です。

-   .NET Framework 2.0 または .NET Framework 2.0 SP1

-   .NET Framework 3.0 または .NET Framework 3.0 SP1

-   .NET Framework 3.5 または .NET Framework 3.5 SP1

**Microsoft SQL Server バージョン**

SQL Server がローカルまたは MED-V 1.0 SP1 サーバーからリモートでインストールされている場合、次のバージョンの Microsoft SQL Server が、MED-V 1.0 SP1 でサポートされます。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server のバージョン</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 2005</p></td>
<td align="left"><p>Express、Standard、Enterprise Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>X86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 2008</p></td>
<td align="left"><p>エクスプレス、標準、またはエンタープライズ</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>X86 または x64</p></td>
</tr>
</tbody>
</table>



**Microsoft Hyper-V Server**

MED-V サーバーは、Microsoft Hyper-v server 環境でサポートされています。

## MED-V 1.0 SP1 のグローバリゼーション情報


MED-V は英語以外の言語ではリリースされませんが、MED-V 1.0 SP1 クライアント、ワークスペース、サーバーインストールでは、次の Windows オペレーティングシステム言語バージョンがサポートされています。

-   英語

-   フランス語

-   ドイツ語

-   イタリア語

-   スペイン語

-   ポルトガル語 (ブラジル)

-   オランダ語 (オランダ)

-   日本語









