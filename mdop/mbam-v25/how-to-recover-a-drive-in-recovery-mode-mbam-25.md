---
title: 回復モードでドライブを回復する方法
description: 回復モードでドライブを回復する方法
author: dansimp
ms.assetid: e126eaf8-9ae7-40fe-a28e-dbd78d26859e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d15f33f461e60fceeed3acbce3a0c82b02b56f98
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823367"
---
# 回復モードでドライブを回復する方法


このトピックでは、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) を使用して、BitLocker で保護されたドライブが回復モードになった場合にエンドユーザーに提供する回復パスワードを取得する方法について説明します。 ユーザーが PIN またはパスワードを紛失または忘れた場合や、信頼済みモジュールプラットフォーム (TPM) チップによってコンピューターの BIOS またはスタートアップファイルの変更が検出された場合、ドライブは回復モードになります。

回復パスワードを取得するには、管理と監視の Web サイトの [**ドライブの回復**] 領域を使用します。 この web サイトの領域にアクセスするには、MBAM ヘルプデスクユーザーロールまたは MBAM Advanced ヘルプデスクユーザーの役割が割り当てられている必要があります。

**注**  
これらの役割は、作成時に異なる名前を指定した可能性があります。 詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。



**重要**  
回復パスワードは1回の使用後に有効期限が切れます。 オペレーティングシステムドライブと固定データドライブでは、単一使用ルールが自動的に適用されます。 リムーバブルドライブの場合は、ドライブが取り外され、グループポリシー設定がアクティブになっているコンピューターで、リムーバブルドライブを管理するために、ドライブが適用されます。



**回復モードでドライブを回復するには**

1.  Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。

2.  左側のウィンドウで、[**ドライブの回復**] を選択して、[**暗号化されたドライブへのアクセスを回復**する] ページを開きます。

3.  回復情報を表示するには、エンドユーザーの Windows ログオンドメインとユーザー名を入力します。

    **注**  
    MBAM Advanced のヘルプデスクユーザーグループの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。



4.  回復キー ID の最初の8桁を入力して、一致する可能性のある回復キーの一覧を表示するか、完全な回復キーを取得するために回復キー ID 全体を入力します。

5.  [**ドライブのロック解除の理由**] ボックスの一覧で、定義済みのオプションのいずれかを選び、[**送信**] をクリックします。

    MBAM は、次の値を返します。

    -   一致する回復パスワードが見つからなかった場合のエラーメッセージ

    -   ユーザーが複数の一致する回復パスワードを持っている場合、一致する可能性がある複数の一致

    -   送信されたユーザーの回復パスワードと回復パッケージ

        **注**  
        破損したドライブを回復する場合、[回復パッケージ] オプションでは、ドライブを復元するために必要な重要な情報を BitLocker に提供します。



~~~
After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

6. パスワードをコピーするには、[**キーのコピー**] をクリックし、メールメッセージに回復パスワードを貼り付けます。 または、[**保存**] をクリックして回復パスワードをファイルに保存します。

   ユーザーが回復パスワードをシステムに入力するか、回復パッケージを使用すると、ドライブのロックが解除されます。



## 関連トピック


[MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





