---
title: Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法
description: Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法
author: dansimp
ms.assetid: 7609ad7a-bb06-47be-b186-0a2db787c8a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 4b2cbf333c705088d0a068521fb65e99551bb1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826227"
---
# Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法


このトピックでは、Windows イメージングおよび展開プロセスの一部として MBAM を使用して、エンドユーザーのコンピューターで BitLocker を有効にする方法について説明します。 ドライブのロックを解除できないことを示す、(インストールフェーズが終了した後に) 黒い画面が表示される場合は、「windows[と構成マネージャーのセットアップ後、windows 10 バージョン1511で BitLocker を事前に使用](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)する」を参照してください。

**前提条件:**

-   既存の Windows イメージ展開プロセス-Microsoft 展開ツールキット (MDT)、Microsoft System Center Configuration Manager、またはその他のイメージングツールまたはプロセスが存在している必要があります。

-   TPM が BIOS で有効になっており、OS に対して表示されている必要がある

-   MBAM サーバーインフラストラクチャが配置され、アクセス可能である必要がある

-   BitLocker で必要なシステムパーティションを作成する必要がある

-   MBAM が完全に BitLocker を有効にするには、イメージング中にコンピューターがドメインに参加している必要があります。

**Windows 展開の一部として MBAM 2.5 SP1 を使用して BitLocker を有効にするには**

1. MBAM 2.5 SP1 では、Windows の展開中に BitLocker を有効にするための推奨される方法は、PowerShell スクリプトを使用することです `Invoke-MbamClientDeployment.ps1` 。

   -   この `Invoke-MbamClientDeployment.ps1` スクリプトは、イメージングプロセス中に BitLocker を enacts します。 BitLocker ポリシーによって要求された場合、MBAM agent は、ドメインユーザーがイメージング後に最初にログオンしたときに、ドメインユーザーが PIN またはパスワードを作成するように直ちに確認します。

   -   MDT、System Center Configuration Manager、または単体のイメージングプロセスで使いやすくなりました。

   -   PowerShell 2.0 以上と互換性がある

   -   TPM キーの保護機能を使用して OS ボリュームを暗号化する

   -   BitLocker 事前プロビジョニングの完全なサポート

   -   必要に応じて FDDs を暗号化する

   -   Windows 7 用のエスクロー TPM OwnerAuth、MBAM は、エスクローの TPM を所有している必要があります。
   Windows 8.1、Windows 10 RTM、Windows 10 バージョン1511では、TPM OwnerAuth のエスクローがサポートされています。
   Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。 Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。 詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)を参照してください。

   -   エスクローの回復キーと回復キーパッケージ

   -   暗号化の状態を直ちに報告する

   -   新しい WMI プロバイダー

   -   詳細なログ記録

   -   堅牢なエラー処理

   `Invoke-MbamClientDeployment.ps1` [Microsoft.com ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=54439)からスクリプトをダウンロードできます。 これは、展開システムで呼び出され、MBAM サーバーで BitLocker ドライブの暗号化を構成し、回復キーを記録するための主要なスクリプトです。

   **MBAM の WMI 展開方法:** 以下の WMI メソッドは、MBAM 2.5 SP1 で追加され、PowerShell スクリプトを使用した BitLocker の有効化をサポートしてい `Invoke-MbamClientDeployment.ps1` ます。

   <a href="" id="mbam-machine-wmi-class"></a>**Mbam \ _MACHINE WMI クラス** 
   **PrepareTpmAndEscrowOwnerAuth:** MBAM 回復サービスを使用して、TPM OwnerAuth を読み取り、MBAM 回復データベースに送信します。 TPM が所有されておらず、自動プロビジョニングがオンになっていない場合は、TPM OwnerAuth を生成し、所有権を取得します。 失敗した場合は、トラブルシューティングのためにエラーコードが返されます。

   **注**Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。 Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。 詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)を参照してください。

