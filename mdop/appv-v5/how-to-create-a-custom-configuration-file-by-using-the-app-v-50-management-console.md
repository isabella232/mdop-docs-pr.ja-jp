---
title: APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法
description: APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法
author: dansimp
ms.assetid: 0d1f6768-be30-4682-8eeb-aa95918b24c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d54e68caa380025b2ff6f3ea79d30f275b589b30
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814330"
---
# APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法


動的構成を使用して、特定のユーザーに対して App-v 5.0 パッケージをカスタマイズすることができます。 ただし、ファイルを使用するには、まず動的ユーザー構成 (.xml) ファイルまたは動的な展開構成ファイルを作成する必要があります。 ファイルの作成は、高度な手動操作です。 動的ユーザー構成ファイルの一般的な情報については、「 [app-v 5.0 の動的構成につい](about-app-v-50-dynamic-configuration.md)て」を参照してください。

次の手順を使用して、App-v 5.0 管理コンソールを使用して動的なユーザー構成ファイルを作成します。

**動的ユーザー構成ファイルを作成するには**

1.  表示するパッケージの名前を右クリックし、[ **active directory アクセスの編集**] を選択して、特定のユーザーグループに割り当てられている構成を表示します。 または、パッケージを選択し、[**編集**] をクリックします。

2.  **アクセス権のある広告エンティティ**のリストを使用して、カスタマイズする広告グループを選びます。 選択されていない場合は、ドロップダウンリストから [**カスタム**] を選択します。 [ **Edit** ] という名前のリンクが表示されます。

3.  **[編集]** をクリックします。 広告グループに割り当てられている動的なユーザー構成が表示されます。

4.  [**詳細設定**] をクリックし、[**構成のエクスポート**] をクリックします。 ファイル名を入力し、[**保存**] をクリックします。 これで、ファイルを編集してユーザーのパッケージを構成できるようになりました。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 





