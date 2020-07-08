---
title: リモート ネットワークの MED-V の構成
description: リモート ネットワークの MED-V の構成
author: dansimp
ms.assetid: 4d2f0081-622f-4a6f-8d73-f8c2108036e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328376046ee5213f3d5bb09be7adf8c81f8508b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826724"
---
# リモート ネットワークの MED-V の構成


MED-V をネットワーク内部からリモートで、またはネットワーク内部からリモートから、またはその両方で動作するように構成することができます。

## <a href="" id="bkmk-howtoconfiguremedvtoworkfrominsideanetworkorremotely"></a>


**ネットワーク内部から動作するように MED-V を構成するには**

-   ネットワーク内の MED-V サーバーとイメージの配布を構成します。

**リモートで動作するように MED-V を構成するには**

1.  インターネットからアクセスできる MED-V サーバーとイメージ配布サーバーを構成します。

2.  必要に応じて、境界ネットワーク (DMZ とも呼ばれます) のリバースプロキシを構成します。

3.  *ClientSettings.xml*ファイルで認証方法を設定します。これは、 **Servers\\Configuration \**フォルダーにあります。

**ネットワーク内部とリモートの両方で動作するように MED-V を構成するには**

1.  ネットワーク内の MED-V サーバーとイメージ配信サーバーを構成します。

2.  インターネットからサーバーにアクセスできることを確認します。

3.  クライアントがサーバーに接続しようとしたときに、クライアントの場所に基づいて適切なサーバー (ネットワーク内またはインターネット経由) に自動的に接続されるように、DNS 解決を構成します。

4.  必要に応じて、境界ネットワークのリバースプロキシを構成します。

5.  *ClientSettings.xml*ファイルで認証方法を設定します。これは、 **Servers\\Configuration \**フォルダーにあります。

**注** 新しい設定を適用する場合は、サービスを再起動する必要があります。

 

-   IIS 認証スキームは、BASIC、DIGEST、NTLM、または NEGOTIATE のいずれかに変更できます。 既定値は NEGOTIATE で、次のエントリを使用します。

    ```xml
    <ImageDistribution>
    <!-- The authentication used for image download. Basic and digest authentication should be used only under SSL.-->
       <!-- The line below can be one of the following: -->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_BASIC</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_DIGEST</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NTLM</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME-->
       <Authentication type="Kidaro.Foundation.Bits.BG_AUTH_SCHEME">
          <BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME>
       </Authentication>
    </ImageDistribution>
    ```

## 関連トピック


[MED-V インフラストラクチャの計画と設計](med-v-infrastructure-planning-and-design.md)

 

 