| パラメーター | 説明 |
| -------- | ----------- |
| RecoveryServiceEndPoint | MBAM 回復サービスのエンドポイントを指定する文字列。 |

一般的なエラーメッセージの一覧を次に示します。

| 一般的な戻り値 | エラー メッセージ |
| -------------------- | ------------- |
|  **S_OK**<br />0 (0x0) | メソッドが正常に処理されました。 |
| **MBAM_E_TPM_NOT_PRESENT**<br />2147746304 (0x80040200) | TPM がコンピューターに存在しないか、BIOS 構成で無効になっています。 |
| **MBAM_E_TPM_INCORRECT_STATE**<br />2147746305 (0x80040201) | TPM が正しい状態ではありません (有効、アクティブ化、所有者インストールが許可されています)。 |
| **MBAM_E_TPM_AUTO_PROVISIONING_PENDING**<br />2147746306 (0x80040202) | 自動プロビジョニングが保留になっているため、MBAM は TPM の所有権を取得できません。 自動プロビジョニングが完了したら、もう一度やり直してください。 |
| **MBAM_E_TPM_OWNERAUTH_READFAIL**<br />2147746307 (0x80040203) | MBAM は、TPM 所有者認証の値を読み取ることができません。 この値は、エスクローが正常に完了した後に削除された可能性があります。 Windows 7 では、TPM が他のユーザーによって所有されている場合、MBAM は値を読み取ることができません。 |
| **MBAM_E_REBOOT_REQUIRED**<br />2147746308 (0x80040204) | TPM を適切な状態に設定するには、コンピューターを再起動する必要があります。 場合によっては、手動でコンピューターを再起動する必要があります。 |
| **MBAM_E_SHUTDOWN_REQUIRED**<br />2147746309 (0x80040205) | TPM を適切な状態に設定するには、コンピューターをシャットダウンして再び有効にする必要があります。 場合によっては、手動でコンピューターを再起動する必要があります。 |
| **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005) | リモートエンドポイントによってアクセスが拒否されました。 |
| **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D) | リモートエンドポイントが存在しないか、見つかりませんでした。 |
| * * WS_E_ENDPOINT_FAILURE<br />2151481357 (0x803D000F) | リモートエンドポイントが要求を処理できませんでした。 |
| **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010) | リモートエンドポイントにアクセスできませんでした。 |
| **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013) | リモートエンドポイントからエラーを含むメッセージを受信しました。 適切なサービスエンドポイントに接続していることを確認します。 |
| **WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020) | エンドポイントアドレス URL が有効ではありません。 URL は "http" または "https" で始める必要があります。 |

   **レポートの状態:** MBAM ステータスレポートサービスを使用して、ボリュームのコンプライアンスステータスを読み取り、MBAM コンプライアンスステータスデータベースに送信します。 状態には、暗号強度、プロテクターの種類、プロテクターの状態、暗号化状態が含まれます。 失敗した場合は、トラブルシューティングのためにエラーコードが返されます。

   | パラメーター | 説明 |
   | --------- | ----------- |
   | ReportingServiceEndPoint | MBAM ステータスレポートサービスのエンドポイントを指定する文字列。 |

   一般的なエラーメッセージの一覧を次に示します。

   | 一般的な戻り値 | エラー メッセージ |
   | -------------------- | ------------- |
   | **S_OK**<br /> 0 (0x0) | メソッドが成功しました |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005) | リモートエンドポイントによってアクセスが拒否されました。|
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D) | リモートエンドポイントが存在しないか、見つかりませんでした。 |
   | **WS_E_ENDPOINT_FAILURE**<br /> 2151481357 (0x803D000F) | リモートエンドポイントが要求を処理できませんでした。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010) | リモートエンドポイントにアクセスできませんでした。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013) | リモートエンドポイントからエラーを含むメッセージを受信しました。 適切なサービスエンドポイントに接続していることを確認します。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020) | エンドポイントアドレス URL が有効ではありません。 URL は "http" または "https" で始める必要があります。 |

   <a href="" id="mbam-volume-wmi-class"></a>**Mbam \ _VOLUME WMI Class** **EscrowRecoveryKey:** ボリュームの回復数値パスワードとキーパッケージを読み取り、mbam 回復サービスを使用して、それらを mbam 回復データベースに送信します。 失敗した場合は、トラブルシューティングのためにエラーコードが返されます。

   | パラメーター | 説明 |
   | --------- | ----------- |
   | RecoveryServiceEndPoint | MBAM 回復サービスのエンドポイントを指定する文字列。 |

   一般的なエラーメッセージの一覧を次に示します。

   | 一般的な戻り値 | エラー メッセージ |
   | -------------------- | ------------- |
   | **S_OK**<br />0 (0x0) | メソッドが成功しました |
   | **FVE_E_LOCKED_VOLUME**<br />2150694912 (0x80310000) | ボリュームがロックされています。 |
   | **FVE_E_PROTECTOR_NOT_FOUND**<br />2150694963 (0x80310033) | ボリュームの数値パスワード保護機能が見つかりませんでした。 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005) | リモートエンドポイントによってアクセスが拒否されました。 |
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D) | リモートエンドポイントが存在しないか、見つかりませんでした。 |
   | **WS_E_ENDPOINT_FAILURE**<br />2151481357 (0x803D000F) | リモートエンドポイントが要求を処理できませんでした。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010) | リモートエンドポイントにアクセスできませんでした。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013) | リモートエンドポイントからエラーを含むメッセージを受信しました。 適切なサービスエンドポイントに接続していることを確認します。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020) | エンドポイントアドレス URL が有効ではありません。 URL は "http" または "https" で始める必要があります。 |
     

