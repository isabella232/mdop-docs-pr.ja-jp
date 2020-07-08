---
title: App-V 用に Windows Server 2008 ファイアウォールを構成する方法
description: App-V 用に Windows Server 2008 ファイアウォールを構成する方法
author: dansimp
ms.assetid: 57f4ed17-0651-4a3c-be1e-29d9520c6aeb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 19e4cda9ac3b908f68e4f69b9663033d8a21ae41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817717"
---
# App-V 用に Windows Server 2008 ファイアウォールを構成する方法


Windows Server2008 を導入することで、ファイアウォールと IPsec コンポーネントが1つのサービスに統合され、このサービスの機能が強化されました。 新しいファイアウォールサービスでは、受信と発信のステートフル検査がサポートされています。 また、グループポリシーを使用して、特定のファイアウォール規則と IPsec ポリシーを構成することもできます。 Windows Server2008 の Windows ファイアウォールの詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151980> 。

次の手順では、SMB または HTTP/HTTPS での ICO と OSD の公開の例外の追加については説明しません。 これらの例外は、Windows Server 2008 ファイアウォールにインストールされているネットワークプロファイルとロールに基づいて自動的に追加されます。

**注** 管理サーバーが RTSP を使用するように構成されている場合は、この手順を繰り返し `sghwsvr.exe` てプログラムを例外として追加します。

App-v ストリーミングサーバーには、RTSPS 通信のプログラム例外が必要です `sglwdsptr.exe` 。 接続用に RTSP を使用する App-v ストリーミングサーバーでは、のプログラム例外も必要です `sglwsvr.exe` 。

 

**Windows Server2008 firewall for App-v を構成するには**

1.  コントロールパネルを使用するか、または [実行] 行に入力して、**高度なセキュリティ管理コンソールを使用して Windows ファイアウォール**を開き `wf.msc` ます。

2.  新しい受信ルールを作成し、[**プログラム**] を選択します。

3.  プログラムパスを選択して、[ `sghwdsptr.exe` 既定で使用されている] の場所を参照し `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` ます。

4.  **[次へ]** をクリックします。

5.  [**操作**] ページで、[**接続を許可する**] を選択し、[**次へ**] をクリックします。

6.  受信ルールに適用する適切な**プロファイル**を選択します。

7.  ルールの名前と説明を入力し、[**完了**] をクリックします。

## 関連トピック


[App-V 用に Windows Server 2003 ファイアウォールを構成する方法](how-to-configure-windows-server-2003-firewall-for-app-v.md)

 

 





