---
title: Client の構成設定について
description: Client の構成設定について
author: dansimp
ms.assetid: 18bb307a-7eda-4dd6-a83e-6afaefd99470
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb547eedf63bf165b1e8f5fd024839b3c2af3e4c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814946"
---
# Client の構成設定について


Microsoft Application Virtualization (App-v) 5.1 クライアントでは、その構成がレジストリに格納されます。 レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。 また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。 このトピックでは、App-v 5.1 クライアント構成の設定を示し、その使い方について説明します。 PowerShell を使用して、クライアント構成の設定を変更することができます。 PowerShell と App-v 5.1 の使用方法について詳しくは、「 [Powershell を使用したアプリの管理-v 5.1](administering-app-v-51-by-using-powershell.md)」をご覧ください。

## <a href="" id="---------app-v-5-1-client-configuration-settings"></a> App-v 5.1 クライアント構成の設定


次の表は、App-v 5.1 クライアントの構成設定に関する情報を示しています。

|設定名 | 設定フラグ | 説明 | オプションを設定する | レジストリキー値 | ポリシーの状態のキーと値が無効になっている |
|-------------|------------|-------------|-----------------|--------------------|--------------------------------------|
| PackageInstallationRoot | PACKAGEINSTALLATIONROOT | すべての新しいアプリケーションと更新プログラムをインストールするディレクトリを指定します。 | String | Streaming\PackageInstallationRoot | ポリシー値が書き込まれていない (構成されていない) |
| パッケージパッケージ | パッケージパッケージ | パッケージコンテンツをダウンロードするためのソースの場所をオーバーライドします。 | String | Streaming\PackageSourceRoot | ポリシー値が書き込まれていない (構成されていない) |
| AllowHighCostLaunch | 利用不可。 |この設定は、従量制課金接続を介して接続された Windows 10 コンピューターで、仮想化されたアプリケーションを起動するかどうかを制御します (4G など)。 | True (有効)、False (無効状態) | Streaming\AllowHighCostLaunch | 0 |
| ReestablishmentRetries | 利用不可。 | ドロップしたセッションを再試行する回数を指定します。 | Integer (0-99) | Streaming\ReestablishmentRetries | ポリシー値が書き込まれていない (構成されていない) |
| ReestablishmentInterval | 利用不可。 | ドロップされたセッションを再確立するまでの試行の秒数を指定します。 | Integer (0-3600) | Streaming\ReestablishmentInterval | ポリシー値が書き込まれていない (構成されていない) |
| LocationProvider | 利用不可。 | IAppvPackageLocationProvider インターフェイスの互換性のある実装の CLSID を指定します。 | String | Streaming\LocationProvider | ポリシー値が書き込まれていない (構成されていない) |
| CertFilterForClientSsl | 利用不可。 | 証明書ストア内の有効な証明書へのパスを指定します。 | String | Streaming\CertFilterForClientSsl | ポリシー値が書き込まれていない (構成されていない) |
| VerifyCertificateRevocationList | 利用不可。 | HTTPS を使用して steaming する前にサーバー証明書の取り消し状態を確認します。 | True (有効)、False (無効状態) | Streaming\VerifyCertificateRevocationList | 0 |
| SharedContentStoreMode | SHAREDCONTENTSTOREMODE | ストリーミングされたパッケージコンテンツをローカルのハードディスクに保存しないように指定します。 | True (有効)、False (無効状態) | Streaming\SharedContentStoreMode | 0 |
| 名前<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | 発行サーバー名 | 発行サーバーの名前が表示されます。 | String | 発行 \ serverId} \ FriendlyName | ポリシー値が書き込まれていない (構成されていない) |
| URL<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | 発行する SERVERURL | 発行サーバーの URL を表示します。 | String | 発行 \ ドメイン \ {serverId} \ URL | ポリシー値が書き込まれていない (構成されていない) |
| GlobalRefreshEnabled<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | GLOBALREFRESHENABLED | グローバル発行の更新 (ブール値) を有効にします。 | True (有効)、False (無効状態) | 発行 \ serverId} \ GlobalEnabled | False |
| GlobalRefreshOnLogon<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | GLOBALREFRESHONLOGON | ログオン時にグローバル公開の更新をトリガーします。 ブール | True (有効)、False (無効状態) | 発行 \ serverId} \ GlobalLogonRefresh | False |
| GlobalRefreshInterval<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | GLOBALREFRESHINTERVAL | GlobalRefreshIntervalUnit を使った公開の更新間隔を指定します。 パッケージの更新を無効にするには、[0] を選びます。 | Integer (0-744) | 発行 \ serverId} \ GlobalPeriodicRefreshInterval | 0 |
| GlobalRefreshIntervalUnit <br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | GLOBALREFRESHINTERVALUNI | 間隔の単位 (Hour 0-23, Day 0-31) を指定します。 | 0 (hour)、1日の場合 | 発行 \ serverId} \ GlobalPeriodicRefreshIntervalUnit | 件 |
| UserRefreshEnabled<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | USERREFRESHENABLED | ユーザー発行の更新 (ブール値) を有効にします。 | True (有効)、False (無効状態) | 発行 \ serverId} \ UserEnabled | False |
| UserRefreshOnLogon 使い方<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | USERREFRESHONLOGON 使い方 | ユーザー公開の更新方法をトリガーします。 ブール<br>文字数 (スペースを含む):60 | True (有効)、False (無効状態) | 発行 \ serverId} \ UserLogonRefresh | False |
| UserRefreshInterval<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | USERREFRESHINTERVAL | UserRefreshIntervalUnit を使った公開の更新間隔を指定します。 パッケージの更新を無効にするには、[0] を選びます。 | 文字数 (スペースを含む):85<br>Integer (0-744 時間) | 発行 \ serverId} \ UserPeriodicRefreshInterval | 0 |
| UserRefreshIntervalUnit<br>**注**この設定は、 **AppvclientConfiguration**コマンドレットを使用して変更することはできません。 **AppvPublishingServer**コマンドレットを使用する必要があります。 | USERREFRESHINTERVALUNIT | 間隔の単位 (Hour 0-23, Day 0-31) を指定します。 | 0 (hour)、1日の場合 | 発行 \ ユーザー \ {serverId} \ UserPeriodicRefreshIntervalUnit | 件 |
| MigrationMode | MIGRATIONMODE | 移行モードでは、以前のバージョンの App-v を使用して作成されたパッケージのショートカットと FTA を、App-v クライアントで変更することができます。 | True (有効状態)False (無効状態) | Coexistence\MigrationMode | |
| CEIPOPTIN | CEIPOPTIN | アプリケーションをさらに向上させるために、App-v 5.1 クライアントを実行しているコンピューターで特定の使用状況情報を収集して返すことを許可します。 | 無効の場合は0有効にする場合は1 | ソフトウェア/Microsoft/AppV/CEIP/CEIPEnable | 0 | 
| EnablePackageScripts | ENABLEPACKAGESCRIPTS | 実行する必要がある構成ファイルのパッケージマニフェストで定義されているスクリプトを有効にします。 | True (有効)、False (無効状態) | \Scripting\EnablePackageScripts | | 
| RoamingFileExclusions | ROAMINGFILEEXCLUSIONS | ユーザーのプロファイルでローミングされない% userprofile% を基準としたファイルパスを指定します。 使用例:/ROAMINGFILEEXCLUSIONS = ' desktop; マイピクチャ ' | | | |
| RoamingRegistryExclusions | ROAMINGREGISTRYEXCLUSIONS | ユーザープロファイルでローミングされないレジストリパスを指定します。 使用例:/ROAMINGREGISTRYEXCLUSIONS = ソフトウェア \\ クラス; ソフトウェア \\ クライアント | String | Integration\RoamingRegistryExclusions | ポリシー値が書き込まれていない (構成されていない) |
| 統合ルートユーザ | 利用不可。 | ユーザーごとに公開されたパッケージの現在のバージョンに関連付けられているシンボリックリンクを作成する場所を指定します。 ショートカットやファイルの種類の関連付けなどのすべての仮想アプリケーションの拡張は、このパスをポイントします。 パスを指定しない場合、パッケージを公開するときにシンボリックリンクは使用されません。 例:%localappdata%\Microsoft\AppV\Client\Integration.| String | 統合と統合 rootuser | ポリシー値が書き込まれていない (構成されていない) |
|統合 Rootグローバル | 利用不可。| グローバルに公開されたパッケージの現在のバージョンに関連付けられているシンボリックリンクを作成する場所を指定します。 ショートカットやファイルの種類の関連付けなどのすべての仮想アプリケーションの拡張は、このパスをポイントします。 パスを指定しない場合、パッケージを公開するときにシンボリックリンクは使用されません。 例:%allusersprofile%\Microsoft\AppV\Client\Integration | String | 統合と統合 rootグローバル | ポリシー値が書き込まれていない (構成されていない) |
| VirtualizableExtensions | 利用不可。 | ローカルにインストールされたアプリケーションを仮想環境で実行できるかどうかを判断するために使用できるファイル名拡張子のコンマ区切りリスト。<br>公開時にショートカット、FTAs、およびその他の拡張ポイントを作成すると、その拡張ポイントに関連付けられたアプリケーションがローカルにインストールされている場合、App-v はファイル名の拡張子を一覧と比較します。 拡張機能がある場合は、 **Runvirtual**コマンドラインパラメーターが追加され、アプリケーションは実質的に実行されます。<br>**Runvirtual**パラメーターの詳細については、「[仮想化されたアプリケーションを使って、仮想環境内でローカルにインストールされたアプリケーションを実行する](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications51.md)」を参照してください。 | String | 統合 \ virtualizableextensions | ポリシーの値が書き込まれない |
| ReportingEnabled | 利用不可。 | クライアントが情報をレポートサーバーに返すことができるようにします。 | True (有効)、False (無効状態) | Reporting\EnableReporting | False |
| ReportingServerURL | 利用不可。 | クライアント情報が保存されている、レポートサーバー上の場所を指定します。 | String | Reporting\ReportingServer | ポリシー値が書き込まれていない (構成されていない) |
| Reportingdatacachlimit | 利用不可。 | レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。 サイズは、メモリ内のキャッシュに適用されます。 上限に達すると、ログファイルがロールオーバーされます。 0 ~ 1024 の間で設定します。 | Integer [0-1024] | Reporting\DataCacheLimit | ポリシー値が書き込まれていない (構成されていない) |
| Reportingの各の Locksize| 利用不可。 | アップロード要求を報告するためにサーバーに送信する最大サイズ (バイト単位) を指定します。 これにより、ログのサイズが大きくなったときに、永続的な送信エラーが発生しないようにすることができます。 1024と無制限の間で設定します。 | Integer [1024-実質無制限] | Reporting\DataBlockSize | ポリシー値が書き込まれていない (構成されていない) |
| ReportingStartTime | 利用不可。 | クライアントの開始時刻を指定して、データをレポートサーバーに送信します。 1日の時刻に対応する0-23 の間に有効な整数を指定する必要があります。 既定では、 **Reportingstarttime**は、現在の日である 10 P. または22で開始されます。<br>**注**この設定は、App-v 5.1 クライアントを実行しているコンピューターが少なくともオフラインになる可能性のある時刻に設定する必要があります。 | 整数 (0 ~ 23) | レポート \ 開始時刻 | ポリシー値が書き込まれていない (構成されていない) |
| ReportingInterval | 利用不可。 | クライアントがデータをレポートサーバーに再送信するために使用する再試行間隔を指定します。 | Integer | Reporting\RetryInterval | ポリシー値が書き込まれていない (構成されていない) |
| ReportingRandomDelay | 利用不可。 | レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。 スケジュールされたタスクが開始されると、クライアントは0と**ReportingRandomDelay**の間のランダムな遅延を生成し、データを送信する前に指定された期間待機します。 これは、サーバーでの競合を防ぐのに役立ちます。 | Integer [0-ReportingRandomDelay] | Reporting\RandomDelay | ポリシー値が書き込まれていない (構成されていない) |
| EnableDynamicVirtualization<br>**重要**この設定は、App-v 5.0 SP2 以降でのみ使用できます。 | 利用不可。 | サポートされているシェルの拡張機能、ブラウザーヘルパーオブジェクト、アクティブな X コントロールを仮想アプリケーションで仮想化して実行できるようにします。 | 1 (有効)、0 (無効) | HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization | |
| EnablePublishingRefreshUI<br>**重要**この設定は、App-v 5.0 SP2 でのみ使用できます。 | 利用不可。 | App-v 5.1 クライアントを実行しているコンピューターの公開更新の進行状況バーを有効にします。 | 1 (有効)、0 (無効) | HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing | |
| HideUI<br>**重要** この設定は、App-v 5.0 SP2 でのみ使用できます。| 利用不可。 | 公開の更新の進行状況バーを非表示にします。 | 1 (有効)、0 (無効) | | |
| プロセスの仮想コンポーネントの方法 | 利用不可。 | プロセスパス (ワイルドカードが含まれている可能性がある) の一覧を指定します。これは、動的仮想化 (サポートされているシェル拡張機能、ブラウザーヘルパーオブジェクト、および ActiveX コントロール) を使用するための候補です。 完全なパスがこれらの項目のいずれかに一致するプロセスのみが、動的仮想化を使うことができます。 | String | Virtualization\ProcessesUsingVirtualComponents | 空の文字列。 |






## 関連トピック


[App-V 5.1 Sequencer および Client の展開](deploying-the-app-v-51-sequencer-and-client.md)

[ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

[APP-V Client を展開する方法](how-to-deploy-the-app-v-client-51gb18030.md)

 

 





