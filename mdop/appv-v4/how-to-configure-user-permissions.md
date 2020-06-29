---
title: ユーザーのアクセス許可を構成する方法
description: ユーザーのアクセス許可を構成する方法
author: dansimp
ms.assetid: 54e69f46-b028-4ad1-9b80-f06ef5c8f559
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3c2581a9f9dddcbc63682d356c777a24222dd62f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817734"
---
# ユーザーのアクセス許可を構成する方法


権限を持っていないユーザーに対して、管理者権限を持たない操作を有効または無効にするには、 **Permissions**レジストリキー (HKEY \ _LOCAL \ _MACHINE ¥) でキー値を編集します。 このキーは主に、管理者権限を持つユーザーがこれらのいずれかのキー値を編集できるようにすることで、特別なセキュリティを提供するのではなく、ユーザーによるミスを防ぐために設計されています。 次の手順は、キーの値を変更する方法の例です。 Application Virtualization (App-v) クライアントのレジストリキーと値の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=121528> 。

**ユーザー権限を変更するには**

1.  ユーザーがオフラインモードでクライアントを実行することを選択できるようにするには、次のキー値を1に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode

2.  ユーザーがユーザーインターフェイスを使用してすべてのアプリケーションを表示できるようにするには、次のキー値を1に設定します。 この値を 0 (ゼロ) に設定すると、ユーザーが利用できるアプリケーションのみを表示できます。

    HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \ 一般法人向け \ すべてのアプリについて (英語)

## 関連トピック


[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

[Application Virtualization Client のユーザー アクセス許可](user-access-permissions-in-application-virtualization-client.md)

 

 





