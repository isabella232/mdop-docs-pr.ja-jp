---
title: App-V 5.0 SP2 リリース ノート
description: App-V 5.0 SP2 リリース ノート
author: dansimp
ms.assetid: fe73139d-240c-4ed5-8e59-6ae76ee8e80c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5e885e67023d0e5c1e36aeb340933c64ae92610e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813330"
---
# App-V 5.0 SP2 リリース ノート


**これらのリリースノートで特定の問題を検索するには、CTRL キーを押しながら F キーを押します。**

App-v 5.0 SP2 をインストールする前に、これらのリリースノートをよくお読みください。

これらのリリースノートには、App-v 5.0 SP2 を正常にインストールするために必要な情報が含まれています。 リリースノートには、製品ドキュメントに記載されていない情報も含まれています。 これらのリリースノートと他の App-v 5.0 ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## 製品ドキュメントについて


App-v 5.0 ドキュメントの詳細については、Microsoft TechNet の「App-v 5.0 のホームページ」を参照してください。

## フィードバックの提供


弊社では、App-v 5.0 についてご意見をお寄せしています。 にフィードバックを送信でき <mdopdocs@microsoft.com> ます。

**注** このメールアドレスはサポートチャネルではありませんが、お客様のフィードバックは、今後のドキュメントや製品リリースの将来の変更を計画するのに役立ちます。

 

MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。

新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。

## アプリケーションの仮想化 5.0 SP2 の修正プログラムパッケージ4の既知の問題


### Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をアンインストールした後、パッケージが機能しなくなる

Application virtualization 5.0 SP2 の修正プログラムパッケージ4を適用したときに公開されるパッケージは、Application Virtualization 5.0 SP2 の修正プログラムパッケージ4が削除された場合に機能しなくなります。

ところ

次のフォルダーが存在する場合は、削除する必要があります。

**% localappdata%**  \\ **Microsoft**  \\ **AppV**  \\ **クライアント**  \\ **VFS**  \\ 公開された各パッケージの** &lt; パッケージ ID &gt; ** 。

**注** このフォルダーを削除するには、管理者特権が必要です。

 

スクリプトを使用するには、コンピューター上の各ユーザーアカウントと、Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をインストールした後に公開された各パッケージ id について、次の操作を行います。

`Rd /s /q “%systemdrive%\users\[UserName]\AppData\Local\Microsoft\AppV\Client\VFS\[Package ID]`

-   ショートカットは、前のセクションのディレクトリからフォルダーを削除した後でも、ユーザーセッションのままになり、ショートカットをクリックしてアプリケーションを再実行することができます。 アプリケーションを再公開する必要はありません。

-   この問題は、Microsoft 2013 など、公開されたパッケージとグローバルに公開されたパッケージの両方に対して発生します。 どちらの種類のパッケージでも、フォルダーを削除する必要があります。

-   ローミングアプリデータ (**% appdata%**) の VFS フォルダーを削除する必要はありません。 **% Localappdata%** のみを削除する必要があります。

### Microsoft Office 統合で間違ったファイルシステムの場所が参照されている

Microsoft Office の統合で、誤ったファイルシステムの場所 (Groove.exe のエラーメッセージ) が表示されます。

ところ

以下の方法のうちのいずれか 1 つを使用します。

1.  アップグレード後に、スタートアップフォルダーのショートカットを削除します。

2.  スクリプトを使用して、スタートアップフォルダーのショートカットを変更します。

3.  展開構成ファイルを使用して、統合ルートへのショートカットのターゲットを指定します。

### <a href="" id="-------------hotfix-package-4-for-application-virtualization-5-0-sp2-installer-can-take-a-long-time"></a> アプリケーションの仮想化 5.0 SP2 インストーラーの修正プログラムパッケージ4には長い時間がかかることがある

Application Virtualization 5.0 SP2 インストーラーの修正プログラムパッケージ4では、既存のパッケージキャッシュに保存されているファイルの数によって、時間がかかる場合があります。

アプリケーションの仮想化 5.0 SP2 インストールの修正プログラムパッケージ4で関連付けられているパッケージのセキュリティ記述子を更新すると、インストールにかかる時間が大幅に大きく影響します。 以前は、インストールのインストールは期間内に標準でした。 ただし、これは、パッケージキャッシュにステージングしたファイルの数に依存するようになりました。

回避策: なし

### JIT パッケージを使用している場合に、Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をアンインストールできない

Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をインストールして、ジャストインタイム仮想化 (JIT) を使用しているときに、この修正プログラムをアンインストールしようとすると、次のすべての条件に該当する場合、操作は失敗します。

-   Windows Installer ファイル (.msi) を使ってインストールした後、Microsoft インストーラーの修正プログラムファイル (.msp) を使用して更新プログラムを適用します。

-   コントロールパネルの [プログラムの追加と削除] を使用して、更新プログラムをアンインストールしようとしています。

-   コンピューターで JIT 対応パッケージが実行されています。

回避策: 次の手順を実行します。

1.  Windows PowerShell を開き、次のコマンドを実行します。

    -   **インポート-モジュール appvclient**

    -   **Get-AppvClientPackage |AppvClientPackage**

2.  [プログラムの追加と削除を使用して更新プログラムをアンインストールする。

## App-v 5.0 SP2 の既知の問題


### <a href="" id="bkmk-folderredirection"></a>App-v クライアントフォルダーリダイレクションが、ファイルを% AppData% から% に移動することができない場合がある

% AppData% が、フォルダーリダイレクション用に構成した共有ネットワークフォルダーである場合、コンピューターを切り替えるか、またはログオフしてもう一度ログインするときに、エンドユーザーが AppData (ローミング) に加えた変更が失われる可能性があります。 このエラーは、最後の既知のアップロードを示すレジストリキー (AppDataTime) がローカルにキャッシュされた AppData との同期を終了するために発生します。

回避策: エンドユーザーがログオンまたはログオフしたときに、関連するパッケージごとに次のレジストリキーを手動で削除します。

``` syntax
HKCU\Software\Microsoft\AppV\Client\Packages\<PACKAGE_GUID>\AppDataTime
```

アプリがログインした後、エンドユーザーがパッケージでアプリケーションを初めて起動すると、アプリ-V は、% LocalAppData% が既に最新の状態である場合でも、zip% AppData% を強制的にダウンロードします。

### <a href="" id="-------------app-v-5-0-service-pack-2--app-v-5-0-sp2--does-not-include-a-new-version-of-the-app-v-server"></a> App-v 5.0 Service Pack 2 (App-v 5.0 SP2) には、新しいバージョンの App-v Server が含まれていない

App-v 5.0 SP2 には、新しいバージョンの App-v Server が含まれていません。 Windows 8.1 を実行している環境で App-v 5.0 SP2 クライアントを展開し、App-v インフラストラクチャを使ってクライアントを管理することを計画している場合は、 [Microsoft Application Virtualization 5.0 Service Pack 1 用の修正プログラムパッケージ2を](https://go.microsoft.com/fwlink/?LinkId=386634)インストールする必要があります。 (https://go.microsoft.com/fwlink/?LinkId=386634)

次のいずれかの方法を使用して App-v 5.0 SP2 クライアントを実行して管理している場合、クライアントの更新は必要ありません。

-   スタンドアロン モード。

-   Configuration Manager

-   サードパーティの ESD。

App-v 5.0 SP2 クライアントは、Windows 8.1 と完全に互換性があります。

回避策: なし。

## リリースノートの著作権情報


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。 その他のすべての商標は、該当する所有者に帰属します。








## 関連トピック


[App-V 5.0 SP2 について](about-app-v-50-sp2.md)

 

 





