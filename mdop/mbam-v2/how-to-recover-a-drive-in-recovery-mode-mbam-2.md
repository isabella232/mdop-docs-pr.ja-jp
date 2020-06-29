---
title: 回復モードでドライブを回復する方法
description: 回復モードでドライブを回復する方法
author: dansimp
ms.assetid: 8b792bc8-b671-4345-9d37-0208db3e5b03
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d5ce509599d0eb800a71360e3be9d0fa3b33f4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825057"
---
# 回復モードでドライブを回復する方法


Microsoft BitLocker の管理と監視 (MBAM) の暗号化されたドライブ回復機能を使用すると、BitLocker で保護されたボリュームにアクセスするために必要なデータと可用性をキャプチャして保存することができます。 BitLocker は回復モードになります。 BitLocker で保護されたボリュームは、PIN またはパスワードを紛失または忘れた場合、またはコンピューターの BIOS または起動ファイルの変更を信頼されたモジュールプラットフォーム (TPM) チップが検出した場合に、回復モードになります。

この手順を使用して一元的なキー回復データシステムにアクセスします。これにより、回復パスワード ID と関連付けられたユーザー識別子が指定されている場合に回復パスワードを提供できます。

**重要**  
Microsoft BitLocker の管理と監視では、使用時に期限切れになる単一使用の回復キーが使用されます。 回復パスワードの1回の使用は、オペレーティングシステムドライブと固定ドライブに自動的に適用されます。 リムーバブルドライブの場合は、ドライブが取り外されたときに適用され、グループポリシー設定がアクティブになっているコンピューターで、リムーバブルドライブを管理するために再挿入とロック解除を行います。



**回復モードでドライブを回復するには**

1.  Web ブラウザーを開き、管理と監視の web サイトに移動します。

2.  ナビゲーションウィンドウで、[**ドライブの回復**] をクリックします。 [暗号化されたドライブへのアクセスを回復する] web ページが開きます。

3.  回復情報を表示するユーザーの Windows ログオンドメインとユーザー名を入力して、一致する回復キーの一覧、または回復キー id 全体を取得し、正確な回復キーを受け取ることができます。

4.  [**ドライブのロックを解除する理由**] ボックスの一覧からいずれかの定義済みオプションを選び、[**送信**] をクリックします。

    **注**  
    MBAM Advanced ヘルプデスクユーザーの場合、ユーザードメインとユーザー ID のエントリは必要ありません。



~~~
MBAM returns the following:

-   An error message if no matching recovery password is found

-   Multiple possible matches if the user has multiple matching recovery passwords

-   The recovery password and recovery package for the submitted user

    **Note**  
    If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.



After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

5. パスワードをコピーするには、[**キーのコピー**] をクリックし、メールメッセージに回復パスワードを貼り付けます。 または、[**保存**] をクリックして回復パスワードをファイルに保存します。

   ユーザーが回復パスワードをシステムに入力するか、回復パッケージを使用すると、ドライブのロックが解除されます。

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)









