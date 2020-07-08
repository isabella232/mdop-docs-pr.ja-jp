---
title: サーバーのイベント ログ
description: サーバーのイベント ログ
author: dansimp
ms.assetid: 04e724d2-28cc-4fa8-86a1-0d4ab0234b11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 269e9b4bc2644fae4dc5796652c7587bb0ef6076
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823384"
---
# サーバーのイベント ログ


このセクションの表では、MBAM サーバーログイベント Id について説明します。

## 構成


次の表には、構成中に MBAM サーバーで発生する可能性があるイベント Id のメッセージとトラブルシューティング情報が含まれています。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">イベント ID</th>
<th align="left">Source</th>
<th align="left">イベントの記号</th>
<th align="left">メッセージ</th>
<th align="left">トラブルシューティング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>103</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>VssRegistrationException</p></td>
<td align="left"><p>VSS 登録中に例外がスローされました。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>104</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>VssDeregistrationException</p></td>
<td align="left"><p>VSS 登録解除中に例外がスローされました。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>300</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>CmdletError</p></td>
<td align="left"><p>フォルダーの削除に失敗しました。</p></td>
<td align="left"><p>タスクの実行中に終了したエラーが発生したことを示します。 さらに、MBAM セットアップを診断するために、ログの他のイベントメッセージを調べます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>301</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>cmdletUnexpectedError</p></td>
<td align="left"><p>予期しないコマンドレットエラー。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>302</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>CmdletWarning</p></td>
<td align="left"><p>コマンドレットの警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>303</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>レットの情報</p></td>
<td align="left"><p>コマンドレットの情報。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。 このイベントは、enabling\disabling (機能の開始) や操作の取り消しなどのコマンドレットによって、タスクが実行されていることを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>400</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>/エラー</p></td>
<td align="left"><p>コンフィギュレーターエラー。</p></td>
<td align="left"><p>MBAM コンフィギュレーターの起動中にエラーが発生したことを示します。 ユーザーに MBAM コンフィギュレーターを起動する適切な権限があることを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>401</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>ConfiguratorUnexpectedError</p></td>
<td align="left"><p>予期しないコンフィギュレーターエラー。</p></td>
<td align="left"><p>MBAM コンフィギュレータータスクの実行中に終了エラーが発生したことを示します。 エラーメッセージには、エラーに関する詳細情報が含まれています。 また、イベントログの他のエラーメッセージを調べて、MBAM セットアップをさらに診断します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>ユーザーによって選択された証明書を取得または検証できない</p></li>
<li><p>レポート URL の解析エラー</p></li>
<li><p>ユーザーのイベントログを開くことができない</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>402</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>/警告</p></td>
<td align="left"><p>コンフィギュレーター警告。</p></td>
<td align="left"><p>MBAM コンフィギュレータータスクが予期したとおりに完了せず、完全に失敗しなかったことを示します。 既知のタスクには、web アプリケーション機能で構成された LocalMachine\My store の見つからない証明書、または保留中のタスクのタイムアウトが含まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>410</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>この情報</p></td>
<td align="left"><p>コンフィギュレーター情報。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。 このイベントは、MBAM コンフィギュレーターによってタスクが呼び出されていることを示します。 既知のタスクには次のものがあります。</p>
<ul>
<li><p>コンフィギュレーターの起動</p></li>
<li><p>MBAM 機能のソフトウェアの前提条件を確認する</p></li>
<li><p>MBAM 機能のパラメーターを検証する</p></li>
<li><p>MBAM 機能の Enabling\disabling\committing</p></li>
<li><p>コンフィギュレーターからの PowerShell スクリプトの生成</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>500</p></td>
<td align="left"><p>Microsoft_Windows_MBAM_Server_Admin</p></td>
<td align="left"><p>WebProviderUnexpectedError</p></td>
<td align="left"><p>Web アプリケーションプロバイダーの予期しないエラーが発生した。</p></td>
<td align="left"><p>MBAM web サイトまたは web サービスを IIS で有効化および構成するときに、エラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>IIS のルートフォルダーが見つかりませんでした</p></li>
<li><p>ファイルの形式が正しくないか、設定が見つからないために web.config の IIS 構成にアクセスできない</p></li>
<li><p>Web アプリケーションの作成または削除に失敗した場合</p></li>
<li><p>IIS アクセス違反</p></li>
</ul>
<p>このエラーは、MBAM が Active Directory (AD) にアクセスしてユーザーアカウントを検証できない場合にも記録されます。 IIS がインストールされていること、適切に構成されていること、IIS サービスが実行されていることを確認します。 すべての MBAM ソフトウェアの前提条件を満たしていることを確認します。 ユーザーに、IIS インスタンスで web アプリケーションを作成するための適切な権限があることを確認します。 ユーザーに AD 内のユーザーアカウントオブジェクトの読み取りアクセス権があることを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>501</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>WebProviderError</p></td>
<td align="left"><p>Web アプリケーションプロバイダーの予期しないエラーが発生した。</p></td>
<td align="left"><p>MBAM web サイトまたは web サービスを IIS で有効化、無効化、または構成しているときにエラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>IIS から基本または WSHttp のバインド情報を読み取ることができない</p></li>
<li><p>IIS 構成ファイルの id セクションまたは id セクションの DNS エントリが見つからない</p></li>
<li><p>レジストリキー HKLM\SOFTWARE\Microsoft\InetStp を開くことができない</p></li>
<li><p>レジストリキー HKLM\SOFTWARE\Microsoft\InetStp から値のパスの Wwwroot を読み取ることができない</p></li>
<li><p>ユーザーは MBAM の予約名で仮想ディレクトリ名を指定しようとしています</p></li>
</ul>
<p>IIS がインストールされ、正しく構成されていることを確認します。 レジストリキー HKLM\SOFTWARE\Microsoft\InetStp: PathWWWRoot が存在し、アクセス可能であることを確認します。 IIS のバインド情報が破損していないことを確認します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>502</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>WebProviderWarning</p></td>
<td align="left"><p>Web アプリケーションプロバイダーの警告。</p></td>
<td align="left"><p>MBAM web サイトまたは web サービスを有効にしているときに、終了しないエラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>アプリプールアカウントのサービスプリンシパル名 (SPN) を検証するための AD へのアクセスエラー</p></li>
<li><p>AD の複数のアカウントに割り当てられているため、SPN の検証が失敗する</p></li>
<li><p>AD のアプリプールアカウントで SPN を登録できない</p></li>
<li><p>SPN が AD のアプリプール以外のアカウントに登録されている</p></li>
<li><p>ロールバック操作中に AD のアプリプールアカウントから SPN を削除できない</p></li>
<li><p>IIS サーバーで IIS_IUSRS グループに [バッチとしてログオン] 権限が付与されているかどうかを確認できない</p></li>
</ul>
<p>イベントメッセージには、特定のエラーに関する詳細情報が含まれます。 MBAM セットアップが実行されているサーバーから広告が到達可能であることを確認します。 MBAM セットアップを実行しているユーザーが、AD のアプリプールアカウントに対する読み取りアクセス許可を持っていることを確認します。 SPN が AD のアプリプールアカウントで既に登録されている場合は、他のアカウントに登録されていないことを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>503</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>WebProviderInformation</p></td>
<td align="left"><p>Web アプリケーションプロバイダー情報。 説明</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。 このイベントは、MBAM セットアップによってタスクが呼び出されていることを示します。 既知のタスクには、バインド情報やルートサイトなどの IIS 構成の取得、サービスプリンシパル名 (SPN) の構成などがあります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>600</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>SetupUnexpectedError</p></td>
<td align="left"><p>予期しないセットアップエラー。</p></td>
<td align="left"><p>Enabling\disabling または MBAM 機能の構成中に終了エラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>エラーの発生後にタスクをロールバックできない</p></li>
<li><p>レジストリからの読み取りエラー</p></li>
<li><p>ファイルシステム内のフォルダーを作成または削除できない</p></li>
<li><p>SQL のバージョン情報を読み取ることができない</p></li>
<li><p>SQL で VSS writer を登録できない</p></li>
</ul>
<p>イベントメッセージには、特定のエラーに関する詳細情報が含まれます。 すべての MBAM ソフトウェアの前提条件を満たしていることを確認します。 MBAM レジストリパス (存在する場合)、HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server、サブキーがすべて読み取り可能であることを確認します。 MBAM セットアップが実行されているサーバーから広告が到達可能であることを確認します。 MBAM セットアップを実行しているユーザーに AD の読み取りアクセス許可が与えられていることを確認します。</p>
<p>VSS ライター登録が成功した場合は、サポートされているバージョンの SQL がインストールされていることと、MBAM セットアップを実行しているユーザーがインスタンスにアクセスできることを確認します。 MBAM 機能を無効にするか、MBAM をアンインストールする場合、MBAM がその web サイトと web サービスを削除できるように、ログファイルや web.config ファイルなどのすべてのファイルが閉じていることを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>601</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>SetupError</p></td>
<td align="left"><p>セットアップエラー。</p></td>
<td align="left"><p>Enabling\disabling または MBAM 機能の構成中に終了エラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>IIS で MBAM 構成を読み取ることができない</p></li>
<li><p>IIS 構成の壊れた appSettings セクション、または設定の誤り</p></li>
<li><p>ホスト名の検証エラー</p></li>
<li><p>SQL のバージョン情報を読み取ることができない</p></li>
<li><p>SQL で VSS writer を登録できない</p></li>
</ul>
<p>イベントメッセージには、特定のエラーに関する詳細情報が含まれます。 IIS がインストールされ、正しく構成されていることを確認します。 すべての MBAM ソフトウェアの前提条件を満たしていることを確認します。 VSS ライター登録が成功した場合は、サポートされているバージョンの SQL がインストールされていることと、MBAM セットアップを実行しているユーザーがインスタンスにアクセスできることを確認します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>602</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>SetupWarning</p></td>
<td align="left"><p>設定の警告。</p></td>
<td align="left"><p>Enabling\disabling または MBAM 機能 (Configuration Manager (CM) インテグレーションまたは MBAM web アプリケーションなど) を構成しているときに、終了しないエラーが発生したことを示します。 既知のエラー: CM の SRS ロールポイントからの MBAM レポートの削除に失敗し、ドメインコントローラーからホスト名を解決できませんでした。 イベントメッセージには、特定のエラーに関する詳細情報が含まれます。</p>
<p>MBAM セットアップが実行されているサーバーから広告が到達可能であることを確認します。 MBAM セットアップを実行しているユーザーが、CM で SRS 役割ポイントとして構成されている SSRS インスタンスのアクセス許可を削除していることを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>603</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>SetupInformation</p></td>
<td align="left"><p>セットアップ情報。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>605</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>Webproviderソフトウェア Checkfailure</p></td>
<td align="left"><p>Web アプリケーションは、1つ以上のソフトウェアの依存関係が満たされていないため、有効にできません。</p></td>
<td align="left"><p>MBAM web site/web サービスのインストール中に、MBAM セットアップは必要な前提条件が適切かどうかを確認します。 このメッセージは、必要な前提条件が見つからないため、MBAM が要求された web サイト/web サービスをインストールできなかったことを示します。 不足している前提条件の詳細については、このメッセージの前にあるエラーメッセージを参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>606</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>SetupParameterValidationFailure</p></td>
<td align="left"><p>サーバー機能を有効にするために必要なパラメーターが指定されていないか、検証に合格しませんでした。</p></td>
<td align="left"><p>MBAM 機能を構成するために必要なパラメーターが指定されていないか、検証をパスしなかったことを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>607</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>SetupParameterValidationFailureWithError</p></td>
<td align="left"><p>サーバー機能を有効にするために必要な指定されたパラメーターを検証しようとしたときにエラーが発生しました。</p></td>
<td align="left"><p>サーバー機能を有効にするために必要な指定されたパラメーターを検証しようとしたときに、エラーが発生したことを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>700</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>DbProviderUnexpectedError</p></td>
<td align="left"><p>データベースプロバイダーの予期しないエラーが発生した。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>701</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>DbProviderError</p></td>
<td align="left"><p>DB プロバイダーエラー。</p></td>
<td align="left"><p>EventDetails セクションに含まれるメッセージは、実際のエラーに関する詳細情報を提供する必要があります。 確認する領域の一部を次に示します。</p>
<ul>
<li><p>MBAM セットアップ指定された接続情報を使用してデータベースに接続できませんでした。 MBAM セットアップに提供される接続文字列の詳細を確認します。</p></li>
<li><p>MBAM セットアップ指定したドメインアカウントの資格情報を使用して、指定されたデータベースに接続できませんでした。 ドメインアカウントのユーザー名とパスワードが有効であることを確認します。</p></li>
<li><p>MBAM セットアップ指定したドメインアカウントの資格情報を使用して、指定されたデータベースに接続できませんでした。 指定したドメインアカウントに、MBAM データベースに接続するために必要な権限があることを確認します。</p></li>
<li><p>Mbam の新しいバージョンの MBAM データベースが既にインストールされている場合、MBAM Dac pac が失敗します。 指定の SQL server に MBAM Db の新しいバージョンが存在しないことを確認します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>702</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>DbProviderWarning</p></td>
<td align="left"><p>DB プロバイダーの警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>703</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>DbProviderInformation</p></td>
<td align="left"><p>DB プロバイダー情報。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>704</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>DbProviderDacError</p></td>
<td align="left"><p>データ層アプリケーションの展開中にエラーが発生しました。</p></td>
<td align="left"><p>MBAM は、データベースをデータ層アプリケーションとしてパッケージ化し、そのデータベースを Microsoft の場合は、そのアプリケーションを登録しようとします。 コンテキストのエラーメッセージは、DAC サービスによって報告されます。 イベントには、発生した問題に関する詳細情報が含まれている必要があります。 エラーメッセージ内の情報を読み、問題のトラブルシューティングを行い、修正します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>705</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>DbProviderDacWarning</p></td>
<td align="left"><p>データ層アプリケーションの展開中に警告が発生しました。</p></td>
<td align="left"><p>MBAM は、データベースをデータ層アプリケーションとしてパッケージ化し、それを Microsoft の場合は、これらのファイルを登録しようとします。 コンテキストの警告メッセージは、DAC サービスによって報告されます。 イベントには、発生した問題に関する詳細情報が含まれている必要があります。 警告メッセージの情報を読み、問題のトラブルシューティングを行い、修正します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>706</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>DbProviderDacInformation</p></td>
<td align="left"><p>データ層アプリケーションの展開中にメッセージが発生しました。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>800</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>ReportProviderUnexpectedError</p></td>
<td align="left"><p>レポートプロバイダーの予期しないエラーが発生した。</p></td>
<td align="left"><p>レポートプロバイダーの予期しないエラーが発生した。 説明{exceptionDetails}次に、考えられる例外の詳細をいくつか示します。</p>
<p><strong>ディレクトリ &#39; {directoryName} の名前の取得中にエラーが発生しました &#39;</strong></p>
<p><strong>ディレクトリ &#39; {directoryName} のファイルの取得中に例外が発生しました &#39;</strong></p>
<p><strong>ディレクトリ &#39; {directoryName} のディレクトリを列挙するときに例外が発生しました &#39;</strong></p>
<p><strong>ファイル &#39; {fileName} のすべてのバイトを読み取り中に例外が発生しました &#39;</strong></p>
<p>MBAM のインストール中に、MBAM セットアップでは、指定したインストールパスにすべてのレポートファイルが unzips されます。 レポートのインストールの一環として、インストールモジュールはインストールパスで解凍されたレポートファイルにアクセスし、SQL Reporting services と通信してレポートファイルを公開します。 上記のエラーは、MBAM が、解凍されたインストールパスでファイル/フォルダーにアクセスできない場合に発生します。 この問題を解決するには、次のヒントを参考にしてください。</p>
<ul>
<li><p>MBAM がインストールされていることを確認します。</p></li>
<li><p>Regkey HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM \ installationpath が存在し、実行しているユーザーがアクセスできることを確認します。</p></li>
<li><p>MBAM インストールパスのファイルを報告するパスが、248文字を超えていないことを確認します。</p></li>
<li><p>MBAM セットアップフォルダーまたは MBAM インストールパスに含まれるファイルが、インストール後に変更されていないことを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、MBAM インストールフォルダーの読み取り/書き込みを許可されていることを確認します。</p></li>
</ul>
<p><strong>Reporting Services の接続に失敗しました。{exceptionDetails}</strong></p>
<p>MBAM レポートのインストール中に、モジュールは SSRS web サービスと通信して、フォルダーを作成し、レポートを公開しようとします。 上記のメッセージは、MBAM が SSRS web サービスを検出または通信できなかったことを示します。 この問題を解決するには、次のヒントを参考にしてください。</p>
<ul>
<li><p>指定したコンピューターに SSRS がインストールされていることを確認します。</p></li>
<li><p>SSRS コンソールを使用して、SSRS が有効で実行中であることを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、SSRS へのアクセスを許可されていることを確認します。</p></li>
</ul>
<p><strong>Reporting Services インスタンス URL &#39; {SSRSInstanceUrl} &#39; を使用して MBAM レポートを削除できませんでした。MBAM レポートに必要な SSRS インスタンスが実行され、正しく構成されていることを確認します。</strong></p>
<p>MBAM インストールに失敗した場合、またはユーザーが MBAM レポート機能を無効にした場合、セットアップモジュールは SSRS レポートを削除します。 上記のメッセージは、MBAM が SSRS レポートを削除できなかったことを示します。 この問題を解決するには、次のヒントを参考にしてください。</p>
<ul>
<li><p>指定したコンピューターに SSRS がインストールされていることを確認します。</p></li>
<li><p>SSRS コンソールを使用して、SSRS が有効で実行中であることを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、SSRS へのアクセスを許可されていることを確認します。</p></li>
</ul>
<p><strong>レポートの発行中にエラーが発生しました。{exceptionDetails}。</strong></p>
<p>MBAM レポートのインストール中に、モジュールは SSRS web サービスと通信して、フォルダーを作成し、レポートを公開しようとします。 上のメッセージは、レポートの発行中に、SSRS web サービスによって報告され、例外が発生したことを示します。 この問題を解決するには、次のヒントを参考にしてください。</p>
<ul>
<li><p>SSRS コンソールを使用して、SSRS が有効で実行中であることを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、SSRS へのレポートのアクセス/公開を許可されていることを確認します。</p></li>
</ul>
<p><strong>グループのユーザー名 &#39; {userName} &#39; のポリシーは既に存在します。 これが正しくない場合は、レポートサービスの重複または無効のポリシーを手動で変更します。</strong></p>
<p>MBAM レポートを公開した後、MBAM セットアップは MBAM レポートのユーザーロール (まだ存在しない場合) を作成し、それに対応するユーザーポリシーを設定します。 上のエラーは、レポートユーザーロールポリシーを設定しているときに、SSRS web サービスで例外がスローされたことを示します。 イベントメッセージに記載されている手順に従い、「」を参照してください &quot; <a href="https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp;ProdVer=8.00&amp;EvtID=rsInvalidPolicyDefinition&amp;EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings&amp;LCID=1033&amp;quot" data-raw-source="https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp;amp;ProdVer=8.00&amp;amp;EvtID=rsInvalidPolicyDefinition&amp;amp;EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings&amp;amp;LCID=1033&amp;quot"> https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp 。ProdVer = 8.00 &amp; evtid = rsInvalidPolicyDefinition &amp; evtsrc =: 文字列 &amp; LCID = 1033&quot </a> ; 詳細については、こちらを参照してください。</p>
<p><strong>SSRS {exceptionDetails} へのアクセスの検証中にエラーが発生しました。</strong></p>
<p>前提条件の確認の一部として、MBAM setup は、ユーザーが SSRS の下にある [アクセス/作成] フォルダーに対する必要な権限を持っているかどうかを確認します。 このエラーメッセージは、SSRS へのアクセスを確認するために例外が発生したことを示します。 デバッグのヒントについては、例外の詳細を参照してください。</p>
<p><strong>SSRS URL の確認中に SOAP エラーが発生しました。{exceptionDetails}</strong></p>
<p><strong>SSRS URL の確認中に web エラーが発生しました。{exceptionDetails}</strong></p>
<p><strong>SSRS URL の確認中に http/https エラーが発生しました。{exceptionDetails}</strong></p>
<p><strong>SSRS URL の確認中にエラーが発生しました。{exceptionDetails}</strong></p>
<p>前提条件チェックの一部として、MBAM セットアップは、指定された SSRS インスタンスに関連付けられている Url を取得し、SSRS web サービスとの通信を試みます。 上記のエラーメッセージは、指定した URL の SSRS web サービスが例外をスローしたことを示しています。詳細については、「例外の詳細」を参照してください。 ここでは、SSRS 通信の問題を解決するためのヒントをいくつか紹介します。</p>
<ul>
<li><p>指定したコンピューターに SSRS がインストールされていることを確認します。</p></li>
<li><p>SSRS コンソールを使用して、SSRS が有効で実行中であることを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、SSRS へのアクセスを許可されていることを確認します。</p></li>
</ul>
<p><strong>SSRS バージョンの取得中にエラーが発生しました。 {exceptionDetails}</strong></p>
<p>前提条件の確認の一部として、MBAM セットアップは WMI を検索して、指定された SSRS インスタンスに関連付けられているバージョン番号を取得します。 上のエラーメッセージは、WMI の照会中に例外が発生したことを示します。 詳細については、「例外の詳細」を参照してください。 次のようなチェックを行うことができます。</p>
<ul>
<li><p>指定したインスタンス名の SSRS が指定のコンピューターにインストールされていることを確認します。</p></li>
<li><p>SSRS コンソールを使用して、SSRS が有効で実行中であることを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、WMI 名前空間の下にある SSRS クラスのクエリを許可されていることを確認します。</p></li>
</ul>
<p><strong>現在のユーザーは、{ssrsWMINamespace} &#39; に WMI 名前空間 &#39; アクセスする権限がありません。</strong></p>
<p><strong>{SsrsWMINamespace} &#39; の名前空間 &#39; の列挙中にエラーが発生しました。 ローカルホスト上の SSRS WMI プロバイダーの RPC サーバーが見つかりません。</strong></p>
<p><strong>{SsrsNamespace} &#39; &#39; 名前空間の列挙中にエラーが発生しました。 ローカルホスト上で SSRS のインスタンスが見つかりません。</strong></p>
<p><strong>WMI へのアクセス中にエラーが発生しました。 インスタンス &#39; {ssrsInstance} &#39; の RPC サーバーが見つかりませんでした。</strong></p>
<p><strong>WMI へのアクセス中にエラーが発生しました。 インスタンス名 &#39; {ssrsInstanceName} &#39; が正しくありません。</strong></p>
<p><strong>WMI へのアクセス中にエラーが発生しました。 ローカルホストで &#39; {ssrsInstanceName} &#39; インスタンスが見つかりません。</strong></p>
<p>前提条件チェックの一部として、MBAM セットアップは WMI を検索して、指定されたインスタンスに関連付けられている WMI 名前空間を取得します。 上のエラーメッセージは、WMI の照会中に例外が発生したことを示します。 詳細については、「例外の詳細」を参照してください。 次のようなチェックを行うことができます。</p>
<ul>
<li><p>指定したインスタンス名の SSRS が指定のコンピューターにインストールされていることを確認します。</p></li>
<li><p>SSRS コンソールを使用して、SSRS が有効で実行中であることを確認します。</p></li>
<li><p>セットアップを実行しているユーザーが、WMI 名前空間の下にあるアクセス/クエリ SSRS クラスを許可していることを確認します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>801</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>ReportProviderError</p></td>
<td align="left"><p>レポートプロバイダーの予期しないエラーが発生した。</p></td>
<td align="left"><p>SQL server reporting services インスタンスの名前が指定されている場合、MBAM は、レポートインスタンスに対応する WMI 名前空間を見つけて、それに接続しようとします。 このエラーは、MBAM が SSRS WMI 名前空間を検索するか、または実行しようとしたときに、MBAM で例外が発生した場合に発生します。 詳細については、このメッセージの前に MBAM セットアップチャネルに記録されているエラーメッセージの情報を参照してください。 次の点を確認できます。</p>
<ul>
<li><p>指定したインスタンス名の SSRS が稼働していることを確認する</p></li>
<li><p>MBAM インストールを実行しているユーザーアカウントに、SSRS WMI 名前空間へのクエリ/接続に必要な権限があることを確認する</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>802</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>ReportProviderWarning 警告</p></td>
<td align="left"><p>レポートプロバイダーの警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>803</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>ReportProviderInformation</p></td>
<td align="left"><p>プロバイダー情報をレポートします。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>900</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>CMProviderUnexpectedError</p></td>
<td align="left"><p>CM provider で予期しないエラーが発生した。</p></td>
<td align="left"><p>MBAM の Configuration Manager (CM) 統合機能を enabling\disabling または構成しているときに、終了エラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>SMS プロバイダー経由で CM サイトサーバーに接続できない</p></li>
<li><p>レジストリからの読み取りエラー</p></li>
<li><p>ファイルシステム内のフォルダーを作成または削除できない</p></li>
<li><p>ローカルコンピューター上の Configuration Manager コンソールのインストールを見つけることができない</p></li>
<li><p>CM で SRS の役割ポイントとして構成されている SSRS インスタンスの情報を取得できない</p></li>
</ul>
<p>イベントメッセージには、特定のエラーに関する詳細情報が含まれます。 すべての MBAM ソフトウェアの前提条件を満たしていることを確認します。 MBAM レジストリパス (存在する場合)、HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server、およびすべてのサブキーが読み取り可能であることを確認します。 MBAM がサポートされている Configuration Manager のバージョンと統合されていることを確認します。 MBAM セットアップが呼び出されているコンピューターに Configuration Manager コンソールがインストールされていることを確認します。また、コンソールを使用してターゲット CM サイトサーバーに接続することもできます。 有効な SSRS インスタンスが CM の SRS ロールポイントとして構成されていること、および MBAM セットアップを実行しているユーザーに SSRS インスタンスの read\write 権限が与えられていることを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>901</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Server/Admin</p></td>
<td align="left"><p>CMProviderError</p></td>
<td align="left"><p>CM provider で予期しないエラーが発生した。</p></td>
<td align="left"><p>MBAM の Configuration Manager (CM) 統合機能を enabling\disabling または構成しているときに、終了エラーが発生したことを示します。 次のような既知のエラーがあります。</p>
<ul>
<li><p>SMS プロバイダー経由で CM サイトサーバーに接続できない</p></li>
<li><p>レジストリからの読み取りエラー</p></li>
<li><p>ファイルシステム内のフォルダーを作成または削除できない</p></li>
<li><p>ローカルコンピューター上の Configuration Manager コンソールのインストールを見つけることができない</p></li>
<li><p>SSRS の ConfigMgr フォルダーが、SRS の役割ポイントレポートのルートフォルダーとして見つからない</p></li>
<li><p>SSRS に ConfigMgr 共有データソースが見つかりませんでした</p></li>
<li><p>CM の SRS 役割ポイントとして構成されている SSRS インスタンスでの SSRS レポートの展開に失敗する</p></li>
<li><p>CM で構成項目とベースラインを作成できない</p></li>
</ul>
<p>イベントメッセージには、特定のエラーに関する詳細情報が含まれます。 すべての MBAM ソフトウェアの前提条件を満たしていることを確認します。 MBAM レジストリパス (存在する場合)、HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server、およびすべてのサブキーが読み取り可能であることを確認します。 MBAM がサポートされている Configuration Manager のバージョンと統合されていることを確認します。 MBAM セットアップが呼び出されているコンピューターに Configuration Manager コンソールがインストールされていることを確認します。また、コンソールを使用してターゲット CM サイトサーバーに接続することもできます。 CM で構成項目、ベースライン、コレクションを作成するために必要な read\write 権限がユーザーにあることを確認します。 有効な SSRS インスタンスが CM の SRS ロールポイントとして構成されていること、および MBAM セットアップを実行しているユーザーに SSRS インスタンスの read\write 権限が与えられていることを確認します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>902</p></td>
<td align="left"><p>Microsoft_Windows_MBAM_Server_Admin</p></td>
<td align="left"><p>CMProviderWarning</p></td>
<td align="left"><p>CM provider の警告。</p></td>
<td align="left"><p>Configuration Manager (CM) 統合機能を有効にしているときに、終了しないエラーが発生したことを示します。 既知のエラーとしては、MBAM サポートされているコンピューターコレクションでのコレクションルールのコミットの失敗、およびその他の SSRS およびネットワーク関連のエラーがあります。</p>
<p>イベントメッセージには、特定のエラーに関する詳細情報が含まれます。 この警告の原因となる操作は、警告の後に廃止されます。 何度か再試行した後にエラーが引き続き発生する場合は、MBAM が実際のエラーで終了する可能性があります。 さらに、MBAM セットアップを診断するために、ログの他のイベントメッセージを調べます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>903</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-サーバー/運用</p></td>
<td align="left"><p>CMProviderInformation</p></td>
<td align="left"><p>CM プロバイダー情報。</p></td>
<td align="left"><p>情報のみトラブルシューティングは不要です。</p></td>
</tr>
</tbody>
</table>

 

