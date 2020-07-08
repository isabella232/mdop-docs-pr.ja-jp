---
title: App-V Package WMI クラス
description: App-V Package WMI クラス
author: dansimp
ms.assetid: 0fc26c3b-9706-4804-be2d-645771dc33ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa452afaaeb2f490c179a928b24de47207d6dc63
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819797"
---
# App-V Package WMI クラス


Application Virtualization (App-v) クライアントでは、 **Package**クラスは、クライアント上のすべての仮想パッケージを表す Windows Management INSTRUMENTATION (WMI) クラスです。 仮想パッケージには、多くの仮想アプリケーションを含めることができます。

## 構文


``` syntax
class Package
{
      string Name;
      string Version;
      string PackageGUID;
      string SftPath;
      uint64 TotalSize;
      uint64 CachedSize;
      uint64 LaunchSize;
      uint64 CachedLaunchSize;
      boolean InUse;
      boolean Locked;
      uint16 CachedPercentage;
      string VersionGUID;
 };
```

## プロパティ


<a href="" id="name"></a>**名前**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージのユーザーフレンドリ名。

<a href="" id="version"></a>**バージョン**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージのバージョン。

<a href="" id="packageguid"></a>**PackageGUID**  
データ型:**文字列**

アクセスの種類: 読み取り専用

修飾子: キー

パッケージ構成とソースファイルの GUID 識別子。

<a href="" id="sftpath"></a>**SftPath**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

SFT ファイルのファイルパス。

<a href="" id="totalsize"></a>**TotalSize**  
データ型: **UInt64**

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージの合計サイズ (kb 単位)。

<a href="" id="cachedsize"></a>**CachedSize**  
データ型: **UInt64**

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージのキャッシュの合計サイズ (kb 単位)。

<a href="" id="launchsize"></a>**LaunchSize**  
データ型: **UInt64**

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージのプライマリ機能ブロックの合計サイズ (kb 単位)。

<a href="" id="cachedlaunchsize"></a>**CachedLaunchSize**  
データ型: **UInt64**

アクセスの種類: 読み取り専用

限定子: なし

キャッシュされている仮想パッケージのプライマリ機能ブロックの合計サイズ (kb 単位)。

<a href="" id="inuse"></a>**InUse**  
データ型:**ブール**型

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージ内の仮想アプリケーションが実行されている場合は**true** 。それ以外の場合は**false**。

<a href="" id="locked"></a>**ロック**  
データ型:**ブール**型

アクセスの種類: 読み取り専用

限定子: なし

仮想パッケージがロックされている場合は**true** 。それ以外の場合は**false**。

<a href="" id="cachedpercentage"></a>**CachedPercentage**  
データ型: **UInt16**

アクセスの種類: 読み取り専用

限定子: なし

キャッシュファイルの割合。 次の式に基づいて、CachedSize/TotalSize ラ100を計算します。

<a href="" id="versionguid"></a>**VersionGUID**  
データ型:**文字列**

アクセスの種類: 読み取り専用

限定子: なし

パッケージバージョンの GUID 識別子。

 

 





