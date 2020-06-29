---
title: App-V Desktop Client のセキュリティ
description: App-V Desktop Client のセキュリティ
author: dansimp
ms.assetid: 216b9c16-7bb4-4f94-b9d8-810501285008
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 26add6f855780113613cf1591c41722643954477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822317"
---
# App-V Desktop Client のセキュリティ


App-v デスクトップクライアントには、以前のバージョンの製品では使用できなかったさまざまなセキュリティ機能強化が用意されています。 これらの変更により、既定ではより高いレベルのセキュリティが提供され、クライアント設定の構成が行われます。

**注** コンピューターに app-v デスクトップクライアントをインストールすると、ソフトウェアは既定で最も安全な設定になります。 ただし、アップグレードする場合、クライアントの以前の設定は保持されます。

 

既定では、App-v デスクトップクライアントは、管理者以外のユーザーが公開の更新およびストリームアプリケーションを実行できるようにするために必要なアクセス許可のみを構成します。 App-v デスクトップクライアントには、次のような追加のセキュリティ強化機能が用意されています。

-   既定では、OSD キャッシュ更新は発行の更新プロセスによってのみ許可されています。

-   ログファイル ( `sftlog.txt` ) は、クライアントへのローカル管理アクセス権を持つアカウントによってのみアクセスできます。

-   ログファイルに最大サイズが設定されました。

-   ログファイルは、アーカイブ設定によって管理されます。

-   システムイベントログが実行されました。

## アクセス許可


デスクトップクライアントをインストールした後は、Microsoft が提供するレジストリまたは ADM テンプレートを使用して、MMC または個々のクライアントを通じて、他のセキュリティ設定を構成することができます。 App-v デスクトップクライアントには、管理者以外のユーザーがデスクトップクライアントのすべての機能にアクセスすることを制限するように設定できる権限があります。 権限の完全な一覧については、「App-v Client ヘルプファイルまたは app-v の操作ガイド」を参照してください。

**重要** 特に、複数のユーザーによって共有されている (ターミナルサーバーなどの) システムで、アクセス権を変更した場合の影響を慎重に検討してください。

 

**注** 環境内のユーザーがコンピューターのローカル管理者権限を持っている場合、アクセス許可は無視されます。

 

### ADM テンプレート

Microsoft Application Virtualization (App-v) では、グループポリシーによって最も一般的なクライアントの設定を構成するために使用できる ADM テンプレートが導入されています。 このテンプレートを使用すると、管理者は一元管理モデルを使用して、多くのクライアント設定を実装して変更することができます。 ADM テンプレートで利用できる設定の一部は、[セキュリティ設定] です。

**重要** ADM テンプレートを使用する場合は、設定がグループポリシーの基本設定であり、完全に管理されたグループポリシーではないことに注意してください。

 

使用している環境にクライアントを正常に展開するための ADM テンプレート、具体的な設定、およびガイダンスの詳細については、「App-v ADM テンプレートのホワイトペーパー」を参照してください [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063) 。

## OSD ファイルの種類の関連付けの削除


組織でユーザーが OSD ファイルから直接アプリケーションを開く必要がない場合は、クライアント上のファイルの種類の関連付けを削除することで、セキュリティを強化できます。 `HKEY_CURRENT_USERS`OSD のキーと `Softgird.osd.file` レジストリエディターを使用して、キーを削除します。 このプロセスをログオンスクリプトまたはインストール後のスクリプトに追加して、これらの変更を自動化することができます。

 

 




