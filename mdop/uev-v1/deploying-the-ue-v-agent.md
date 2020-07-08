---
title: UE-V エージェントの展開
description: UE-V エージェントの展開
author: dansimp
ms.assetid: ec1c16c4-4be0-41ff-93bc-3e2b1afb5832
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 19f3b798ad7d3a43b0a274a25dd97b651435de51
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827184"
---
# UE-V エージェントの展開


Microsoft User Experience Virtualization (UE-V) agent は、UE-V を使用してアプリケーションと Windows の設定をローミングする各コンピューターで実行する必要があります。 1つの installer ファイル AgentSetup.exe、32ビットと64ビットの両方のオペレーティングシステムに UE-V エージェントをインストールします。 UE-V Agent のコマンドラインパラメーターは、次のとおりです。

**AgentSetup.exe コマンドラインのパラメーター**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>コマンドラインパラメーター</strong></th>
<th align="left"><strong>定義</strong></th>
<th align="left"><strong>備考</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/help または/h または/?</p></td>
<td align="left"><p>[AgentSetup.exe の使用状況] ダイアログボックスを表示します。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsStoragePath</p></td>
<td align="left"><p>設定が保存される場所を定義する汎用名前付け規則 (UNC) パスを示します。</p></td>
<td align="left"><p>% username% または% computername% の環境変数が受け入れられます。 スクリプトには、エスケープされた変数が必要です。</p>
<p><strong>既定値 </strong> : &lt; なし &gt; (Active Directory ユーザーのホーム)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SettingsTemplateCatalogPath</p></td>
<td align="left"><p>新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを示します。</p></td>
<td align="left"><p>カスタム設定の場所テンプレートでのみ必須</p></td>
</tr>
<tr class="even">
<td align="left"><p>RegisterMSTemplates</p></td>
<td align="left"><p>インストール時に既定の Microsoft テンプレートを登録する必要があるかどうかを指定します。</p></td>
<td align="left"><p>True |返し</p>
<p><strong>既定値 </strong> : True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>方法</p></td>
<td align="left"><p>使用する同期方法を指定します。</p></td>
<td align="left"><p>OfflineFiles |-</p>
<p><strong>既定 </strong> : offlinefiles</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncTimeoutInMilliseconds</p></td>
<td align="left"><p>コンピューターが設定の保存場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を指定します。</p></td>
<td align="left"><p><strong>既定値 </strong> : 2000 ミリ秒</p>
<p>(最大2秒待ちます)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncEnabled</p></td>
<td align="left"><p>UE-V の同期を有効にするか、無効にするかを指定します。</p></td>
<td align="left"><p>True |返し</p>
<p><strong>既定値 </strong> : True</p></td>
</tr>
<tr class="even">
<td align="left"><p>Maxパッケージパッケージ</p></td>
<td align="left"><p>UE-V agent でファイルのしきい値を超えたことを報告した場合に、設定パッケージのファイルサイズをバイト単位で指定します。</p></td>
<td align="left"><p>&lt;大きさ&gt;</p>
<p><strong>既定値 </strong> : なし (警告のしきい値なし)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>CEIPEnabled</p></td>
<td align="left"><p>カスタマーエクスペリエンス向上プログラムに参加するための設定を指定します。 True に設定すると、インストーラー情報が Microsoft カスタマーエクスペリエンス向上プログラムのサイトにアップロードされます。 False に設定すると、情報はアップロードされません。</p></td>
<td align="left"><p>True |返し</p>
<p><strong>既定値 </strong> : False</p>
<p><strong>Windows 7 の </strong> 場合: True</p></td>
</tr>
</tbody>
</table>

 

インストール時に、SettingsStoragePath コマンドラインパラメーターは設定値の保存場所を指定します。 UE-V Agent を展開する前に、設定の保存場所を定義することができます。 設定の保存場所が定義されていない場合、UE-V は Active Directory ユーザーのホームディレクトリを設定の保存場所として使います。 セットアップ時に SettingsStoragePath 構成を指定し、その値の一部として% username% を使用すると、ユーザーがログインするすべてのコンピューターまたはセッションで同じユーザー設定のエクスペリエンスがローミングされます。 SettingsStoragePath 値の一部として%username%\\%computername% 変数を指定すると、各コンピューターの設定の操作性が維持されます。

