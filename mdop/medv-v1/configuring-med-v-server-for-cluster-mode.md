---
title: クラスター モードの MED-V サーバーの構成
description: クラスター モードの MED-V サーバーの構成
author: dansimp
ms.assetid: 41f0b2a3-4ce9-48e1-a6fb-4c13c4228515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddb7dd5af65d8a465c5c1884bb27a3027621bac1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826717"
---
# クラスター モードの MED-V サーバーの構成


クラスターモードでは、MED-V サーバーを構成できます。 クラスターモードでは、2つのサーバーが使われ、両方のサーバーに対して同一のファイルがすべてファイルシステムに配置されます。 サーバーは、ファイルをローカルに保存するのではなく、ファイルシステムからファイルにアクセスします。

## <a href="" id="bkmk-howtoconfigurethemedvserverinclustermode"></a>


**クラスターモードで MED-V サーバーを構成するには**

1.  いずれかのサーバーに MED-V をインストールして構成します。

2.  すべてのサーバーがアクセスできる中央の場所で共有ネットワークを作成します。

3.  * &lt; InstallDir &gt; //Dns/configurationserver*フォルダーの内容を共有ネットワークにコピーします。

4.  指定したすべてのサーバーに MED-V サーバーをインストールします。

5.  共有ネットワークで、すべての MED-V サーバーシステムアカウントへのフルアクセスを割り当てます。

6.  各サーバーで、次の操作を行います。

    1.  * &lt; InstallDir &gt; //dns/ServerConfiguration.xml*ファイルで、 * &lt; storepath &gt; *の値を共有ネットワークパスに設定します。

    2.  使用しているサーバーから* &lt; instsalldir &gt; /servers/KeyPair.xml*ファイルをすべての med-v サーバーにコピーします。

    3.  MED-V サービスを再起動します。

**注** すべてのサーバーのローカル設定が同じ (リッスンポート、IIS サーバー、管理アクセス許可、レポートデータベースなど) の場合は、 * &lt; InstallDir/servers &gt; /ServerSettings.xml*をすべてのサーバーで共有することもできます。

 

## 関連トピック


[MED-V インフラストラクチャの計画と設計](med-v-infrastructure-planning-and-design.md)

 

 





