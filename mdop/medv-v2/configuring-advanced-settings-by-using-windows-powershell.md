---
title: Windows PowerShell を使用した高度な設定の構成
description: Windows PowerShell を使用した高度な設定の構成
author: dansimp
ms.assetid: 437a31cc-2a11-456f-b448-b0b869fb53f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a3ece3f76f6e982913aad2b25cfe0084542f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827394"
---
# Windows PowerShell を使用した高度な設定の構成


作成する MED-V ワークスペースパッケージには、MED-V ワークスペースパッケージをテストして展開する前に編集できる Windows PowerShell スクリプト (. ps1) ファイルが含まれています。 このセクションでは、MED-V ワークスペースを展開する前に Windows PowerShell を使用して、MED-V 構成設定を管理するための情報とガイダンスを提供します。

## MED-V での Windows PowerShell コマンドレットの使用


Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 では、次の Windows PowerShell コマンドレットを使用できます。

**新規-MedvConfiguration**

**エクスポート-MedvConfiguration**

**新規-MedvWorkspace**

**エクスポート-MedvWorkspace**

MED-V の Windows PowerShell コマンドレットにアクセスするには、Windows PowerShell を開き、次のコマンドを入力して、MED-V モジュールをインポートします。

``` syntax
Import-Module microsoft.medv
```

モジュールをインポートした後は、Windows PowerShell 標準のヘルプコマンド、 **man** 、または**get ヘルプ**を使用して、コマンドレットのインラインヘルプにアクセスできます。 たとえば、使用可能なパラメーターの完全な一覧を含む、**新しい-MedvConfiguration**コマンドレットの説明にアクセスするには、次のコマンドを入力します。

``` syntax
get-help New-MedvConfiguration
```

特定のパラメーターのヘルプを表示することもできます。 たとえば、VmMemory パラメーターのヘルプを表示するには、次のように入力します。

``` syntax
get-help New-MedvConfiguration -parameter VmMemory
```

すべての MED-V 構成設定とその既定値の一覧を表示するには、次のコマンドを入力します。

``` syntax
New-MedvConfiguration -ForceDefaults
```

すべての MED-V 構成設定とその現在の値の一覧を表示するには、次のコマンドを入力します。

``` syntax
gwmi -Class "Setting” -Namespace "root/microsoft/medv”
```

## カスタム設定での MED-V ワークスペースの作成


MED-V Workspace パッケージャーを使って MED-V ワークスペースパッケージを正常に作成した後、Windows PowerShell スクリプトが、パッケージャーファイルを保存するために指定したフォルダーに生成されます。 このスクリプトの内容は、編集可能な一部の MED-V 構成設定を示しています。

次の手順に従って、スクリプトをカスタマイズし、Windows PowerShell で実行して、新しい設定で MED-V ワークスペースを作成することができます。

**重要** 管理者の資格情報で Windows PowerShell を実行し、Windows PowerShell の実行ポリシーによってスクリプトの実行が許可されていることを確認します。

1.  MED-V Workspace パッケージャーによって生成された Windows PowerShell スクリプトを編集するか、または必要な構成設定で新しいスクリプトを作成します。

2.  管理者の資格情報で Windows PowerShell を実行し、コマンドプロンプトで次のコマンドを入力します。

    ``` syntax
    & “.\<workspacename>.ps1”
    ```

    このコマンドは、Windows PowerShell スクリプトを実行し **、新しい med-v ワークレットを**実行して新しい med-v ワークスペースパッケージを生成します。 新しいパッケージャーファイルは、MED-V ワークスペースパッケージャーファイルを保存するために最初に指定したフォルダーに保存されます。 このコマンドレットの詳細については、Windows PowerShell のヘルプを参照してください。

 

## レジストリファイルへの MED-V 構成のエクスポート


Med-v のワークスペースをインストールした後で、MED-V 構成設定を更新できます。 **新しい-MedvConfiguration**コマンドレットを使用して、変更するパラメーターを指定します。 たとえば、仮想マシンのメモリ設定を変更するレジストリファイルを作成するには、次のコマンドを入力します。

``` syntax
New-MedvConfiguration  -VmMemory 1024 | Export-MedvConfiguration -Path c:\medvConfiguration\myConfig.reg
```

生成されたレジストリファイルをホストコンピューターから MED-V ワークスペースにインポートして、新しい構成設定を適用することができます。

## 関連トピック


[MED-V ワークスペースの構成設定の管理](managing-med-v-workspace-configuration-settings.md)

[MED-V ワークスペース パッケージをテストして展開する](test-and-deploy-the-med-v-workspace-package.md)

 

 





