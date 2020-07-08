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
ms.openlocfilehash: 76703cf4c7297401e6516830bf194cef741d60ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827097"
---
# UE-V 1.0 のアーキテクチャの概要


このトピックでは、Microsoft User Experience Virtualization (UE-V) 設定のローミングソリューションの高レベルのアーキテクチャ要素について説明します。 次の要素は、標準の UE-V 展開に含まれています。

![ue-v agent アーキテクチャ図](images/ue-vagentarchitecturaldiagram.gif)

UE-V Agent は、UE-V の [設定] の場所テンプレートで指定されているように、アプリケーションとオペレーティングシステムのプロセスを監視します。 アプリケーションまたはオペレーティングシステムが起動すると、設定が設定パッケージから読み取られ、コンピューターに適用されます。 アプリケーションが閉じるか、オペレーティングシステムがロックまたはシャットダウンされると、設定は、設定の保存場所にある UE-V 設定パッケージに保存されます。

## 設定の保存場所


設定の保存場所は、ユーザーエクスペリエンス仮想化エージェントが読み取りと書き込みの設定にアクセスするファイル共有です。 この場所は、Active Directory のホームディレクトリか、UE-V のインストール時に定義されます。 UE-V agent のインストール中に場所を設定するか、後でグループポリシー、WMI、または PowerShell を使用して場所を設定することができます。 この場所は、ユーザーがアクセスできる一般的なファイル共有に配置できます。 インストール時に設定の保存場所が設定されていない場合、UE-V は Active Directory のホームディレクトリを使用します。 UE-V agent は、場所を確認し、ユーザー設定の保存とアクセスを行うユーザーから非表示になっているシステムフォルダーを作成します。 設定記憶域の詳細については、「 [ue-v の環境の準備](preparing-your-environment-for-ue-v.md)」を参照してください。

## UE-V Agent


UE-V agent は、ユーザーエクスペリエンスの仮想化によって同期される設定を持つ各コンピューターにインストールされます。 エージェントは、設定に加えられたすべての変更について、登録済みアプリケーションとオペレーティングシステムを監視し、それらの設定をコンピューター間で同期します。 設定は、アプリケーションの起動時に設定の保存場所からアプリケーションに適用されます。 設定は、アプリケーションが閉じるときに設定の保存場所に保存されます。 オペレーティングシステムの設定は、ユーザーがログオンしたとき、コンピューターのロックが解除されたとき、またはユーザーがリモートデスクトッププロトコル (RDP) を使ってリモートでコンピューターに接続したときに適用されます。 エージェントは、ユーザーがログオフしたとき、コンピューターがロックされているとき、またはリモート接続が切断されたときに設定を保存します。 UE-V Agent の詳細については、「 [ue-v の環境の準備](preparing-your-environment-for-ue-v.md)」を参照してください。

## <a href="" id="bkmk-settingslocationtemplate"></a>設定場所テンプレート


設定場所テンプレートは、ユーザーエクスペリエンスの仮想化によって監視される設定の場所を定義する XML ファイルです。 これらの設定テンプレートで定義された設定の場所のみが、UE-V Agent を実行しているコンピューターでキャプチャまたは適用されます。 設定場所テンプレートには、コンピューター上の値が格納されている場所のみが設定されています。

UE-V には、一部の Microsoft アプリケーションや Windows 設定の設定の場所を指定する、設定の場所テンプレートのセットが含まれています。 管理者は、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成できます。

[UE-V 1.0 を使用して同期するアプリケーションの計画](planning-which-applications-to-synchronize-with-ue-v-10.md)

[UE-V 1.0 のカスタム テンプレートの展開計画](planning-for-custom-template-deployment-for-ue-v-10.md)

[カスタム UE-V テンプレートと UE-V Generator の操作](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## 設定パッケージ


アプリケーションの設定と Windows の設定は、UE-V Agent によって作成される設定パッケージに保存されます。 設定パッケージは、設定場所テンプレートで表示される設定のコレクションです。 これらの設定パッケージは、ローカルに保存され、設定の保存場所にコピーされます。 "最終書き込み wins" は、1人のユーザーが複数のコンピューターをストレージの場所に同期したときに保持される設定を決定します。 1台のコンピューターで実行されるエージェントは、他のコンピューターで実行されているエージェントとは無関係に、設定の場所の読み取りと書き込みを行います。 最後に書き込まれた設定と値は、次のエージェントが設定の保存場所から読み取りを行ったときに適用されます。

![ue-v generator プロセス](images/ue-vgeneratorprocess.gif)

## 設定テンプレートカタログ


設定テンプレートカタログは、UE-V のコンピューター上のフォルダーパス、またはカスタム設定の場所テンプレートをすべて保存するサーバーメッセージブロック (SMB) ネットワーク共有です。 UE-V agent は、新しいまたは更新されたテンプレートをこの場所から取得します。 UE-V agent は、毎日この場所をチェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。 前回のチェック以降、このフォルダーで追加または更新されたテンプレートは、UE-V エージェントによって登録されます。 UE-V agent は、このフォルダーから削除されたテンプレートを deregisters します。 テンプレートは、タスクスケジューラによって1日に登録および登録解除されます。 UE-V に含まれている既定の設定場所テンプレートのみを使用する場合は、設定テンプレートカタログは不要です。 設定展開カタログの詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。

## ユーザーエクスペリエンスの仮想化ジェネレーター


ユーザーエクスペリエンスの仮想化ジェネレーターを使用すると、エンタープライズで使用され、ローミング設定ソリューションに含めるアプリケーションの設定の場所を保存する、カスタム設定の場所テンプレートを作成できます。 UE-V Generator は、レジストリ値の位置とアプリケーションの設定ファイルを検出し、その場所を設定場所テンプレートの XML ファイルに記録します。 次に、これらの設定場所テンプレートをユーザーコンピューターに配布できます。 UE-V Generator を使用すると、管理者は、既存のテンプレートを編集したり、別の XML エディターで作成されたテンプレートを検証したりすることもできます。

UE-V Generator は、アプリケーションを監視し、その設定が保存されている場所を記録します。 これを行うには、HKEY \ _CURRENT \ _USER registry、または**users**の下にあるファイルフォルダーの中で、アプリが読み取りまたは書き込みを行う場所を監視します。 \ \ [ユーザー名 \] **\ \ の**ユーザー名 \] \ | ユーザー  \\  **Roaming and Users**名 \] \ **appdata**  \\  **ローカル**。

検出プロセスでは、ログインしたユーザーが値を書き込むことができないレジストリキーとファイルは除外されます。 これらは、XML ファイルには含まれません。 また、検出プロセスでは、Windows オペレーティングシステムのコア機能に関連付けられたレジストリキーとファイルは除外されます。

UE-V Generator の詳細については、「 [Ue-v generator のインストール](installing-the-ue-v-generator.md)」を参照してください。

## 関連トピック


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[User Experience Virtualization 1.0 の概要](getting-started-with-user-experience-virtualization-10.md)

[User Experience Virtualization 1.0 について](about-user-experience-virtualization-10.md)

[カスタム UE-V テンプレートと UE-V Generator の操作](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





