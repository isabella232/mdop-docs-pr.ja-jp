---
title: コマンド ラインを使用してシーケンス処理されたアプリケーション パッケージをアップグレードする方法
description: コマンド ラインを使用してシーケンス処理されたアプリケーション パッケージをアップグレードする方法
author: dansimp
ms.assetid: 682fac46-c71d-4731-831b-81bfd5032764
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eade2ced43852419176f635918f0a6b7c3444aee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816487"
---
# コマンド ラインを使用してシーケンス処理されたアプリケーション パッケージをアップグレードする方法


コマンドラインを使用して仮想アプリケーションをアップグレードするには、次の手順を使用します。 コマンドラインを使用して既存の仮想アプリケーションパッケージをアップグレードすると、元のバージョンの sft ファイルが削除されます。 コマンドラインを使用してパッケージをアップグレードする前に、関連付けられた sft ファイルをバックアップしておく必要があります。

**仮想アプリケーションをアップグレードするには**

1.  Application Virtualization (App-v) Sequencer を実行しているコンピューターでコマンドプロンプトを開くには、[**スタート**]、[**実行**]、[ **cmd**] の各オプションを選びます。 **[OK]** をクリックします。

2.  コマンドプロンプトで、App-v Sequencer がインストールされている場所を指定します。 たとえば、コマンドプロンプトでは、次のように入力します。 **cd c: cd c/l Microsoft Application Virtualization Sequencer**

3.  コマンドプロンプトで、次のコマンドを入力します。引用符で囲まれたテキストを値で置き換えます。

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **注**  
    追加のパラメーターを指定するには、アップグレードするアプリケーションの複雑さに応じてコマンドラインを使用します。 App-v の Sequencer で使用できるパラメーターの完全な一覧については、「[コマンドラインパラメーター](command-line-parameters.md)」を参照してください。



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. Enter**キーを押します**。

## 関連トピック


[コマンド ラインを使用して仮想アプリケーションを管理する方法](how-to-manage-virtual-applications-using-the-command-line.md)









