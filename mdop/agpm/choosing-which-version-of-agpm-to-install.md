---
title: インストールする AGPM のバージョンの選択
description: インストールする AGPM のバージョンの選択
author: dansimp
ms.assetid: 31357d2a-bc23-4e15-93f4-0beda8ab7a7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/05/2017
ms.openlocfilehash: b09ea8161b6801c62552f1c0d0ef8455dc111e2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819097"
---
# インストールする AGPM のバージョンの選択


Microsoft の高度なグループポリシー管理 (AGPM) の各リリースでは、Windows オペレーティングシステムの特定のバージョンがサポートされています。 同じ1行のオペレーティングシステムで AGPM クライアントと AGPM サーバーを実行することを強くお勧めします。 たとえば、windows 10 では windows Server 2016、windows 8.1 は windows Server2012 R2 などです。

このドメインのオペレーティングシステムの最新バージョンに AGPM サーバーをインストールすることをお勧めします。 AGPM グループポリシー管理コンソール (GPMC) を使用して、グループポリシーオブジェクト (Gpo) のバックアップと復元を行います。 新しいバージョンの GPMC は、以前のバージョンでは利用できないその他のポリシー設定を提供するため、最新バージョンのオペレーティングシステムを使用して、さらに多くのポリシー設定を管理できます。

すべてのバージョンの AGPM は、AGPM が実行されているオペレーティングシステムと同じバージョンまたはそれ以前のバージョンで導入されたポリシー設定のみを管理できます。 たとえば、Windows Server 2012 に AGPM 4.0 SP2 をインストールした場合、Windows Server 2012 以前で導入されたポリシー設定を管理することはできますが、後で導入されたポリシー設定は Windows 8.1 または Windows Server2012 R2 で管理することはできません。

AGPM サーバー上の GPMC のバージョンが、管理者がグループポリシーを管理するために使用するコンピューター上のバージョンよりも古い場合、AGPM サーバーでは、古いバージョンの GPMC で利用できないポリシー設定を保存することはできません。 Windows に含まれるグループ ポリシーの設定のスプレッドシートについては、[Windows および Windows Server のグループ ポリシー設定のリファレンスに関するページ](https://go.microsoft.com/fwlink/p/?LinkId=613627)をご覧ください。

## AGPM 4.0 SP3


Windows 10 を実行しているコンピューターで Gpo を管理している場合は、AGPM 4.0 SP3 を使用する必要があります。 Windows 10 オペレーティングシステムを実行しているコンピューターには、以前のバージョンの AGPM をインストールすることはできません。

表1に、AGPM 4.0 SP3 をインストールできるオペレーティングシステムと、AGPM 4.0 SP3 を使って管理できるポリシー設定を示します。

**表 1: AGPM 4.0 SP3 でサポートされているオペレーティングシステムとポリシー設定**

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
<td align="left"><p>Windows Server 2016 または Windows 10</p></td>
<td align="left"><p>Windows Server 2016 または Windows 10</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2</p></td>
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>KB 4015786 で説明されている警告でサポートされています <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></a>
</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2012 R2 または Windows 8.1</p></td>
<td align="left"><p>Windows Server2012 R2 または Windows 8.1</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2012 R2、Windows Server 2012、または Windows 8.1</p></td>
<td align="left"><p>Windows Server 2012 または Windows 8.1</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista Service Pack 1 (SP1)</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、Windows 8、または Windows7</p></td>
<td align="left"><p>サポートされていないアプリ</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や基本設定項目は報告または編集できません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP2


Windows Server2012 R2 または Windows 8.1 が実行されているコンピューターを使って Gpo を管理している場合は、AGPM 4.0 SP2 を使用する必要があります。 これらのオペレーティングシステムを実行しているコンピューターには、以前のバージョンの AGPM をインストールすることはできません。

表1に、AGPM 4.0 SP2 をインストールできるオペレーティングシステムと、AGPM 4.0 SP2 を使用して管理できるポリシー設定を示します。

**表 2: AGPM 4.0 SP2 でサポートされているオペレーティングシステムとポリシー設定**

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
<td align="left"><p>Windows Server2012 R2、Windows Server 2012、または Windows 8.1</p></td>
<td align="left"><p>Windows Server 2012 または Windows 8.1</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista Service Pack 1 (SP1)</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>サポートされていないアプリ</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や基本設定項目は報告または編集できません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 SP1


表2に、AGPM 4.0 SP1 をインストールできるオペレーティングシステムと、AGPM 4.0 SP1 を使って管理できるポリシー設定を示します。

**表 3: AGPM 4.0 SP1 でサポートされているオペレーティングシステムとポリシー設定**

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
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされますが、Windows 8.1 のみに存在するポリシー設定または設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、Windows Server2008R2、または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server 2012、Windows Server2008R2、または Windows7</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、Windows Server2008R2、または Windows7 にのみ存在するポリシー設定または設定項目を報告したり、編集したりすることはできません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0


表3に、AGPM 4.0 をインストールできるオペレーティングシステムと、AGPM 4.0 を使って管理できるポリシー設定を示します。

**表 4: AGPM 4.0 でサポートされているオペレーティングシステムとポリシー設定**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">AGPM サーバーでサポートされているオペレーティングシステム</th>
<th align="left">AGPM クライアントでサポートされているオペレーティングシステム</th>
<th align="left">AGPM のサポート</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされていますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされていないアプリ</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や基本設定項目は報告または編集できません。</p></td>
</tr>
</tbody>
</table>

 

## AGPM 4.0 より前の AGPM のバージョン


表4は、AGPM 4.0 より前のバージョンの AGPM をインストールできるオペレーティングシステムを示しています。 オペレーティングシステムが表示されない場合は、そのオペレーティングシステムに AGPM をインストールすることはできません。

**表 5: AGPM 4.0 より前のバージョンの AGPM でサポートされているオペレーティングシステム**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">インストールできる AGPM のバージョン</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>3.0</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista SP1</p></td>
<td align="left"><p>3.0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Vista (サービスパックがインストールされていない場合) (32 ビット)</p></td>
<td align="left"><p>2.5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 (32 ビット)</p></td>
<td align="left"><p>2.5</p></td>
</tr>
</tbody>
</table>

 

## MDOP 技術の入手方法


AGPM 4.0 SP2 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 関連トピック


[高度なグループ ポリシーの管理](index.md)

 

 





