---
title: App-V 5.0 SP3 リリース ノート
description: App-V 5.0 SP3 リリース ノート
author: dansimp
ms.assetid: bc4806e0-2aba-4c7b-9ecc-1b2cc54af1d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b6d5834e4d0c953365f955922403c1a7a2058b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813323"
---
# App-V 5.0 SP3 リリース ノート


Microsoft Application Virtualization (App-v) 5.0 SP3 の既知の問題を以下に示します。

## 新しい5.0 アプリのインストール後にサーバーファイルが削除されない


App-v 5.0 SP1 サーバーをアンインストールしてから、app-v 5.0 SP3 サーバーをインストールすると、インストールが失敗し、管理サーバーのバージョンが正しくインストールされません。 次のエラーが表示されます。

`[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {bee44f0f-05be-48e4-81dd-d34a83600b95}, type: Upgrade, scope: PerMachine, version: 5.0.1218.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.``[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {e1ca9d65-0ebf-4fd5-98e5-00d6453967a4}, type: Upgrade, scope: PerMachine, version: 5.0.1224.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.`

この問題は、App-v 5.0 SP1 をアンインストールしたときにサーバーファイルが削除されないために発生します。そのため、App-v 5.0 SP3 のインストールプロセスでは、新しいインストールの代わりにアップグレードが誤って行われます。

**回避策**: 次のレジストリキーを削除してから、App-V 5.0 SP3 のインストールを開始します。

`HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## AD DS に問い合わせると、一部のアプリケーションが正しく動作しない場合がある


更新されたグループメンバーシップのために Active Directory ドメインサービスを照会することによって更新されたパッケージを受け取った場合、アプリケーションがユーザーのアクセストークンに依存していると、一部のアプリケーションが正しく動作しないことがあります。 さらに、グループメンバーシップのクエリを頻繁に行うと、ドメインコントローラーの過負荷が発生する可能性があります。 ユーザーアクセストークンの詳細については、「[アクセストークン](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx)」を参照してください。

**回避策**: 更新されたグループメンバーシップを照会する前に、ユーザーがログオフしてから再びログインするまで待ちます。 更新されたグループメンバーシップを照会するには、「 [Microsoft Application Virtualization 5.0 Service Pack 1 の修正プログラムパッケージ 2](https://support.microsoft.com/kb/2897087)」に記載されているレジストリキーを使わないでください。






## 関連トピック


[App-V 5.0 SP3 について](about-app-v-50-sp3.md)

 

 





