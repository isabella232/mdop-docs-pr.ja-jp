---
title: Microsoft Application Virtualization 4.6 SP2 について
description: Microsoft Application Virtualization 4.6 SP2 について
author: dansimp
ms.assetid: 1429e314-9c38-472b-8687-3bed6cf0015c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 16303380782a086cfd750c7a8b2f99bf4f4c8b5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820017"
---
# Microsoft Application Virtualization 4.6 SP2 について


Microsoft Application Virtualization (App-v) 4.6 SP2 には、このトピックで説明するいくつかの拡張機能と新機能が用意されています。

**注意** このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。 Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。 レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。 Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。 レジストリは、自分の責任において変更してください。

 

**Windows 8 および Windows Server 2012 のサポート**

App-v 4.6 SP2 では、Windows 8 と Windows Server 2012 のリモートデスクトップサービスのサポートが追加されています。

**App-v 5.0 クライアントとの共存のサポート**

App-v 4.6 SP2 は、Microsoft Application Virtualization 5.0 クライアントとの共存をサポートしています。 App-v 4.6 SP2 クライアントとの共存のために App-v 5.0 クライアントを構成する方法については、「App-v 5.0 ドキュメント」を参照してください。 App-v 5.0 の詳細については、TechNet の「 [Application Virtualization 5](https://go.microsoft.com/fwlink/?LinkId=267599) 」を参照してください。

**保護モードで Adobe Reader X を仮想化する機能**

次の手順に従って、その保護モード機能を有効にして Adobe Reader X を仮想化することができます。 以前は、Adobe Reader X を仮想化するために、保護モードを無効にする必要がありました。

App-v の Sequencer を起動する前に、[HKEY] の下に次のレジストリ値を作成します \ _LOCAL \ _MACHINE \\ フトウェア \\ 4 \ ソフトの上書き:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>名前</p></td>
<td align="left"><p>種類</p></td>
<td align="left"><p>データ</p></td>
<td align="left"><p>説明</p></td>
</tr>
<tr class="even">
<td align="left"><p>EnableVFSPassthrough</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>件</p></td>
<td align="left"><p><strong> </strong> 起動フェーズ中に Adobe Reader X を保護モードで起動するには、この値を1に設定します。</p></td>
</tr>
</tbody>
</table>

 

**注** 64ビットオペレーティングシステムを実行しているコンピューターの場合は、_MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides. で [_LOCAL HKEY] にレジストリ値を作成します。

 

Adobe Reader X パッケージの各 OSD ファイルで、POLICIES 要素の下に次の項目を追加し &lt; &gt; ます。

`<VIRTUAL_FILE_SYSTEM_PASS_THROUGH>TRUE</VIRTUAL_FILE_SYSTEM_PASS_THROUGH>`

`<VIRTUAL_REGISTRY_PASS_THROUGH>TRUE</VIRTUAL_REGISTRY_PASS_THROUGH>`

`<ENFORCE_ACLS_ON_VREG_MODIFY>TRUE</ENFORCE_ACLS_ON_VREG_MODIFY>`

**新しい Sequencer コマンドラインパラメーター**

Sequencer の GUI を使用してパッケージアクセラレータ (PA) を作成する場合は、パッケージアクセラレータを適用する管理者に対してパッケージ化と展開のガイダンスを提供する RTF または TXT ファイルを選ぶことができます。 この機能は、Sequencer CLI を使って利用できるようになりました。

`/ACCELERATORDESCRIPTIONFILE:PathToDescriptionFile`

パッケージアクセラレーターの作成時にパッケージ化と展開のガイダンスを提供する RTF または TXT ファイルへのパスを指定します。

**Microsoft アプリケーションのエラーレポートをインストールする必要がなくなりました**

setup.msi を使用して App-v 4.6 SP2 クライアントをインストールしているときに、Microsoft アプリケーションエラー報告 (dw20shared.msi) をインストールする必要がなくなりました。 App-V 4.6 SP2 では、Microsoft エラー報告機能が使用されるようになりました。 詳細については、「 [Setup.msiを使用して App-v クライアントをインストールする方法](https://go.microsoft.com/fwlink/?LinkId=267237)」を参照してください。

**顧客のフィードバックと修正プログラムのロールアップ**

App-v 4.6 SP2 には、アプリ-V 4.6 SP1 のリリース以降に発生した問題に対処するための修正プログラムが含まれています。 App-v 4.6 SP2 には、Microsoft Application Virtualization 4.6 SP1 修正プログラム6を含む最新の修正プログラムが含まれています。

## このセクションの内容


<a href="" id="app-v-4-6-sp2-release-notes"></a>[App-V 4.6 SP2 リリース ノート](https://go.microsoft.com/fwlink/?LinkId=267600)  
App-v 4.6 SP2 の既知の問題に関する最新情報を提供します。

 

 





