---
title: ヘルプ デスク ポータルを使用する方法
description: ヘルプ デスク ポータルを使用する方法
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826327"
---
# ヘルプ デスク ポータルを使用する方法


MBAM 管理と監視の web サイト (ヘルプデスクポータルとも呼ばれます) は、Microsoft BitLocker の管理と監視 (MBAM) サーバーインフラストラクチャの一部としてインストールされている、BitLocker ドライブ暗号化の管理インターフェイスです。 以下のセクションでは、この web サイトを使用してレポートを確認し、エンドユーザーのドライブを回復して、エンドユーザーの TPMs を管理する方法について説明します。

## <a href="" id="bkmk-reports"></a>レポート


MBAM は、Active Directory とクライアントコンピューターから情報を収集します。これにより、複数のレポートを実行して、BitLocker の使用状況とコンプライアンスを監視することができます。 管理と監視の web サイトの [**レポート**] セクションを使用して、エンタープライズのコンプライアンス、個々のコンピューター、およびキーの回復アクティビティに関するレポートを生成できます。 各レポートの説明については、「 [MBAM レポートについ](understanding-mbam-reports-mbam-2.md)て」を参照してください。

**レポートにアクセスするには**

1.  Web ブラウザーを開き、MBAM 管理と監視の web サイトに移動します。

2.  左側のウィンドウで [**レポート**] を選択します。

3.  トップメニューバーで、生成するレポートの種類を選択します。 レポートを保存するには、[レポート] メニューバーの [**エクスポート**] ボタンをクリックします。

MBAM レポートの実行方法の詳細については、「 [Mbam レポートを生成する方法](how-to-generate-mbam-reports-mbam-2.md)」を参照してください。

## <a href="" id="bkmk-drirec"></a>ドライブの回復


管理と監視の web サイトの**ドライブ回復**機能により、特定の管理者の役割 (ヘルプデスクのユーザーなど) が、Mbam クライアントで収集された回復キーデータにアクセスできるようになります。 BitLocker で保護されたドライブにアクセスするには、このデータを使うことができます。 回復モードのドライブを復元する方法については、「[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)」を参照してください。

また、移動された、または破損したドライブを復元することもできます。

-   [移動されたドライブを回復する方法](how-to-recover-a-moved-drive-mbam-2.md)

-   [破損しているドライブを回復する方法](how-to-recover-a-corrupted-drive-mbam-2.md)

BitLocker で保護されたドライブを回復する方法の詳細については、「 [MBAM での Bitlocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)」を参照してください。

## <a href="" id="bkmk-manatpm"></a>TPM を管理する


管理および監視 web サイトの TPM の管理機能を使うと、ユーザーに、MBAM クライアントによって収集された TPM データへのアクセス許可 ("MBAM ヘルプデスクユーザー" など) が与えられます。 TPM ロックアウトでは、管理者は管理と監視の web サイトを使って、TPM のロックを解除するために必要なパスワードファイルを取得することができます。 Tpm ロックアウト後に TPM をリセットする方法については、「 [Tpm ロックアウトをリセットする方法](how-to-reset-a-tpm-lockout-mbam-2.md)」を参照してください。

## <a href="" id="bkmk-helpdesk"></a> MBAM ヘルプデスクのタスク


管理と監視の web サイトを使用して、BitLocker で保護されたハードウェアの管理、ドライブの回復、レポートの実行など、多くの管理タスクを行うことができます。 管理と監視の web サイトの URL は、既定では http:// &lt; *mbamadministration servername*ですが、 &gt; インストールプロセス中にカスタマイズすることはできます。

**注** 管理と監視の web サイトで提供されるさまざまな機能にアクセスするには、ユーザーアカウントに関連付けられた適切なロールを持っている必要があります。 ユーザーロールの概要については、「 [MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-2.md)」を参照してください。

 

管理と監視の web サイトを使用して実行できるタスクについては、次のリンクを参照してください。

-   [TPM ロックアウトをリセットする方法](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [移動されたドライブを回復する方法](how-to-recover-a-moved-drive-mbam-2.md)

-   [破損しているドライブを回復する方法](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [紛失したコンピューターの BitLocker 暗号化の状態を確認する方法](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





