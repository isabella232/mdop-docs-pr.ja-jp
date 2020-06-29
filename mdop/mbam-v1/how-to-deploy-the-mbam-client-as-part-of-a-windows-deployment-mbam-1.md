---
title: Windows 展開の一部として MBAM クライアントを展開する方法
description: Windows 展開の一部として MBAM クライアントを展開する方法
author: dansimp
ms.assetid: 8704bf33-535d-41da-b9b2-45b60754367e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a63311bcc93d84472ceff5c80c9222fefd5445c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824914"
---
# Windows 展開の一部として MBAM クライアントを展開する方法


Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 コンピューターのイメージングと Windows の展開プロセス中にクライアントコンピューターで BitLocker 管理と暗号化を有効にすることにより、BitLocker クライアントを組織に統合することができます。

**注**  
MBAM クライアントシステム要件を確認するには、「 [mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。



Windows 展開の最初のイメージングステージの間に BitLocker を使用してクライアントコンピューターを暗号化すると、MBAM 実装の管理オーバーヘッドを軽減できます。 この方法では、展開されているすべてのコンピューターに既に BitLocker が実行されており、正しく構成されていることも保証されます。

**Warning**  
このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。 Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。 レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。 Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。 レジストリは、自分の責任において変更してください。



**Windows 展開の一部としてコンピューターを暗号化するには**

1.  組織で、BitLocker のトラステッドプラットフォームモジュール (TPM) プロテクターまたは TPM + PIN プロテクターオプションの使用を計画している場合は、MBAM の最初の展開前に TPM チップをアクティブ化する必要があります。 TPM チップをアクティブ化すると、プロセスの後の再起動が不要になり、TPM チップが組織の要件に従って適切に構成されていることを確認できます。 コンピューターの BIOS で TPM チップを手動でアクティブ化する必要があります。 TPM チップの構成方法の詳細については、製造元のドキュメントを参照してください。

2.  MBAM クライアントエージェントをインストールします。

3.  コンピューターをドメインに参加させることをお勧めします。

    -   コンピューターがドメインに参加していない場合は、MBAM キーの回復サービスに回復パスワードは保存されません。 既定では、MBAM は、回復キーが保存されていない限り、暗号化を実行することはできません。

    -   コンピューターが、MBAM サーバーに回復キーが保存される前に回復モードで起動した場合、コンピューターを再イメージする必要があります。 使用できる回復方法はありません。

4.  管理者としてコマンドプロンプトを開き、MBAM サービスを停止して、サービスを [**手動**] または **[オンデマンド**] に設定します。 次に、以下のコマンドを実行します。

    **net stop mbamagent**

    **sc config mbamagent start = demand**

5.  MBAM エージェントのレジストリ設定を設定して、グループポリシーを無視し、TPM を**オペレーティングシステムのみ暗号化**として実行します。これを行うには、regedit を実行し、次に、 **regedit.exe**を実行して、レジストリキーテンプレートを c/the ¥¥¥¥ files ¥¥¥¥ |

6.  Regedit で、HKLM\\SOFTWARE\\Microsoft\\MBAM にアクセスし、次の表に示す設定を構成します。

    レジストリエントリ

    構成設定

    DeploymentTime

    0 = オフ

    1 = 展開時のポリシー設定を使用する (既定)

    UseKeyRecoveryService

    0 = キーエスクローを使わない (この場合、次の2つのレジストリエントリは必要ありません)。

    1 = キー回復システムでキーエスクローを使用する (既定)

    推奨: コンピューターは、キー回復サービスと通信できる必要があります。 続行する前に、コンピューターがサービスと通信できることを確認します。

    KeyRecoveryOptions

    0 = 回復キーのみをアップロードする

    1 = 回復キーとキー回復パッケージ (既定) をアップロードする

    KeyRecoveryServiceEndPoint

    この値は、キーの回復 web サーバーの URL に設定します。

    例: http:// &lt; computer name &gt; /MBAMRecoveryAndHardwareService/CoreService.svc.



~~~
**Note**  
MBAM policy or registry values can be set here to override the previously set values.
~~~



7. MBAM クライアントを展開するときに、MBAM エージェントはシステムを再起動します。 この再起動の準備ができたら、管理者としてコマンドプロンプトで次のコマンドを実行します。

   **net start mbamagent**

8. コンピューターが再起動し、BIOS によって TPM の変更を許可するかどうかを確認するメッセージが表示されたら、変更を承諾します。

9. Windows クライアントオペレーティングシステムのイメージングプロセスで、暗号化を開始する準備ができたら、MBAM エージェントサービスを再起動します。 [開始] を [**自動**] に設定するには、管理者としてコマンドプロンプトを開き、次のコマンドを実行します。

   **sc config mbamagent start = auto**

   **net start mbamagent**

10. バイパスレジストリ値を削除します。 これを行うには、regedit を実行し、HKLM\\SOFTWARE\\Microsoft レジストリエントリを参照して、 **Mbam**ノードを右クリックし、[**削除**] をクリックします。

## 関連トピック


[MBAM 1.0 クライアントの展開](deploying-the-mbam-10-client.md)