アーキテクチャ固有の Windows インストーラー (.msi) ファイルは、32ビットと64ビットの両方のインストーラーに加えて、UE-V エージェントのインストール用に提供されています。 AgentSetupx86.msi または AgentSetupx64.msi のインストールファイルは、AgentSetup.exe ファイルよりも小さく、エージェントの展開が合理化される可能性があります。 AgentSetup.exe installer のコマンドラインパラメーターは、Windows インストーラー (.msi) のインストールでサポートされています。

**注** UE-V agent のインストールまたはアンインストール中には、AgentSetup.exe ファイルまたは AgentSetup &lt; arch ファイルを使用できますが、両方を使用することはでき &gt; ません。 Ue-v agent をインストールするために使用されたのと同じファイルを使用して、UE-V Agent をアンインストールする必要があります。

 

UE-V agent をインストールする場合は、必ず正しい変数形式を使用してください。 次の表では、AgentSetup.exe または Windows インストーラー (.msi) のインストールファイルを使用するための展開オプションの例を示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>展開の種類</strong></th>
<th align="left"><strong>展開の説明</strong></th>
<th align="left"><strong>例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コマンドプロンプト</p></td>
<td align="left"><p>コマンドプロンプトから UE-V agent をインストールする場合は、% ^ username% 変数形式を使用します。 設定の記憶域のパスにスペースが含まれているために引用符が必要な場合は、展開用のバッチスクリプトファイルを使います。</p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>バッチスクリプト</p></td>
<td align="left"><p>UE-V Agent をバッチスクリプトファイルからインストールする場合は、%% username%% 変数形式を使います。 この install メソッドを使う場合は、%% 文字の変数をエスケープする必要があります。 この文字がないと、スクリプトは実行時ではなく、インストール時に username 変数を展開します。 UE-V は、すべてのユーザーに対して1つの設定の保存場所を使用します。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p>PowerShell プロンプトまたは PowerShell スクリプトから UE-V agent をインストールする場合は、% username% 変数形式を使用します。</p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>電子ソフトウェアの配布 (Configuration Manager ソフトウェアの展開の展開など)</p></td>
<td align="left"><p>Configuration Manager を使用して UE-V Agent をインストールする場合は、^% username ^% 変数形式を使用します。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>

 

**注** U EV エージェントをインストールするには、管理者権限が必要です。 UE-V agent を実行するには、コンピューターの再起動が必要になります。

 

## ネットワーク共有からの UE-V エージェントの展開方法


UE-V agent を展開するには、次のメソッドを使用できます。

-   Windows インストーラー (.msi) ファイルをインストールできる電子ソフトウェア配布 (ESD) ソリューション。

-   共有に一元的に保存されている Windows Installer (.msi) ファイルを参照するインストールスクリプト。

-   コンピューターでインストールプログラムを手動で実行します。

ネットワーク共有から UE-V agent を展開するには、次の手順を実行します。

**ネットワーク共有から UE-V Agent をインストールして構成するには**

1.  ユーザーが "読み取り" アクセス許可を持つネットワーク共有で UE-V agent インストールファイル (AgentSetup.exe) をステージングします。

2.  UE-V agent をインストールするユーザーコンピューターにスクリプトを展開します。 スクリプトでは、設定の保存場所を指定する必要があります。

**UE-V Agent を更新する**

UE-V エージェントソフトウェアの更新プログラムは、Microsoft Update を通じて提供されます。 UE-V agent のアップグレード中に、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループが更新されることがあります。 UE-V agent の更新プログラムは、エンタープライズソフトウェア配布 (ESD) インフラストラクチャを使用して展開できます。

## 関連トピック


[UE-V 1.0 の展開](deploying-ue-v-10.md)

[UE-V 1.0 でサポートされている構成](supported-configurations-for-ue-v-10.md)

[UE-V 1.0 の設定の保存場所の展開](deploying-the-settings-storage-location-for-ue-v-10.md)

[UE-V Generator のインストール](installing-the-ue-v-generator.md)

User Experience Virtualization Agent の展開
 

 





