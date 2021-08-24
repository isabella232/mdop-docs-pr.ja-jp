---
title: UE-V 1.0 のアーキテクチャの概要
description: UE-V 1.0 のアーキテクチャの概要
author: dansimp
ms.assetid: d54f9f10-1a4d-4e56-802d-22d51646e1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b54a9a207f9b74ad3d028cf4ab1f9842d59b0b3a
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910452"
---
# <a name="high-level-architecture-for-ue-v-10"></a>UE-V 1.0 のアーキテクチャの概要


このトピックでは、ローミング ソリューションの Microsoft User Experience Virtualization (UE-V) のUE-Vについて説明します。 次の要素は、標準の展開のUE-Vです。

![ue-v エージェントのアーキテクチャ図。](images/ue-vagentarchitecturaldiagram.gif)

このUE-Vエージェントは、アプリケーションとオペレーティング システム プロセスを監視し、設定場所テンプレートで識別UE-V確認します。 アプリケーションまたはオペレーティング システムが起動すると、設定が設定パッケージから読み取り、コンピューターに適用されます。 アプリケーションが閉じるとき、またはオペレーティング システムがロックまたはシャットダウンされた場合、設定は設定の保存場所にある UE-V設定パッケージに保存されます。

## <a name="settings-storage-location"></a>設定の保存場所


設定の保存場所は、ユーザー エクスペリエンス仮想化エージェントが読み取りおよび書き込み設定にアクセスするファイル共有です。 この場所は、Active Directory ホーム ディレクトリか、インストール時にUE-Vされます。 UE-V エージェントのインストール中に場所を設定するか、後でグループ ポリシー、WMI、または PowerShell を使用して設定できます。 この場所は、ユーザーがアクセスできる共通のファイル共有に対して指定できます。 インストール中に保存場所が設定されている設定がない場合UE-V Active Directory のホーム ディレクトリが使用されます。 このUE-Vエージェントは場所を確認し、ユーザー設定を保存してアクセスするユーザーから非表示のシステム フォルダーを作成します。 設定ストレージの詳細については、「[環境を準備する」を参照UE-V。](preparing-your-environment-for-ue-v.md)

## <a name="ue-v-agent"></a>UE-V エージェント


ユーザー UE-Vエージェントは、ユーザー エクスペリエンス仮想化によって同期される設定を使用して各コンピューターにインストールされます。 エージェントは、登録済みのアプリケーションとオペレーティング システムの設定に対する変更を監視し、それらの設定をコンピューター間で同期します。 設定が開始されると、設定の保存場所からアプリケーションに適用されます。 その後、アプリケーションが閉じると、設定は設定の保存場所に保存されます。 オペレーティング システムの設定は、ユーザーがログオンした場合、コンピューターのロックが解除されている場合、またはリモート デスクトップ プロトコル (RDP) を使用してリモートでコンピューターに接続するときに適用されます。 エージェントは、ユーザーがログオフした場合、コンピューターがロックされている場合、またはリモート接続が切断された場合に設定を保存します。 クライアント エージェントの詳細については、「UE-V環境の準備[」を参照UE-V。](preparing-your-environment-for-ue-v.md)

## <a name="settings-location-templates"></a><a href="" id="bkmk-settingslocationtemplate"></a>設定場所テンプレート


設定場所テンプレートは、ユーザー エクスペリエンス仮想化によって監視される設定の場所を定義する XML ファイルです。 これらの設定テンプレートで定義されている設定の場所だけが、エージェント エージェントを実行しているコンピューター UE-Vされます。 設定場所テンプレートには設定値が含まれるのではなく、値がコンピューターに保存されている場所だけが含まれます。

UE-Vには、一部の Microsoft アプリケーションの設定場所と設定を指定する設定場所テンプレートのセットWindowsがあります。 管理者は、ユーザー設定の場所テンプレートを作成するには、ユーザー設定ジェネレーター UE-V使用します。

[UE-V 1.0 を使用して同期するアプリケーションの計画](planning-which-applications-to-synchronize-with-ue-v-10.md)

