---
title: MED-V の仮想 PC イメージの作成
description: MED-V の仮想 PC イメージの作成
author: dansimp
ms.assetid: 5e02ea07-25b9-41a5-a803-d70c55eef586
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 84e45f9ff7213abdd6288bcd750238436d3ab68c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823664"
---
# MED-V の仮想 PC イメージの作成


MED-V 用の仮想 PC (VPC) イメージを作成するには、次の手順を実行する必要があります。

1.  [VPC イメージを作成](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)します。

2.  [MED ワークスペースの .msi パッケージを VPC イメージにインストール](#bkmk-howtoinstallthemedvworkspacemsipackage)します。

3.  [VPC イメージに対して、med-v 仮想マシンの前提条件ツールを実行](#bkmk-howtorunthevirtualmachineprerequisitestool)します。

4.  [VPC イメージの仮想マシンの前提条件を手動で構成](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites)します。

5.  [Sysprep を med-v イメージ用に構成](#bkmk-howtoconfiguresysprepformedvimages)します (省略可能)。

6.  [Microsoft VIRTUAL PC をオフに](#bkmk-turningoffmicrosoftvirtualpc)します。

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a>Microsoft Virtual PC を使用して仮想 PC イメージを作成する


Microsoft Virtual PC を使用して仮想 PC イメージを作成する方法については、「仮想 pc のドキュメント」を参照してください。

詳細については、以下を参照してください。

-   [Windows Virtual PC のヘルプ](https://go.microsoft.com/fwlink/?LinkId=182378)

-   [仮想マシンを作成し、ゲストオペレーティングシステムをインストールする](https://go.microsoft.com/fwlink/?LinkId=182379)

## <a href="" id="bkmk-howtoinstallthemedvworkspacemsipackage"></a>MED-V のワークスペース .msi パッケージをインストールする方法


仮想 PC イメージを作成したら、MED-V workspace .msi パッケージをイメージにインストールします。

**MED-V ワークスペースのイメージをインストールするには**

1.  仮想マシンを起動して、MED-V の workspace パッケージを内部にコピーします。

    MED-V のワークスペースパッケージは*MED-V\_workspace\_x.msi*と呼ばれます。ここで、 *x*はバージョン番号です。

    たとえば、 *MED-V\_workspace\_1.0.65.msi*とします。

2.  MED-V のワークスペース .msi パッケージをダブルクリックして、インストールウィザードの指示に従います。

    **注**  
    新しい MED-V バージョンがリリースされ、既存の Virtual PC イメージが更新されたら、既存の MED-V workspace パッケージをアンインストールし、コンピューターを再起動して、新しい MED-V workspace パッケージをインストールします。



~~~
**Note**  
After the MED-V workspace .msi package is installed, other products that replace GINA cannot be installed.
~~~



## <a href="" id="bkmk-howtorunthevirtualmachineprerequisitestool"></a>仮想マシンの前提条件ツールを実行する方法


仮想マシン (VM) の前提条件ツールは、いくつかの前提条件を自動化するためのウィザードです。

**注**  
ウィザードでは多くのパラメーターを設定できますが、MED-V の適切な機能に必要なプロパティは構成できません。



**仮想マシンの前提条件ツールを実行するには**

1.  MED-V のワークスペース .msi パッケージをインストールした後、Windows の [**スタート**] メニューで [すべてのプログラム] を選びます** &gt; &gt; **。

    **注**  
    仮想マシンの前提条件ツールを実行しているユーザーは、ローカル管理者権限が必要であり、ログインしているユーザーだけである必要があります。



~~~
The **MED-V VM Prerequisite Wizard Welcome** page appears.
~~~

2. **[次へ]** をクリックします。

3. [ **Windows の設定**] ページで、次の構成プロパティから構成するものを選択します。

   -   **ユーザーの個人の履歴情報をクリアする**

   -   **ローカルプロファイルの一時ディレクトリをクリアする**

   -   **[開始]、[ログオン]、[ログオフ] を使用して、次の Windows イベントのサウンドを無効にする**

   **注**  
   グループポリシーでは、Windows のページセーバーを有効にしないでください。



4. **[次へ]** をクリックします。

5. **Internet Explorer**の [設定] ページで、次の構成可能なプロパティから、構成するものを選択します。

   -   **オートコンプリート機能を使用しない**

   -   **ショートカットを起動するための windows の再使用を無効にする**

   -   **閲覧の履歴を消去する**

   -   **Internet Explorer 7 でタブ表示を有効にする**

6. **[次へ]** をクリックします。

7. [ **Windows Services** ] ページで、次の構成プロパティから構成するものを選択します。

   -   **セキュリティセンターサービス**

   -   **タスクスケジューラサービス**

   -   **自動更新サービス**

   -   **システムの復元サービス**

   -   **インデックスサービス**

   -   **ワイヤレスゼロ構成**

   -   **ユーザーの切り替えの高速化**

8. **[次へ]** をクリックします。

9. Windows の**自動ログオン**ページで、次の操作を行います。

   1.  [ **Windows の自動ログオンを有効にする**] チェックボックスをオンにします。

   2.  **ユーザー名**と**パスワード**を割り当てます。

10. [**適用**] をクリックし、表示される確認ボックスで [**はい]** をクリックします。

11. [**概要**] ページで、[**完了**] をクリックしてウィザードを終了します。

**注**  
グループポリシーによって、前提条件ツールで設定した必須設定が上書きされていないことを確認します。



## <a href="" id="bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites"></a>MED-V 仮想マシンの手動インストールの前提条件を構成する方法


仮想マシンの前提条件ツールを使用して構成することはできません。また、手動で実行する必要があります。

-   仮想マシンの設定

    Microsoft Virtual PC 本体で次の仮想マシン設定を構成することをお勧めします。

    -   フロッピーディスクドライブを無効にします。

    -   元に戻す-ディスク (**設定の &gt; 取り消し-ディスク**) を無効にします。

    -   画像に仮想 CPU が1つしかないことを確認します。

    -   仮想マシンとユーザーの間の相互作用を排除します (たとえば、ユーザー入力を要求するメッセージなどの公開されたアプリケーションに関連していない場合)。

-   イメージの設定

    イメージ内で次の手動設定を構成します。

    1.  [**電源オプションのプロパティ**] ウィンドウで、休止状態とスリープを無効にします。

    2.  最新の Windows 更新プログラムを適用します。

    3.  [ **Windows の起動と回復**] ダイアログボックスの [**システムエラー** ] セクションで、[**自動的に再起動**する] チェックボックスをオフにします。

    4.  画像が VLK のライセンスキーを使用していることを確認します。

-   VPC の追加機能のインストール

    [**操作**] メニューで、[ **Virtual Machine の追加機能のインストールまたは更新**] を選びます。

-   印刷を設定する

    MED-V ワークスペースからの印刷は、次のいずれかの方法で構成できます。

    -   仮想マシンにプリンターを追加します。

    -   ホストコンピューターで構成されているプリンターを使用して印刷を許可します。

## <a href="" id="bkmk-howtoconfiguresysprepformedvimages"></a>Sysprep を MED-V イメージ用に構成する方法


MED-V ワークスペースでは、固有のセキュリティ ID (SID) を割り当てるために Sysprep を構成できます。特に、複数の MED-V ワークスペースが1台のコンピューターで実行されている場合です。 Sysprep を使ってドメインに参加することはお勧めしません。代わりに、「[スクリプトアクションのセットアップ方法](how-to-set-up-script-actions.md)」の説明に従って、med-v join domain スクリプトアクションを使います。

**注**  
Sysprep は、Windows オペレーティングシステム用の Microsoft のシステム準備ユーティリティです。



**MED-V ワークスペースで Sysprep を構成するには**

1.  *Sysprep*という名前のシステムドライブのルートにディレクトリを作成します。

2.  Windows インストール CD からシステムドライブのルートに*deploy.cab*を抽出するか、Microsoft Web サイトから最新の展開ツールの更新プログラムをダウンロードします。

    -   Windows 2000 の場合は、「 [windows 2000 の展開ツールの更新プログラム](https://go.microsoft.com/fwlink/?LinkId=143001)」を参照してください。

    -   Windows XP の場合は、「 [WINDOWS xp の展開ツールの更新プログラム](https://go.microsoft.com/fwlink/?LinkId=143000)」を参照してください。

3.  **セットアップマネージャー** (setupmgr.exe) を実行します。

4.  セットアップマネージャーウィザードに従います。

Sysprep を構成し、MED-V ワークスペースを作成したら、Sysprep を実行する必要があります。

**Sysprep を実行するには**

1.  システムドライブのルートにある Sysprep フォルダーで、システム準備ツール (Sysprep.exe) を実行します。

2.  警告メッセージボックスが表示されたら、[ **OK]** をクリックします。

3.  [ **Sysprep のプロパティ**] ダイアログボックスで、[**ライセンス認証の猶予期間をリセット**し、**ミニセットアップを使用する**] チェックボックスをオンにします。

4.  [再**シール**] をクリックします。

5.  表示される確認メッセージボックスに記載されている情報に問題がある場合は、[**キャンセル**] をクリックして選択内容を変更します。

6.  [ **OK** ] をクリックして、システム準備プロセスを完了します。

## <a href="" id="bkmk-turningoffmicrosoftvirtualpc"></a>Microsoft Virtual PC の無効化


すべてのコンポーネントをインストールして構成したら、Microsoft Virtual PC を閉じて、[**無効にする**] を選びます。

## 関連トピック


MED-V イメージの作成[スクリプトアクションのセットアップ方法](how-to-set-up-script-actions.md)









