---
title: UE-V 2.0 の新機能
description: UE-V 2.0 の新機能
author: dansimp
ms.assetid: 5d852beb-f293-4e3a-a33b-c40df59a7515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a7566bd82432dcf7e4c46e1fa3e66e55d1515b79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824964"
---
# UE-V 2.0 の新機能


Microsoft User Experience Virtualization (UE-V) 2.0 では、UE-V 1.0 と比べてこれらの新機能が提供されます。 [Microsoft User Experience Virtualization (ue-v) 2.0 のリリースノート](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)には、ue-v 2.0 リリースに関する詳細情報が記載されています。

## クライアント側キャッシュ (CSC) は不要になりました


このバージョンの UE-V は、**同期プロバイダー**を紹介しています。これにより、Windows のオフラインファイル機能の要件が、クライアント側の設定のキャッシュをサポートするように置き換えられます。

UE-V は、アプリケーションを開いたり閉じたりしたとき、または Windows がロックまたはロック解除されたとき、またはログオンまたはログオフしたときにのみ設定を同期するために使用されます。

-   "**Trigger events**" を使用してローカルアプリケーションと Windows の設定をアウトバンドで同期します。

-   スケジュールされた**タスク**を使用して、エンタープライズ要件に合わせて選んだ任意の間隔 (既定では30分ごと) に設定のストレージパッケージを同期します。

特定の条件を使うと、同期の頻度が高くなります。

-   ユーザーが新しい会社設定センターアプリケーションで [**今すぐ同期**] ボタンをクリックすると、設定が同期されます。

-   同期プロバイダーは、スケジュールされた同期タスクを待つことなく、1つのアプリケーションで開始することもできます。 たとえば、アプリケーションが閉じている場合、設定の変更はローカルキャッシュに書き込まれ、同期プロバイダープロセスは非同期的に実行され、新しい設定の変更は設定の保存場所に移動されます。

## Windows アプリの同期


Windows アプリの開発者は、どの設定を同期するかを定義できます。これらの設定は、UE-V を使ってキャプチャおよび同期できるようになりました。

既定では、UE-V は、windows 8 と Windows 8.1 に含まれている多くの Windows アプリの設定を同期します。 同期されたアプリの一覧は、Windows PowerShell、Windows Management Instrumentation (WMI)、またはグループポリシーを使って変更できます。

**注** UE-V は、ドメインユーザーがサインイン資格情報を Microsoft アカウントにリンクしている場合、Windows アプリの設定を同期しません。 このリンクにより、設定が Microsoft OneDrive に同期されるため、UE-V のみがデスクトップアプリケーションを同期します。

 

## Microsoft アカウントのリンク


Microsoft アカウントでサインインしている場合、または Microsoft アカウントをドメインアカウントにリンクしている場合、OneDrive を使用した設定の同期は Windows 8 に新しくなりました。 ドメインユーザーが UE-V を使用し、Microsoft アカウントにサインインしている場合は、次のようにします。

-   UE-V はデスクトップアプリケーションの設定のみを同期します。

-   Microsoft アカウントでは、Windows アプリの設定と Windows デスクトップの設定が処理されます

## 会社設定センター


会社設定センターという UE-V 2 のアプリケーションを介して、どの設定を同期するかをユーザーが制御できるようにすることができます。 [会社の設定] センターは、UE-V エージェントと共にインストールされ、ユーザーはコントロールパネル、[**スタート**] メニューまたは**スタート**画面、および ue-v 通知領域のアイコンからアクセスできます。

[会社設定センター] には、同期されている設定が表示され、ユーザーは UE-V の同期状態を確認できます。 ユーザーに許可した場合、ユーザーは会社設定センターを使用して、同期する設定を選ぶことができます。 [**今すぐ同期**] ボタンをクリックして、すべての設定をすぐに同期することもできます。






## 関連トピック


[UE-V 2.x の概要](get-started-with-ue-v-2x-new-uevv2.md)

[UE-V の展開を準備する](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

 

 





