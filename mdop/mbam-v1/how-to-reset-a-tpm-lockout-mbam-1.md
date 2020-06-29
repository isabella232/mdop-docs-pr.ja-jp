---
title: TPM ロックアウトをリセットする方法
description: TPM ロックアウトをリセットする方法
author: dansimp
ms.assetid: 91ec6666-1ae2-4e76-9459-ad65c405f639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde77a12e97d050777dac15d4106124ec111b3cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812922"
---
# TPM ロックアウトをリセットする方法


Microsoft BitLocker の管理と監視 (MBAM) の暗号化されたドライブの回復機能には、データのキャプチャとストレージ、およびトラステッドプラットフォームモジュール (TPM) を管理するために必要なツールの可用性が含まれます。 このトピックでは、ビット \ _admmon \ _tlanextref 管理 web サイトで中央キー回復データシステムにアクセスする方法について説明します。 キー回復データシステムでは、コンピューターの id と関連付けられているユーザー識別子が指定されている場合、TPM 所有者パスワードファイルを提供できます。

TPM ロックアウトは、ユーザーが誤った PIN を何度も入力した場合に発生する可能性があります。 TPM ロックアウトの前に、ユーザーが間違った PIN を入力できる回数は、コンピューターの製造元の仕様に基づいています。

**TPM ロックアウトをリセットするには**

1.  MBAM 管理 web サイトを開きます。

2.  ナビゲーションウィンドウで、[ **TPM の管理**] を選びます。 [TPM の**管理**] ページが開きます。

3.  コンピューターとコンピューター名の完全修飾ドメイン名 (FQDN) を入力します。 ユーザーの Windows ログオンドメインとユーザーのユーザー名を入力します。 [ **TPM 所有者パスワードファイルの要求の理由**] ドロップダウンメニューで、定義済みのオプションのいずれかを選択します。 **[送信]** をクリックします。

4.  MBAM は、次のいずれかを返します。

    -   一致する TPM 所有者パスワードファイルが見つからなかった場合のエラーメッセージ

    -   送信されたコンピューターの TPM 所有者パスワードファイル

    **注** 上級のヘルプデスクユーザーの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。

     

5.  取得すると、所有者パスワードが表示されます。 このパスワードを tpm ファイルに保存するには、[**保存**] ボタンをクリックします。

6.  ユーザーは、TPM 管理コンソールを実行し、[ **tpm ロックアウトのリセット**] オプションを選択し、tpm のロックアウトをリセットする tpm 所有者パスワードファイルを指定します。

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam.md)

 

 





