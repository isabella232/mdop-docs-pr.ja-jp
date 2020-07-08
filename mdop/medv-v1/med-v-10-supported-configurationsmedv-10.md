---
title: MED-V 1.0 でサポートされる構成
description: MED-V 1.0 でサポートされる構成
author: dansimp
ms.assetid: 74643de6-549e-4177-a559-6407e156ed3a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3b8ffdfb6e34fe7888ea5ace0ff7264bd978a548
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812610"
---
# MED-V 1.0 でサポートされる構成


このトピックでは、お客様の環境に Microsoft Enterprise Desktop Virtualization (MED-V) 1.0 をインストールして実行するために必要な要件を示します。

## MED-V 1.0 クライアントシステム要件


### MED-V クライアントオペレーティングシステム要件

次の表は、MED-V 1.0 クライアントインストールでサポートされているオペレーティングシステムを示しています。

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
<td align="left"><p>ビジネス、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>



**注**  
MED-V クライアントは、ネイティブ x64 モードでは実行されません。 代わりに、MED-V は、64ビットコンピューター上の windows 64 ビット (WOW64) モードの Windows で実行されます。



### <a href="" id="med-v-1-0-client-configuration-"></a>MED-V 1.0 クライアント構成

**.NET Framework のバージョン**

以下のバージョンの Microsoft .NET Framework は、MED-V 1.0 クライアントのインストールでサポートされています。

-   .NET Framework 2.0 または .NET Framework 2.0 SP1

-   .NET Framework 3.0 または .NET Framework 3.0 SP1

-   .NET Framework 3.5 または .NET Framework 3.5 SP1

**仮想化エンジン**

Microsoft サポート技術情報の記事974918で説明されている修正プログラムを含む microsoft Virtual PC 2007 SP1 は、次の構成での MED-V 1.0 クライアントのインストールでサポートされています。

-   静的仮想ハードディスク (VHD) ファイル

-   同じディレクトリ内にある複数の VHD ファイル

-   動的 VHD ファイル

**インターネット ブラウザー**

Windows Internet Explorer 7 と Windows Internet Explorer 8 は、MED-V 1.0 クライアントのインストールでサポートされています。

**Microsoft Hyper-V Server**

MED-V クライアントは、Microsoft Hyper-v server 環境ではサポートされていません。

## MED-V 1.0 ワークスペースシステム要件


### MED-V ワークスペースのオペレーティングシステム要件

次の表は、MED-V 1.0 ワークスペースでサポートされているオペレーティングシステムの一覧です。

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



### <a href="" id="med-v-1-0-workspace-configuration-"></a>MED-V 1.0 ワークスペースの構成

**.NET Framework のバージョン**

MED-V を使用するには、MED-V 1.0 workspace のインストールでサポートされている次のいずれかのバージョンの Microsoft .NET Framework が必要です。

-   .NET Framework 2.0 SP1

-   .NET Framework 3.0 SP1

-   .NET Framework 3.5 または .NET Framework 3.5 SP1

**注**  
MED-V ワークスペースが将来のバージョンの MED-V と互換性があることを確認するには、.NET Framework 3.5 SP1 が推奨されます。



**インターネット ブラウザー**

Windows Internet Explorer 6 SP2 と Windows Internet Explorer 7 は、MED-V 1.0 ワークスペースのインストールでサポートされています。

### <a href="" id="med-v-workspace-images-"></a>MED-V ワークスペースのイメージ

MED-V ワークスペースの画像は、Virtual PC 2007 SP1 を使用して作成する必要があります。

## MED-V 1.0 サーバーシステム要件


### MED-V 1.0 サーバーオペレーティングシステム要件

次の表は、MED-V 1.0 サーバーインストールでサポートされているオペレーティングシステムの一覧です。

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
<td align="left"><p>なし</p></td>
<td align="left"><p>X86 または x64</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-server-configuration-"></a>MED-V 1.0 サーバーの構成

**.NET Framework のバージョン**

MED-V を使用するには、MED-V 1.0 workspace のインストールでサポートされている次のいずれかのバージョンの Microsoft .NET Framework が必要です。

-   .NET Framework 2.0 または .NET Framework 2.0 SP1

-   .NET Framework 3.0 または .NET Framework 3.0 SP1

-   .NET Framework 3.5 または .NET Framework 3.5 SP1

**Microsoft SQL Server バージョン**

次のバージョンの Microsoft SQL Server は、SQL Server がローカルにインストールされているか、または MED-V 1.0 サーバーからリモートでインストールされている場合に、MED-V 1.0 でサポートされます。

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

## MED-V 1.0 のグローバリゼーション情報


MED-V は英語以外の言語ではリリースされませんが、MED-V 1.0 クライアント、ワークスペース、サーバーのインストールでは、次の Windows オペレーティングシステム言語バージョンがサポートされています。

-   英語

-   フランス語

-   ドイツ語

-   イタリア語

-   スペイン語

-   ポルトガル語 (ブラジル)









