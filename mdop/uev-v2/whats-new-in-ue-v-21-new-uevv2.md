---
title: UE-V 2.1 の新機能
description: UE-V 2.1 の新機能
author: dansimp
ms.assetid: 7f385183-7d97-4602-b19a-baa710334ade
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7816fc8309a29347048172b2104750140c483587
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826264"
---
# UE-V 2.1 の新機能


ユーザーエクスペリエンスの仮想化2.1 には、UE-V 2.0 と比較して、これらの新機能が用意されています。 [Microsoft User Experience Virtualization (ue-v) 2.1 のリリースノート](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)には、ue-v 2.1 リリースに関する詳細情報が記載されています。

## Office 2013 の設定場所テンプレート


UE-V 2.1 には、Outlook 署名のサポートが強化された Microsoft Office 2013 の設定場所テンプレートが含まれています。 UE-V 2.1 では、署名データはユーザーデバイス間で同期されます。 新規、返信、転送メールの既定の署名設定の同期が追加されました。 ユーザーは、既定の署名設定を選択する必要がなくなりました。

**注** ユーザーが Outlook の署名を同期するすべてのデバイスに対して、Outlook プロファイルを作成する必要があります。 プロファイルがまだ作成されていない場合は、ユーザーがそれを作成し、そのデバイスで Outlook を再起動して、署名の同期を有効にすることができます。

 

以前の UE-V には、自動的に配布され、UE-V エージェントに登録された Microsoft Office 2010 設定場所テンプレートが含まれていました。 UE-V 2.1 は Office 365 と連携して、office 2013 の設定が Office 365 によってローミングされているかどうかを確認します。 設定が Office 365 によってローミングされている場合は、UE-V でローミングされません。 [Office 2013 のユーザーとローミングの設定の概要](https://go.microsoft.com/fwlink/p/?LinkID=391220)については、こちらを参照してください。

UE-V 2.1 を使用して設定の同期を有効にするには、次のいずれかの操作を行います。

-   グループポリシーを使用して Office 365 の同期を無効にする

-   Office 2013 のインストール中に Office 365 の同期操作を有効にしない

UE-V 2.1 は[、office 2013 と office 2010 のテンプレートを](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)同梱しています。 このリリースでは、Office 2007 テンプレートが削除されます。 ユーザーは、引き続き UE-V 2.0 以前の Office 2007 テンプレートを使うことができます。また、[ここ](https://go.microsoft.com/fwlink/p/?LinkID=246589)に記載されている ue-v テンプレートギャラリーからテンプレートを取得することもできます。

## 分散ファイルシステムの名前空間ユーザーの修正


UE-V では、Syncproviderping が有効になっている UE-V 構成を追加することで、分散ファイルシステム名前空間 (DFSN) のサポートが強化されています。 PowerShell または WMI を使ってこの構成を無効にすると、ユーザーは UE-V ping を無効にすることができます。 DFSN サーバーを使用すると、これらのサーバーが ping に応答しないため、UE-V ping でエラーが発生します。 応答不可は、UE-V が設定を同期しないようにします。 UE-V による ping を無効にすると、UE-V の同期が正常に機能します。

UE-V ping を無効にするには、次の PowerShell コマンドレットを使用します。

``` syntax
Set-UevConfiguration -DisableSyncProviderPing
```

## 資格情報の同期


UE-V 2.1 を使用すると、ユーザーは Windows Credential Manager に保存されている資格情報と証明書を同期することができます。 このコンポーネントは既定では無効になっています。 このコンポーネントを有効にすると、ユーザーはドメインの資格情報と証明書を同期したままにすることができます。ユーザーはデバイスで1回サインインすることができます。これらの資格情報は、そのユーザーが UE-V 対応のすべてのデバイスでローミングします。 [Ue-v 2.1 で資格情報を管理](https://technet.microsoft.com/library/dn458932.aspx#creds)する詳細情報を提供します。

**注** Windows 8 以降では、Credential Manager には web 資格情報が含まれています。 これらの資格情報は、ユーザーのデバイス間で同期されません。

 

## UE-V と Microsoft アカウントの同期


UE-V は、Microsoft アカウントの同期とも呼ばれる、OneDrive との同期設定がオンになっているかどうかを検出します。 Microsoft アカウントが設定を同期するように構成されていない場合、UE-V は、Windows アプリ、AppX パッケージ、および Windows デスクトップのデバイス間の設定を同期します。 これにより、ユーザーは、エンタープライズファイアウォールの外部との同期を行わずに、ストアアプリ、音楽、画像、その他の Microsoft アカウント対応アプリケーションにアクセスできます。 UE-V は、グループポリシーが OneDrive との設定の同期を停止するかどうかを確認します。または、ユーザーがユーザーコントロールで**このコンピューターの設定の同期**を無効にしているかどうかを確認します。

## 外部の SyncMethod のサポート


**外部**と呼ばれる新しい[syncmethod の構成](https://technet.microsoft.com/library/dn554321.aspx)では、ユーザーコンピューター上のローカルフォルダーに ue-v 設定が書き込まれる場合、任意の外部同期エンジン (OneDrive For business、ワークフォルダー、Sharepoint、Dropbox など) を使って、これらの設定をユーザーがアクセスするさまざまなコンピューターに適用することができます。

## VDI モードのサポートの強化


UE-V 2.1 には、エンドユーザー間で共有される[VDI セッションのサポート](https://technet.microsoft.com/library/dn458932.aspx#vdi)が含まれています。 管理者として、特殊な VDI テンプレートを登録して構成することができます。これにより、UE-V は永続的でない VDI セッションに対してすべての機能をそのまま維持できます。

**注** 非永続的な VDI セッションで VDI モードを有効にしていない場合、バックアップ/復元や LKG などの一部の機能は動作しません。

 

## 管理のバックアップと復元


Set-UevTemplateProfile PowerShell コマンドレットを使用して、**バックアップ**または**ローミング (既定)** プロファイルに設定場所テンプレートを配置することにより、ユーザーが新しいデバイスを採用したときに追加の設定を復元することができます。 これにより、ユーザー設定に加えて、コンピューターの設定を新しいコンピューターと同期することができます。 バックアッププロファイルに割り当てられたテンプレートは、そのデバイスにバックアップされ、デバイスごとに構成されます。 [Ue-v で管理バックアップと復元を管理](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)する詳細については、「x」を参照してください。

## 追加の Windows 設定の同期


UE-V は、タッチキーボードのパーソナライズとスペルチェック辞書を同期し、最近のアプリと画面の端の設定のアプリ切り替えを有効にして、Windows 8 と Windows 8.1 デバイスの間で同期します。






## 関連トピック


[UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

[UE-V の展開を準備する](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

 

 





