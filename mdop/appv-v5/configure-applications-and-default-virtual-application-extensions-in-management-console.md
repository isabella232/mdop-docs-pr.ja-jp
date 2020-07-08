---
title: 管理コンソールでアプリケーションと既定の仮想アプリケーションの拡張機能を構成する
description: 管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法
author: dansimp
ms.assetid: 1e1941d3-fb22-4077-8ec6-7a0cb80335d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2019
ms.openlocfilehash: 7c29ba0e40cf1adbc2b2297124cfb245a65a7ffe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814706"
---
#   管理コンソールでアプリケーションと既定の仮想アプリケーションの拡張機能を構成する

既定のパッケージの拡張子を*表示*して*構成*するには、次の手順を使用します。

**仮想アプリケーションの既定の拡張機能を表示して構成するには**

1.  構成するパッケージを表示するには、App-v 5.1 管理コンソールを開きます。 構成するパッケージを選択し、パッケージ名を右クリックして、[**既定の構成の編集**] を選択します。

2.  指定したパッケージに含まれているアプリケーションを表示するには、[**既定の構成**] ウィンドウで [**アプリケーション**] をクリックします。 パッケージのショートカットを表示するには、[**ショートカット**] をクリックします。 そのパッケージのファイルの種類の関連付けを表示するには、[**ファイルの種類**] をクリックします。

3.  アプリケーションの拡張機能を有効にするには、[**有効に**する] を選びます。

    ショートカットを有効にするには、**ショートカットを有効**にします。 選択したアプリケーションに新しいショートカットを追加するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**新しいショートカットの追加**] を選択します。 ショートカットを削除するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**ショートカットの削除**] を選択します。 既存のショートカットを編集するには、アプリケーションを右クリックし、[**ショートカットの編集**] を選択します。

4.  その他のアプリケーションの拡張子を表示するには、[**詳細設定**] をクリックし、[**設定のエクスポート**] をクリックします。 ファイル名を入力し、[**保存**] をクリックします。 パッケージに関連付けられているすべてのアプリケーション拡張機能は、構成ファイルを使って表示できます。

5.  他のアプリケーションの拡張子を編集するには、構成ファイルを変更し、[インポート] をクリックして、[**この構成を上書き**] をクリックします。 変更したファイルを選択し、[**開く**] をクリックします。 ダイアログボックスで、[**上書き**] をクリックして処理を完了します。

>**注**アップロードに失敗し、構成ファイルのサイズが4MB より上の場合は、サーバーで許可される最大ファイルサイズを大きくする必要があります。 これを行うには、構成ファイルのサイズよりも大きい値 (KB 単位) の maxRequestLength 属性を、26行目の httpRuntime 要素に追加し `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config` ます。  
たとえば、をに変更すると、 `<httpRuntime targetFramework="4.5"/>` `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` 最大サイズは 8 mb になります。


App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





