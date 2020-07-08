---
title: MBAM 1.0 のリリース ノート
description: MBAM 1.0 のリリース ノート
author: dansimp
ms.assetid: d82fddde-c360-48ef-86a0-d9b5fe066861
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 705fd1b936da1454081dd14a7f075f642fc4a405
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826027"
---
# MBAM 1.0 のリリース ノート


**これらのリリースノートで特定の問題を検索するには、CTRL キーを押しながら F キーを押します。**

Microsoft BitLocker の管理と監視 (MBAM) をインストールする前に、これらのリリースノートをよくお読みください。

これらのリリースノートには、MBAM の正常なインストールに必要な情報が含まれています。 リリースノートには、製品ドキュメントに記載されていない情報も含まれています。 リリースノートとその他の MBAM ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## 製品ドキュメントについて


MBAM ドキュメントの詳細については、「Microsoft TechNet の MBAM ホームページ」を参照してください。

MBAM ドキュメントのダウンロード可能なコピーを入手するには、 <https://go.microsoft.com/fwlink/p/?LinkId=225356> Microsoft ダウンロードセンターを参照してください。

## フィードバックの提供


当社では、MBAM についてのご意見をお寄せしています。 にフィードバックを送信でき <mdopdocs@microsoft.com> ます。

**注** このメールアドレスはサポートチャネルではありませんが、お客様のフィードバックは、今後のドキュメントや製品リリースの将来の変更を計画するのに役立ちます。

 

MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。

新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。

## MBAM 1.0 の既知の問題


このセクションには、MBAM セットアップとインストールに関する既知の問題に関するリリースノートが記載されています。

### <a href="" id="if-you-select-the--use-a-certificate-to-encrypt-the-network-communication--option-during-setup--existing-database-connections-and-dependent-applications-can-stop-functioning-"></a>セットアップ時に [証明書を使用してネットワーク通信を暗号化する] オプションを選択した場合、既存のデータベース接続と依存アプリケーションが機能しなくなることがある

回復とハードウェアデータベースまたはコンプライアンスステータスデータベース機能のいずれかをインストールした後は、**暗号化されたネットワーク通信**用に mbam を構成できます。 暗号化されたネットワーク通信用に MBAM を設定すると、MBAM Setup は、該当するデータベースと、管理/監視サーバーとコンプライアンスおよび監査レポートサーバー機能の両方の間の通信に Secure Sockets Layer (SSL) を使用するように SQL Server データベースエンジンのインスタンスを構成します。

-   SQL Server データベースエンジンのインスタンスが SSL を使用するように構成されていない場合は、MBAM セットアップでその処理が構成されます。 これにより、SQL Server データベースエンジンのインスタンスで MBAM 以外のデータベースを使用しようとしているアプリケーションが、データベースと通信できなくなることがあります。

-   SQL Server データベースエンジンのインスタンスが既に SSL を使用するように構成されている場合は、ユーザーがセットアップ時に選択した証明書を使用するように構成されます。 この証明書が既に使用されていたものと異なる場合は、SQL Server データベースエンジンのインスタンスで SQL Server データベースを使用するアプリケーションが実行されないようにすることができます。

**回避策:**-

### ローカル管理者アカウントを使用している場合、インストール中に MBAM セットアップが失敗する

ローカル管理者アカウントを使用している場合、MBAM セットアップが失敗します。 ログファイルには、次の情報が含まれています。

``` syntax
Locating group 'MBAM Report Users'
Adding <GUID>' to group 'MBAM Report Users'
Locating group 'MBAM Recovery and Hardware DB Access'
Adding 'S-1-5-20' to group 'MBAM Recovery and Hardware DB Access'
Exception: A new member could not be added to a local group because the member has the wrong account type.
 
  StackTrace:    at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SDSUtils.ApplyChangesToDirectory(Principal p, StoreCtx storeCtx, GroupMembershipUpdater updateGroupMembership, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.Update(Principal p)
   at Microsoft.Windows.Mdop.BitlockerManagement.Setup.Groups.CreateGroupsDeferred(Session session)
  InnerException:Exception: A new member could not be added to a local group because the member has the wrong account type.
 
    InnerException:StackTrace:    at System.DirectoryServices.AccountManagement.UnsafeNativeMethods.IADsGroup.Add(String bstrNewItem)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
CustomAction MbamCreateGroupsDeferred returned actual error code 1603 (note this may not be 100% accurate if translation happened inside sandbox)
Action ended 11:41:29: InstallExecute. Return value 3.
```

**回避策:** MBAM をインストールする場合は、サーバーコンピューターの管理者資格情報を持つドメインアカウントを使用します。

### MBAM セットアップ [ネットワーク通信を暗号化しない] を選択した場合、SSL を使用しないように SQL Server データベースエンジンのインスタンスを再設定します。

回復とハードウェアのデータベースまたはコンプライアンスステータスのデータベースのいずれかをインストールする場合は、[暗号化された**ネットワーク通信**] を選択して、[セットアップ] を使って mbam を構成することができます。 ネットワーク通信を暗号化しないことにした場合、MBAM セットアップは、SSL を使用しないように SQL Server データベースエンジンのインスタンスを再構成します。

