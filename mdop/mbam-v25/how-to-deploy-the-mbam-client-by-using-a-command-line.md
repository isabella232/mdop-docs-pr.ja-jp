---
title: コマンド ラインを使用して MBAM クライアントを展開する方法
description: コマンド ラインを使用して MBAM クライアントを展開する方法
author: dansimp
ms.assetid: ac1d4ffe-c26d-41c9-9737-a4f2b37fde24
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 416d76ad876c5114e3a8764111b6a15c879b13b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824487"
---
# コマンド ラインを使用して MBAM クライアントを展開する方法


コマンドラインを使用して、Microsoft BitLocker 管理および監視 (MBAM) クライアントソフトウェアを展開することができます。

## MBAM クライアントソフトウェアを展開するためのコマンドライン


MBAM クライアントソフトウェアを展開するときに、コマンドプロンプトで次のコマンドを入力して、エンドユーザーライセンス契約に自動的に同意します。

**MBAMClientSetup.exe/acceptEula = Yes**

**注** **/Ju**と **/jm**のコマンドラインオプションはサポートされていないため、mbam クライアントソフトウェアのインストールに使用することはできません。

 

コマンドプロンプトで次のコマンドを入力して、MSP を抽出してインストールします。

**MBAMClientSetup.exe &lt; の MSI を抽出するための/extract path &gt; = Yes**

次のコマンドを実行して、サイレントモードで MSI をインストールします。

**&lt;は、展開された MSI/QB ALLUSERS への msiexec/i パス &gt; = 1 REBOOT = ReallySuppress**

**注** MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。 ただし、EULA に同意した後は、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することができます。

 

## <a href="" id="optin-for-microsoft-updates-1-command-line-option"></a>OPTIN \ _FOR \ _MICROSOFT \ _UPDATES = 1 コマンドラインオプション


必要に応じて、クライアントソフトウェアのインストール中にコマンドラインオプションを指定して、 `OPTIN_FOR_MICROSOFT_UPDATES=1` クライアントコンピューターに Microsoft 更新プログラムを自動的にインストールすることができます。 このオプションを指定すると、Microsoft Update が自動的に起動し、クライアントソフトウェアのインストールが完了した後にインストールできる更新プログラムが検索されます。

このコマンドラインオプションは、次のいずれかのインストール方法で使うことができます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">を使用して MBAM クライアントソフトウェアをインストールする</th>
<th align="left">例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>MBAMClientSetup.exe</strong></p></td>
<td align="left"><p><strong>MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES = 1</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>msiexec/i MBAMClient.msi</strong></p></td>
<td align="left"><p><strong>msiexec/i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES = 1</strong></p></td>
</tr>
</tbody>
</table>

 


## 関連トピック


[MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)

 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




