---
title: UE-V 2.1 SP1 の新機能
description: UE-V 2.1 SP1 の新機能
author: dansimp
ms.assetid: 9a40c737-ad9a-4ec1-b42b-31bfabe0f170
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1f4b6210d95795c352a7ef1402b0353c6f52774b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827427"
---
# UE-V 2.1 SP1 の新機能


User Experience Virtualization 2.1 SP1 は、UE-V 2.1 と比較して、これらの新機能を提供します。 [Microsoft User Experience Virtualization (ue-v) 2.1 SP1 のリリースノート](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)には、UE-V 2.1 SP1 のリリースに関する詳細情報が記載されています。

## Windows 10 のサポート


UE-V 2.1 SP1 は、以前のバージョンの UE-V でサポートされているのと同じソフトウェアに加えて、Windows 10 のサポートを追加します。

### Microsoft Azure との互換性

Windows 10 では、エンタープライズユーザーは、Windows アプリの設定と Windows オペレーティングシステムの設定を OneDrive ではなく Azure に同期することができます。 オンプレミスのドメインに参加しているコンピューターでのみ、Windows 10 enterprise の同期機能を UE-V と共に使用できます。 Windows 10 と UE-V の共存を有効にするには、各クライアントまたはグループポリシーのいずれかの PowerShell を使用して、次の UE-V テンプレートを無効にする必要があります。

[Microsoft ユーザーエクスペリエンスの仮想化] ノードの下にある [グループポリシー] で、次のポリシー設定を構成します。

-   "Windows アプリを同期しない" を有効にする

-   "Windows の設定の同期" を無効にする

### Windows 10 のサポートで設定の同期動作が変更されました

UE-V 2.1 SP1 では、Windows 10 デバイス間のタスクバーの設定が移動します。 ただし、UE-V は、以前のオペレーティングシステムが実行されている Windows 10 デバイスとデバイスとの間で、タスクバーの設定を同期しません。

また、UE-V 2.1 SP1 では、Windows 10 での Microsoft 電卓と以前のオペレーティングシステムの Microsoft 電卓の間での設定は同期されません。

## ローミングネットワークプリンターに追加されたサポート


UE-V 2.1 SP1 では、ネットワークプリンターをデバイス間でローミングできるため、ネットワーク上のデバイスにログオンしたときに、ユーザーはネットワークプリンターにアクセスできます。 これには、既定として設定したプリンターのローミングも含まれます。

UE-V でのプリンターローミングには、次のいずれかのシナリオが必要です。

-   プリントサーバーは、新しいデバイスにローミングしたときに必要なドライバーをダウンロードできます。

-   ローミングネットワークプリンターのドライバーは、そのネットワークプリンターにアクセスする必要があるすべてのデバイスにプレインストールされています。

-   プリンタードライバーは、Windows Update から入手できます。

**注** UE-V プリンターローミング機能では、両面印刷などのプリンター設定や基本設定はローミング**されません**。

 

## Office 2013 の設定場所テンプレート


UE-V 2.1 および 2.1 SP1 には、Outlook 署名のサポートが強化された Microsoft Office 2013 設定場所テンプレートが含まれています。 新規、返信、転送メールの既定の署名設定の同期が追加されました。 ユーザーは、既定の署名設定を選択する必要がなくなりました。

**注** ユーザーが Outlook の署名を同期するすべてのデバイスに対して、Outlook プロファイルを作成する必要があります。 プロファイルがまだ作成されていない場合は、ユーザーがそれを作成し、そのデバイスで Outlook を再起動して、署名の同期を有効にすることができます。

 

以前の UE-V には、自動的に配布され、UE-V エージェントに登録された Microsoft Office 2010 設定場所テンプレートが含まれていました。 UE-V 2.1 は Office 365 と連携して、office 2013 の設定が Office 365 によってローミングされているかどうかを確認します。 設定が Office 365 によってローミングされている場合は、UE-V でローミングされません。 [Office 2013 のユーザーとローミングの設定の概要](https://go.microsoft.com/fwlink/p/?LinkID=391220)については、こちらを参照してください。

UE-V 2.1 を使用して設定の同期を有効にするには、次のいずれかの操作を行います。

-   グループポリシーを使用して Office 365 の同期を無効にする

-   Office 2013 のインストール中に Office 365 の同期操作を有効にしない

UE-V 2.1 は[、office 2013 と office 2010 のテンプレートを](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)同梱しています。 このリリースでは、Office 2007 テンプレートが削除されます。 ユーザーは、引き続き UE-V 2.0 以前の Office 2007 テンプレートを使うことができます。また、[ここ](https://go.microsoft.com/fwlink/p/?LinkID=246589)に記載されている ue-v テンプレートギャラリーからテンプレートを取得することもできます。






## 関連トピック


[UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

[UE-V の展開を準備する](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

 

 





