---
title: App-V と Windows AppLocker の相互運用性
description: App-V と Windows AppLocker の相互運用性
author: dansimp
ms.assetid: 9a488034-607d-411c-b495-ff184c726f49
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6f67bb87c0a4474acee3c4982b65c930e86c4917
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822314"
---
# App-V と Windows AppLocker の相互運用性


Microsoft Application Virtualization (App-v) クライアントのバージョン 4.5 SP1 は、Windows 7 の AppLocker 機能をサポートしています。 AppLocker 機能を使用すると、IT 管理者はコンピューターでの実行を制限するアプリケーションを指定できます。 このドキュメントでは、App-v の仮想環境と仮想化されたアプリケーションと連携するように AppLocker の規則を構成する方法について説明します。

**注** 仮想アプリケーションの Windows AppLocker ルールを構成するには、まず windows AppLocker を有効にする必要があります。 Windows AppLocker を有効にする方法の詳細については、 [Windows applocker](https://go.microsoft.com/fwlink/?LinkId=156732) ( https://go.microsoft.com/fwlink/?LinkId=156732) .

 

## 仮想アプリケーションの Windows AppLocker ルールを構成する


ローカル管理者は、プログラムの実行可能ファイル (.exe ファイル)、Windows インストーラーファイル (.msi および .msp ファイル)、スクリプト (.ps、.bat、.cmd、.vbs、.js ファイル) の実行を制限する Windows AppLocker ルールを作成できます。 これを行うには、管理者は、App-v クライアントがインストールされていて、すべての関連仮想アプリケーションがクライアントキャッシュにストリーミングされている参照コンピューターを使用します。 次に、管理者は、参照コンピューターのローカルセキュリティポリシー Microsoft 管理コンソール (MMC) スナップインの [Windows AppLocker] セクションを使用して、ルールを作成します。

ルールを作成するディレクトリパスまたは特定のファイルを参照するときに、非表示の共有へのパスを使用して、App-v ドライブにアクセスできます。 たとえば、アプリ-V ドライブがドライブ Q の場合、\\ Localhost\\ Q $ を参照することができます。ただし、ルールを作成するには、パスを編集して、\\ ¥ Localhost\\ Q $ への参照を削除し、代わりに Q:\\ を使用する必要があります。 参照コンピューターで各アプリケーションを起動して、アプリケーションのファイルにアクセスする必要があります。また、\ ¥ localhost¥ Q $ を参照するには、管理者権限が必要です。

 

 





