---
title: MED-V トリム転送テクノロジ
description: MED-V トリム転送テクノロジ
author: dansimp
ms.assetid: 2744e855-a486-4028-9606-f0084794ec65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa11c8036954070bbff465a6ad78992fdd52f3a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826187"
---
# MED-V トリム転送テクノロジ


## <a href="" id="bkmk-medvtrimtransfertechnology"></a>


MED-V の高度なトリム移行の重複除去技術は、LAN または WAN 経由で初期および更新された仮想マシンのイメージをダウンロードすることによって、複数のエンドユーザーに対して、MED-V ワークスペース仮想マシンをトランスポートするために必要なネットワーク帯域幅を削減します。

この画期的なテクノロジでは、既存のローカルデータを使用して仮想マシンのイメージを作成します。多くの場合、仮想マシンの大半 (システムファイルやアプリケーションファイルなど) がエンドユーザーのディスクに既に存在していることを意味します。 たとえば、windowsxp を含む仮想マシンが、ローカルコピーを実行しているクライアントに配信された場合、MED-V は冗長な WindowsXP 要素を転送から自動的に削除します。 有効な機能のあるワークスペースを確保するために、MED-V クライアントは、使用される前にローカルデータの整合性を確認します。これにより、データのローカルブロックは、目的の仮想マシンイメージ内のデータとまったく同じように動作することが保証されます。 一致しないブロックは使用されません。

このプロセスでは、帯域幅を効率的に透過し、未使用のネットワークと CPU リソースを使用して、バックグラウンドで転送を実行します。

新しいイメージのバージョンに更新する場合 (たとえば、管理者が新しいアプリケーションまたは更新プログラムを配布する場合)、変更された要素 ("差分") のみがダウンロードされ、仮想マシン全体ではなく、必要なネットワーク帯域幅と配信時間が大幅に減少します。

ホストオペレーティングシステムに基づいて、トリム転送プロトコルの一部として、ホスト上でインデックスを作成するフォルダーを構成することができます。 これらの設定は*ClientSettings.xml*ファイルで構成されます。この設定は、 **Servers\\Configuration \**フォルダーにあります。

新しい設定を適用する場合は、サービスを再起動する必要があります。

```xml
<HostIndexingXP type="System.String[]"> 
- <ArrayOfString>
<string>%WINDIR%</string> 
<string>%ProgramFiles%\Common Files</string> 
<string>%ProgramFiles%\Internet Explorer</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
<string>%ProgramFiles%\Windows NT</string> 
<string>%ProgramFiles%\Messenger</string> 
<string>%ProgramFiles%\Adobe</string> 
<string>%ProgramFiles%\Outlook Express</string> 
</ArrayOfString> 
</HostIndexingXP> 
- <HostIndexingVista type="System.String[]"> 
- <ArrayOfString> 
<string>%WINDIR%\MSAgent</string> 
<string>%WINDIR%\winsxs</string> 
<string>%WINDIR%\system</string> 
<string>%WINDIR%\system32</string> 
<string>%WINDIR%\Microsoft.NET</string> 
<string>%WINDIR%\SoftwareDistribution</string> 
<string>%WINDIR%\L2Schemas</string> 
<string>%WINDIR%\Cursors</string> 
<string>%WINDIR%\Boot</string> 
<string>%WINDIR%\Help</string> 
<string>%WINDIR%\assembly</string> 
<string>%WINDIR%\inf</string> 
<string>%WINDIR%\fonts</string> 
<string>%WINDIR%\Installer</string> 
<string>%WINDIR%\IME</string> 
<string>%WINDIR%\Resources</string> 
<string>%WINDIR%\servicing</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
</ArrayOfString> 
</HostIndexingVista>
```

 

 





