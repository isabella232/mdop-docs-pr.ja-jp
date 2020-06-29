---
title: Windows Vista の適切な資格情報を割り当てる方法
description: Windows Vista の適切な資格情報を割り当てる方法
author: dansimp
ms.assetid: cc11d2af-a350-4d16-ba7b-f9c1d89e14b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 111dafea505133f123cf8531a2891a452e725ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821367"
---
# Windows Vista の適切な資格情報を割り当てる方法


次の手順に従って、適切な windows Vista の資格情報を使用して App-v デスクトップクライアントを構成します。

**注** この手順は、ドメインに参加していない各コンピューターで完了する必要があります。 環境内のドメインに参加していないコンピューターの数によっては、非常に面倒な操作になることがあります。 Credential Manager のスクリプトとコマンドラインインターフェイスを使用すると、管理者がこのプロセスを自動化するのに役立ちます。

 

**Windows Vista を実行している App-v クライアントに適切な資格情報を割り当てるには**

1.  Windows Vista を実行している App-v デスクトップクライアントで管理者権限がある場合は、[**ユーザーアカウント**] コントロールパネル (クラシックコントロールパネル) を開きます。

2.  左側のタスクウィンドウで、[**ユーザーアカウント**から**ネットワークパスワードを管理**する] を選択します。

3.  [**ユーザー名とパスワードの保存**] 画面の [**追加**] を選択します。

4.  [**保存されている資格情報のプロパティ**] 画面で、app-v インフラストラクチャの情報を入力します。

    1.  **ログオン:** 発行サーバーの外部名。

    2.  **ユーザー名:** フォーム Domain\\Username. の外部ユーザーのユーザー名

    3.  **パスワード:**[**ユーザー名**] フィールドに入力されたユーザーアカウントのパスワードです。

    4.  **資格情報の種類**を選択したままにして、[ **OK]** をクリックします。

5.  **[閉じる]** をクリックします。 資格情報は、App-v インフラストラクチャへの適切な認証のために資格情報ストアに保存されます。

## 関連トピック


[ドメインに参加しているクライアントとドメインに参加していないクライアント](domain-joined-and-non-domain-joined-clients.md)

[Windows XP の適切な資格情報を割り当てる方法](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





