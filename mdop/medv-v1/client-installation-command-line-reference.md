---
title: クライアント インストールのコマンド ライン リファレンス
description: クライアント インストールのコマンド ライン リファレンス
author: dansimp
ms.assetid: 122a593d-3314-4e9b-858a-08a25ed00c32
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 708daf82699c63dfaa1f99ae595911cf6bad3737
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826727"
---
# クライアント インストールのコマンド ライン リファレンス


**コマンドラインから MED-V をインストールするには**

1.  コマンドラインで、MED-V パッケージを実行し、次の表で説明されている任意のパラメーターを指定します。

2.  MED-V パッケージは*MED-V\_x.msi*と呼ばれます。ここで、 *x*はバージョン番号です。

    たとえば、 *MED-V\_1.0.65.msi*とします。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">値</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/quiet</p></td>
<td align="left"><p></p></td>
<td align="left"><p>サイレントインストール</p></td>
</tr>
<tr class="even">
<td align="left"><p>/log &lt; ログファイルへの完全なパス&gt;</p></td>
<td align="left"><p>ログファイルへの完全パス。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>インストールディレクトリへの完全パス。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>VMSFOLDER</p></td>
<td align="left"><p>仮想マシンフォルダーへの完全パス。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALL_ADMIN_TOOLS</p></td>
<td align="left"><p><strong>1, 0</strong></p>
<p>既定値: <strong> 0</strong></p></td>
<td align="left"><p>MED-V 管理ツールをインストールします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>START_AUTOMATICALLY</p></td>
<td align="left"><p><strong>1, 0</strong></p>
<p>既定値: <strong> 0</strong></p></td>
<td align="left"><p>ユーザーが Windows にログオンするたびに、MED-V クライアントが自動的に開始されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SERVER_ADDRESS</p></td>
<td align="left"><p>ホスト名または IP</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SERVER_PORT</p></td>
<td align="left"><p>ポート</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SERVER_SSL</p></td>
<td align="left"><p><strong>1, 0</strong></p>
<p><strong>https </strong> または <strong> http の場合</strong></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>START_MEDV</p></td>
<td align="left"><p><strong>1, 0</strong></p>
<p>既定値: <strong> 1</strong></p></td>
<td align="left"><p>MED-V のインストール完了時に MED-V を開始します。</p>
<div class="alert">
<strong>注</strong><br/><p>MED-V がシステムによってインストールされている場合は、START_MEDV = 0 を設定することをお勧めします。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>DESKTOP_SHORTCUT</p></td>
<td align="left"><p><strong>1, 0</strong></p>
<p>既定値: <strong> 1</strong></p></td>
<td align="left"><p>デスクトップに、MED-V クライアントを起動するショートカットを作成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MINIMAL_RAM_REQUIRED</p></td>
<td align="left"><p>MB 単位の RAM</p></td>
<td align="left"><p>MED-V をインストールするときには、コンピューターの RAM の最小容量が指定されているかどうかを確認します。 存在しない場合、インストールは中止されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SKIP_OS_CHECK</p></td>
<td align="left"><p><strong>1, 0</strong></p></td>
<td align="left"><p>オペレーティングシステムの検証を省略します。</p></td>
</tr>
</tbody>
</table>











