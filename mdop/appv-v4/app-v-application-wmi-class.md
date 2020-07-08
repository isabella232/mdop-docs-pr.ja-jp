---
title: App-V Application WMI クラス
description: App-V Application WMI クラス
author: dansimp
ms.assetid: b79b0d5a-ba57-442f-8bb4-d7154fc056f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a4e1e49e35b231ddb2a480a06c46e364121ac2d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822324"
---
# App-V Application WMI クラス


Application Virtualization (App-v) クライアントでは、 **application**クラスは、クライアント上のすべての仮想アプリケーションを表す Windows Management INSTRUMENTATION (WMI) クラスです。

次の構文は、管理オブジェクト形式 (MOF) コードから簡素化されています。 このコードには、継承されたすべてのプロパティが含まれています。

## 構文


``` syntax
class Application
{
      string Name;
      string Version;
      string PackageGUID;
      datetime LastLaunchOnSystem;
      uint32 GlobalRunningCount;
      boolean Loading;
      string OriginalOsdPath;
      string CachedOsdPath;
};
```

## 要件


## プロパティ


<a href="" id="name"></a>**名前**  
データ型:**文字列**

アクセスの種類: 読み取り専用

修飾子: キー

仮想アプリケーションの表示名。

<a href="" id="version"></a>**バージョン**  
データ型:**文字列**

アクセスの種類: 読み取り専用

修飾子: キー

仮想アプリケーションのバージョン。

<a href="" id="packageguid"></a>**PackageGUID**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

仮想アプリケーションが関連付けられているパッケージの GUID です。

<a href="" id="lastlaunchonsystem"></a>**LastLaunchOnSystem**  
データ型: **DateTime**

アクセスの種類: 読み取り専用

限定子: なし

仮想アプリケーションが起動された最後の日付と時刻。

<a href="" id="globalrunningcount"></a>**GlobalRunningCount**  
データ型: **UInt32**

アクセスの種類: 読み取り専用

限定子: なし

直接開始された仮想アプリケーションのインスタンスの数。

<a href="" id="loading"></a>**読み込み中**  
データ型:**ブール**型

アクセスの種類: 読み取り専用

限定子: なし

仮想アプリケーションが開始されている場合は**true** 。それ以外の場合は**false**。

<a href="" id="originalosdpath"></a>**発信経路**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

App-v クライアントに登録された OSD ファイルの元のファイルパス。

<a href="" id="cachedosdpath"></a>**CachedOsdPath**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

アプリケーションのローカルで OSD ファイルがキャッシュされている場合は、OSD ファイルのファイルパス。

 

 





