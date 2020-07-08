---
title: コマンド ラインを使用してクライアントをインストールする方法
description: コマンド ラインを使用してクライアントをインストールする方法
author: dansimp
ms.assetid: ed372403-64ff-48ff-a3cd-a46cad04a4d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca594e1399b4ca4f680f68efffcd011fdc5f042
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817324"
---
# コマンド ラインを使用してクライアントをインストールする方法


このセクションのトピックでは、setup.exe または setup.msi を使用して、Application Virtualization (App-v) デスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントのいずれかをインストールする手順について説明します。 セットアッププログラムを実行するには、管理者権限が必要です。

オプションのコマンドラインパラメーターを使用して、インストール時に特定の構成設定を App-v クライアントに適用することができます。 パラメーターの使用の詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。 クライアントを展開する前に (たとえば、グループポリシーを使用して)、レジストリ設定をコンピューターに適用した場合、これらの設定は保持され、その他のコマンドラインパラメーターが適用されます。 コマンドラインパラメーターの値によって、同じ設定の既存の値が置き換えられます。

**注** VDI server の実装などの読み取り専用キャッシュで使用するように App-v クライアントをインストールする場合、キャッシュが読み取り専用のときにクライアントがアプリケーションを更新しないように、 *Autoloadtarget*パラメーターを NONE に設定する必要があります。

 

これらのパラメーターをインストール後に設定する方法について詳しくは、コマンドライン (Application Virtualization (App-v) 運用ガイド) を[使って、App-v クライアントのレジストリ設定を構成する方法](https://go.microsoft.com/fwlink/?LinkId=169355)をご覧ください https://go.microsoft.com/fwlink/?LinkId=169355) 。

**注** ユーザーのコンピューターの構成設定がクライアントのインストールパスに依存する場合は、Application Virtualization (App-v) 4.5 クライアントで、以前のバージョンとは異なるフォルダーにインストールファイルがコピーされることに注意してください。 既定では、App-v 4.5 クライアントの新規インストールによって、そのインストールファイルが¥¥ Program files ¥ Microsoft Application Virtualization Client フォルダーにコピーされます。 以前のバージョンのクライアントが既にインストールされている場合は、App-v 4.5 クライアントインストーラーを実行すると、既存のインストールフォルダーを使って既存のクライアントのアップグレードが実行されます。

 

\ [テンプレートトークンの値 \]

**注** App-v バージョン4.6 以降の場合、App-v クライアントをインストールすると、SFTLDR.DLL が Windows\\system32 ディレクトリにコピーされます。 App-v クライアントが64ビットシステムにインストールされている場合、SFTLDR\_WOW64.DLL は Windows\\SysWOW64 ディレクトリにコピーされます。

 

\ [テンプレートトークンの値 \]

## このセクションの内容


次のトピックでは、setup.exe または setup.msi を使って、Application Virtualization (App-v) デスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントのいずれかをインストールする方法について説明します。

<a href="" id="how-to-install-the-app-v-client-by-using-setup-exe"></a>[setup.exe を使用して App-V Client をインストールする方法](how-to-install-the-app-v-client-by-using-setupexe-new.md)  
setup.exe プログラムを使用して、App-v クライアントをインストールするための詳しい手順について説明します。

<a href="" id="how-to-install-the-app-v-client-by-using-setup-msi"></a>[setup.msi を使用して App-V Client をインストールする方法](how-to-install-the-app-v-client-by-using-setupmsi-new.md)  
setup.msi プログラムを使用して、必要なソフトウェアと App-v クライアントをインストールするための詳しい手順について説明します。

## 関連トピック


[Application Virtualization Client インストーラーのコマンド ライン パラメーター](application-virtualization-client-installer-command-line-parameters.md)

[Application Virtualization Client を手動でインストールする方法](how-to-manually-install-the-application-virtualization-client.md)

[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)

[App-V Client をアンインストールする方法](how-to-uninstall-the-app-v-client.md)

 

 





