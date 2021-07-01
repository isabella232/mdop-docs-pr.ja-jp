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
ms.openlocfilehash: cd4086ca6bb2ea8d253ea3b743f4efe7efbbb6c1
ms.sourcegitcommit: 325c4b77f9a9df0f3de268457fed06184623bb94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "11626184"
---
# <a name="how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deployment"></a>Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法

> [!IMPORTANT]
> これらの手順は、Configuration Manager BitLocker 管理には関係ではありません。 `Invoke-MbamClientDeployment.ps1`PowerShell スクリプトは、Configuration Manager の BitLocker 管理ではサポートされていません。 これには、Configuration Manager タスク シーケンス中の BitLocker 回復キーのエスクローが含まれます。 さらに、Configuration Manager Current Branch 2103 から、Configuration Manager BitLocker Management は MBAM キー回復サービス サイトを使用してキーをエスクローしなくなりました。 Configuration Manager Current Branch 2103 以降で PowerShell スクリプトを使用しようとすると、Configuration Manager サイトで重大な問題 `Invoke-MbamClientDeployment.ps1` が発生する可能性があります。 既知の問題には、ポリシーストームを引き起こす可能性のあるすべてのデバイスを対象とした大量のポリシーの作成が含まれます。 これにより、Configuration Manager のパフォーマンスが大幅に低下し、主に管理ポイントSQLパフォーマンスが低下します。

このトピックでは、エンド ユーザーのコンピューターで BIT Windows Locker を有効にする方法について説明します。 ドライブのロックを解除できないことを示す黒い画面が再起動時 (インストール フェーズが終了した後) が表示される場合は、「Windows 10 バージョン[1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)でプレプロビジョニング BitLocker を使用する場合は、以前の Windows バージョンが "セットアップ Windows と Configuration Manager" の手順の後で開始しない」を参照してください。

**前提条件:**

-   既存のイメージWindows展開プロセス (Microsoft Deployment Toolkit (MDT)、Microsoft System Center Configuration Manager、その他のイメージング ツールまたはプロセス) を配置する必要があります。

-   TPM は BIOS で有効にし、OS から表示する必要があります。

-   MBAM サーバー インフラストラクチャが配置され、アクセス可能である必要があります

-   BitLocker で必要なシステム パーティションを作成する必要があります

-   MBAM が BitLocker を完全に有効にする前に、コンピューターがイメージング中にドメインに参加している必要があります

**MBAM 2.5 SP1 を使用して BitLocker を展開の一部としてWindowsするには**

