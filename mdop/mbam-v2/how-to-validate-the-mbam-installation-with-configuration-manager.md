---
title: Configuration Manager で MBAM のインストールを検証する方法
description: Configuration Manager で MBAM のインストールを検証する方法
author: dansimp
ms.assetid: 8e268539-91c3-4e8a-baae-faf3605da818
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 500c6f6ee5138b5677bf1fa20e2627a56981df1f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822637"
---
# Configuration Manager で MBAM のインストールを検証する方法


構成マネージャーを使用して Microsoft BitLocker 管理と監視 (MBAM) をインストールした後、次の手順に従って、インストールによって MBAM の必要なすべての機能が正しく設定されていることを確認します。

**Configuration Manager を使用して MBAM サーバー機能のインストールを検証するには**

1.  System Center Configuration Manager が展開されているサーバーで、[**コントロールパネル]** を開きます。 プログラムをアンインストールまたは変更するために使用するプログラムを選択します。 **Microsoft BitLocker の管理と監視**が、プログラムと機能の一覧に表示されることを確認します。

    **注** インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。

     

2.  Configuration Manager コンソールを使用して、"MBAM サポートされているコンピューター" という新しいコレクションが表示されていることを確認します。

    Configuration Manager 2007 でコレクションを表示するには、[**サイトデータベース**( &lt; **SiteCode** &gt;  -  &lt; **ServerName** &gt; 、 &lt; **SiteName** &gt; )]、[**コンピューターの管理**] のいずれかをクリックします。

    SystemCenter2012 ConfigurationManager でコレクションを表示するには、[**アセット And コンプライアンス**ワークスペース]、[**デバイスコレクション**] のいずれかをクリックします。

3.  Configuration Manager コンソールを使用して、次のレポートが**Mbam**フォルダーに一覧表示されていることを確認します。

    -   BitLocker コンピューターのコンプライアンス

    -   BitLocker エンタープライズコンプライアンスダッシュボード

    -   BitLocker Enterprise コンプライアンスの詳細

    -   BitLocker Enterprise コンプライアンスの概要

    Configuration Manager 2007 でレポートを表示するには、[**レポート**]、[ **reporting Services**]、[\\ \ \ \ &lt; **ServerName** &gt; ]、[**レポートフォルダー** ] のいずれかをクリックします。

    SystemCenter2012 ConfigurationManager のレポートを表示するには、[**監視**ワークスペース]、[**レポート**]、[**レポート**] のいずれかをクリックします。

4.  Configuration Manager コンソールを使用して、構成基準 "BitLocker Protection" が表示されていることを確認します。

    Configuration Manager 2007 で構成基準を表示するには、[**必要な構成管理**]、[**構成基準**] のいずれかをクリックします。

    SystemCenter2012 ConfigurationManager で構成基準を表示するには、[**資産とコンプライアンス**のワークスペース]、[**コンプライアンスの設定**]、[**構成基準**] のいずれかをクリックします。

5.  Configuration Manager コンソールを使用して、次の新しい構成項目が表示されていることを確認します。

    -   BitLocker 固定データドライブの保護

    -   BitLocker オペレーティングシステムドライブの保護

    Configuration Manager 2007 で構成項目を表示するには、[**必要な構成管理**]、[**構成項目**] の順にクリックします。

    SystemCenter2012 ConfigurationManager で構成項目を表示するには、[**資産とコンプライアンス**のワークスペース]、[**コンプライアンス設定**]、[**構成項目**] の順にクリックします。

## 関連トピック


[Configuration Manager による MBAM の展開](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





