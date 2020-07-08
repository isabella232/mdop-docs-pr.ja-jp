---
title: MED-V インストール ファイルのコマンド ライン オプション
description: MED-V インストール ファイルのコマンド ライン オプション
author: dansimp
ms.assetid: 7b8cd3e4-1d09-44a0-b690-f85b0d0a6b02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39582a592a59a4d0e81ef406edc6a984497275c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826467"
---
# MED-V インストール ファイルのコマンド ライン オプション


Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールまたはアンインストールするときに、コマンドプロンプトでインストールファイルを実行するオプションがあります。 このセクションでは、コマンドプロンプトで MED-V をインストールまたはアンインストールするときに指定できるさまざまなオプションについて説明します。

### コマンドライン引数

次のコマンドライン引数を、それぞれの MED-V インストールファイルと共に使うことができます。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">インストールファイル</th>
<th align="left">引数</th>
<th align="left">受け入れられる値</th>
<th align="left">型</th>
<th align="left">説明</th>
<th align="left">既定値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Host Agent</p></td>
<td align="left"><p>MEDVDIR</p></td>
<td align="left"><p>&lt;インストールパス&gt;</p></td>
<td align="left"><p>インストール</p></td>
<td align="left"><p>インストールされているディレクトリを変更する</p></td>
<td align="left"><p>インストールは、プログラムのエンタープライズデスクトップ仮想化に進みます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V ワークスペースパッケージャー</p></td>
<td align="left"><p>MEDVDIR</p></td>
<td align="left"><p>&lt;インストールパス&gt;</p></td>
<td align="left"><p>インストール</p></td>
<td align="left"><p>インストールされているディレクトリを変更する</p></td>
<td align="left"><p>インストールは、プログラムのエンタープライズデスクトップ仮想化に進みます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V ワークスペース</p></td>
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>&lt;インストールパス&gt;</p></td>
<td align="left"><p>インストール</p></td>
<td align="left"><p>インストールされているディレクトリを変更する</p></td>
<td align="left"><p>インストールは ProgramData\Microsoft\Medv\Workspace. に進みます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V ワークスペース</p></td>
<td align="left"><p>VHD の上書き</p></td>
<td align="left"><p>0 または 1</p></td>
<td align="left"><p>インストール</p></td>
<td align="left"><p>VHD が存在する場合 (0) または既存の VHD (1) を上書きすると、インストールが失敗します。</p></td>
<td align="left"><p>仮想ハードディスク (VHD) が既に存在する場合、上書きは行われず、インストールが失敗します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V ワークスペース</p></td>
<td align="left"><p>SUPPRESSMEDVLAUNCH</p></td>
<td align="left"><p>0 または 1</p></td>
<td align="left"><p>インストール</p></td>
<td align="left"><p>MED-V ワークスペースをインストールした後、開始 (0) または start (1) MED-V を実行します。</p></td>
<td align="left"><p>ユーザーインターフェイス (UI) を使って MED-V ワークスペースをインストールした場合、[完了] ページのチェックボックスで、 <strong> </strong> med-v を開始するかどうかが制御されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V ワークスペース</p></td>
<td align="left"><p>DELETEDISKS ディスク</p></td>
<td align="left"><p>0 または 1</p></td>
<td align="left"><p>アンインストール</p></td>
<td align="left"><p>Keep (0) または delete (1) の場合は、MED-V で作成された Vhd</p></td>
<td align="left"><p>Vhd は削除されません。</p></td>
</tr>
</tbody>
</table>

 

### コマンドライン引数の例

次の例では、MED-V workspace パッケージャーによって作成された MED-V ワークスペースをインストールします。 インストールファイルは Temp ディレクトリにログファイルを作成し、quiet モードでインストールファイルを実行しますが、完了時に MED-V ホストエージェントを起動しません。 インストールファイルでは、以前のインストールで残っていた VHD が、同じ名前で上書きされます。

``` syntax
setup.exe /l* %temp%\medv-workspace-install.log /qn SUPPRESSMEDVLAUNCH=1 OVERWRITEVHD=1
```

次の例では、以前にインストールされた MED-V ワークスペースをアンインストールします。 インストールファイルは Temp ディレクトリにログファイルを作成し、quiet モードでインストールファイルを実行します。 インストールファイルは、残っている仮想ハードディスクのファイルをファイルシステムから削除します。

``` syntax
%ProgramData%\Microsoft\Medv\Workspace\uninstall.exe /l* %temp%\medv-workspace-uninstall.log /qn DELETEDIFFDISKS=1
```

## 関連トピック


[MED-V コンポーネントを展開する](deploy-the-med-v-components.md)

[MED-V テクニカル リファレンス](technical-reference-for-med-v.md)

 

 





