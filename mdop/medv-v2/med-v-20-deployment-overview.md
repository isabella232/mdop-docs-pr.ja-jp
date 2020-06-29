---
title: MED-V 2.0 展開の概要
description: MED-V 2.0 展開の概要
author: dansimp
ms.assetid: 0b8998ea-c46f-4c81-a304-f380b2ed7cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ec2a5f86ac7d63295bd7c550bcb0a90004987e42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826107"
---
# MED-V 2.0 展開の概要


このセクションでは、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールして展開する方法に関する一般的な情報と手順について説明します。

## 概要


MED-V 2.0 はアプリケーションモデルに基づくものであり、アプリケーションを展開するために使うメソッドを使用して、MED-V の展開と管理を行うことができます。 展開された MED-V ソリューションには、MED-V ホストエージェントとゲストエージェントの2つのコンポーネントが含まれています。 MED-V Host Agent は Windows 7 デスクトップ上にインストールされ、med-v ゲストエージェントは MED-V ワークスペース内の Windows XP にインストールされています。 Med-v には、med-v ワークスペースの作成と構成に必要な情報とツールを提供する MED-V Workspace パッケージャーも含まれています。

**重要**  
MED-V では、MED-V Workspace パッケージャー、MED-V ホストエージェント、およびすべてのユーザーの MED-V ワークスペースのインストールのみがサポートされます。 現在のユーザーの MED-V をインストールするには、 **ALLUSERS = ""** を選択します。コンポーネントのインストールと med-v ワークスペースのセットアップでエラーが発生します。



### MED-V インストールファイル

MED には、MED-V の実行に必要な次のインストールファイルが含まれています。

**MED-V ホストエージェントインストールファイル**

ホストエージェントのインストールファイルには、MED-V\_HostAgent\_Setup.exe という名前が付けられます。 このファイルは、企業全体の MED-V の展開の一部として、関連する各エンドユーザーのコンピューターに配布され、インストールされます。

**MED-V ワークスペースパッケージャーインストールファイル**

MED-V Workspace パッケージャーのインストールファイルには、MED-V\_WorkspacePackager\_Setup.exe という名前が付いています。 このファイルを使用して、管理者の権限とアクセス許可を持っているコンピューターに、MED-V Workspace パッケージャーをインストールします。 デスクトップ管理者は、med-v ワークスペースパッケージャーを使って、MED-V ワークスペースの作成と管理を行います。

**注**  
MED-V ゲストエージェントは、初回セットアップ時に自動的にインストールされます。



### MED-V 展開プロセス

次に、MED-V のインストールと展開プロセスの概要を示します。

1.  管理者の資格情報を持ち、MED-V ワークスペースパッケージの構築に使用するコンピューターに、MED-V ワークスペースパッケージャーをインストールします。 詳細については、「 [Med-v ワークスペースパッケージャーをインストールする方法](how-to-install-the-med-v-workspace-packager.md)」を参照してください。

2.  Med-v イメージを準備し、med-v ワークスペースパッケージャーを使って、MED-V ワークスペースパッケージを作成します。 詳細については、「 [med-v の操作](operations-for-med-v.md)」を参照してください。

3.  企業全体で必要な MED-V コンポーネントを展開します。 MED-V の必要なコンポーネントは、Windows 仮想 PC、MED-V ホストエージェント、および MED-V ワークスペースです。

**重要**  
MED-V コンポーネントをインストールするには、管理者の資格情報が必要です。 エンドユーザーが MED-V をインストールしている場合は、管理者資格情報を入力するように求められます。 または、電子ソフトウェア配布 (ESD) システムを使用してインストールする場合は、コンテキストで管理者資格情報を提供できます。



### MED-V コンポーネント

エンタープライズ全体で展開する MED-V コンポーネントは、次のように構成されています。

**Windows 仮想 PC**

互換性解決のために、Windows 仮想 PC イメージ内の MED-V 関数を使用します。 Windows Virtual PC と Windows 7 用更新プログラム (KB977206) が必要です。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

**MED-V ホストエージェントインストールファイル**

MED-V\_HostAgent\_Setup.exe。

**MED-V ワークスペースインストールファイル**

MED ワークスペースのインストールファイルは、次のように構成される MED-V workspace パッケージをビルドすると作成されます。

MED-V ワークスペースインストールを実行する setup.exe 実行可能プログラム

&lt;Med-v (MED) _workspace \ _name &gt;

&lt; &gt; 圧縮された仮想ハードディスクである VHD \ _filename ファイル

構成設定用のファイル ( &lt; ワークスペース \ _name &gt; .reg と &lt; ワークスペース \ _name &gt; . ps1)

MED-V を展開するには、ホストコンピューターまたはホストコンピューターからアクセスできる共有に、必要なすべてのインストールファイルをコピーします。 Windows Virtual PC、MED-V Host Agent、および MED-V ワークスペースのコンポーネントインストールファイルを実行します。 次に、med-v ホストエージェントを起動して、MED-V の初回セットアップを完了します。

インストールは手動で実行できます。 ただし、コンポーネントの展開を自動化するには、電子的なソフトウェアの配布方法を使用することをお勧めします。 詳細については、「[電子ソフトウェア配布システムを通じて med-v のワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)」を参照してください。

**注**  
インストールオプションを制御するために使用できるコマンドライン引数の詳細については、「 [Med-v インストールファイルのコマンドラインオプション](command-line-options-for-med-v-installation-files.md)」を参照してください。



## 展開の手順


企業全体で MED-V を展開する場合は、インストールと初回のセットアップの2つの主要な考慮事項があります。

### インストール

