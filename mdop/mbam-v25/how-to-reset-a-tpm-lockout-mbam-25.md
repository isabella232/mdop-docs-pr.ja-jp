---
title: TPM ロックアウトをリセットする方法
description: TPM ロックアウトをリセットする方法
author: dansimp
ms.assetid: dd20a728-c52e-48e6-9f6c-1311c71dee74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5aea277e80c54fb01d1a6c00b62f0c617d1ad12
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823324"
---
# TPM ロックアウトをリセットする方法


このトピックでは、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) を使って TPM ロックアウトをリセットする方法について説明します。 エンドユーザーが誤った PIN を入力した回数が多すぎると、TPM ロックアウトが発生する可能性があります。 TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。

管理と監視の Web サイトの [ **tpm の管理**] 領域から、コンピューター ID と関連付けられたユーザー識別子を提供するときに tpm 所有者のパスワードファイルを提供する、一元管理されたキーの回復データシステムにアクセスできます。

管理と監視の Web サイトの [TPM の管理] 領域にアクセスするには、MBAM ヘルプデスクユーザーロールまたは MBAM Advanced のヘルプデスクユーザーの役割が割り当てられている必要があります。 これらの役割は、管理者が Active Directory で作成するグループです。 これらのグループには任意の名前を使用できます。 詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。

MBAM と TPM の所有権の詳細については、「 [mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-tpm)」を参照してください。

**TPM ロックアウトをリセットするには**

1.  Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。

2.  左側のウィンドウで、[ **tpm の管理**] をクリックし、[ **tpm の管理**] ページを開きます。

3.  コンピューターの完全修飾ドメイン名とコンピューター名を入力します。

4.  エンドユーザーの Windows ログオンドメインとユーザー名を入力して、TPM 所有者パスワードファイルを取得します。

    **注** MBAM Advanced のヘルプデスクユーザーグループの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。

     

5.  [ **TPM 所有者パスワードファイルの要求の理由**] ボックスの一覧で、要求の理由を選択し、[**送信**] をクリックします。

    MBAM は、次のいずれかの値を返します。

    -   一致する TPM 所有者パスワードファイルが見つからなかった場合のエラーメッセージ

    -   送信されたコンピューターの TPM 所有者パスワードファイル

    TPM 所有者パスワードを取得した後、所有者パスワードが表示されます。

6.  パスワードを tpm ファイルに保存するには、[**保存**] ボタンをクリックします。

7.  **管理と監視の Web サイト**の [ **tpm の管理**] 領域で、[ **tpm ロックアウトのリセット**] オプションを選択し、tpm 所有者パスワードファイルを指定します。

    TPM ロックアウトがリセットされ、エンドユーザーのアクセスが復元されます。

    **重要** TPM ハッシュ値または TPM 所有者パスワードファイルにエンドユーザーを指定しないでください。 TPM 情報は変更されないため、ファイルをエンドユーザーに提供すると、セキュリティ上のリスクが生じます。

     



## 関連トピック


[MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





