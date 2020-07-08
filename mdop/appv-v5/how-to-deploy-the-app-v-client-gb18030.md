---
title: APP-V Client を展開する方法
description: APP-V Client を展開する方法
ms.author: dansimp
author: dansimp
ms.assetid: 9c4e67ae-ddaf-4e23-8c16-72d029a74a27
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/05/2018
ms.openlocfilehash: 4e246e13bf59f167eade77200afd866c6a3c41fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814122"
---
# APP-V Client を展開する方法


Microsoft Application Virtualization (App-v) 5.0 クライアントとリモートデスクトップサービスクライアントをインストールするには、次の手順を使用します。 ターゲットコンピューターのオペレーティングシステムと一致するバージョンのクライアントをインストールする必要があります。

<a href="" id="bkmk-clt-install-prereqs"></a>**始める前に行うこと**

1. ソフトウェアの前提条件を確認してインストールします。

   インストールする App-v のバージョンに対応する必須ソフトウェアをインストールします。

   - [App-V 5.0 SP3 について](about-app-v-50-sp3.md)

   - App-v 5.0 SP1 およびアプリ-V 5.0 SP2 –これらのバージョンには新しい前提条件はありません。

   - [App-V 5.0 の前提条件](app-v-50-prerequisites.md)

2. インストールに適用できるように、クライアントの共存とサポートされていないシナリオを確認します。


   |                                               |                                                                                                                            |
   |-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
   |      共存するアプリ-V クライアントを展開する       | [App-V 5.0 Sequencer および Client の展開計画](planning-for-the-app-v-50-sequencer-and-client-deployment.md) |
   | サポートされていない、または限定されたインストールシナリオ |                         [App-V 5.0 でサポートされる構成](app-v-50-supported-configurations.md)                         |

   ---

3. クライアントのレジストリ、ログ、トラブルシューティング情報の場所を確認します。

#### クライアントレジストリ情報
<ul><li>既定では、App-v 5.0 クライアントをインストールした後、クライアント情報は次のレジストリキーのレジストリに格納されます。<p><p><code>HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\APPV\CLIENT</code></li><li>App-v クライアントを実行しているコンピューターに仮想化されたパッケージを展開すると、関連付けられたパッケージデータは次の場所に格納されます。<p><p><code>C:\ProgramData\App-V</code><p><p>ただし、次のレジストリキーを使用して、この場所を再構成することができます。<p><p><code>HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\SOFTWARE\MICROSOFT\APPV\CLIENT\STREAMING\PACKAGEINSTALLATIONROOT</code></li></ul>

#### クライアントログファイル                  
<ul><li>App-v 5.0 クライアントに関連付けられているログファイル情報については、次のログを検索します。<p><p><code>Event logs/Applications and Services Logs/Microsoft/AppV</code></li><li>App-v 5.0 SP3 では、一部のログが統合され、次の場所に移動されています。<p><p><code>Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog</code><p><p>移動したログの一覧については、「 [app-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-event-logs-moved)て」を参照してください。</li><li>App-v 5.0 クライアントを実行しているコンピューターに現在保存されているパッケージは、次の場所に保存されます。<p><p><code>C:\ProgramData\App-V\<<em>package id</em>>\<<em>version id</em>></code></li></ul>

#### クライアントのインストールのトラブルシューティング情報
- **% Temp%** フォルダーのエラーログを参照してください。 
- ログファイルを確認するには、[**スタート**] をクリックし、「 **% temp%**」と入力して、 **appv_ ログ**を探します。 

## App-v 5.0 クライアントをインストールするには

1. アプリがインストールされているコンピューターに、App-v 5.0 クライアントインストールファイルをコピーします。<p><p>次のクライアントの種類から選びます。


   |                  クライアントの種類                  |          使用するファイル          |
   |-----------------------------------------------|-------------------------------|
   |        クライアントの標準バージョン         |   **appv_client_setup.exe**   |
   | クライアントのリモートデスクトップサービスバージョン | **appv_client_setup_rds.exe** |

   ---

