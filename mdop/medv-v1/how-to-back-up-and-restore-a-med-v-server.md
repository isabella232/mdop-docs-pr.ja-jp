---
title: MED-V サーバーをバックアップおよび復元する方法
description: MED-V サーバーをバックアップおよび復元する方法
author: dansimp
ms.assetid: 8d05e3a4-279b-4ce6-a319-8a09e7a30c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51cfe3727896ed68a1fd67441174a294a1073cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823087"
---
# MED-V サーバーをバックアップおよび復元する方法


サーバー上にある XML ファイルをバックアップして、サーバー上のデータが失われた場合に復元することができます。

**MED-V サーバーのバックアップを作成するには**

-   * &lt; InstallDir &gt; \\Servers\\ConfigurationServer*にある次のファイルをバックアップします。

    **注** 構成が既定の設定から変更されている場合は、ファイルが別の場所に保存されている可能性があります。

     

    -   ClientPolicy.xml

    -   ClientSettings.xml

    -   ConfigurationFiles.xml

    -   OrganizationPolicy.xml

    -   WorkspaceKeys.xml

    **注** ServerSettings.xml ファイルもバックアップすることができます。 ただし、特定の構成が変更されている場合 (たとえば、元のサーバーでは、MED-V の VM ディレクトリは "*C:\\Vms*" にあり、そのようなディレクトリは新しいサーバーに存在しません)、エラーが発生する可能性があります。

     

**MED-V サーバーを復元するには**

1.  新しい MED-V サーバーをインストールします。

2.  バックアップファイルを次のディレクトリにコピーします。

    *&lt;InstallDir &gt; \\Servers\\ConfigurationServer*

3.  MED-V サービスを再起動します。

 

 





