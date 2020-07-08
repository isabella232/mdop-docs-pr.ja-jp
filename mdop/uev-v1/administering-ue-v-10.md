---
title: UE-V 1.0 の管理
description: UE-V 1.0 の管理
author: dansimp
ms.assetid: c399ae8d-c839-4f84-9bfc-adacd8f89f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4dcafd1949dcedd195569dabb7540ce55a2f1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822697"
---
# UE-V 1.0 の管理


Microsoft User Experience Virtualization (UE-V) を展開した後、さまざまな進行中の管理タスクを実行できる必要があります。 これらのインストール後のタスクについては、次のセクションで説明します。

## UE-V リソースの管理


UE-V のライフサイクルでは、UE-V agent の構成を管理する必要があります。また、設定パッケージなどのリソースの保存場所を管理する必要があります。 紛失した設定を回復するために、UE-V をインストールする前に、ユーザーの設定を元の状態に復元するなどのタスクを実行することが必要な場合があります。 次のトピックでは、UE-V リソースの管理に関するガイダンスを提供します。

### UE-V のスケジュールされたタスクの頻度の変更

UE-V が [設定] テンプレートカタログの新しい、更新、または削除されたユーザー設定の場所テンプレートをチェックするときに管理するスケジュール済みタスクを構成できます。

[UE-V のスケジュールされたタスクの頻度の変更](changing-the-frequency-of-ue-v-scheduled-tasks.md)

### <a href="" id="sharing-settings-location-templates-with-the-ue-v-template-gallery-"></a>UE-V テンプレート ギャラリーを使用した設定場所テンプレートの共有

UE-V のテンプレートギャラリーでは、UE-V 設定の場所テンプレートの共有が容易になります。 ギャラリーでは、他のユーザーと共有したり、他のユーザーが作成したテンプレートをダウンロードしたりするために、設定場所テンプレートをアップロードすることができます。

[UE-V テンプレート ギャラリーを使用した設定場所テンプレートの共有](sharing-settings-location-templates-with-the-ue-v-template-gallery.md)

### アプリケーションと Windows の設定を UE-V 1.0 と同期させる

UE-V の WMI 機能と PowerShell 機能により、設定パッケージを復元することができます。 WMI コマンドと PowerShell コマンドを使用すると、アプリケーションの設定と Windows の設定を、UE-V agent を起動した後に初めてアプリケーションを起動したときにコンピューター上にあった設定値に戻すことができます。

[UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)

### グループ ポリシー オブジェクトを使用した UE-V の構成

グループポリシーを使って、UE-V によるコンピューター上の設定の同期方法を定義した設定を変更することができます。

[グループ ポリシー オブジェクトを使用した UE-V の構成](configuring-ue-v-with-group-policy-objects.md)

### PowerShell と WMI を使用した UE-V の管理

PowerShell と WMI を使って、UE-V によるコンピューター上の設定の同期方法を定義する設定を変更できます。

[PowerShell と WMI を使用した UE-V 1.0 エージェントの管理](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

### UE-V 設定パッケージの移行

新しいサーバーまたはバックアップ目的で、ユーザー設定パッケージを再配置できます。

[UE-V 設定パッケージの移行](migrating-ue-v-settings-packages.md)

## この製品のその他のリソース


[UE-V 1.0 の操作](operations-for-ue-v-10.md)

 

 





