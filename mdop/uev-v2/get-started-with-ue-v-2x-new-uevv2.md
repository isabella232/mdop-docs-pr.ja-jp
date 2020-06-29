---
title: UE-V 2.x の概要
description: UE-V 2.x の概要
author: dansimp
ms.assetid: 526ecbf0-0dee-4f0b-b017-8f8d25357b14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 02/13/2017
ms.openlocfilehash: d3f01dd67ea9e5f6cfcf5dc3425265deff3f7df1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823287"
---
# UE-V 2.x の概要


このガイドの手順に従って、小規模のテスト環境で Microsoft User Experience Virtualization (UE-V) 2.0 または2.1 をすばやく展開します。 これにより、UE-V が企業内の複数のデバイスでユーザー設定を管理するための適切なソリューションであるかどうかを判断するのに役立ちます。

**注** このセクションの情報は、ドキュメントの残りの部分でさらに詳しく説明されています。 つまり、UE-V 2 が適切なソリューションであり、それを評価する必要がないとわかっている場合は、すぐに、 [ue-v 2 x の展開を準備](prepare-a-ue-v-2x-deployment-new-uevv2.md)することができます。

 

UE-V の標準インストールでは、Microsoft Windows と Office の既定の設定と、多くの Windows アプリの設定が同期されます。 テスト環境に、ネットワークアクセスを共有する2人以上のユーザーコンピューターが含まれていることを確認します。この場合は、短時間でのみ UE-V を評価します。

