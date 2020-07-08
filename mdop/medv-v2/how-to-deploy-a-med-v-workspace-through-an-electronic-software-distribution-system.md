---
title: 電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法
description: 電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法
author: dansimp
ms.assetid: b5134c35-e1de-470c-93f8-ead6218d9dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56d21b0c2f010f63c04056d9fadd7763531bd9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812994"
---
# 電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法


電子ソフトウェア配布システムは、低速または高速のネットワーク接続を介して、さまざまなコンピューターにソフトウェアを効率的に移動するように設計されています。 以下のセクションでは、ソフトウェア配布システムを使用して、企業全体で MED-V ワークスペースを展開するのに役立つ情報と手順について説明します。

**注**  
どのソフトウェア配布ソリューションを使用する場合でも、特定の解決策の要件について理解している必要があります。 System Center Configuration Manager 2007 R2 またはそれ以降のバージョンを使用している場合は、Microsoft テクニカルライブラリの[Configuration Manager ドキュメントライブラリ](https://go.microsoft.com/fwlink/?LinkId=66999)を参照してください ( https://go.microsoft.com/fwlink/?LinkId=66999) .



**重要**  
System Center Configuration Manager 2007 SP2 を使用していて、MED-V ワークスペースが**NAT**モードで動作するように構成されている場合、仮想マシンはインターネットベースのクライアントとして分類され、コンテンツをダウンロードする最も近い配布ポイントを検索することはできません。

[Med-v によって管理される vm の機能を改善するための修正プログラム](https://go.microsoft.com/fwlink/?LinkId=201088)( https://go.microsoft.com/fwlink/?LinkId=201088) med-v によって管理され、 **NAT**モードで動作するように構成されている仮想マシンに新機能が追加されています)。 新しい機能により、仮想マシンは最も近い配布ポイントにアクセスできます。 そのため、管理者は仮想マシンとホストコンピューターを同じ方法で管理することができます。 この修正プログラムは、最初にサイトサーバーにインストールしてから、クライアントでインストールする必要があります。

更新プログラムは公開されています。 ただし、Microsoft サービスのライセンス契約に同意するように求められる場合があります。 この修正プログラムを取得するには、連続する web ページの指示に従います。



バッチファイルを使用して、MED-V コンポーネントを一緒に展開することもできますが、これを行うには、Windows 仮想 PC のインストール後に再起動する必要があります。 この要件を回避するには、すべてのコンポーネントをインストールした後、1回の再起動を指定します。 MED-V ワークスペースのインストールによって RUNKEY にエントリが配置されるため、単一の再起動でも MED-V が自動的に開始されます。

**ソフトウェア配布システムを使用して MED-V ワークスペースを展開するには**

1.  電子ソフトウェア配布システムでコンピューターとユーザーのグループを、コンピューター/ユーザーのターゲットセットとして定義します。

2.  配布する必要がある Microsoft インストールファイルごとにパッケージを作成します。 必要なファイルと、それらをインストールする順序を次に示します。

    1.  **Windows VIRTUAL PC** –まだインストールされていない場合は (コンピューターの再起動が必要)。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    2.  **Windows VIRTUAL PC の追加と更新プログラム**(まだインストールされていない場合)。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    3.  **Med-v Host Agent インストールファイル**–ホストエージェント (med-v \ _HostAgent \ _Setup インストールファイル) をインストールします。 詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。

        **Warning**  
        MED-V Host Agent をインストールする前に Internet Explorer を閉じます。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。 また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。



    4.  Med-v ワークスペースの**インストーラー、VHD、セットアップの実行可能ファイル**( **med-v workspace パッケージャー**で作成) 詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。

        **重要**  
        圧縮仮想ハードディスクファイル (medv) とセットアップ実行可能プログラム (setup.exe) は、MED-V workspace installer と同じフォルダーに存在する必要があります。 次に、setup.exe を実行して、MED-V ワークスペースインストーラーをインストールします。



~~~
    **Tip**  
    Because problems can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



3. サイレントモードで実行するようにパッケージを構成します (ユーザーの操作は必要ありません)。

   サイレントモードで実行している場合、Internet Explorer が実行されている場合はそれを閉じるか、MED-V ホストエージェントを起動するように求めるメッセージが表示されなくなります。 どちらの操作も、コンピューターを再起動したときに実行されます。

   **注**  
   Windows Virtual PC をインストールするには、コンピューターを再起動する必要があります。 再起動を抑制して、MED-V をインストールするために必要な前提条件を無視した場合は、1つのインストールプロセスを作成し、すべてのコンポーネントを同時にインストールすることができます。 これは、コマンドライン引数を使って行うこともできます。 これらの引数の例については、「[電子ソフトウェア配布システムを介して Med-v コンポーネントを展開する方法](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch)」を参照してください。 MED-V は、コンピューターを再起動したときに自動的に開始されます。



4. Windows Virtual PC をインストールする前に、MED-V とそのコンポーネントをインストールします。 このトピックで後述するバッチファイルの例を参照してください。

   **重要**  
   必要な VPC コンポーネントの前に MED-V コンポーネントをインストールできるように、例として、[ **\ _PREREQUISITES 無視**] オプションを選びます。 1回の再起動を許可するには、MED-V コンポーネントをこの順序でインストールします。



5. インストールおよびソフトウェア配布システム (ターゲットプラットフォーム、空きディスク領域など) に必要なその他の要件を特定します。

6. パッケージをコンピューター/ユーザーのターゲットセットに割り当てます。

   コンピューターが実行されている間、ソフトウェア配布システムクライアントは、新しいパッケージが利用可能であることを認識し、定義と要件に従ってパッケージのインストールを開始します。 インストールは、サイレントモードで実行する必要があります。 これは、すべてのパッケージがインストールされるまで、再起動を必要としない単一のプロセスとして実行することをお勧めします。

7. インストールが完了したら、更新されたコンピューターを再起動します。

   ソフトウェア配布システムによっては、コンピューターの再起動をスケジュールしたり、通常の作業中にエンドユーザーが手動でコンピューターを再起動したりすることができます。 コンピューターの再起動後、MED-V はエンドユーザーがログオンした後に自動的に開始されます。 MED-V が初めて開始されるときには、初回のセットアップが実行されます。

初めてセットアップを開始したときに、指定した仮想ハードディスクのサイズと、起動時に MED-V ワークスペースに適用されたポリシーの数に応じて、セットアップが完了するまで数分かかることがあります。 エンドユーザーは、通知領域の MED-V アイコンを見て、進捗状況を追跡できます。 初めてセットアップする場合の詳細については、「 [med-v 2.0 の展開の概要](med-v-20-deployment-overview.md)」を参照してください。

**バッチファイルを使用して MED-V ワークスペースをインストールするには**

1.  管理者の資格情報を使用して、コマンドプロンプトでインストールを実行します。

2.  各コンポーネントを1つのディレクトリに配置します。 ネットワーク共有から実行する場合は、medv ファイルを展開するために長い時間が必要です。

3.  ベストプラクティスとして、Windows 仮想 PC と Windows 仮想 PC ホットフィックスは、MED-V Host Agent ファイルと MED-V ワークスペースパッケージファイルの後にインストールすることをお勧めします。 このため、Windows Update では、再起動を要求することによって、インストールプロセスに干渉することはありません。

4.  バッチファイルが完了したら、コンピューターを再起動します。

再起動すると、ユーザーに対して、初回のセットアップを実行して、MED-V の構成を完了するように求められます。

次の例では、指定された引数を使って、1つのプロセスで64ビット MED-V コンポーネントをインストールする方法を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">引数</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/norestart</p></td>
<td align="left"><p>Windows 仮想 PC と Windows 仮想 PC の更新プログラムをインストールして、ホストコンピューターを再起動しないようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/quiet</p></td>
<td align="left"><p>ユーザーの操作なしで、MED-V コンポーネントを quiet モードでインストールします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/qn</p></td>
<td align="left"><p>ユーザーインターフェイスを使わずに、MED-V コンポーネントをインストールします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>IGNORE_PREREQUISITES</p></td>
<td align="left"><p>Windows 仮想 PC をチェックせずにインストールします。</p>
<div class="alert">
<strong>注</strong><br/><p>この引数を指定するのは、このインストールの一部として Windows Virtual PC をインストールする場合のみです。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>オーバー・ WRITEVHD</p></td>
<td align="left"><p>MED-V ワークスペースのインストールを強制し、生成される可能性のあるプロンプトを表示しないようにします。</p></td>
</tr>
</tbody>
</table>



## 例


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## 関連トピック


[MED-V 2.0 展開の概要](med-v-20-deployment-overview.md)

[Windows 7 イメージで MED-V ワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)









