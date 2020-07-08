---
title: Application Virtualization Client のハードウェア要件とソフトウェア要件
description: Application Virtualization Client のハードウェア要件とソフトウェア要件
author: dansimp
ms.assetid: 8b877a2c-5721-4b22-a47f-e2838d58ab12
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5b828f59ba36099b4f6a545cd5bbcb3c72d24e3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819734"
---
# Application Virtualization Client のハードウェア要件とソフトウェア要件


このトピックでは、Application Virtualization デスクトップクライアントをインストールする場合に推奨されるハードウェアとソフトウェアの構成と、リモートデスクトップサービス (以前のターミナルサービス) 用の Application Virtualization クライアントについて説明します。

## Application Virtualization デスクトップクライアント


次の一覧は、Application Virtualization デスクトップクライアントの推奨される最小ハードウェア要件とソフトウェア要件を示しています。 要件は、Microsoft Application Virtualization (App-v) 4.6 SP2 の後に記載されています。その後に、App-v 4.6 SP2 より前のバージョンの要件が示されています。

**注** Application Virtualization (App-v) デスクトップクライアントでは、ホストオペレーティングシステムの要件を超えて、追加のプロセッサや RAM リソースは必要ありません。

 

### ハードウェア要件

ハードウェア要件は、すべてのバージョンに適用されます。

-   「プロセッサ」—使用しているオペレーティングシステムに推奨されるシステム要件を参照してください。

-   RAM: 使用しているオペレーティングシステムに推奨されるシステム要件を参照してください。

-   [Disk] —キャッシュのインストールと6GB の30MB。

### App-v 4.6 SP2 のソフトウェア要件

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
<th align="left">アーキテクチャ SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>プロフェッショナルエディション</p></td>
<td align="left"><p>読み</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>ビジネス、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>Pro または Enterprise Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
</tbody>
</table>