2. **Microsoft 展開ツールキット (MDT) と PowerShell を使用して MBAM を展開する**

   1.  MDT で、新しい展開共有を作成するか、既存の展開共有を開きます。

       **注**  
       `Invoke-MbamClientDeployment.ps1`PowerShell スクリプトは、任意のイメージングプロセスまたはツールで使うことができます。 このセクションでは、MDT を使用してこれを統合する方法について説明します。手順は、他のプロセスやツールとの統合に似ています。

       **注意**  
       BitLocker の事前プロビジョニング (WinPE) を使用していて、TPM 所有者認証値を維持する場合は、 `SaveWinPETpmOwnerAuth.wsf` インストールが完全なオペレーティングシステムに再起動される直前に、WinPE にスクリプトを追加する必要があります。 **このスクリプトを使っていない場合は、再起動時に TPM 所有者認証値が失われます。**

   2.  展開 `Invoke-MbamClientDeployment.ps1` する** &lt; &gt; \\ スクリプトを共有**します。 事前プロビジョニングを使用している場合は、 `SaveWinPETpmOwnerAuth.wsf` ファイルを** &lt; deploymentshare &gt; ¥¥のスクリプト**にコピーします。

   3.  MBAM 2.5 SP1 クライアントアプリケーションを展開共有のアプリケーションノードに追加します。

       1.  [**アプリケーション**] ノードで [**新しいアプリケーション**] をクリックします。

       2.  [**ソースファイルを含むアプリケーション**] を選択します。 **[次へ]** をクリックします。

       3.  [**アプリケーション名**] に「mbam 2.5 SP1 クライアント」と入力します。 **[次へ]** をクリックします。

       4.  が保存されているディレクトリに移動 `MBAMClientSetup-<Version>.msi` します。 **[次へ]** をクリックします。

       5.  作成するディレクトリとして「MBAM 2.5 SP1 クライアント」と入力します。 **[次へ]** をクリックします。

       6.  コマンドラインで Enter キーを押す `msiexec /i MBAMClientSetup-<Version>.msi /quiet` 。 **[次へ]** をクリックします。

       7.  残りの既定値をそのまま使用して、アプリケーションの新規作成ウィザードを完了します。

   4.  MDT で、展開共有の名前を右クリックし、[**プロパティ**] をクリックします。 [**ルール**] タブをクリックします。次の行を追加します。

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       [OK] をクリックしてウィンドウを閉じます。

   5.  [タスクシーケンス] ノードで、Windows 展開に使用する既存のタスクシーケンスを編集します。 必要に応じて、新しいタスクシーケンスを作成するには、[**タスクシーケンス**] ノードを右クリックし、[**新しいタスクシーケンス**] を選択して、ウィザードを完了します。

       選択したタスクシーケンスの [**タスクシーケンス**] タブで、次の手順を実行します。

       1.  [**プレインストール**] フォルダーの下で、bitlocker を有効にする (使用されているスペースのみを暗号化する) 場合は、[ **Bitlocker を有効にする (オフライン)** ] オプションを有効にします。

       2.  事前プロビジョニングを使用して TPM OwnerAuth を保持し、MBAM が後でエスクローできるようにするには、次の操作を行います。

           1.  **オペレーティングシステムのインストール**手順を確認する

           2.  新しい**Run コマンドライン**ステップを追加する

           3.  手順に名前を指定する**TPM OwnerAuth を保持**する

           4.  コマンドラインを注に設定し `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **ます。** windows 10 バージョン1607以降では、WINDOWS のみが TPM の所有権を取得できます。 Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。 詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)を参照してください。

       3.  [**状態の復元**] フォルダーで、[ **BitLocker を有効にする**] タスクを削除します。

       4.  [**カスタムタスク**] の下の [**状態の復元**] フォルダーで、新しい**インストールアプリケーション**タスクを作成し、「 **mbam Agent をインストール**する」という名前を指定します。 [**単一のアプリケーションをインストール**する] ラジオボタンをクリックし、前に作成した mbam 2.5 SP1 クライアントアプリケーションを参照します。

       5.  [**カスタムタスク**] の下の [**状態の復元**] フォルダーで、次の設定を使用して (Mbam 2.5 SP1 クライアントアプリケーションの実行後に) 新しい**PowerShell スクリプト**タスクを作成します (お使いの環境に応じてパラメーターを更新します)。

           -   名前: MBAM の BitLocker を構成する

           -   PowerShell スクリプト: `Invoke-MbamClientDeployment.ps1`

           -   引き

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p>-RecoveryServiceEndpoint</p></td>
               <td align="left"><p>必須かどうか</p></td>
               <td align="left"><p>MBAM 回復サービスのエンドポイント</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-StatusReportingServiceEndpoint</p></td>
               <td align="left"><p>省略可能。</p></td>
               <td align="left"><p>MBAM ステータスレポートサービスのエンドポイント</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-EncryptionMethod</p></td>
               <td align="left"><p>省略可能。</p></td>
               <td align="left"><p>暗号化方法 (既定: AES 128)</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-EncryptAndEscrowDataVolume</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>データボリュームとエスクローデータボリューム回復キーを暗号化するように指定する</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-WaitForEncryptionToComplete</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>暗号化が完了するまで待機することを指定します。</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-DoNotResumeSuspendedEncryption</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>展開スクリプトが中断された暗号化を再開しないように指定する</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreEscrowOwnerAuthFailure</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>TPM 所有者の認証エスクローエラーを無視するように指定します。 これは、MBAM が TPM 所有者認証を読み取ることができないシナリオで使用する必要があります。たとえば、TPM 自動プロビジョニングが有効になっている場合</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-IgnoreEscrowRecoveryKeyFailure</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>ボリューム回復キーのエスクローエラーを無視するように指定する</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreReportStatusFailure</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>状態レポートエラーを無視するように指定する</p></td>
               </tr>
               </tbody>
               </table>

                 

**Windows 展開の一部として MBAM 2.5 またはそれ以前のバージョンを使用して BitLocker を有効にするには**

1.  MBAM クライアントをインストールします。 手順については、「[コマンドラインを使用して MBAM クライアントを展開する方法](how-to-deploy-the-mbam-client-by-using-a-command-line.md)」を参照してください。

2.  コンピューターをドメインに参加させる (推奨)。

    -   コンピューターがドメインに参加していない場合は、MBAM キーの回復サービスに回復パスワードは保存されません。 既定では、MBAM は、回復キーが保存されていない限り、暗号化を実行することはできません。

    -   MBAM サーバーに回復キーが保存される前に、コンピューターが回復モードで起動した場合、回復方法はありません。また、コンピューターを再イメージする必要があります。

3.  管理者としてコマンドプロンプトを開き、MBAM サービスを停止します。

4.  次のコマンドを入力して、サービスを**手動**または**オンデマンド**に設定します。

    **net stop mbamagent**

    **sc config mbamagent start = demand**

5.  MBAM クライアントがグループポリシー設定を無視するようにレジストリ値を設定します。代わりに、[暗号化] を設定して、Windows がそのクライアントコンピューターに展開された時刻を開始します。

    **注意** この手順では、Windows レジストリを変更する方法について説明します。 レジストリエディターを誤って使用すると、Windows の再インストールが必要になる重大な問題が発生する可能性があります。 レジストリエディターの不正使用によって生じた問題を解決することはできません。 レジストリエディターは、各自の責任において使用してください。

    1.  TPM を**オペレーティングシステムのみの暗号化**用に設定して、Regedit.exe を実行してから、レジストリキーテンプレートを、c/c + MDOP ¥でインポートします。

    2.  Regedit.exe で、HKLM\\SOFTWARE\\Microsoft\\MBAM にアクセスし、次の表に示す設定を構成します。

        **注** MBAM に関連するグループポリシー設定またはレジストリ値は、次のように設定できます。 これらの設定は、以前に設定された値を無視します。

        レジストリエントリ構成の設定

        DeploymentTime

        0 = オフ

        1 = 展開時のポリシー設定 (既定) を使用– Windows がクライアントコンピューターに展開されたときに暗号化を有効にするには、この設定を使います。

        UseKeyRecoveryService

        0 = キーエスクローを使用しません (この場合、次の2つのレジストリエントリは必要ありません)。

        1 = キー回復システムでキーエスクローを使用する (既定)

        これは、MBAM が回復キーを保存できるようにするための推奨設定です。 コンピューターは、MBAM キーの回復サービスと通信できる必要があります。 続行する前に、コンピューターがサービスと通信できることを確認します。

        KeyRecoveryOptions

        0 = 回復キーのみをアップロードする

        1 = 回復キーとキー回復パッケージ (既定) をアップロードする

        KeyRecoveryServiceEndPoint

        この値は、キー回復サービスを実行しているサーバーの URL (http:// &lt; コンピューター名/MBAMRecoveryAndHardwareService/CoreService.svc. など) に設定します。 &gt;


6.  Mbam クライアントの展開中に、MBAM クライアントがシステムを再起動します。 この再起動の準備ができたら、管理者としてコマンドプロンプトで次のコマンドを実行します。

    **net start mbamagent**

7.  コンピューターが再起動し、BIOS からプロンプトが表示されたら、TPM の変更を承諾します。

8.  Windows クライアントオペレーティングシステムのイメージングプロセスで、暗号化を開始する準備ができたら、コマンドプロンプトを管理者として開き、次のコマンドを入力して、[開始] を [**自動**] に設定し、Mbam クライアントエージェントを再起動します。

    **sc config mbamagent start = auto**

    **net start mbamagent**

9.  バイパスレジストリ値を削除するには、Regedit.exe を実行し、HKLM\\SOFTWARE\\Microsoft レジストリエントリに移動します。 **Mbam**ノードを右クリックし、[**削除**] をクリックします。

## 関連トピック

[MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)

[MBAM 2.5 クライアントの展開計画](planning-for-mbam-25-client-deployment.md)

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