## 操作


次の表には、MBAM を実行しているときに発生する可能性があるイベント Id のメッセージとトラブルシューティング情報が含まれています。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">イベント ID</th>
<th align="left">Source</th>
<th align="left">イベントの記号</th>
<th align="left">メッセージ</th>
<th align="left">トラブルシューティング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>件</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>WebAppSpnError</p></td>
<td align="left"><p>アプリケーション: {SiteName} {VirtualDirectory} に、次のサービスプリンシパル名 (Spn) が含まれていません: {ListOfSpns} アカウントに必要な Spn を登録してください。 {ExecutionAccount}。</p></td>
<td align="left"><p>統合 Windows 認証を成功させるには、必要な Spn が適切である必要があります。 このメッセージは、MBAM アプリケーションに必要な SPN が正しく構成されていないことを示します。 このイベントに含まれる詳細は、詳細情報を提供する必要があります。</p>
<p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md#bkmk-prereqsams" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md#bkmk-prereqsams)">詳細については、「mbam 2.5 Server のスタンドアロンおよび構成マネージャー統合トポロジの前提条件」の「サービスプリンシパル名 (SPN)」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4d</p></td>
<td align="left"><p>Microsoft-Windows-MBAM Web/Operational</p></td>
<td align="left"><p>PerformanceCounterError</p></td>
<td align="left"><p>パフォーマンスカウンターの取得中にエラーが発生しました。</p>
<p>メッセージ: {EventMessage} カテゴリ: {Category Ofperformancecounter} パフォーマンスカウンター: {NameOfPerformanceCounter} インスタンス: {"パフォーマンスカウンターカテゴリインスタンスの名前" 例外: {ExceptionThrown}</p>
<p>トレースメッセージには、実際の例外メッセージが含まれています。ここでは、次の内容について説明します。</p>
<p><strong>ArgumentNullException </strong> : この例外は、要求されたパフォーマンスカウンターの category、counter、またはインスタンスが無効である場合にスローされます。</p>
<p><strong>InvalidOperationException </strong> : 区分名が空の文字列 ( &quot; &quot; ) です。-または counterName は空の文字列 ( &quot; &quot; ) です。</p>
<p>または、要求された読み取り/書き込みアクセス許可の設定がこのカウンターでは無効です。</p>
<p>または、指定されたカテゴリは存在しません (readOnly が true の場合)。</p>
<p>または、指定されたカテゴリが .NET Framework のカスタムカテゴリではありません (readOnly が false の場合)。</p>
<p>または、指定されたカテゴリがマルチインスタンスとしてマークされていて、パフォーマンスカウンターをインスタンス名で作成する必要があります。</p>
<p>-または-instanceName が127文字を超えています。</p>
<p>-または-区分区分と counterName は、さまざまな言語にローカライズされています。</p>
<p><strong>System.componentmodel.annotations </strong> : システム API へのアクセス時にエラーが発生しました。</p>
<p><strong>PlatformNotSupportedException </strong> : プラットフォームは windows 98 または Windows me (me) であり、パフォーマンスカウンターをサポートしていません。</p>
<p><strong>と unauthorizedaccessexception </strong> : 管理者権限なしで実行されているコードがパフォーマンスカウンターを読み取ろうとしました。</p></td>
<td align="left"><p>イベントに含まれるメッセージは、スローされた例外についての詳細情報を提供します。 と unauthorizedaccessexception がスローされた場合は、MBAM 実行アカウント (アプリプール) がパフォーマンスカウンター Api にアクセスできることを確認します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>100</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>AdminServiceRecoveryDbError</p></td>
<td align="left"><p><strong>GetMachineUsers </strong> : データベースからユーザー情報を取得するときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetRecoveryKey </strong> : データベースから回復キーを取得しているときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetRecoveryKey </strong> : データベースからユーザー情報を取得するときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetRecoveryKeyIds </strong> : データベースから回復キー id を取得しているときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetTpmHashForUser </strong> : 回復データベースから TPM ハッシュデータを取得するときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetTpmHashForUser </strong> : 回復データベースから TPM ハッシュデータを取得するときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Querydriverecoverdata </strong> : データベースからドライブの回復データを取得するときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Queryrecoverykeyidforuser </strong> : データベースから回復キー id を取得しているときにエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>QueryVolumeUsers </strong> : データベースからユーザー情報を取得するときにエラーが発生しました。</p></td>
<td align="left"><p>このメッセージは、MBAM 回復データベースとの通信中に例外が発生した場合に記録されます。 例外に関する具体的な詳細については、トレースに含まれている情報を参照してください。</p>
<p>トラブルシューティングの詳細な手順については、TechNet の記事「 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> SQL Server データベースエンジンへの接続に関するトラブルシューティング」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>101</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>Adminservicecomplirunning Dberror</p></td>
<td align="left"><p><strong>GetRecoveryKey </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetRecoveryKeyIds </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>GetTpmHashForUser </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Queryrecoverykeyidforuser </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Querydriverecoverdata </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}</p></td>
<td align="left"><p>このメッセージは、MBAM コンプライアンスデータベースの通信中に例外が発生した場合に記録されます。 例外に関する具体的な詳細については、トレースに含まれている情報を参照してください。</p>
<p>トラブルシューティングの詳細な手順については、TechNet の記事「 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> SQL Server データベースエンジンへの接続に関するトラブルシューティング」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>102</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>AgentServiceRecoveryDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>このメッセージは、MBAM エージェントサービスが回復データベースと通信しようとしたときに、例外が発生したことを示します。 例外に関する特定の情報を取得するには、イベントに含まれるメッセージを参照してください。</p>
<p><a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)">SQL Server データベースエンジンへの接続に関するトラブルシューティングを行う方法については、TechNet の記事「 </a> mbam 回復データベースで接続または実行するために必要な権限があるかどうかを確認する」を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>103</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>AgentServiceError</p></td>
<td align="left"><p>クライアントコンピューターアカウントまたはデータ移行ユーザーアカウントを検出できません。 または</p>
<p>発信者番号認識のアカウント確認に失敗しました。</p></td>
<td align="left"><p>&quot;Postkeyrecoveryinfo &quot; 、 &quot; isrecoverykeyresetrequired &quot; 、 &quot; commitrecoverykeyrest &quot; 、または &quot; GetTpmHash &quot; web メソッドを mbam Agent services で呼び出すたびに、呼び出し元のコンテキストを取得して発信者の資格情報を取得します。 発信者のコンテキストが null または空の場合、MBAM エージェントサービスは、 &quot; クライアントコンピューターアカウントまたはデータ移行ユーザーアカウントを検出できません。&quot;</p>
<p>発信者が &quot; &quot; is コンピューターアカウントであり、呼び出し元がコンピューターアカウントではない場合、または web メソッドが excepting をユーザーアカウントとして使用することを想定していて、発信者がユーザーアカウントであり、発信者がデータ移行グループアカウントのメンバーではない場合は、発信者番号通知のメッセージアカウントの確認失敗が記録されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>104</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>StatusServiceComplianceDbConfigError</p></td>
<td align="left"><p>&quot;レジストリのコンプライアンスデータベース接続文字列が空です。&quot;</p></td>
<td align="left"><p>このメッセージは、コンプライアンス db 接続文字列が無効な場合に記録されます。</p>
<p>レジストリキー HKLM\Software\Microsoft\MBAM Server\Web\ComplianceDBConnectionString の値を確認する</p></td>
</tr>
<tr class="even">
<td align="left"><p>105</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>Statusservicecomplirunning Dberror</p></td>
<td align="left"><p></p></td>
<td align="left"><p>このエラーは、MBAM web サイト/web サービスが Mbamコンプライアンスデータベースに接続できなかったことを示します。</p>
<p>「 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> SQL Server データベースエンジンへの接続に関するトラブルシューティング」を参照して、 </a> IIS アプリプールアカウントが mbam コンプライアンスデータベースに接続できることを確認する方法については、TechNet の記事を参照してください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>106</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>ヘルプデスクエラー</p></td>
<td align="left"><p>URL {url} への要求によって内部エラーが発生しました。 または</p>
<p>実行コンテキスト情報の取得中にエラーが発生しました。 サービスプリンシパル名 (SPN) の登録を確認できません。 または</p>
<p>サービスプリンシパル名 (SPN) 登録の確認中にエラーが発生しました。</p></td>
<td align="left"><p>ヘルプデスクアプリケーションでハンドルされない例外が発生したことを示します。 MBAM 管理者操作チャネルのログエントリを確認して、特定の例外を見つけます。 /</p>
<p>最初のヘルプデスク web サイトの読み込み操作中に、SPN のチェックが実行されます。 SPN を確認するために、ヘルプデスクは、ヘルプデスクの web サイトに対応した実行アカウント情報、IIS Sitename、ApplicationVirtualPath を必要とします。 このエラーメッセージは、これらの1つ以上が無効であるか、存在しない場合に記録されます。 /</p>
<p>このメッセージは、SPN の確認を実行しているときにセキュリティ例外がスローされたことを示します。 「イベントの詳細」セクションに含まれている例外を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>107</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>SelfServicePortalError</p></td>
<td align="left"><p>ユーザーの回復キーを取得しているときにエラーが発生しました。 EventDetails: {ExceptionMessage}-または-</p>
<p>実行コンテキスト情報の取得中にエラーが発生しました。 サービスプリンシパル名 (SPN) の登録を確認できません。 EventDetails: User: {username Id} アプリケーション: {SiteName\ApplicationVirtualPath}-または-</p>
<p>サービスプリンシパル名 (SPN) 登録の確認中にエラーが発生しました。 EventDetails: {ExceptionMessage}</p></td>
<td align="left"><p>回復キーを取得する要求が行われたときに、予期しない例外がスローされたことを示します。 「イベントの詳細」セクションに含まれる例外メッセージを参照してください。 MBAM のヘルプデスクでトレースが有効になっている場合は、「トレースデータ」を参照して詳細な例外メッセージを取得してください。 /</p>
<p>最初の読み込み操作では、セルフサービスポータル (SSP) は、セルフサービス web サイトに対応する実行アカウント情報、IIS Sitename、および ApplicationVirtualPath を取得して、SPN を確認します。 このエラーメッセージは、これらのうち1つ以上が無効な場合に記録されます。 /</p>
<p>このメッセージは、SPN の確認を実行しているときにセキュリティ例外がスローされたことを示します。 「イベントの詳細」セクションに含まれている例外を参照してください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>108</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>Domainコントローラーエラー</p></td>
<td align="left"><p>ドメイン名 {DomainName} の解決中にエラーが発生しました。メモリ割り当てエラーが発生しました。 または</p>
<p>DsGetDcName メソッドを呼び出せませんでした。 EventDetails: {ExceptionMessage}</p></td>
<td align="left"><p>ドメイン名を解決するために、MBAM は &quot; DsGetDcName &quot; windows API を活用しています。 このメッセージは &quot; 、DsGetDcName が &quot; &quot; &quot; メモリ割り当てエラーを示す ERROR_NOT_ENOUGH_MEMORY したときに記録されます。 /</p>
<p>このメッセージ &quot; &quot; は、ホストシステムで DsGetDcName API メソッドが利用できないことを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>109</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>WebAppRecoveryDbError</p></td>
<td align="left"><p>回復データベースの構成の読み取り中にエラーが発生しました。 回復データベースへの接続文字列が構成されていません。 メッセージ: {message}-または</p>
<p><strong>DoesUserHaveMatchingRecoveryKey </strong> : ユーザーの回復キー id の取得中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Querydriverecoverdata </strong> : ドライブ回復データの取得中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Queryrecoverykeyidforuser </strong> : ユーザーの回復キー id の取得中にエラーが発生しました。 メッセージ: {message}-または</p>
<p>回復データベースから TPM パスワードハッシュを取得しているときにエラーが発生しました。 EventDetails: {ExceptionMessage}</p></td>
<td align="left"><p>このメッセージは、HKLM\Software\Microsoft\MBAM Server\Web\RecoveryDBConnectionString の回復データベース接続文字列情報が無効であることを示し &quot; &quot; ます。 指定されたレジストリキーの値を確認します。 /</p>
<p>残りのメッセージが記録されている場合は、TechNet の記事に記載されているトラブルシューティング手順を参照してください <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 。 SQL Server データベースエンジンに接続し </a> て、アプリプールの資格情報を使って、IIS サーバーから Mbam 回復データベースへの接続が可能かどうかを確認する方法について説明します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>110</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>WebAppComplianceDbError</p></td>
<td align="left"><p>コンプライアンスデータベースの構成を読み取り中にエラーが発生しました。 コンプライアンスデータベースへの接続文字列が構成されていません。 または</p>
<p><strong>GetRecoveryKeyForCurrentUser </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Queryrecoverykeyidforuser </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}-または</p>
<p><strong>Queryrecoverykeyidforuser </strong> : コンプライアンスデータベースへの監査イベントのログ記録中にエラーが発生しました。 メッセージ: {message}</p></td>
<td align="left"><p>このメッセージは、HKLM\Software\Microsoft\MBAM Server\Web\ComplianceDBConnectionString でのコンプライアンス db 接続文字列情報が無効であることを示し &quot; &quot; ます。 上のレジストリキーに対応する値を確認します。 /</p>
<p>残りのメッセージが記録されている場合は、TechNet の記事に記載されているトラブルシューティング手順を参照してください <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 。 SQL Server データベースエンジンに接続し </a> て、アプリプールの資格情報を使って、IIS サーバーから Mbam コンプライアンスデータベースへの接続が可能かどうかを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>111</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>WebAppDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>これらのエラーは、次の2つの条件のいずれかを示します。</p>
<ul>
<li><p>MBAM websites/web サイトは、Mbamコンプライアンスまたは MBAMRecovery データベースに接続できませんでした</p></li>
<li><p>MBAM websites/web サイトの実行アカウント (アプリプールアカウント) で、Mbamコンプライアンスまたは MBAMRecovery データベースで GetVersion のストアドプロシージャを実行できませんでした</p></li>
</ul>
<p>イベントに含まれるメッセージは、例外に関する詳細情報を提供します。</p>
<p>「 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> SQL Server データベースエンジンへの接続に関するトラブルシューティング」を参照して、 </a> mbam 実行アカウント (アプリプールアカウント) が mbam コンプライアンス/回復データベースに接続できるかどうかを確認し、GetVersion ストアドプロシージャを実行するための権限が与えられていることを確認する方法について説明します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>112</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/Admin</p></td>
<td align="left"><p>WebAppError</p></td>
<td align="left"><p>サービスプリンシパル名 (SPN) 登録の確認中にエラーが発生しました。 EventDetails: {ExceptionMessage}</p></td>
<td align="left"><p>SPN の確認を実行するために、MBAM は Active Directory を照会して、Spn でマップされた実行アカウントの一覧を取得します。 MBAMApplicationHost.configを照会して、 &quot; &quot; mbam web サイトバインドを取得します。 このエラーメッセージは、MBAM が Active Directory と通信できなかったか、または applicationHost.config ファイルを読み込めなかったことを示します。</p>
<p>実行アカウント (アプリプールアカウント) に、AD または ApplicationHost.config ファイルに対するクエリのアクセス許可が与えられていることを確認します。 ApplicationHost.config ファイル内のサイトバインディングエントリも確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>200</p></td>
<td align="left"><p>Microsoft-Windows-MBAM Web/Operational</p></td>
<td align="left"><p>Helpデスク情報</p></td>
<td align="left"><p>管理 web サイトアプリケーションが正常に見つかり、サポートされているバージョンの回復データベースに接続されました。 または</p>
<p>管理 web サイトアプリケーションが正常に見つかり、サポートされているバージョンのコンプライアンスデータベースに接続されました。</p></td>
<td align="left"><p>MBAM ヘルプデスクの web サイトから回復/コンプライアンスデータベースへの接続に成功したことを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>201</p></td>
<td align="left"><p>Microsoft-Windows-MBAM Web/Operational</p></td>
<td align="left"><p>SelfServicePortalInformation</p></td>
<td align="left"><p>セルフサービスポータルアプリケーションが見つかり、サポートされているバージョンの回復データベースに接続されました。 または</p>
<p>セルフサービスポータルアプリケーションが正常に見つかり、サポートされているバージョンのコンプライアンスデータベースに接続されました。</p></td>
<td align="left"><p>MBAM セルフサービスポータルからの回復/コンプライアンスデータベースへの正常な接続を示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>202</p></td>
<td align="left"><p>Microsoft-Windows-MBAM Web/Operational</p></td>
<td align="left"><p>WebAppInformation</p></td>
<td align="left"><p>アプリケーションの Spn が正しく登録されている。</p></td>
<td align="left"><p>MBAM ヘルプデスクの web サイトに必要な Spn が、実行中のアカウントに対して適切に登録されていることを示します。</p></td>
</tr>
</tbody>
</table>

 


## 関連トピック


[MBAM 2.5 テクニカル リファレンス](technical-reference-for-mbam-25.md)

[クライアントのイベント ログ](client-event-logs.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