Setup.exe の方法を使用している場合は、次のソフトウェアの前提条件が自動的にインストールされます。 Setup.msi インストールプログラムを使用している場合は、最初に次の製品をインストールする必要があります。
- **Microsoft visual c++ 2005 Sp1 再頒布可能パッケージ (x86)**— Microsoft visual C++ 2005 Sp1 再頒布可能パッケージ (x86) のインストールの詳細については、「 [microsoft VISUAL C++ 2005 Sp1 再頒布可能パッケージ (](https://go.microsoft.com/fwlink/?LinkId=119961) x86) (x86) ()」を参照してください https://go.microsoft.com/fwlink/?LinkId=119961) 。 App-v クライアントのバージョン 4.5 SP2 の場合は、 [Microsoft Visual C++ 2005 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム](https://go.microsoft.com/fwlink/?LinkId=169360)(で Vcredist\_x86.exe をダウンロード https://go.microsoft.com/fwlink/?LinkId=169360) します。
  -   **Microsoft CORE Xml サービス (msxml) 6.0 SP1 (x86)**— MICROSOFT Core xml SERVICES (msxml) 6.0 SP1 (x86) のインストールの詳細については、「 [Microsoft core XML services (MSXML) 6.0 sp1 (x86](https://go.microsoft.com/fwlink/?LinkId=63266) )」 (x86) () を参照してください https://go.microsoft.com/fwlink/?LinkId=63266) 。

Application Virtualization (App-v) 4.6 デスクトップクライアントの場合、Setup.exe メソッドを使用している場合は、次の追加ソフトウェアの前提条件が自動的にインストールされます。 Setup.msi インストールプログラムを使用している場合は、他にも記載されているその他の前提条件をインストールする必要があります。

-   **Microsoft VisualC + + 2008SP1 再頒布可能パッケージ (x86)**: Microsoft visualc + + 2008 Sp1 再頒布可能パッケージ (x86) のインストールの詳細については、「 [microsoft visualc + + 2008 Sp1 再頒布可能パッケージ (x86)」 (x86) ()](https://go.microsoft.com/fwlink/?LinkId=150700)を参照してください https://go.microsoft.com/fwlink/?LinkId=150700) 。

### App-v 4.6 SP2 より前のバージョンのソフトウェア要件

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
<th align="left">アーキテクチャ SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>プロフェッショナルエディション</p></td>
<td align="left"><p>SP2 または SP3</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>ビジネス、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p>Service pack、SP1、または SP2 がない</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7 ¹</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
</tbody>
</table>
¹ App-v 4.5 SP1 および SP2 でサポートされているアプリ-V 4.6 および 4.6 SP1 のみ

Application Virtualization (App-v) 4.6 デスクトップクライアントでは、これらのオペレーティングシステムの x86 および x64 Sku がサポートされています。

Setup.exe の方法を使用している場合は、次のソフトウェアの前提条件が自動的にインストールされます。 Setup.msi インストールプログラムを使用している場合は、最初に次の製品をインストールする必要があります。

-   <strong>Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x86) </strong> — Microsoft Visual c++ 2005 Sp1 再頒布可能パッケージ (x86) のインストールの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=119961" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=119961)"> Microsoft visual C++ 2005 Sp1 再頒布可能パッケージ (x86) </a> ( <a href="https://go.microsoft.com/fwlink/?LinkId=119961" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=119961"> https://go.microsoft.com/fwlink/?LinkId=119961 )」を参照してください </a> 。 App-v クライアントのバージョン 4.5 SP2 の場合は、 <a href="https://go.microsoft.com/fwlink/?LinkId=169360" data-raw-source="[Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360)"> Microsoft Visual C++ 2005 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム () から Vcredist_x86.exe をダウンロード </a> <a href="https://go.microsoft.com/fwlink/?LinkId=169360" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=169360"> https://go.microsoft.com/fwlink/?LinkId=169360 </a> してください。

-   <strong>Microsoft Core XML サービス (MSXML) 6.0 SP1 (x86) </strong> : Microsoft CORE Xml services (msxml) 6.0 SP1 (x86) のインストールの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=63266" data-raw-source="[Microsoft Core XML Services (MSXML) 6.0 SP1 (x86)](https://go.microsoft.com/fwlink/?LinkId=63266)"> MICROSOFT Core xml SERVICES (msxml) 6.0 sp1 (x86) ()」を参照してください </a> <a href="https://go.microsoft.com/fwlink/?LinkId=63266" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=63266"> https://go.microsoft.com/fwlink/?LinkId=63266 </a> 。

-   <strong>Microsoft アプリケーションエラー報告 </strong> : このソフトウェアのインストールプログラムは、 <strong> </strong> 自己解凍アーカイブファイルの Support\Watson フォルダーに含まれています。

Application Virtualization (App-v) 4.6 デスクトップクライアントの場合、Setup.exe メソッドを使用している場合は、次の追加ソフトウェアの前提条件が自動的にインストールされます。 Setup.msi インストールプログラムを使用している場合は、他にも記載されているその他の前提条件をインストールする必要があります。

-   <strong>Microsoft Visual C++ 2008 SP1 再頒布可能パッケージ (x86) </strong> — Microsoft Visual c++ 2008 Sp1 再頒布可能パッケージ (x86) のインストールの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=150700" data-raw-source="[Microsoft Visual C++ 2008 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=150700)"> Microsoft visual C++ 2008 Sp1 再頒布可能パッケージ (x86) </a> ( <a href="https://go.microsoft.com/fwlink/?LinkId=150700" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=150700"> https://go.microsoft.com/fwlink/?LinkId=150700 )」を参照してください </a> 。

## リモートデスクトップサービスのアプリケーション仮想化クライアント

リモートデスクトップサービスのアプリケーション仮想化クライアントに推奨されるハードウェアとソフトウェアの要件を次に示します。 要件は appv461_3 の最初に記載されています。その後、App-v 4.6 SP2 の前にあるバージョンの要件を示します。

リモートデスクトップサービスの Application Virtualization (App-v) クライアントでは、ホストオペレーティングシステムの要件を超えて、追加のプロセッサリソースや RAM リソースを必要としません。

### ハードウェア要件

ハードウェア要件は、すべてのバージョンに適用されます。

-   「プロセッサ」—使用しているオペレーティングシステムに推奨されるシステム要件を参照してください。

-   RAM: 使用しているオペレーティングシステムに推奨されるシステム要件を参照してください。 これらの要件は、ユーザーとアプリケーションの数によっても異なります。

-   [Disk] —キャッシュのインストールと6GB の30MB。

### App-v 4.6 SP2 のソフトウェア要件

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
<th align="left">アーキテクチャ SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

Setup.exe の方法を使用している場合は、次のソフトウェアの前提条件が自動的にインストールされます。 Setup.msi インストールプログラムを使用している場合は、最初に次の製品をインストールする必要があります。

-   **Microsoft VisualC + + 2005SP1 再頒布可能パッケージ (x86)**— Microsoft visualc + + 2005 Sp1 再頒布可能パッケージ (x86) のインストールの詳細については、「 [microsoft visualc + + 2005 sp1 パッケージ (](https://go.microsoft.com/fwlink/?LinkId=119961) x86)」 (x86) () を参照してください https://go.microsoft.com/fwlink/?LinkId=119961) 。 App-v クライアントのバージョン 4.5 SP2 の場合、 [Microsoft Visual C++ 2005 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム](https://go.microsoft.com/fwlink/?LinkId=169360)() から Vcredist\_x86.exe をダウンロード https://go.microsoft.com/fwlink/?LinkId=169360) します。

-   **Microsoft CORE Xml サービス (msxml) 6.0 sp1 (x86)**: MICROSOFT Core xml SERVICES (msxml) 6.0 sp1 (x86) のインストールの詳細については、「 [Microsoft core XML services (MSXML) 6.0 sp1 (x86](https://go.microsoft.com/fwlink/?LinkId=63266) )」を参照してください https://go.microsoft.com/fwlink/?LinkId=63266) 。

-   **Microsoft アプリケーションエラー報告**: このソフトウェアのインストールプログラムは、自己解凍アーカイブファイルの**support¥ Watson**フォルダーに含まれています。

Application Virtualization (App-v) 4.6 デスクトップクライアントの場合、Setup.exe メソッドを使用している場合は、次の追加ソフトウェアの前提条件が自動的にインストールされます。 Setup.msi インストールプログラムを使用している場合は、他にも記載されているその他の前提条件をインストールする必要があります。

-   **Microsoft VisualC + + 2008SP1 再頒布可能パッケージ (x86)**: Microsoft visualc + + 2008 Sp1 再頒布可能パッケージ (x86) のインストールの詳細については、「 [microsoft visualc + + 2008 Sp1 再頒布可能パッケージ (x86)」 (x86) ()](https://go.microsoft.com/fwlink/?LinkId=150700)を参照してください https://go.microsoft.com/fwlink/?LinkId=150700) 。

### App-v 4.6 SP2 より前のバージョンのソフトウェア要件

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
<th align="left">アーキテクチャ SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

リモートデスクトップサービスの Application Virtualization (App-v) 4.6 クライアントは、これらのオペレーティングシステムの x86 および x64 Sku をサポートしています。

## 関連トピック
- [Application Virtualization Sequencer のハードウェア要件とソフトウェア要件](application-virtualization-sequencer-hardware-and-software-requirements.md)
- [Application Virtualization のシステム要件](application-virtualization-system-requirements.md)
- [コマンド ラインを使用してクライアントをインストールする方法](how-to-install-the-client-by-using-the-command-line-new.md)
- [Application Virtualization Client を手動でインストールする方法](how-to-manually-install-the-application-virtualization-client.md)
- [Application Virtualization Client をアップグレードする方法](how-to-upgrade-the-application-virtualization-client.md)
