---
title: アプリケーションの仮想化アプリケーションで UE-V を使用する
description: アプリケーションの仮想化アプリケーションで UE-V を使用する
author: dansimp
ms.assetid: 4644b810-fc48-4fd0-96e4-2fc6cd64d8ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221d21c5815b36b57a04a0299352e5fe64f657c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827274"
---
# アプリケーションの仮想化アプリケーションで UE-V を使用する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 は、App-v パッケージまたは UE-V のテンプレートに必要な変更を加えずに、Microsoft Application Virtualization (App-v) アプリケーションをサポートしています。 ただし、仮想化された App-v アプリケーションで直接 UE-V Generator を実行することはできないため、追加の手順が必要です。 代わりに、アプリケーションをローカルにインストールして、テンプレートを生成し、仮想化されたアプリケーションにテンプレートを適用する必要があります。 UE-V は、app-v 4.5、App-v 4.6、および App-v 5.0 パッケージをサポートしています。

## App-v アプリケーションの UE-V 設定の同期


UE-V は、アプリケーションがローカルにインストールされているか、またはアプリケーションがローカルにインストールされているかにかかわらず、アプリがプログラム名によって開かれているかどうかを監視します。 UE-V は、アプリケーションが起動すると、App-v のプロセスを監視し、ユーザーの設定の記憶域のパスに保存されているすべての設定を適用して、アプリケーションを正常に起動できるようにします。 UE-V では、app-v アプリケーションを監視し、関連するファイルとレジストリパスを仮想化された場所に自動的に変換します。これは、アプリ間の物理的な場所とは異なります。

 **仮想化されたアプリケーションの設定の同期を実装するには**

1.  UE-V Generator を実行して、コンピューター間で設定を同期するローカルにインストールされたアプリケーションの設定を収集します。 このプロセスでは、設定場所テンプレートを作成します。 Microsoft Office 2010 テンプレートなどの組み込みテンプレートを使用している場合は、この手順をスキップしてください。 UE-V Generator の実行について詳しくは、「[カスタムアプリケーションの ue-v の展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates)」をご覧ください。

2.  まだ実行していない場合は、App-v アプリケーションパッケージをインストールします。

3.  設定テンプレートカタログの場所にテンプレートを発行するか、Windows PowerShell コマンドレットを使用してテンプレートを手動でインストールし `Register-UEVTemplate` ます。

    **注** 新しく作成したテンプレートを設定テンプレートカタログに発行する場合、同期プロバイダーが設定を更新するまで、クライアントはテンプレートを受け取りません。 このプロセスを手動で開始するには、**タスクスケジューラ**を開き、[**タスクスケジューラライブラリ**]、[ **Microsoft**]、[ **ue-v**] の順に展開します。 [結果] ウィンドウで、[**テンプレートの自動更新**] を右クリックし、[**実行**] をクリックします。

     

4.  App-v パッケージを起動します。






## 関連トピック


[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

 

 