1. MBAM 2.5 SP1 では、PowerShell スクリプトを使用して、Windows展開中に BitLocker を有効にするための推奨される方法 `Invoke-MbamClientDeployment.ps1` です。

   -   スクリプト `Invoke-MbamClientDeployment.ps1` は、イメージング プロセス中に BitLocker を実行します。 BitLocker ポリシーで要求された場合、MBAM エージェントは、イメージング後にドメイン ユーザーが最初にログオンするときに、すぐにドメイン ユーザーに PIN またはパスワードの作成を求めるメッセージを表示します。

   -   MDT、System Center Configuration Managerスタンドアロンイメージングプロセスで使いやすい

   -   PowerShell 2.0 以上と互換性がある

   -   TPM キー プロテクタを使用して OS ボリュームを暗号化する

   -   BitLocker の事前プロビジョニングを完全にサポート

   -   必要に応じて FDD を暗号化する

   -   Escrow TPM OwnerAuth Windows 7 の場合、MBAM はエスクローが発生するために TPM を所有している必要があります。
   RT Windows 10 M Windows 8.1バージョン 1511 Windows 10バージョン 1511 では、TPM OwnerAuth のエスクローがサポートされています。
   バージョン Windows 10 1607 以降の場合、TPM のWindowsを取得できるのはユーザーのみです。 addiiton では、Windowsプロビジョニング時に TPM 所有者パスワードが保持されない場合があります。 詳細については [、「TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 」を参照してください。

   -   Escrow 回復キーと回復キー パッケージ

   -   暗号化の状態を直ちに報告する

   -   新しい WMI プロバイダー

   -   詳細なログ

   -   堅牢なエラー処理

   スクリプトは、ダウンロード `Invoke-MbamClientDeployment.ps1` センターから [Microsoft.com ダウンロードできます](https://www.microsoft.com/download/details.aspx?id=54439)。 これは、展開システムが BitLocker ドライブの暗号化を構成し、MBAM Server で回復キーを記録するために呼び出す主なスクリプトです。

   **MBAM の WMI 展開方法:** PowerShell スクリプトを使用して BitLocker を有効にするための次の WMI メソッドが MBAM 2.5 SP1 `Invoke-MbamClientDeployment.ps1` に追加されました。

   <a href="" id="mbam-machine-wmi-class"></a>**MBAM\_Machine WMI クラス** 
   **PrepareTpmAndEscrowOwnerAuth:** TPM OwnerAuth を読み取り、MBAM 回復サービスを使用して MBAM 回復データベースに送信します。 TPM が所有されていない場合、自動プロビジョニングがオンではない場合は、TPM OwnerAuth が生成され、所有権が取得されます。 エラーが発生した場合は、トラブルシューティングのためにエラー コードが返されます。

   **メモ**バージョン Windows 10 1607 以降の場合、TPM のWindowsを取得できるのはユーザーのみです。 addiiton では、Windowsプロビジョニング時に TPM 所有者パスワードが保持されない場合があります。 詳細については [、「TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 」を参照してください。

| パラメーター | 説明 |
| -------- | ----------- |
| RecoveryServiceEndPoint | MBAM 回復サービス エンドポイントを指定する文字列。 |

一般的なエラー メッセージの一覧を次に示します。

| 一般的な戻り値 | エラー メッセージ |
| -------------------- | ------------- |
|  **S_OK**<br />0 (0x0) | メソッドが成功しました。 |
| **MBAM_E_TPM_NOT_PRESENT**<br />2147746304 (0x80040200) | TPM がコンピューターに存在しないか、BIOS 構成で無効になっています。 |
| **MBAM_E_TPM_INCORRECT_STATE**<br />2147746305 (0x80040201) | TPM が正しい状態ではありません (有効、アクティブ化、所有者のインストールが許可されます)。 |
| **MBAM_E_TPM_AUTO_PROVISIONING_PENDING**<br />2147746306 (0x80040202) | 自動プロビジョニングが保留中のため、MBAM は TPM の所有権を取得できません。 自動プロビジョニングが完了したら、もう一度やり直してください。 |
| **MBAM_E_TPM_OWNERAUTH_READFAIL**<br />2147746307 (0x80040203) | MBAM は TPM 所有者の承認値を読み取りできません。 値は、エスクローが成功した後に削除された可能性があります。 7 Windows、TPM が他のユーザーによって所有されている場合、MBAM は値を読み取りできません。 |
| **MBAM_E_REBOOT_REQUIRED**<br />2147746308 (0x80040204) | TPM を正しい状態に設定するには、コンピューターを再起動する必要があります。 コンピューターを手動で再起動する必要がある場合があります。 |
| **MBAM_E_SHUTDOWN_REQUIRED**<br />2147746309 (0x80040205) | TPM を正しい状態に設定するには、コンピューターをシャットダウンしてオンに戻す必要があります。 コンピューターを手動で再起動する必要がある場合があります。 |
| **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005) | リモート エンドポイントによってアクセスが拒否されました。 |
| **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D) | リモート エンドポイントが存在しないか、見つからなかった。 |
| **WS_E_ENDPOINT_FAILURE<br />2151481357 (0x803D000F) | リモート エンドポイントは要求を処理できません。 |
| **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010) | リモート エンドポイントに到達できません。 |
| **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013) | リモート エンドポイントから障害を含むメッセージが受信された。 正しいサービス エンドポイントに接続していることを確認します。 |
| **WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020) | エンドポイント アドレス URL が無効です。 URL は "http" または "https" で始まる必要があります。 |

   **ReportStatus:** MBAM 状態レポート サービスを使用して、ボリュームのコンプライアンス状態を読み取り、MBAM コンプライアンス状態データベースに送信します。 この状態には、暗号強度、プロテクタの種類、プロテクタの状態、暗号化状態が含まれます。 エラーが発生した場合は、トラブルシューティングのためにエラー コードが返されます。

   | パラメーター | 説明 |
   | --------- | ----------- |
   | ReportingServiceEndPoint | MBAM 状態レポート サービス エンドポイントを指定する文字列。 |

   一般的なエラー メッセージの一覧を次に示します。

   | 一般的な戻り値 | エラー メッセージ |
   | -------------------- | ------------- |
   | **S_OK**<br /> 0 (0x0) | メソッドが成功しました |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005) | リモート エンドポイントによってアクセスが拒否されました。|
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D) | リモート エンドポイントが存在しないか、見つからなかった。 |
   | **WS_E_ENDPOINT_FAILURE**<br /> 2151481357 (0x803D000F) | リモート エンドポイントは要求を処理できません。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010) | リモート エンドポイントに到達できません。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013) | リモート エンドポイントから障害を含むメッセージが受信された。 正しいサービス エンドポイントに接続していることを確認します。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020) | エンドポイント アドレス URL が無効です。 URL は "http" または "https" で始まる必要があります。 |

   <a href="" id="mbam-volume-wmi-class"></a>**MBAM\_Volume WMI クラス** **EscrowRecoveryKey:** ボリュームの回復数値パスワードとキー パッケージを読み取り、MBAM 回復サービスを使用して MBAM 回復データベースに送信します。 エラーが発生した場合は、トラブルシューティングのためにエラー コードが返されます。

   | パラメーター | 説明 |
   | --------- | ----------- |
   | RecoveryServiceEndPoint | MBAM 回復サービス エンドポイントを指定する文字列。 |

   一般的なエラー メッセージの一覧を次に示します。

   | 一般的な戻り値 | エラー メッセージ |
   | -------------------- | ------------- |
   | **S_OK**<br />0 (0x0) | メソッドが成功しました |
   | **FVE_E_LOCKED_VOLUME**<br />2150694912 (0x80310000) | ボリュームがロックされています。 |
   | **FVE_E_PROTECTOR_NOT_FOUND**<br />2150694963 (0x80310033) | ボリュームの数値パスワード プロテクタが見つかりませんでした。 |
   | **WS_E_ENDPOINT_ACCESS_DENIED**<br />2151481349 (0x803D0005) | リモート エンドポイントによってアクセスが拒否されました。 |
   | **WS_E_ENDPOINT_NOT_FOUND**<br />2151481357 (0x803D000D) | リモート エンドポイントが存在しないか、見つからなかった。 |
   | **WS_E_ENDPOINT_FAILURE**<br />2151481357 (0x803D000F) | リモート エンドポイントは要求を処理できません。 |
   | **WS_E_ENDPOINT_UNREACHABLE**<br />2151481360 (0x803D0010) | リモート エンドポイントに到達できません。 |
   | **WS_E_ENDPOINT_FAULT_RECEIVED**<br />2151481363 (0x803D0013) | リモート エンドポイントから障害を含むメッセージが受信された。 正しいサービス エンドポイントに接続していることを確認します。 |
   | **WS_E_INVALID_ENDPOINT_URL**<br />2151481376 (0x803D0020) | エンドポイント アドレス URL が無効です。 URL は "http" または "https" で始まる必要があります。 |
     

