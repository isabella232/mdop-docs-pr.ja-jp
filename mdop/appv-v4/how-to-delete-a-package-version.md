---
title: パッケージのバージョンを削除する方法
description: パッケージのバージョンを削除する方法
author: dansimp
ms.assetid: a55adb9d-ffa6-4df3-a2d1-5e0c73c35e1b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc77e60ac9745033ae8f074ae71db0cb8517a202
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817564"
---
# パッケージのバージョンを削除する方法


Application Virtualization Server 管理コンソールで、複数のバージョンがあるパッケージについては、次の手順を使用して1つ以上のバージョンを削除し、残りのバージョンのパッケージを引き続きストリームできます。 この操作を行うと、サーバー上のファイルをより効率的に管理したり、古いバージョンを削除したりすることができます。

**注** バージョンの削除を選択すると、クライアントコンピューターが引き続き使用している可能性があることを示す確認ボックスが表示されます。 使用中のバージョンを削除する前に、ユーザーにアプリケーションを終了してアンロードするように指示する必要があります。

 

**パッケージバージョンを削除するには**

1.  Application Virtualization Server 管理コンソールの左側のパネルで、[**パッケージ**] を展開します。

2.  削除するバージョンが含まれているパッケージをクリックします。

3.  中央のウィンドウで、削除するパッケージのバージョンを右クリックし、[**削除**] を選択します。

4.  確認ウィンドウを読み、[**はい**] をクリックして操作を完了します。

    **注** ユーザーが切断された操作を実行している場合は、次回サーバーに接続するときに、そのユーザーのアプリケーションは新しいバージョンに置き換えられます。 すべてのユーザーがアプリケーションを更新したことを確認したら、古いバージョンを削除できます。

     

## 関連トピック


[パッケージを削除する方法](how-to-delete-a-packageserver.md)

[サーバー管理コンソールでパッケージを管理する方法](how-to-manage-packages-in-the-server-management-console.md)

 

 





