---
title: TPM ロックアウトをリセットする方法
description: TPM ロックアウトをリセットする方法
author: dansimp
ms.assetid: 20719ab2-18ae-4d3b-989a-539341909816
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6453473ec09c2033346c7e464c08dbfdfe046d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825054"
---
# TPM ロックアウトをリセットする方法


Microsoft BitLocker の管理と監視 (MBAM) の暗号化されたドライブの回復機能には、データのキャプチャとストレージ、およびトラステッドプラットフォームモジュール (TPM) を管理するために必要なツールの可用性が含まれます。 このトピックでは、管理と監視の web サイトで中央キー回復データシステムにアクセスする方法について説明します。これにより、コンピューター ID と関連付けられているユーザー識別子が指定されたときに TPM 所有者パスワードファイルを提供できます。

TPM ロックアウトは、ユーザーが誤った PIN を入力した回数が何度も超えた場合に発生する可能性があります。 TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。

MBAM が TPM を所有している場合にのみ、TPM ロックアウトをリセットできます。

**TPM ロックアウトをリセットするには**

1.  Web ブラウザーを開き、管理と監視の web サイトに移動します。

2.  左側のナビゲーションウィンドウで、[ **tpm の管理**] を選択し、[ **tpm の管理**] ページを開きます。

3.  コンピューターとコンピューター名の完全修飾ドメイン名を入力し、ユーザーの Windows ログオンドメインとユーザーのユーザー名を入力して、TPM 所有者パスワードファイルを取得します。

4.  [ **TPM 所有者パスワードファイルの要求の理由**] ボックスの一覧で、要求の理由を選択し、[**送信**] をクリックします。

    MBAM は、次のいずれかの値を返します。

    -   一致する TPM 所有者パスワードファイルが見つからなかった場合のエラーメッセージ

    -   送信されたコンピューターの TPM 所有者パスワードファイル

    **注**  
    上級のヘルプデスクユーザーの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。



~~~
After the TPM owner password is retrieved, the owner password is displayed.
~~~

5. パスワードを tpm ファイルに保存するには、[**保存**] ボタンをクリックします。

   ユーザーは TPM 管理コンソールを実行し、[ **tpm ロックアウトのリセット**] オプションを選択し、tpm のロックアウトをリセットする tpm 所有者パスワードファイルを指定します。

   **重要**  
   ヘルプデスク管理者は、TPM ハッシュ値または TPM 所有者パスワードファイルをエンドユーザーに提供しないようにします。 TPM 情報は変更されないため、ファイルがエンドユーザーに提供されている場合は、セキュリティ上のリスクを招く可能性があります。



## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)









