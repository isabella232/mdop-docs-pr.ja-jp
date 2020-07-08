---
title: Windows XP の適切な資格情報を割り当てる方法
description: Windows XP の適切な資格情報を割り当てる方法
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819324"
---
# Windows XP の適切な資格情報を割り当てる方法


次の手順を使用して、適切な WindowsXP の資格情報を持つように App-v デスクトップクライアントを構成します。

**注** この手順を完了すると、ドメインに参加していないクライアントは、ドメインに参加しなくても公開更新を実行できます。

 

**WindowsXP を実行している App-v クライアントに適切な資格情報を割り当てるには**

1.  WindowsXP を実行している App-v クライアントの管理者権限がある場合は、[**ユーザーアカウント**] コントロールパネル (クラシックコントロールパネル) を開きます。

2.  [**詳細設定] タブ**をクリックし、[**パスワードの管理**] を選択します。

3.  [**ユーザー名とパスワードの保存**] 画面で、[**追加**] をクリックします。

4.  [**ログオン情報のプロパティ**] 画面で、次のフィールドに app-v インフラストラクチャからの情報を入力します。

    1.  **サーバー:** 発行サーバーの外部名の名前。

    2.  **ユーザー名:** フォーム Domain\\username. の外部ユーザーのユーザー名

    3.  **パスワード:**[**ユーザー名**] フィールドに入力されたユーザーアカウントのパスワードです。

5.  **[OK]** をクリックします。 資格情報はクライアントに保存されます。

## 関連トピック


[ドメインに参加しているクライアントとドメインに参加していないクライアント](domain-joined-and-non-domain-joined-clients.md)

[Windows Vista の適切な資格情報を割り当てる方法](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