2. インストールファイルをダブルクリックし、[**インストール**] をクリックします。 インストールが開始される前に、インストーラーは、不足している[アプリ– V 5.0 の前提条件](app-v-50-prerequisites.md)をコンピューターで確認します。

3. ソフトウェアライセンス条項を確認して同意し、Microsoft Update を使用するかどうか、Microsoft カスタマーエクスペリエンス向上プログラムに参加するかどうかを選択して、[**インストール**] をクリックします。

4. [**セットアップが正常に完了しました**] ページで、[**閉じる**] をクリックします。

   インストールにより、**プログラム**で次のような app-v クライアントのエントリが作成されます。

   -   **.exe**

   -   **.msi**

   -   **言語パック**

   >[!NOTE]
   >インストール後、.exe ファイルのみをアンインストールできます。


## スクリプトを使用して App-v 5.0 クライアントをインストールするには

1. 必要なすべての必須ソフトウェアをターゲットコンピューターにインストールします。 [開始する前に実行する操作を](#bkmk-clt-install-prereqs)参照してください。 .Msi ファイルを使用してクライアントをインストールした場合、前提条件が見つからないと、インストールが失敗します。

2. スクリプトを使用して App-v 5.0 クライアントをインストールするには、 **appv\_client\_setup.exe**で次のパラメーターを使用します。

   >[!NOTE]
   >クライアントの Windows インストーラー (.msi) では、 **/log**パラメーターを除き、同じスイッチセットがサポートされています。

   |                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           /INSTALLDIR            |                                                                                                                                                               インストールディレクトリを指定します。 使用例:<p><p>**/INSTALLDIR = C:\Program Files\AppV Client**                                                                                                                                                                |
   |            /CEIPOPTIN            |                                                                                                                                                          カスタマーエクスペリエンス向上プログラムへの参加を可能にします。 使用例:<p><p>**/CEIPOPTIN = [0 \ | 1 \]**                                                                                                                                                           |
   |             /Muoptin             |                                                                                                                                                                                 Microsoft Update を有効にします。 使用例:<p><p>**/MUOPTIN = [0 \ | 1 \]**                                                                                                                                                                                  |
   |     /Packageinstallationroot     |                                                                                                                                         すべての新しいアプリケーションと更新プログラムをインストールするディレクトリを指定します。 使用例: <p><p>**/Packageinstallationroot = ' C:\ App/ep V パッケージ '**                                                                                                                                         |
   |        /パッケージ ourceroot        |                                                                                                                                                  パッケージコンテンツをダウンロードするためのソースの場所をオーバーライドします。 使用例:<p><p>**/パッケージ ourceroot = ' <http://packageStore> '**                                                                                                                                                  |
   |            /自動ロード             |                                                                                           特定のコンピューター上の App-v 5.0 で新しいパッケージを読み込む方法を指定します。 次のオプションが有効になっています: [1];すべてのパッケージを自動的に読み込む [2];または、パッケージを自動的に読み込まない [0] を選びます。 使用例:<p><p>**/自動ロード = [0 \ | 1 \ | 2 \]**                                                                                           |
   |     /Sharedcontentstoremode      |                                                                                                                                           ストリーミングされたパッケージコンテンツをローカルのハードディスクに保存しないように指定します。 使用例: <p><p>**/SHAREDCONTENTSTOREMODE = [0 \ | 1 \]**                                                                                                                                            |
   |          /MIGRATIONMODE          |                                                                                                                     以前のバージョンで作成されたパッケージに関連付けられているショートカットと FTAs App-v 5.0 クライアントが変更できるようにします。 使用例:<p><p>**/MIGRATIONMODE = [0 \ | 1 \]**                                                                                                                     |
   |      /ENABLEPACKAGESCRIPTS       |                                                                                                                                   パッケージマニフェストファイルまたは実行する構成ファイルで定義されているスクリプトを有効にします。 使用例:<p><p>**/ENABLEPACKAGESCRIPTS = [0 \ | 1 \]**                                                                                                                                   |
   |    /ROAMINGREGISTRYEXCLUSIONS    |                                                                                                                                      ユーザープロファイルでローミングされないレジストリパスを指定します。 使用例:<p><p>**/ROAMINGREGISTRYEXCLUSIONS = ソフトウェア \ クラス; ソフトウェア \ クライアント**                                                                                                                                      |
   |      /ROAMINGFILEEXCLUSIONS      |                                                                                                                                  ユーザーのプロファイルでローミングされない% userprofile% を基準としたファイルパスを指定します。 使用例: <p><p>**/ROAMINGFILEEXCLUSIONS ' desktop; マイピクチャ '**                                                                                                                                   |
   |   /S [1-5] 発行サーバー名    |                                                                                                                                                           発行サーバーの名前が表示されます。 使用例:<p><p>**/S2PUBLISHINGSERVERNAME = MyPublishingServer**                                                                                                                                                            |
   |    /S [1-5] 発行する SERVERURL    |                                                                                                                                                                発行サーバーの URL を表示します。 使用例:<p><p>**/S2PUBLISHINGSERVERURL = \\ pubserver**                                                                                                                                                                |
   |   /S [1-5] GLOBALREFRESHENABLED    |                                                                                                                                                                    グローバル発行の更新を有効にします。 使用例:<p><p>**/S2GLOBALREFRESHENABLED = [0 \ | 1 \]**                                                                                                                                                                     |
   |   /S [1-5] GLOBALREFRESHVALU    |                                                                                                                                                             ユーザーがログオンしたときにグローバル公開の更新を開始します。 使用例:<p><p>**/S2LOGONREFRESH = [0 \ | 1 \]**                                                                                                                                                              |
   |   /S [1-5] GLOBALREFRESHINTERVAL   |                                                                                                                                         公開の更新間隔を指定します。ここで、 **0**は定期的に更新されないことを示します。 使用例: **/S2PERIODICREFRESHINTERVAL = [0-744]**                                                                                                                                         |
   | /S [1-5] GLOBALREFRESHINTERVALUNIT |                                                                                                                                                            間隔の単位 (時間 [0]、日数 [1]) を指定します。 使用例:<p><p>**/S2GLOBALREFRESHINTERVALUNIT = [0 \ | 1 \]**                                                                                                                                                            |
   |    /S [1-5] USERREFRESHENABLED     |                                                                                                                                                                          ユーザー公開の更新を有効にします。 使用例: **/S2USERREFRESHENABLED = [0 \ | 1 \]**                                                                                                                                                                          |
   |    /S [1-5] USERREFRESHONLOGON 詳細     |                                                                                                                                                              ユーザーがログオンしたときにユーザーの公開更新を開始します。 使用例:<p><p>**/S2LOGONREFRESH = [0 \ | 1 \]**                                                                                                                                                               |
   |    /S [1-5] USERREFRESHINTERVAL    |                                                                                                                                         公開の更新間隔を指定します。ここで、 **0**は定期的に更新されないことを示します。 使用例: **/S2PERIODICREFRESHINTERVAL = [0-744]**                                                                                                                                         |
   |  /S [1-5] USERREFRESHINTERVALUNIT  |                                                                                                                                                             間隔の単位 (時間 [0]、日数 [1]) を指定します。 使用例:<p><p>**/S2USERREFRESHINTERVALUNIT = [0 \ | 1 \]**                                                                                                                                                             |
   |               /Log               |                                                                                                                                                ログ情報が保存されている場所を指定します。 既定の場所は% Temp% です。 使用例:<p><p>**/log C:\logs\log.log**                                                                                                                                                |
   |                /q                |                                                                                                                                                                                                無人インストールを指定します。                                                                                                                                                                                                |
   |             /REPAIR              |                                                                                                                                                                                               以前のクライアントインストールを修復します。                                                                                                                                                                                               |
   |            /NORESTART            | クライアントのインストール後にコンピューターが再起動しないようにします。<p><p>このパラメーターを使用すると、各更新プログラムをインストールした後にエンドユーザーのコンピューターが再起動しないようにし、都合のよいときに再起動をスケジュールすることができます。 たとえば、Service Pack のインストール後に、再起動しなくても、App-v 5.0 SPX をインストールしてから、修正プログラムパッケージ Y をインストールすることができます。 インストール後、App-v の使用を開始する前に再起動する必要があります。 |
   |            /UNINSTALL            |                                                                                                                                                                                                       クライアントをアンインストールします。                                                                                                                                                                                                        |
   |           /ACCEPTEULA            |                                                                                                                                              ライセンス契約を承諾します。 これは、無人インストールの場合に必要になります。 使用例:<p><p>**/ACCEPTEULA**または **/ACCEPTEULA = 1**                                                                                                                                               |
   |             /レイアウト              |                                                                                                                               関連付けられているレイアウトアクションを指定します。 また、Windows インストーラー (.msi) とスクリプトファイルも、App-v 5.0 をインストールせずにフォルダーに展開します。 値は予期されません。                                                                                                                                |
   |            /Layoutdir            |                                                                                                                                                 レイアウトディレクトリを指定します。 文字列値が必要です。 使用例:<p><p>**/Layoutdir = "C:\ Application Virtualization クライアント"**                                                                                                                                                  |
   |          /?、/h、/help           |                                                                                                                                                                                      以前のインストールパラメーターに関するヘルプを要求します。                                                                                                                                                                                      |

   ---

## Windows インストーラー (.msi) ファイルを使用して App-v 5.0 クライアントをインストールするには

1. ターゲットコンピューターに必要な前提条件をインストールします。 [開始する前に実行する操作を](#bkmk-clt-install-prereqs)参照してください。 前提条件が満たされていない場合、インストールは失敗します。

2. アプリ-V 5.0 Windows Installer (.msi) ファイルを使用してクライアントをインストールする前に、ターゲットコンピューターに保留中の再起動がないことを確認します。 Windows インストーラのファイルには、保留中の再起動のフラグは設定されません。

3. ターゲットコンピューターに次のいずれかの Windows インストーラーファイルを展開します。 指定するファイルは、ターゲットコンピューターの構成と一致している必要があります。


   |                       展開の種類                        |      このファイルを展開       |
   |-----------------------------------------------------------------|-----------------------------|
   | コンピューターで32ビットの Microsoft Windows オペレーティングシステムが実行されている |   appv_client_MSI_x86.msi   |
   | コンピューターで64ビットの Microsoft Windows オペレーティングシステムが実行されている |   appv_client_MSI_x64.msi   |
   | アプリ-V 5.0 リモートデスクトップサービスクライアントを展開しています  | appv_client_rds_MSI_x64.msi |

   ---

4. 次の表の情報を使用して、ターゲットコンピューターの目的の言語に基づいて、**インストールする適切**な言語パックを選びます。 表の**xxxx**は、言語パックのターゲットロケールを示しています。

   **始める前に知っておくべきこと:** 

   -  言語パックは、標準の App-v 5.0 クライアントと、App-V 5.0 クライアントのリモートデスクトップサービスバージョンの両方に共通です。

   -  **.Exe**を使って app-v 5.0 クライアントをインストールする場合、インストーラーは、ターゲットコンピューターで実行されているオペレーティングシステムと一致する言語パックのみを展開します。

   -  追加の言語パックをターゲットコンピューターに展開するには、 **Windows Installer (.msi) ファイルを使用して**、この手順に従って app-v 5.0 クライアントをインストールします。

   |                       展開の種類                        |       このファイルを展開       |
   |-----------------------------------------------------------------|------------------------------|
   | コンピューターで32ビットの Microsoft Windows オペレーティングシステムが実行されている | appv_client_LP_xxxx_ x86.msi |
   | コンピューターで64ビットの Microsoft Windows オペレーティングシステムが実行されている | appv_client_LP_xxxx_ x64.msi |

   ---

   App-v**の提案をお寄せ**ください。 [候補](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)を追加または投票します。 <p><p>**App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の展開](deploying-app-v-50.md)

[Client の構成設定について](about-client-configuration-settings.md)

[App-V 5.0 Client をアンインストールする方法](how-to-uninstall-the-app-v-50-client.md)