-   SQL Server データベースエンジンのインスタンスが既に SSL を使用するように構成されている場合、MBAM セットアップは、SQL Server データベースエンジンのインスタンスの SSL を無効にします。 これにより、SQL Server データベースエンジンのインスタンスの MBAM データベースに関連していないデータベースを使用するアプリケーション間の通信のセキュリティが変更されます。

**回避策:**-

### インターネットインフォメーションサービス (IIS) 管理スクリプトとツール web サーバー機能の前提条件が見つからない

MBAM セットアップは IIS 管理スクリプトとツール web サーバー機能に依存していますが、必須ではありません。 サーバーのセットアップでは、この機能が見つからない場合に MBAM をインストールできます。 ただし、これにより、backup service MBAM VSS Writer は、Windows Management Instrumentation (WMI) とインターネットインフォメーションサービス (IIS) プロバイダーを見つけることができないため、起動して停止します。 この状態にはエラーメッセージはありません。ただし、イベントログで発生します。 IIS 管理スクリプトとツールを使用せずに MBAM をインストールすると、バックアップ操作が MBAM で実行されなくなります。

**回避策:** MBAM セットアップを開始する前に、IIS 管理スクリプトとツール web サーバー機能がインストールされていることを確認します。

### <a href="" id="mbam-setup-stops-responding-during-the--installing-selected-features--phase-when-setup-is-configured-to-use-a-certificate"></a>セットアップが証明書を使用するように構成されているときに、MBAM セットアップが "選択された機能をインストールしています" フェーズで応答を停止する

MBAM セットアップの [選択し**た機能をインストール**しています。をインストールしています。セットアップが終了しました。 これは、[**証明書を使用してネットワーク通信を暗号化する**] オプションを選択した後、回復とハードウェアデータベースまたはコンプライアンスステータスデータベースのインストール中に発生します。 さらに、SQL Server データベースエンジンのインスタンスがセットアップ時に指定された証明書にアクセスできない場合、MBAM セットアップは応答を停止します。

**回避策:** 証明書のアクセス許可を更新して、SQL Server データベースエンジンの該当するインスタンスの Windows サービスで証明書にアクセスできるようにします。 データベースエンジンで証明書を使用するために、SQL Server データベースエンジンのインスタンスを実行するアカウントを変更することもできます。 証明書のアクセス許可を確認するには、コマンドプロンプトで次のコマンドを入力します。 **certutil-v-ストア MY**

### SQL Server Reporting Services をインストールすると、MBAM セットアップが一時停止する

MBAM のインストール中に、SQL Server Reporting Services (SSRS) のインスタンスを選択すると、SSRS インスタンスが利用できないか、または正しく構成されていないと、MBAM セットアップが SSRS インスタンスと通信しようとしていて、最大1分間一時停止することがあります。

**回避策:** セットアッププログラムが SSRS のインスタンスに接続しようとしている間、MBAM セットアップが再開されるまで、少なくとも1分待ちます。

### <a href="" id="administration-and-monitoring-server-does-not-run-after-setup-"></a>セットアップ後に管理と監視サーバーが実行されない

MBAM セットアップで管理と監視のサーバー機能が正常にインストールされると、mbam 管理者の web サイトにアクセスしようとしたときに、エラーメッセージが表示されます。 この問題は、次のいずれかの理由で発生します。

-   MBAM インストール後に、管理サーバーと監視サーバーの1つ以上の前提条件が削除されました。

-   1つ以上の前提条件がサーバーにインストールされた後、MBAM セットアップを実行する前に削除されました。

**回避策:** MBAM のマニュアルを確認して、すべての MBAM 前提条件がインストールされていることを確認します。

### セットアップ中に [ドキュメント] リンクをクリックすると、セットアップの完了後にアプリケーションエラーが表示される

セットアップでドキュメントのリンクをクリックし、[**キャンセル]** または [**完了**] をクリックしてセットアッププログラムを閉じると、アプリケーションエラーメッセージが表示されます。 この問題は、Windows タスクスケジューラのアクセス違反エラーが原因で発生します。

**回避策:**-. このエラーは無視してかまいません。

### 失敗した MBAM セットアップで新しいデータベースが削除されない

MBAM セットアップに失敗した場合、セットアップで新しく作成したデータベースが削除されないことがあります。 これにより、以降のインストール時にエラーが発生する可能性があります。

**回避策:** 以降のインストール時にデータベースインスタンスに別の名前を選択します。

### MBAM セットアップで、ネットワーク負荷分散の有効なクラスター証明書が認識されない

MBAM 管理と監視サーバーのインストール中に、[ネットワーク暗号化] オプションが選択されていると、クラスター証明書は有効な証明書として認識されません。 データベースとの通信用の証明書がインストールされていても、負荷分散クラスターによる通信が拒否される場合は、有効として認識されます。

**回避策:** 証明書に関連付けられている証明書失効リスト (CRL) がアクセス可能であることを確認するか、または CRL を使用して検証を必要としない証明書を使用します。

## リリースノートの著作権情報


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。 その他のすべての商標は、該当する所有者に帰属します。



## 関連トピック


[MBAM 1.0 の概要](about-mbam-10.md)

 

 





