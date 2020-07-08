---
title: MED-V ワークスペースの数と種類の特定
description: MED-V ワークスペースの数と種類の特定
author: dansimp
ms.assetid: 11642253-6b1f-4c4a-a11e-48d8a360e1ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e0c9ed4b0ce92d0ca752525b847405bbce90a270
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827264"
---
# MED-V ワークスペースの数と種類の特定


MED-V は、Windows XP を必要とする、またはホストコンピューター上のバージョンとは異なるバージョンの Internet Explorer が必要なアプリケーションを実行するための仮想環境を作成します。 この仮想環境は、MED-V ワークスペースと呼ばれます。

Windows 7 に移行する際に、組織が直面するアプリケーションの互換性の要件によっては、特定のユーザーまたは部門のみが、MED-V ワークスペースを必要とする場合があります。 展開を計画するときは、企業で必要な MED-V ワークスペースの数を決定する必要があります。 また、各 MED-V ワークスペースの要件も定義する必要があります。

## MED-V ワークスペースの数と種類を特定する


MED-V ワークスペースを作成する企業のコンピューターとグループを特定します。 通常、これらは、Windows 7 に移行できないアプリケーションへのアクセスを必要とするユーザーです。 移行できないアプリケーションと、これらのアプリケーションを実行するために MED-V ワークスペースが必要なユーザーを特定します。

さらに、Windows 7 用に最適化されていないイントラネットアドレスがある場合もあります。 MED-V ワークスペースには、Internet Explorer ブラウザーが用意されており、Windows 7 に移行する準備がまだできていない web アドレスにエンドユーザーがアクセスできるようになっています。 MED-V の展開を準備および計画する際には、ホストコンピューターの Internet Explorer から MED-V ワークスペースの Internet Explorer にリダイレクトする URL アドレスの一覧を特定してコンパイルする必要があります。

最後に、ディスク容量の要件を評価する必要があります。 ほとんどの MED-V ワークスペースは、2ギガバイト (GB) 以上です。 システムで利用可能なディスク領域は、ユーザーの数と MED-V の構成によっては、すぐに使うことができます。 また、会社の優先する配布方法では、追加のスペースが必要になる場合もあります。 通常、MED-V ワークスペースを使用するには、少なくとも 10 GB のディスク領域を解放する必要がありますが、画像のサイズによって大きく異なります。

### MED-V ワークスペースに必要なディスク領域を計算する

MED-V workspace には、インストールされているホストコンピューターのメモリとディスク領域が必要です。 少なくとも、ホストには 2 GB のディスク領域が必要です。 ディスク領域は可変であり、ユーザーの MED-V ワークスペースのアプリケーションとデータの数によって異なります。

MED-V には、最低 10 GB のディスク領域をお勧めします。 この金額は、基本的な Windows XP ワークスペースと、基本的にインストールされたアプリケーションと web リダイレクションを使用できます。 また、ホストスワップドライブで利用可能な領域も用意されています。 基本構成では、MED-V と1つの展開された MED-V ワークスペースで、6 ~ 8 GB の範囲で利用できます。 MED-V ワークスペースに多数のアプリケーションを含める場合、またはコンピューターあたり複数のユーザーがいる場合は、次の計算を使用して、MED-V ワークスペースで必要なディスク領域をより正確に特定できます。

*ベース VHD + (コンピューターあたり x (差分ディスク + 保存された状態))*

必要なディスク領域を計算するには、次のことを確認します。

-   **ベース VHD のサイズ**– med-v ワークスペースの作成に使用された仮想ハードディスク。

    **重要** Medv ファイルが圧縮されているため、medv ファイルのサイズを計算に使用しないでください。

     

-   [**コンピューターごと**] – med-v は、コンピューター上のユーザーごとに med-v ワークスペースを作成します。MED-V ワークスペースでは、ユーザーがログオンするたびにディスク領域が消費され、MED-V ワークスペースが作成されます。

-   **差分ディスクのサイズ**-基本 VHD との差を追跡するために使用されます。 このサイズは、仮想ハードディスクにアプリケーションとソフトウェア更新プログラムを追加するときに異なります。 差分ディスクは、med-v を初めて起動したときに、各 Hyper-v ユーザーに対して作成されます。

-   保存された**状態ファイルのサイズ**。仮想マシンで状態を維持するために使用されます。 通常、これは、仮想マシンに割り当てられている RAM よりわずかに大きくなります。 たとえば、1 GB の RAM を割り当てると、1081000 KB のファイルが作成されます。

次の例は、2.6 GB の仮想ハードディスクを持つ MED-V ワークスペースの3人のユーザーに基づいて計算したものです。

*2.6 gb + (3 x (1.5 gb + 1gb)) = 10.1 gb*

**注** MED-V のベストプラクティスは、ラボ展開を使用して要件を検証することで、必要な領域を計算することです。

 

### ファイルのサイズを確認するためのファイルを見つける

次の場所には、コンピューターとユーザー設定のファイルが含まれています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">型</th>
<th align="left">位置情報</th>
<th align="left">ファイル</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ベース VHD</p></td>
<td align="left"><p>%ProgramData%\Microsoft\Medv\Workspace</p></td>
<td align="left"><p><em>InternalName </em> - <em> InternalName </em> は、Med-v ワークスペースパッケージャーで選択した仮想ハードディスクの名前です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>差分ディスク</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\MEDV\v2\Virtual マシン</p></td>
<td align="left"><p><em>WorkspaceName </em></p></td>
</tr>
<tr class="odd">
<td align="left"><p>保存された状態ファイル</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\MEDV\v2\Virtual マシン</p></td>
<td align="left"><p><em>WorkspaceName </em> vsv</p></td>
</tr>
</tbody>
</table>

 

### 共有の MED-V ワークスペースに必要なディスク領域を計算する

1台のコンピューターで共有の MED-V ワークスペースの展開を計算する場合、MED-V では、すべてのユーザーに対して1つの差分ディスクしか構成されていないため、計算でコンピューターあたりのユーザー数は "1" になります。

%ProgramData%\\Microsoft\\Medv\\AllUsers. では、差分ディスクと、共有された MED-V ワークスペースの保存された状態ファイルを見つけることができます。

## 関連トピック


[MED-V 展開を定義して計画する](define-and-plan-your-med-v-deployment.md)

[MED-V の計画](planning-for-med-v.md)

 

 





