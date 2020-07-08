---
title: System Center Configuration Manager 2012 で UE-V を構成する
description: System Center Configuration Manager 2012 で UE-V を構成する
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824407"
---
# System Center Configuration Manager 2012 で UE-V を構成する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 をインストールした後、必要な機能を使用するには、UE-V が構成されている必要があります。 UE-V 構成パックでは、管理者は System Center Configuration Manager 2012 SP1 以降のコンプライアンス設定機能を使用して、UE-V および Configuration Manager がインストールされているサイト間で一貫した構成を適用することができます。

## UE-V 構成パックでサポートされる機能


UE-V 構成パックには、次のタスクを実行するためのツールが含まれています。

-   UE-V 設定の場所テンプレートの配布ベースラインを作成または更新します。

    -   登録または登録解除する UE-V テンプレートを定義する

    -   テンプレートが追加または更新されたときの UE-V テンプレート構成項目とベースラインの更新

    -   標準構成項目の修復を使用して UE-V テンプレートを配布および登録する

-   UE-V Agent policy 構成項目を作成または更新して、これらの設定を設定またはクリアします。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>最大パッケージサイズ</p></td>
    <td align="left"><p>Windows アプリの同期を有効/無効にする</p></td>
    <td align="left"><p>アプリケーションの起動時に同期を待つ</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>インポートの遅延を設定する</p></td>
    <td align="left"><p>一覧にない Windows アプリを同期する</p></td>
    <td align="left"><p>ログオン時に同期を待つ</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>設定のインポート通知</p></td>
    <td align="left"><p>IT の連絡先 URL</p></td>
    <td align="left"><p>同期のタイムアウトを待つ</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>設定の記憶域のパス</p></td>
    <td align="left"><p>IT 担当者に連絡する説明のテキスト</p></td>
    <td align="left"><p>設定テンプレートカタログのパス</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>同期の有効化</p></td>
    <td align="left"><p>有効になっているトレイアイコン</p></td>
    <td align="left"><p>UE-V agent service を開始/停止する</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>同期方法</p></td>
    <td align="left"><p>初めて使用するときの通知</p></td>
    <td align="left"><p>ローミング設定を行う Windows アプリを定義する</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>同期のタイムアウト</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   UE-V が実行されていることを確認して、コンプライアンスを確認します。

## UE-V Agent Policy 構成項目を生成する


すべての UE-V エージェントのポリシーと構成は、UevAgentPolicyGenerator.exe ツールを使用して生成された単一の構成項目を通じて配布されます。 このツールは、XML 構成ファイルから目的の構成を読み取り、コンピューターをコンプライアンスにするために必要な検出と修復の設定を含む CI を作成します。

UE-V Agent policy 構成項目の CAB ファイルは、次のパラメーターを含む UevTemplateBaselineGenerator.exe コマンドラインツールを使って作成されます。

-   サイトの &lt; サイトコード&gt;

-   PolicyName &lt; name &gt; オプション: 存在しない場合は "Ue-v agent Policy" の既定値

-   PolicyDescription &lt; description &gt; オプション: 存在しない場合は説明が表示される

-   CabFilePath で &lt; 構成項目への完全パスを設定します。CAB ファイル&gt;

-   &lt;エージェント構成 XML ファイルへのフルパスを設定する&gt;

**注** これらのスクリプトを環境内で実行できるようにするには、PowerShell の実行ポリシーを変更する必要がある場合があります。 Configuration Manager コンソールで次の手順を実行します。

1.  **管理 &gt; クライアント設定の &gt; プロパティ**を選択する

2.  [**ユーザーエージェント**] タブで、 **PowerShell 実行ポリシー**を [**バイパス**] に設定します。

<a href="" id="create"></a>**最初の UE-V ポリシー構成項目を作成する**

1.  既定の設定構成ファイルを、UE-V 構成パックのインストールディレクトリから ConfigMgr 管理コンソールに表示される場所にコピーします。

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    既定の構成ファイルには、次の5つのセクションが含まれます。

    <a href="" id="computer-policy"></a>**コンピューターポリシー**  
    すべての UE-V のコンピューターレベル設定。 DesiredState 属性には、

    -   レジストリで割り当てられた値を使用するように**設定**する

    -   **オフ**にして設定を削除する

    -   構成項目を現在の状態のままにしておくための**アンマネージ**

    このセクションの線は削除しないでください。 代わりに、Configuration Manager で現在の値または既定の値を変更しない場合は、DesiredState を ' Unmanaged ' に設定します。

    <a href="" id="currentcomputeruserpolicy"></a>**CurrentComputerUserPolicy**  
    すべての UE-V のユーザーレベル設定。 これらのエントリは、ユーザーのコンピューター設定より優先されます。 DesiredState 属性には、

    -   レジストリで割り当てられた値を使用するように**設定**する

    -   **オフ**にして設定を削除する

    -   構成項目を現在の状態のままにしておくための**アンマネージ**

    このセクションの線は削除しないでください。 代わりに、Configuration Manager で現在の値または既定の値を変更しない場合は、DesiredState を ' Unmanaged ' に設定します。

    <a href="" id="services"></a>**サービス**  
    このセクションのサービス操作の項目を制御します。 既定の構成ファイルには、UevAgentService のエントリが1つ含まれています。 DesiredState 属性は、**実行**または**停止**に設定できます。

    <a href="" id="windows8appscomputerpolicy"></a>**Windows8AppsComputerPolicy**  
    すべてのコンピューターレベルの Windows アプリ同期設定。 このセクションに記載されている各パッケージには、DesiredState を割り当てることができます。

    -   設定をローミングにすることを**許可**

    -   **無効**。ローミングから設定できないようにする

    -   UE-V コントロールからエントリが削除されるようにすることを**オフ**にしました

    このセクションには、PowerShell コマンドレット GetAppxPackage を使って表示できるインストール済み Windows アプリの一覧に基づいて、追加の行を追加することができます。

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**Windows8AppsCurrentComputerUserPolicy**  
    個々のユーザーに対してコンピューターの設定を上書きする設定を使用して、Windows8AppsComputerPolicy と同じです。