1.  **Windows 仮想 pc** -インストール中、WINDOWS 仮想 pc を使用する med-v と、windows 7 の必須更新プログラム (KB977206)。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    MED-V をインストールする前に、Windows 7 インストールの一部としてインストールするか、または MED-V の一部としてインストールすることができます。 ただし、MED-V には展開のメカニズムは含まれていません。これらは、電子ソフトウェア配布 (ESD) システムまたは Windows 7 イメージの一部として展開する必要があります。

    **重要**  
    バッチファイルを使用して MED-V コンポーネントをインストールする場合は、MED-V ホストエージェントと MED-V ワークスペースパッケージファイルの後に Windows 仮想 PC と Windows 仮想 PC ホットフィックスをインストールすることをお勧めします。 このため、Windows Update では、再起動を要求することによって、インストールプロセスに干渉することはありません。



~~~
**Note**  
After you install Windows Virtual PC, the computer must be restarted.
~~~



2. **Med-v Host agent** – med-v が実行される Windows 7 コンピューターに Med-v host agent をインストールします。 MED-V ワークスペースをインストールする前に、これをインストールして、Windows 仮想 PC がインストールされていることを確認する必要があります。

3. **Med-v ワークスペース**– Med-v ワークスペースパッケージャー: setup.exe、. medv、.msi ファイルを使用して、このインストールで必要なファイルを作成します。 MED-V ワークスペースをインストールするには、setup.exe を実行します。これにより、必要に応じて他のファイルがトリガーされます。 インストールでは、ローカルコンピューターの実行キーの下のレジストリにエントリが格納され、Windows が起動すると常に MED-V が実行される MED-V ホストエージェントが起動します。

   **重要**  
   MED-V ワークスペースのインストールは、エンドユーザーによって対話式で実行するか、または電子ソフトウェア配布システムを使ってサイレントに実行できます。 MED-V workspace をインストールするには管理者の資格情報が必要であるため、エンドユーザーは MED-V ワークスペースをインストールするには、コンピューターの管理者である必要があります。 または、通常、電子ソフトウェア配布システムはシステムコンテキストで実行され、十分な権限があります。



~~~
**Tip**  
Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



### 初回のセットアップ

MED-V とその必須コンポーネントをインストールした後、MED-V を構成する必要があります。 MED-V の構成は、初回のセットアップと呼ばれます。 **Med-v ワークスペースパッケージャー**を使って、サイレントまたは対話形式で実行するための初回のセットアップを構成できます。 MED-V の初回のセットアップでは、エンドユーザーは、MED-V ワークスペースに対して認証するためにパスワードを入力する必要がありますが、それ以外の場合は、ユーザーに対してほとんど非表示にすることができます。 通知は通知領域に表示されます。たとえば、初回のセットアップが完了し、アプリケーションが準備できている場合です。 MED-V の初回セットアップ時に発生するアクションを次に示します。

1.  仮想ハードディスクを構成する必要があります。 ミニセットアップでは、Windows XP のイメージが実行され、展開されます。 通常、これは非表示のウィンドウで発生しますが、MED-V はこの構成時に表示されるように構成できます。

2.  ミニセットアップが完了すると、ESD ソフトウェアやその他のアプリケーションのインストール、イメージの構成などの追加構成を行うために必要なコマンドを実行できます。 これらは、Sysprep.inf ファイルで呼び出すことができますが、必須ではありません。 詳細については、「 [med-v 用に Windows 仮想 PC イメージを構成する](configuring-a-windows-virtual-pc-image-for-med-v.md)」を参照してください。

3.  Ftscompletion.exe は、構成の最後の手順として実行されます。 このプロセスは、MED-V 構成を完了し、ユーザーを RDP グループに追加して、MED-V ワークスペースへのアクセス、ログのコピー、med-v ワークスペースの準備ができている MED-V の通知を行い、MED-V ワークスペースを再起動します。 このプロセスでは、MED-V ワークスペースが作成されたときに、そのユーザーを MED-V ワークスペースの管理者として追加することもできます。 通常、Ftscompletion.exe は、Sysprep と inf ファイルを通じて呼び出されますが、スクリプトなどの別の方法で実行することもできます。 ただし、Ftscompletion.exe は、ワークステーションが構成されたときに実行される最後の操作である必要があります。 詳細については、「 [med-v 用に Windows 仮想 PC イメージを構成する](configuring-a-windows-virtual-pc-image-for-med-v.md)」を参照してください。

4.  Ftscompletion.exe で MED-V ワークスペースを再起動した後、エンドユーザーはログオンしています。 初めてセットアップしたときにパスワードを保存していない場合は、もう一度入力を求められます。 次に、MED-V ワークスペースが開始され、ユーザーに対して構成されます。 構成には、グループポリシーの適用が含まれます。

    Windows XP のアプリケーション互換性環境で適切なポリシーのみを適用することをお勧めします。 たとえば、通常、デスクトップパーソナル化ポリシーを適用する必要がないため、無効にする必要があります。 ローカルプロファイルのみを許可する方法について詳しくは、「[ローミングユーザープロファイルのグループポリシー設定](https://go.microsoft.com/fwlink/?LinkId=205072)」をご覧ください https://go.microsoft.com/fwlink/?LinkId=205072) 。

初回のセットアップが完了した後、公開されたアプリケーションの準備ができたことがエンドユーザーに通知されます。 これらのユーザーは、[**スタート**] メニューから med-v ワークスペースにインストールされているアプリケーションにアクセスできます。

## 関連トピック


[MED-V の展開環境を準備する](prepare-the-deployment-environment-for-med-v.md)

[MED-V の展開](deployment-of-med-v.md)









