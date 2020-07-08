---
title: UE-V 1.0 でサポートされている構成
description: UE-V 1.0 でサポートされている構成
author: dansimp
ms.assetid: d90ab83e-741f-48eb-b1d8-a64cb9259f7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a84514317de8a4cfd9df9c94a9a130933b00874a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825554"
---
# UE-V 1.0 でサポートされている構成


Microsoft User Experience Virtualization (UE-V) では、次の構成がサポートされています。

**注** Microsoft は、現在のサービスパックと、場合によっては、上記の service pack のサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。

 

## UE-V Agent および UE-V Generator でサポートされている構成


次の表は、ユーザーエクスペリエンスの仮想化ジェネレーターと User Experience Virtualization agent をサポートしているオペレーティングシステムを示しています。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>オペレーティング システム</strong></th>
<th align="left"><strong>エディション</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>システムアーキテクチャ</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>Ultimate、Enterprise、または Professional エディション</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>.NET Framework 3.5 SP1</p>
<p>.NET Framework 4 (ジェネレーター)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター、または Web サーバー</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>.NET Framework 3.5 SP1</p>
<p>.NET Framework 4 (ジェネレーター)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>Enterprise または Professional エディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
<td align="left"><p>.NET Framework 4 または .NET Framework 3.5 SP1 (エージェント)</p>
<p>.NET Framework 4 (ジェネレーター)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>.NET Framework 4 または .NET Framework 3.5 SP1 (エージェント)</p>
<p>.NET Framework 4 (ジェネレーター)</p></td>
</tr>
</tbody>
</table>

 

UE-V に固有の特殊な RAM 要件はありません。

UE-V agent をインストールするには、管理者権限が必要です。また、UE-V agent を実行するには、コンピューターを再起動する必要があります。

**重要** UE-V を適切に機能させるには、Windows 8 の [同期の設定] 機能を無効にする必要があります。 Windows 8 と UE-V の両方の設定を同期すると、予期しない同期動作が発生します。

 

### <a href="" id="requirements-for-the-offline-files-feature-"></a>オフラインファイル機能の要件

UE-V agent は、ネットワークに接続されていないコンピューター (リモートオフィスに配置されているノート pc やコンピューターなど) と、仮想デスクトップインターフェイス (VDI) セッションをホストする Windows サーバーなど、常に企業ネットワークに接続されているコンピューターなどのユーザー設定を同期できます。

UE-V の既定の構成では、Windows のオフラインファイル機能を使用して設定が同期されます。 オフラインファイルを使用すると、コンピューターが企業ネットワークから離れるときでも、ユーザーの設定が使用可能になります。 設定に加えた変更は、エンタープライズネットワークへの接続が再確立されたときに、設定の保存場所と自動的に同期されます。 オフラインファイルを使用すると、リモートオフィスに配置されているコンピューターでも、低速または限定された接続でユーザーの設定を利用できるようになります。

企業ネットワークから離れてしまう可能性があるコンピューターの設定を同期するには、UE-V agent の展開を開始する前に、オフラインファイル機能を有効にして開始する必要があります。 Windows7 では、オフラインファイル機能は既定で有効になっています。 Windows Server2008R2、Windows Server 2012、Windows 8 では、この機能は既定で無効になっています。 オフラインファイル機能が有効になっていない場合、UE-V 設定の同期は失敗します。

-   **Windows 7**

    Windows 7 では、オフラインファイル機能は既定で有効になっています。 必要に応じて、管理者特権のコマンドプロンプトで次のコマンドを使用して、オフラインファイルを有効にすることができます。

    ``` syntax
    sc config CscService start=auto
    ```

-   **Windows 8**

    Windows 8 バージョンでは、オフラインファイル機能は既定で無効になっています。 Windows 8 では、管理者特権のコマンドプロンプトで次のコマンドを使用して、オフラインファイルを有効にすることができます。

    ``` syntax
    sc config CscService start=auto
    ```

-   **Windows Server 2008 R2、Windows Server 2012**

    Windows Server 2008 R2 または Windows Server 2012 では、オフラインファイル機能は既定ではインストールされません。 オフラインファイル機能を有効にするには、デスクトップエクスペリエンスパックがインストールされている必要があります。 これは、オフラインファイル機能を含むオプションのサーバーコンポーネントです。 インストールが完了したら、昇格されたコマンドプロンプトで次のコマンドを使用して、オフラインファイル機能を起動します。

    ``` syntax
    sc config csc start= system
    ```

    ``` syntax
    sc config cscservice start= auto
    ```

設定の同期を開始するには、コンピューターを再起動する必要があります。

### 常に利用可能な接続を備えたコンピューターの同期

VDI セッションをホストしている Windows Server コンピューターなどの、常に企業ネットワークに接続されているコンピューターで UE-V を使用する場合は、オフラインファイルを無効にする必要があります。

UE-V agent がオフラインファイルを使わずに設定を同期するように構成されている場合、設定ストレージサーバーは標準のネットワーク共有として扱われます。 設定は、ネットワークが利用可能になったときに同期されます。 この構成では、アプリケーション設定のインポートが延期された場合に通知を受け取るように UE-V agent を構成できます。

オフラインファイル機能が使用されない場合は、UE-V エージェントの展開の前または実行中に、UE-V の既定の動作を無効にする必要があります。 UE-V のオフラインファイルを無効にするには、次のいずれかの操作を行います。

-   UE-V agent を展開する前に、UE-V グループポリシー設定の [オフラインファイルを使わない] チェックボックスをオンにします。

-   UE-V のインストール時に、 `SyncMethod = None` コマンドプロンプトまたはバッチファイルで AgentSetup.exe パラメーターを設定します。 エージェントの展開方法の詳細については、「 [Ue-v agent の展開](deploying-the-ue-v-agent.md)」を参照してください。

UE-V の [オフラインファイル] 設定を無効にして、インストール時に**Syncmethod**パラメーターを指定しなかった場合、ue-v agent のインストールは失敗します。 PowerShell または WMI でオフラインファイルを無効にすることもできます。 WMI コマンドと PowerShell コマンドの詳細については、「 [ue-v 1.0 エージェントと powershell と WMI を使ったパッケージの管理](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)」を参照してください。

設定の同期を開始するには、コンピューターを再起動する必要があります。

### UE-V PowerShell 機能の前提条件

エージェントの UE-V PowerShell 機能を使用するには、.NET Framework バージョン 3.5 SP1 を有効にし、PowerShell バージョン2.0 以降を使用する必要があります。

### UE-V Generator のサポートに関する前提条件

カスタム設定の場所テンプレートを作成するために使用されるコンピューターに、UE-V Generator をインストールします。 このコンピューターには、設定をローミングするアプリケーションがインストールされている必要があります。 UE-V Generator ソフトウェアを実行しているコンピューターの管理者グループのメンバーである必要があります。 さらに、UE-V Generator は、NTFS ファイルシステムを使用するコンピューターにインストールされている必要があります。 UE-V Generator ソフトウェアには、.NET Framework バージョン4が必要です。 詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。

## 関連トピック


[UE-V 1.0 の計画](planning-for-ue-v-10.md)

[UE-V に対応する環境の準備](preparing-your-environment-for-ue-v.md)

[UE-V 1.0 の展開](deploying-ue-v-10.md)

[Ue-v 1.0 向けの設定の保存場所を展開](deploying-the-settings-storage-location-for-ue-v-10.md)するユーザーエクスペリエンス仮想化に対応した構成

[UE-V Generator のインストール](installing-the-ue-v-generator.md)

[UE-V エージェントの展開](deploying-the-ue-v-agent.md)

 

 





