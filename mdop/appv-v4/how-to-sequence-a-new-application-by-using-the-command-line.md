---
title: コマンド ラインを使用して新しいアプリケーションをシーケンス処理する方法
description: コマンド ラインを使用して新しいアプリケーションをシーケンス処理する方法
author: dansimp
ms.assetid: c3b5c842-6a91-4d0a-9a22-c7b8d1aeb09a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ea7b1222dc00a0a4649cb342ac1ba41338484889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816687"
---
# コマンド ラインを使用して新しいアプリケーションをシーケンス処理する方法


コマンドラインを使用して、新しいアプリケーションの順序を調整することができます。 コマンドラインを使用すると、多数の仮想アプリケーションを作成する必要がある場合や、連続したアプリケーションを定期的に作成する必要がある場合に便利です。

**重要**  
コマンドラインの順序指定では、既定のシーケンスのみを使用できます。 順序を指定するアプリケーションの既定のインストール設定を変更する必要がある場合は、Application Virtualization (App-v) Sequencer を使用して、仮想アプリケーションを手動で変更するか、仮想アプリケーションを更新する必要があります。 App-v Sequencer を使用した仮想アプリケーションの更新の詳細については、「[既存の仮想アプリケーションをアップグレードする方法](how-to-upgrade-an-existing-virtual-application.md)」を参照してください。



コマンドラインを使用して仮想アプリケーションを作成するには、次の手順に従います。

**コマンドラインを使用してアプリケーションをシーケンスするには**

1.  App-v Sequencer を実行しているコンピューターで、[**スタート**]、[**実行**] の順に選択してコマンドプロンプトを開き、「 **cmd**」と入力します。 **[OK]** をクリックします。

2.  コマンドプロンプトを使用して、App-v Sequencer がインストールされている場所を指定します。 たとえば、コマンドプロンプトでは、次のように入力します。 **cd c: cd c/l Microsoft Application Virtualization Sequencer**

3.  コマンドプロンプトで、次のコマンドを入力します。引用符で囲まれたテキストを値で置き換えます。

    `SFTSequencer /INSTALLPACKAGE:"pathtoMSI" /INSTALLPATH:"pathtopackageroot" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **注**  
    順序を設定するアプリケーションの複雑さに応じてコマンドラインを使用して、追加のパラメーターを指定できます。 App-v の Sequencer で使用できるパラメーターの完全な一覧については、「 [Sequencer コマンドラインパラメーター](sequencer-command-line-parameters.md)」をご覧ください。



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
<td align="left"><p><em>pathtoMSI</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtopackageroot</em></p></td>
<td align="left"><p>Specify the package root directory.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. Enter**キーを押します**。

## 関連トピック


[App-v Sequencer を使用して仮想アプリケーションを作成またはアップグレードする方法](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[Sequencer コマンド ライン エラー コード](sequencer-command-line-error-codes.md)

[Sequencer コマンド ライン パラメーター](sequencer-command-line-parameters.md)