[UE-V 1.0 のカスタム テンプレートの展開計画](planning-for-custom-template-deployment-for-ue-v-10.md)

[カスタム UE-V テンプレートと UE-V Generator の操作](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## <a name="settings-packages"></a>設定パッケージ


アプリケーション設定とWindows設定は、エージェントによって作成される設定パッケージにUE-Vされます。 設定パッケージは、設定場所テンプレートで表される設定のコレクションです。 これらの設定パッケージは、ビルドされ、ローカルに保存され、設定の保存場所にコピーされます。 "Last write wins" は、1 人のユーザーが複数のコンピューターをストレージの場所に同期するときに保持される設定を決定します。 1 台のコンピューターで実行されるエージェントは、他のコンピューターで実行されるエージェントとは別に、設定の場所に対して読み取りおよび書き込みを行います。 直近に書き込まれた設定と値は、次のエージェントが設定の保存場所から読み取る際に適用されます。

![ue-v ジェネレーター プロセス。](images/ue-vgeneratorprocess.gif)

## <a name="settings-template-catalog"></a>設定テンプレート カタログ


設定テンプレート カタログは、すべてのカスタム設定の場所テンプレートをUE-Vサーバー メッセージ ブロック (SMB) ネットワーク共有上のフォルダー パスです。 このUE-Vエージェントは、この場所から新しいテンプレートまたは更新されたテンプレートを取得します。 このUE-Vエージェントは、この場所を毎日 1 回チェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。 前回のチェック以降にこのフォルダーに追加または更新されたテンプレートは、UE-Vされます。 このUE-Vエージェントは、このフォルダーから削除されたテンプレートを登録解除します。 テンプレートは、タスク スケジューラによって 1 日に 1 回登録および登録解除されます。 既定の設定の場所テンプレートのみを使用する場合は、UE-Vテンプレート カタログは不要です。 設定展開カタログの詳細については、「Planning for Custom Template Deployment for UE-V [1.0」を参照してください](planning-for-custom-template-deployment-for-ue-v-10.md)。

## <a name="user-experience-virtualization-generator"></a>ユーザー エクスペリエンス仮想化ジェネレーター


User Experience Virtualization Generator を使用すると、カスタム設定の場所テンプレートを作成し、エンタープライズで使用されるアプリケーションの設定場所を保存し、ローミング設定ソリューションに含める必要があります。 このUE-Vジェネレーターは、レジストリ値の場所とアプリケーションの設定ファイルを検出し、それらの場所を設定場所テンプレート XML ファイルに記録します。 その後、これらの設定場所テンプレートをユーザー コンピューターに配布できます。 またUE-Vジェネレーターを使用すると、管理者は既存のテンプレートを編集したり、別の XML エディターで作成されたテンプレートを検証したりすることもできます。

このUE-Vジェネレーターは、アプリケーションを監視して、設定の保存場所を検出して記録します。 これを行うには、アプリケーションが HKEY\_CURRENT\_USER レジストリまたは [ユーザー\\[ユーザー名\] \\ **AppData****** ローミングとユーザー  \\  **** \\ \[User name\] \\ **AppData**  \\  **Local**の下のファイル フォルダーで読み取りまたは書き込みを行う場所を監視します。

検出プロセスでは、ログインしているユーザーが値を書き込めないレジストリ キーとファイルが除外されます。 これらはいずれも XML ファイルに含まれません。 検出プロセスでは、オペレーティング システムの主要な機能に関連付けられているレジストリ キーとファイルWindowsします。

ジェネレーターの詳細については、「UE-Vジェネレーターのインストール[」をUE-Vしてください](installing-the-ue-v-generator.md)。

## <a name="related-topics"></a>関連トピック


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[User Experience Virtualization 1.0 の概要](getting-started-with-user-experience-virtualization-10.md)

[User Experience Virtualization 1.0 について](about-user-experience-virtualization-10.md)

[カスタム UE-V テンプレートと UE-V Generator の操作](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





