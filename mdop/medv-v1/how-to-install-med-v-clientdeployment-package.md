---
title: MED-V クライアントをインストールする方法
description: MED-V クライアントをインストールする方法
author: dansimp
ms.assetid: bfac6de7-d96d-4b3e-bd8b-183e051e53c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2e4468b15c0c196bf605b1b5d129ab38678ec74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827194"
---
# MED-V クライアントをインストールする方法


展開パッケージベースのシナリオでは、MED-V クライアントインストールは展開パッケージに含まれ、パッケージから直接インストールされます。

**重要**  
画像が含まれていない展開パッケージを使用する場合は、画像が Web にアップロードされていること、または展開パッケージをインストールする前に事前ステージフォルダーにプッシュされていることを確認します。



**展開パッケージをインストールするには**

1.  次のいずれかの操作を行います。

    -   Web から MED-V パッケージをダウンロードします。

    -   展開 USB または DVD をホストドライブに挿入します。

2.  MED-V が自動的に起動しない場合は、[MED-VAutoInstaller.exe] をダブルクリックします。

    既にインストールされているコンポーネントと、現在インストールされているコンポーネントの一覧を示すダイアログボックスが表示されます。

    **注**  
    ホストコンピューター上にサポートされていないバージョンの Microsoft 仮想 PC が存在する場合は、既存のバージョンをアンインストールしてインストーラーをもう一度実行するように指示するメッセージが表示されます。



~~~
**Note**  
If an older version of the MED-V client exists, it will prompt you asking whether you want to upgrade.



Depending on the components that have been installed, you might need to reboot. If rebooting is necessary, a message appears notifying you that you must reboot.
~~~

3. 必要に応じて、コンピューターを再起動します。

   インストールが完了すると、MED-V が開始され、インストールが完了したことを通知するメッセージが表示されます。

4. 次のユーザー名とパスワードを使用して MED-V にログインします。

   -   ドメイン名とユーザー名を入力し、その後、MED-V での操作が許可されているドメインユーザーのパスワードを入力します。

       例: "domain \ _name \\ user\ _name", "password"

## 関連トピック


[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)

[MED-V イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)

[クライアント インストールのコマンド ライン リファレンス](client-installation-command-line-reference.md)









