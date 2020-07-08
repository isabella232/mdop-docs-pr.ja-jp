---
title: MED-V 2.0 でサポートされる構成
description: MED-V 2.0 でサポートされる構成
author: dansimp
ms.assetid: 88f1d232-aa01-45ab-8da7-d086269250b5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0fed090ec04cf67a32b13533f4003c01ae167493
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825217"
---
# MED-V 2.0 でサポートされる構成


お客様の環境は、ここで説明した構成要件を満たしている可能性があるため、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールして実行することができます。 ホストのオペレーティングシステム、ディスク容量、および MED-V ワークスペースの要件などの要件が含まれています。

## MED-V 2.0 ホストコンピューターの要件


### MED-V 2.0 ホストオペレーティングシステム要件

次の表は、ホストコンピューターでの MED-V 2.0 インストールでサポートされているオペレーティングシステムを示しています。

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
<td align="left"><p>Windows7</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極</p></td>
<td align="left"><p>なしまたは SP1</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
</tbody>
</table>

 

次の表は、MED-V 2.0 でサポートされている各オペレーティングシステムに必要な最小限の RAM を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">最低限必要な RAM</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7 x86</p></td>
<td align="left"><p>2</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows7 x64</p></td>
<td align="left"><p>2</p></td>
</tr>
</tbody>
</table>

 

### 最小推奨ディスク領域

少なくとも10GB の使用可能な記憶域をお勧めします。 ただし、必要なディスク領域は、MED-V ワークスペースで公開されているアプリケーションの数によって大きく異なります。

### <a href="" id="med-v-2-0-host-configuration-"></a>MED-V 2.0 ホスト構成

**.NET Framework のバージョン**

.NET Framework 3.5 SP1 バージョンの Microsoft .NET Framework は、MED-V 2.0 で必要です。 ただし、.net framework 3.5 が既にインストールされている場合は、.NET Framework 4 以降のバージョンをインストールできます。

**仮想化エンジン**

Microsoft サポート技術情報の記事977206で説明されている修正プログラムを含む Windows 仮想 Pc は、MED-V 2.0 でサポートされています。

**インターネット ブラウザー**

Windows Internet Explorer8 と Windows Internet Explorer 9 は、MED-V 2.0 でサポートされています。

**Microsoft サーバー環境**

MED-V Host Agent と MED-V ワークスペースパッケージャーは、どのサーバー環境でもサポートされていません。

## MED-V 2.0 ワークスペースの要件


### MED-V 2.0 ワークスペースのオペレーティングシステム要件

次の表は、MED-V 2.0 ワークスペースでサポートされているオペレーティングシステムの一覧です。

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
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>プロフェッショナルエディション</p></td>
<td align="left"><p>読み</p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="med-v-2-0-workspace-configuration-"></a>MED-V 2.0 ワークスペース構成

**.NET Framework のバージョン**

.NET Framework 3.5 SP1 バージョンの Microsoft .NET Framework のみが、MED-V 2.0 ワークスペースのインストールでサポートされています。

**インターネット ブラウザー**

Windows Internet Explorer6、Windows internet Explorer7、Windows Internet Explorer8、windows Internet Explorer9 は、MED-V 2.0 ワークスペースのインストールでサポートされています。

### MED-V 2.0 ワークスペースの作成

MED-V 2.0 ワークスペースパッケージを作成するために使用される仮想ハードディスクは、Windows Virtual PC を使用して作成する必要があります。

## MED-V 2.0 のグローバリゼーション情報


### MED-V 2.0 Host Agent のグローバリゼーション情報

MED-V 2.0 ホストエージェントでは、次の Windows オペレーティングシステムの言語バージョンがサポートされています。

-   フランス語

-   イタリア語

-   ドイツ語

-   スペイン語

-   韓国語

-   日本語

-   ポルトガル語 (ブラジル)

-   ロシア語

-   繁体字中国語

-   簡体字中国語

-   オランダ語

-   スウェーデン語

-   デンマーク語

-   フィンランド語

-   ポルトガル語

-   ノルウェー語

-   ポーランド語

-   トルコ語

-   ハンガリー語

-   チェコ語

-   ギリシャ語

-   スロバキア語

-   スロベニア語

### MED-V 2.0 ワークスペースパッケージャーのグローバリゼーション情報

以下の Windows オペレーティングシステムの言語バージョンは、MED-V 2.0 Workspace パッケージャーでサポートされています。

-   フランス語

-   イタリア語

-   ドイツ語

-   スペイン語

-   韓国語

-   日本語

-   ポルトガル語 (ブラジル)

-   ロシア語

-   繁体字中国語

-   簡体字中国語

## 関連トピック


[MED-V の展開](deployment-of-med-v.md)

 

 





