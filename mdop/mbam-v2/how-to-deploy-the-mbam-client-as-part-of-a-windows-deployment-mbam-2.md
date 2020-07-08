---
title: Windows 展開の一部として MBAM クライアントを展開する方法
description: Windows 展開の一部として MBAM クライアントを展開する方法
author: dansimp
ms.assetid: 67387de7-8b02-4412-9850-3b8d8e5c18af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d75e5748167d2d4866f98e9d3611584067ecd418
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824624"
---
# Windows 展開の一部として MBAM クライアントを展開する方法


Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。 トラステッドプラットフォームモジュール (TPM) チップが搭載されているコンピューターの場合、イメージングと Windows 展開プロセスの一部としてクライアントコンピューター上の BitLocker 管理と暗号化を有効にすることで、BitLocker クライアントを組織に統合することができます。

**注**  
Microsoft BitLocker 管理およびクライアントシステム要件の監視については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。



Windows 展開の最初のイメージングステージで BitLocker を使用してクライアントコンピューターを暗号化すると、組織に MBAM を実装するために必要な管理オーバーヘッドを軽減することができます。 また、展開されているすべてのコンピューターに、既に BitLocker が実行されており、正しく構成されていることも確認します。

**注**  
このトピックの手順では、Windows レジストリの変更について説明します。 レジストリエディターを誤って使用すると、Windows の再インストールが必要になる深刻な問題が発生する可能性があります。 Microsoft は、レジストリエディターの不正使用によって発生した問題を解決できないことを保証できません。 レジストリエディターは、各自の責任において使用してください。



**Windows 展開の一部としてコンピューターを暗号化するには**

1.  組織で、BitLocker のトラステッドプラットフォームモジュール (TPM) プロテクターまたは TPM + PIN プロテクターオプションの使用を計画している場合は、最初の MBAM の展開前に TPM チップをアクティブ化する必要があります。 TPM チップをアクティブ化すると、プロセスの後の再起動が不要になり、TPM チップが組織の要件に従って適切に構成されていることを確認できます。 コンピューターの BIOS で TPM チップを手動で有効にする必要があります。

    **注**  
    一部のベンダーは、オペレーティングシステム内から BIOS で TPM チップを有効にしてアクティブ化するためのツールを提供しています。 TPM チップの構成方法の詳細については、製造元のドキュメントを参照してください。



2.  Microsoft BitLocker 管理および監視クライアントエージェントをインストールします。

3.  コンピューターをドメインに参加させる (推奨)。

    -   コンピューターがドメインに参加していない場合、回復パスワードは MBAM キーの回復サービスに保存されません。 既定では、MBAM は、回復キーが保存されていない限り、暗号化を実行することはできません。

    -   コンピューターが、MBAM サーバーに回復キーが保存される前に回復モードで起動した場合、コンピューターを再イメージする必要があります。 使用できる回復方法はありません。

4.  管理者としてコマンドプロンプトを実行し、MBAM サービスを停止してから、サービスを**手動**または**オンデマンド**に設定してから、次のコマンドを入力します。

    **net stop mbamagent**

    **sc config mbamagent start = demand**

5.  MBAM エージェントのレジストリ設定を設定して、グループポリシーを無視し、**オペレーティングシステムのみの暗号化**については、 **Regedit**を実行して TPM を実行してから、このレジストリキーテンプレートを、c/c/1/30/30/30/@/一度インポートします。

6.  Regedit で、HKLM\\SOFTWARE\\Microsoft\\MBAM にアクセスし、次の表に記載されている設定を構成します。

    レジストリエントリ

    構成設定

    DeploymentTime

    0 = オフ

    1 = 展開時のポリシー設定を使用する (既定)

    UseKeyRecoveryService

    0 = キーエスクローを使用しません (この場合、次の2つのレジストリエントリは必要ありません)。

    1 = キー回復システムでキーエスクローを使用する (既定)

    推奨: コンピューターは、キー回復サービスと通信できる必要があります。 続行する前に、コンピューターがサービスと通信できることを確認します。

    KeyRecoveryOptions

    0 = 回復キーのみをアップロードする

    1 = 回復キーとキー回復パッケージ (既定) をアップロードする

    KeyRecoveryServiceEndPoint

    この値をキー回復 web サーバーの URL に設定します (たとえば、http:// &lt; computer name &gt; /MBAMRecoveryAndHardwareService/CoreService.svc.)。



~~~
**Note**  
MBAM policy or registry values can be set here to override previously set values.
~~~



7. MBAM クライアントを展開するときに、MBAM エージェントはシステムを再起動します。 この再起動の準備ができたら、管理者としてコマンドプロンプトで次のコマンドを実行します。

   **net start mbamagent**

8. コンピューターが再起動し、BIOS によって TPM の変更を許可するかどうかを確認するメッセージが表示されたら、変更を承諾します。

9. Windows クライアントオペレーティングシステムのイメージングプロセスでは、暗号化を開始する準備ができたら、MBAM agent サービスを再起動し、管理者としてコマンドプロンプトを実行し、次のコマンドを入力して、[開始] を [**自動**] に設定します。

   **sc config mbamagent start = auto**

   **net start mbamagent**

10. Regedit を実行し、HKLM\\SOFTWARE\\Microsoft レジストリエントリに移動して、バイパスレジストリ値を削除します。 **Mbam**ノードを削除するには、ノードを右クリックし、[**削除**] をクリックします。

## 関連トピック


[MBAM 2.0 クライアントの展開](deploying-the-mbam-20-client-mbam-2.md)