2. **Microsoft Deployment Toolkit (MDT) と PowerShell を使用して MBAM を展開する**

   1.  MDT で、新しい展開共有を作成するか、既存の展開共有を開きます。

       **備考**  
       `Invoke-MbamClientDeployment.ps1`PowerShell スクリプトは、任意のイメージング プロセスまたはツールで使用できます。 このセクションでは、MDT を使用して統合する方法を示しますが、手順は他のプロセスやツールとの統合に似ています。

       **注意**  
       BitLocker プレプロビジョニング (WinPE) を使用し、TPM 所有者の承認値を維持する場合は、インストールが完全なオペレーティング システムに再起動される直前に WinPE でスクリプトを追加する必要があります。 `SaveWinPETpmOwnerAuth.wsf` **このスクリプトを使用しない場合、再起動時に TPM 所有者の承認値が失われる可能性があります。**

   2.  `Invoke-MbamClientDeployment.ps1` ** &lt; DeploymentShare &gt; \\Scripts にコピーします**。 事前プロビジョニングを使用している場合は、ファイルを `SaveWinPETpmOwnerAuth.wsf` ** &lt; DeploymentShare &gt; \\Scripts にコピーします**。

   3.  展開共有の [アプリケーション] ノードに MBAM 2.5 SP1 クライアント アプリケーションを追加します。

       1.  [アプリケーション] **ノードで、[** 新しいアプリケーション] **をクリックします**。

       2.  [ソース **ファイルを含むアプリケーション] を選択します**。 **[次へ]** をクリックします。

       3.  [ **アプリケーション名]** に「MBAM 2.5 SP1 クライアント」と入力します。 **[次へ]** をクリックします。

       4.  を含むディレクトリを参照します `MBAMClientSetup-<Version>.msi` 。 **[次へ]** をクリックします。

       5.  作成するディレクトリに「MBAM 2.5 SP1 Client」と入力します。 **[次へ]** をクリックします。

       6.  コマンド `msiexec /i MBAMClientSetup-<Version>.msi /quiet` ラインで入力します。 **[次へ]** をクリックします。

       7.  残りの既定値を受け入れて、新しいアプリケーション ウィザードを完了します。

   4.  MDT で、展開共有の名前を右クリックし、[プロパティ] を **クリックします**。 [ルール] **タブをクリック** します。次の行を追加します。

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       [OK] をクリックしてウィンドウを閉じます。

   5.  [タスク シーケンス] ノードで、展開に使用する既存のタスク Windowsします。 必要な場合は、[タスク シーケンス] ノードを右クリックし、[新**** しいタスク シーケンス] を**** 選択し、ウィザードを完了することで、新しいタスク シーケンスを作成できます。

       選択した **タスク シーケンスの** [タスク シーケンス] タブで、次の手順を実行します。

       1.  WinPE **で BitLocker** を有効にする場合は、[プレインストール] フォルダーでオプションのタスク [BitLocker を有効 **にする (オフライン)** を有効にします。これは、使用済み領域のみを暗号化します。

       2.  事前プロビジョニングを使用するときに TPM OwnerAuth を保持し、MBAM が後でエスケープできるようにするには、次の手順を実行します。

           1.  [オペレーティング システム **のインストール] 手順を見** つける

           2.  その後に新 **しいコマンド ラインの実行** 手順を追加する

           3.  ステップに名前を **付け、TPM OwnerAuth を保持する**

           4.  コマンド ラインを `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **[メモ]** に設定します。Windows 10バージョン 1607 以降の場合、TPM のWindowsを取得できるのはユーザーのみです。 addiiton では、Windowsプロビジョニング時に TPM 所有者パスワードが保持されない場合があります。 詳細については [、「TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 」を参照してください。

       3.  [状態の **復元] フォルダー** で **、[BitLocker の有効化] タスクを削除** します。

       4.  [カスタム タスク **] の [状態の** 復元] **フォルダー**で、新しい **[** アプリケーションのインストール] タスクを作成し、[MBAM エージェントのインストール **] という名前を付きます**。 [単 **一アプリケーションのインストール]** ラジオ ボタンをクリックし、前に作成した MBAM 2.5 SP1 クライアント アプリケーションを参照します。

       5.  [カスタム**タスク]** **** の [状態の復元] フォルダーで、次の設定を使用して新しい**PowerShell**スクリプト実行タスク (MBAM 2.5 SP1 クライアント アプリケーション ステップの後) を作成します (環境に応じてパラメーターを更新します)。

           -   名前: MBAM 用に BitLocker を構成する

           -   PowerShell スクリプト: `Invoke-MbamClientDeployment.ps1`

           -   パラメーター:

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
               <td align="left"><p>MBAM 回復サービス エンドポイント</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-StatusReportingServiceEndpoint</p></td>
               <td align="left"><p>省略可能。</p></td>
               <td align="left"><p>MBAM 状態レポート サービス エンドポイント</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-EncryptionMethod</p></td>
               <td align="left"><p>省略可能。</p></td>
               <td align="left"><p>暗号化方法 (既定: AES 128)</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-EncryptAndEscrowDataVolume</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>データ ボリュームとエスクロー データ ボリュームの回復キーを暗号化する場合に指定する</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-WaitForEncryptionToComplete</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>暗号化が完了するのを待つ場合に指定する</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-DoNotResumeSuspendedEncryption</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>展開スクリプトが一時停止された暗号化を再開しない</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreEscrowOwnerAuthFailure</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>TPM 所有者認証のエスクローエラーを無視するように指定します。 これは、TPM の自動プロビジョニングが有効になっている場合など、MBAM が TPM 所有者認証を読み取れないシナリオで使用する必要があります。</p></td>
               </tr>
               <tr class="even">
               <td align="left"><p>-IgnoreEscrowRecoveryKeyFailure</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>ボリューム回復キーのエスクローエラーを無視するように指定する</p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p>-IgnoreReportStatusFailure</p></td>
               <td align="left"><p>スイッチ</p></td>
               <td align="left"><p>状態報告の失敗を無視するように指定する</p></td>
               </tr>
               </tbody>
               </table>

                 

**MBAM 2.5 以前を使用して BitLocker を展開の一部としてWindowsするには**

1.  MBAM クライアントをインストールします。 手順については、「コマンド ライン [を使用して MBAM クライアントを展開する方法」を参照してください](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。

2.  コンピューターをドメインに参加します (推奨)。

    -   コンピューターがドメインに参加していない場合、回復パスワードは MBAM キー回復サービスに保存されません。 既定では、MBAM では、回復キーを格納できない限り、暗号化は許可されません。

    -   回復キーが MBAM Server に保存される前にコンピューターが回復モードで開始した場合、回復方法は使用できません。コンピューターを再イメージ化する必要があります。

3.  管理者としてコマンド プロンプトを開き、MBAM サービスを停止します。

4.  次のコマンドを入力**して、サービス****を手動**またはオンデマンドに設定します。

    **net stop mbamagent**

    **sc config mbamagent start= demand**

5.  MBAM クライアントがグループ ポリシー設定を無視し、代わりに暗号化を設定して、Windows がクライアント コンピューターに展開される時刻を開始するようにレジストリ値を設定します。

    **注意**  
    この手順では、レジストリを変更する方法Windows説明します。 レジストリ エディターを誤って使用すると、重大な問題が発生し、レジストリ エディターを再インストールする必要Windows。 レジストリ エディターの誤った使用に起因する問題を解決できる保証はありません。 レジストリ エディターは、ご自身のリスクで使用してください。

    1.  TPM for **オペレーティング**システムのみの暗号化を設定し、Regedit.exe を実行し、レジストリ キー テンプレートを C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg からインポートします。

    2.  このRegedit.exe HKLM\\SOFTWARE\\Microsoft\\MBAM に移動し、次の表に示す設定を構成します。

        **備考**  
        MBAM に関連するグループ ポリシー設定またはレジストリ値は、ここで設定できます。 これらの設定は、以前に設定した値を上書きします。

        レジストリ エントリ構成の設定

        DeploymentTime

        0 = Off

        1 = 展開時間ポリシー設定を使用する (既定) – この設定を使用して、クライアント コンピューターに展開Windows暗号化を有効にします。

        UseKeyRecoveryService

        0 = キーエスクローを使用しない (この場合、次の 2 つのレジストリ エントリは必要ありません)

        1 = キー回復システムでキーエスクローを使用する (既定)

        これは、MBAM が回復キーを格納できる推奨設定です。 コンピューターが MBAM キー回復サービスと通信できる必要があります。 続行する前に、コンピューターがサービスと通信できると確認します。

        KeyRecoveryOptions

        0 = 回復キーのみをアップロードする

        1 = Uploads Recovery Key and Key Recovery Package (既定値)

        KeyRecoveryServiceEndPoint

        この値は、キー回復サービスを実行しているサーバーの URL (http:// コンピューター名 &lt; &gt; /MBAMRecoveryAndHardwareService/CoreService.svc など) に設定します。


6.  MBAM クライアントは、MBAM クライアントの展開中にシステムを再起動します。 この再起動の準備ができたら、管理者としてコマンド プロンプトで次のコマンドを実行します。

    **net start mbamagent**

7.  コンピューターが再起動し、BIOS からメッセージが表示されたら、TPM の変更を受け入れる。

8.  Windows クライアント オペレーティング システムイメージング プロセス中に、暗号化を開始する準備ができたら、管理者としてコマンド プロンプトを開き、次のコマンドを入力して開始を **[自動**] に設定し、MBAM クライアント エージェントを再起動します。

    **sc config mbamagent start= auto**

    **net start mbamagent**

9.  バイパス レジストリ値を削除するには、Regedit.exeを実行し、HKLM\\SOFTWARE\\Microsoft レジストリ エントリに移動します。 MBAM ノードを **右クリックし、[** 削除] を **クリックします**。

## <a name="related-topics"></a>関連トピック

[MBAM 2.5 クライアントの展開](deploying-the-mbam-25-client.md)

[MBAM 2.5 クライアントの展開計画](planning-for-mbam-25-client-deployment.md)

## <a name="got-a-suggestion-for-mbam"></a>MBAM の提案を受け取った場合
- ここで提案を追加または投票 [します](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。
- MBAM の問題については [、MBAM TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