-   [手順 1: 前提条件を確認](#step1)します。サポートされている構成の詳細など、環境が ue-v を実行できることを確認します。

-   [手順 2: ue-v 2 の設定の保存場所を展開し](#step2)ます。すべての ue-v 展開では、同期された設定値を含む設定パッケージの場所が必要になります。

-   [手順 3: ue-v 2 エージェントを展開](#step3)する: ue-v を使用して設定を同期するには、デバイスで ue-v エージェントをインストールして実行している必要があります。

-   [手順 4: ue-v 2 の評価展開をテスト](#step4)する: ue-v エージェントがインストールされている2台のコンピューターでいくつかのテストを実行し、ue-v のしくみを確認します。

それです！ この手順を実行すると、UE-V が企業でどのように機能するかを評価することができます。

**さらに詳しい評価:** さらに、一部のサードパーティ製と基幹業務[用の](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)アプリケーションを構成して、ue-v を使って設定を同期するように設定することもできます。

## <a href="" id="step1"></a>手順 1: 前提条件を確認する


続行する前に、お使いの環境で UE-V を実行するための要件が含まれていることを確認してください。

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
<th align="left"><strong>オペレーティング システム</strong></th>
<th align="left"><strong>エディション</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>システムアーキテクチャ</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>Ultimate、Enterprise、または Professional エディション</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター、または Web サーバー</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4 以上</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>Enterprise または Pro</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 または Windows Server 2012 R2</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 10、1607以前の verison</p></td>
<td align="left"><p>Enterprise または Pro</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>.NET Framework 4.5</p></td>
</tr>
</tbody>
</table>

**注:** Windows 10 バージョン1607以降では、UE-V は[windows 10 For Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)に含まれており、Microsoft デスクトップ最適化パックの一部ではなくなっています。

また。。。

-   **MDOP ライセンス:** この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 企業のお客様は、Microsoft ソフトウェアアシュアランスで MDOP を入手できます。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「MDOP の入手方法」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   インストールする任意のコンピューターの**管理者資格情報**

## <a href="" id="step2"></a>手順 2: UE-V 2 の設定の保存場所を展開する


設定のパッケージファイルにユーザー設定が保存されている標準ネットワーク共有である、設定の保存場所を展開する必要があります。 設定記憶域共有を作成する場合は、必要なユーザーへのアクセスを制限する必要があります。 [設定を展開するストレージの場所の詳細に](https://technet.microsoft.com/library/dn458891.aspx#ssl)ついては、こちらを参照してください。

**ネットワーク共有を作成する**

1.  新しいセキュリティグループを作成し、UE-V ユーザーをそのグループに追加します。

2.  UE-V 設定パッケージが保存されている中央のコンピューターに新しいフォルダーを作成し、そのフォルダーへのグループアクセス許可を使用して、UE-V ユーザーにアクセスを許可します。 UE-V をサポートしている管理者は、この共有フォルダーへのアクセス許可を持っている必要があります。

3.  ユーザーが接続したときにディレクトリを作成するためのアクセス許可を UE-V users に割り当てます。 そのディレクトリのすべてのサブディレクトリに完全なアクセス許可を付与しますが、上記のいずれにもアクセスをブロックします。

    1.  [設定の保存場所] フォルダーに対して、次の共有レベルのサーバーメッセージブロック (SMB) 権限を設定します。

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong>ユーザーアカウント</strong></th>
        <th align="left"><strong>推奨されるアクセス許可</strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>すべてのユーザー</p></td>
        <td align="left"><p>権限なし</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V ユーザーのセキュリティグループ</p></td>
        <td align="left"><p>フルコントロール</p></td>
        </tr>
        </tbody>
        </table>

         

    2.  [設定の保存場所] フォルダーに、次の NTFS ファイルシステムの権限を設定します。

        <table>
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong>ユーザーアカウント</strong></th>
        <th align="left"><strong>推奨されるアクセス許可</strong></th>
        <th align="left"><strong>Folder</strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>作成者/所有者</p></td>
        <td align="left"><p>フルコントロール</p></td>
        <td align="left"><p>サブフォルダーとファイルのみ</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V ユーザーのセキュリティグループ</p></td>
        <td align="left"><p>フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</p></td>
        <td align="left"><p>このフォルダーのみ</p></td>
        </tr>
        </tbody>
        </table>

         

**セキュリティに関するメモ:**

Windows Server オペレーティングシステムを実行しているコンピューターで設定記憶域共有を作成する場合は、UE-V を構成して、ローカル管理者グループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認します。 この追加のセキュリティを有効にするには、Windows Server レジストリエディターで次の設定を指定します。

1.  **"RepositoryOwnerCheckEnabled"** という名前の**REG \ _DWORD**のレジストリキーを**HKEY \ _LOCAL \ _MACHINE ¥**$ ¥の設定に追加します。

2.  レジストリキーの値を*1*に設定します。

## <a href="" id="step3"></a>手順 3: UE-V 2 エージェントを展開する


UE-V Agent は、ユーザーのコンピューターとデバイスの間でアプリケーションと Windows の設定を同期します。 評価目的で、同じユーザーに属するテスト環境の少なくとも2台のコンピューターにエージェントをインストールします。

コマンドラインから AgentSetup.exe ファイルを実行して、UE-V Agent をインストールします。 これは、32ビットと64ビットの両方のオペレーティングシステムにインストールされます。

``` syntax
AgentSetup.exe SettingsStoragePath=\\server\settingsshare\%username%
```

手順2でネットワーク共有として SettingsStoragePath コマンドラインパラメーターを指定する必要があります。 [Ue-v agent を展開すると、](https://technet.microsoft.com/library/dn458891.aspx#agent)詳細な情報が提供されます。

## <a href="" id="step4"></a>手順 4: UE-V 2 の評価展開をテストする


Ue-v の評価展開でいくつかのテストを実行できるようになりました。 UE-V のしくみについて説明します。

****

1.  1台目のコンピューター (コンピューター A) で、次のような変更を加えます。

    1.  Windows デスクトップを開き、タスクバーをウィンドウの別の場所に移動します。

    2.  既定のフォントを変更します。

    3.  電卓を開き、[**指数**] に設定します。

    4.  Windows [PowerShell と WMI を使った ue-v の設定の場所テンプレートの管理](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)に関する説明に従って、windows アプリの動作を変更します。

    5.  Microsoft アカウント設定の同期とローミングプロファイルを無効にします。

2.  コンピューターからログオフする設定は、ユーザーがロック、ログオフ、アプリケーションの終了時、または同期プロバイダーの実行時 (既定では30分ごと) に、UE-V 設定パッケージに保存されます。

3.  2台目のコンピューター (コンピューター B) に、コンピューター A と同じユーザーとしてログインします。

4.  Windows デスクトップを開き、タスクバーの場所がコンピューター A と一致することを確認します。既定のフォントが一致していること、および電卓が [**指数**] に設定されていることを確認します。 また、Windows アプリに加えた変更も確認してください。

コンピューター B の設定を元のコンピューターに戻すことができます。 次に、コンピューター B をログオフし、コンピューター A にログインして変更を確認します。

## この製品のその他のリソース


-   [Microsoft User Experience Virtualization (UE-V) 2. x](index.md)

-   [UE-V の展開を準備する](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

-   [UE-V 2. x のトラブルシューティング](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