2.  目的の状態と値のフィールドを変更して構成ファイルを編集します。

3.  ConfigMgr 管理コンソールを実行しているコンピューターで、次のコマンドを実行します。

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  ConfigMgr コンソールまたは PowerShell インポート-CMConfigurationItem を使用して CAB ファイルをインポートする

**UE-V ポリシー構成項目を更新する**

1.  目的の状態と値のフィールドを変更して構成ファイルを編集します。

2.  [[最初の Ue-v ポリシー構成] 項目](#create)の手順3からコマンドを実行します。 PolicyName パラメーターで名前を変更した場合は、必ず同じ名前を入力してください。

3.  CAB ファイルを再インポートします。 ConfigMgr のバージョンが更新されます。

## UE-V テンプレートのベースラインを生成する
UE-V テンプレートは、複数の構成項目を含むベースラインを使って配布されます。 各構成項目には、1つの UE-V テンプレートをインストールするために必要な検出と修復のスクリプトが含まれています。 実際の UE-V テンプレートは、標準の構成項目機能を使用して、配布用の修復スクリプト内に埋め込まれます。

UE-V テンプレートベースラインは、次のパラメーターを含む UevTemplateBaselineGenerator.exe コマンドラインツールを使って作成されます。

-   サイトの &lt; サイトコード&gt;

-   BaselineName &lt; name &gt; (オプション: 存在しない場合は、既定で "Ue-v のテンプレート配布ベースライン")

-   BaselineDescription &lt; description &gt; (オプション: 存在しない場合は説明が表示されます)

-   TemplateFolder &lt; ue-v テンプレートフォルダー&gt;

-   コンマ区切りの &lt; テンプレートファイルの一覧を登録する&gt;

-   コンマ区切りテンプレートリストの登録を解除する &lt;&gt;

-   &lt;生成するベースライン CAB ファイルの CabFilePath フルパス&gt;

結果として、構成マネージャーへのインポートの準備ができたベースライン CAB ファイルが用意されています。 将来の日付でテンプレートを更新または追加した場合は、同じベースライン名を使用してコマンドを再実行できます。 変更されたテンプレートの CI バージョンの更新に、CAB の結果をインポートします。

### <a href="" id="create2"></a>最初の UE-V テンプレートベースラインを作成する

1.  ConfigMgr 管理コンソールを実行しているコンピューターに表示される安定したフォルダーの場所に、"マスタ" の UE-V テンプレートセットを作成します。 テンプレートが追加または更新されると、このフォルダーは配布用にプルされます。 テンプレートの最初の一覧は、UE-V がインストールされているコンピューターからコピーできます。 既定のテンプレートの場所は¥ c/Virtualization\\Templates.

2.  テンプレートジェネレーターコマンドを追加できる text.bat ファイルを作成します。 これは省略可能ですが、コマンドパラメーターを保存すると再生成がより簡単になります。

3.  ベースラインを生成するためのコマンドとパラメーターを .bat ファイルに追加します。 次の例では、メモ帳と電卓を配布する基準計画を作成します。

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  .Bat ファイルを実行して、構成マネージャーへのインポートの準備が整った UevTemplateBaseline.cab を作成します。

### UE-V テンプレートベースラインを更新する

テンプレートジェネレーターはテンプレートのバージョンを使って、テンプレートを更新する必要があるかどうかを判断します。 テンプレートを変更してバージョンを更新すると、ベースラインジェネレーターは、マスターフォルダー内のテンプレートと ConfigMgr サーバー上の CI に含まれているテンプレートを比較します。 相違点が見つかった場合は、生成された基準計画と変更された CI のバージョンが更新されます。

新しいメモ帳テンプレートを配布するには、次の手順を実行します。

1.  テンプレートの version 要素にあるテンプレートとテンプレートのバージョンを更新し &lt; &gt; ます。

2.  テンプレートをマスターテンプレートディレクトリにコピーします。

3.  「[最初の Ue-v テンプレートベースラインを作成](#create2)する」の手順3で作成した .bat ファイルでコマンドを実行します。

4.  本体または PowerShell のインポート用のベースラインを使用して、生成された CAB ファイルを ConfigMgr にインポートします。

## UE-V 構成パックを入手する


Configuration Manager 2012 SP1 以降の UE-V 構成パックは、[ここ](https://go.microsoft.com/fwlink/?LinkId=317263)からダウンロードできます。






## 関連トピック


[UE-V 2.x の構成を管理する](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





