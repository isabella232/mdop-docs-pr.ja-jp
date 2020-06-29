---
title: 電子ソフトウェア配布を使用して App-V 5.1 パッケージを展開する方法
description: 電子ソフトウェア配布を使用して App-V 5.1 パッケージを展開する方法
author: dansimp
ms.assetid: e1957a5a-1f18-42da-b2c1-a5ae5a4cca7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a9ed5fbb264f8fb9676d7fa18fe4de8019ea8e79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814186"
---
# 電子ソフトウェア配布を使用して App-V 5.1 パッケージを展開する方法


電子ソフトウェア配布 (ESD) システムを使用して、app-v 5.1 仮想アプリケーションを app-v クライアントに展開することができます。 詳細については、使用している ESD で利用できるドキュメントを参照してください。

コンポーネントの要件と、ESD を使って App-v パッケージを展開するオプションについては、「[電子ソフトウェア配布システムを使用してアプリ5.1 の展開を計画する](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md)」を参照してください。

ESD を伴う App-v クライアントコンピューターにパッケージを公開するには、次のいずれかの方法を使用します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サードパーティの ESD によって提供される機能</p></td>
<td align="left"><p>サードパーティの ESD の機能を使用します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>スタンドアロンの Windows インストーラー</p></td>
<td align="left"><p>アプリケーションの最初の順序で作成された関連付けられた Windows インストーラー (.msi) ファイルを使用して、ターゲットクライアントコンピューターにアプリケーションをインストールします。 Windows Installer ファイルには、パッケージを構成し、必要なパッケージファイルをクライアントにコピーするために使用される、関連付けられた App-v 5.1 パッケージファイル情報が含まれています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p>PowerShell コマンドレットを使用して、仮想化されたアプリケーションを展開します。 PowerShell と App-v 5.1 の使用方法の詳細については、「 <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)"> Powershell を使用したアプリの管理-v 5.1」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>

 

**ESD を使って App-v 5.1 パッケージを展開するには**

1.  環境内のコンピューターに app-v 5.1 Sequencer をインストールします。 Sequencer のインストールの詳細については、「 [sequencer をインストールする方法](how-to-install-the-sequencer-51beta-gb18030.md)」を参照してください。

2.  アプリ-V 5.1 Sequencer を使って、仮想アプリケーションを作成します。 仮想アプリケーションの作成について詳しくは、「 [app-v 5.1 で仮想化されたアプリケーションを作成および管理](creating-and-managing-app-v-51-virtualized-applications.md)する」をご覧ください。

3.  仮想アプリケーションを作成したら、ESD ソリューションを使用してパッケージを展開します。

    System Center Configuration Manager を使用している場合は、App-v 5.1 と System Center2012 Configuration Manager を使用する方法について、「 [Configuration manager でのアプリケーション管理の概要」を](https://go.microsoft.com/fwlink/?LinkId=281816)参照してください。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





