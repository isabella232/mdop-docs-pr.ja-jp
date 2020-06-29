---
title: Differential SFT ファイルを使用する方法
description: Differential SFT ファイルを使用する方法
author: dansimp
ms.assetid: 607e30fd-2f0e-4e2f-b669-0b3f010aebb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 85cc45f9665569d77fcf275db6dbc080eb919229
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816387"
---
# Differential SFT ファイルを使用する方法


Microsoft Application Virtualization (App-v) Sequencer は、アプリケーションをシーケンスするときに、すべての仮想アプリケーションのファイルのコンテンツと構成情報を格納するために SFT ファイル (sft) を作成します。 App-v のバージョン4.5 では、差分の SFT (dsft) ファイルが導入されています。 Sequencer を使って既存のパッケージのアップグレードを作成した後で、このファイルを生成し、元のシーケンスされたアプリケーションパッケージと新しいバージョンの違いのみを格納することができます。 このため、新しいバージョンのアプリケーションでは、完全な SFT ファイルよりもずっと小さく、低帯域幅のネットワーク接続を経由してパッケージの更新を送信することによる影響を減らします。 ただし、この使用は特定の制限された状況でのみサポートされます。 この機能は、特に電子ソフトウェア配布 (ESD) システムを使用して、ローカルファイルサーバーで低帯域幅接続を使用しているユーザーのグループを管理するために使用されるようにすることを目的としています。また、App-v ストリーミングサーバーを使用していません。

Configuration Manager は、既に組み込まれている低帯域幅の展開をサポートしているため、構成 Manager2007 を使用してユーザーを管理している場合は、差分の SFT ファイルを使用する必要はありません。 また、Application Virtualization (App-v) 管理またはストリーミングサーバーをアクティブなアップグレードで使用している場合、クライアントは古いパッケージバージョンと新しいパッケージバージョンの違いのみを取得するため、この操作は必要ありません。

次の手順では、Sequencer のインストールに含まれている mkdiffpkg.exe を使用して、仮想アプリケーションパッケージのアップグレードを完了した後に、差分の SFT ファイルを作成して、差分の SFT ファイルを展開する方法について説明します。 この手順を完了すると、パッケージがクライアントコンピューターから何らかの方法でアンロードされた場合に、ユーザーが次にアプリケーションを実行しようとしたときに、クライアントは、ローカルファイル共有から完全なパッケージ V2 をストリーム処理するように設定された上書き URL に戻ります。 これにより、アプリケーションの起動時にユーザーがエラーにならないようになります。 クライアント全体が破損したり、アンインストールされたりした場合は、アップグレードされたパッケージ (V2) の完全バージョンをクライアントに展開するように ESD システムを構成することをお勧めします。

パッケージのアップグレードの詳細については、「App-v 4.5 の運用ガイド」の「既存の仮想アプリケーションをアップグレードする方法」を参照してください。 <https://go.microsoft.com/fwlink/?LinkId=133129>

**注** 必須条件として、ESD の対象となるすべてのユーザーコンピューターは、ローカルキャッシュに V1 の sft ファイルを完全にロードしている必要があります。また、すべてのコンピューターでファイルストリーミングが有効になっている必要があります。

 

**同一の SFT ファイルを使用するには**

1.  管理者権限を持つアカウントを使用して、Sequencer コンピューターにログオンします。 Sequencer でアップグレードの元のパッケージ (V1) を開き、パッケージを新しいバージョン (V2) にアップグレードして、新しいバージョンの sft として保存します。

2.  App V 4.5 Sequencer インストールフォルダーでコマンドウィンドウを開き、次のコマンドを実行します。

    `“mkdiffpkg.exe V2.sft V2.dsft”`

3.  ESD システムまたはその他のファイルのコピープロセスを使用して、完全な V2 パッケージコンテンツファイル (V2) を、適切な接続のネットワーク接続のユーザーコンピューターからアクセスできるローカルファイル共有にコピーします。

4.  ESD システムを使用して、各ユーザーのコンピューターに、2つの差分の SFT ファイル (V2) のコピーを配置します。

5.  V2. dsft ファイルをインポートするには、各ユーザーのコンピューター上で次の SFTMIME コマンドを実行します。

    `“SFTMIME load package:<package name> /SFTPATH <path to V2.dsft>”`

6.  次の SFTMIME コマンドを各ユーザーのコンピューターで実行して、"上書き URL" を設定して、V2 のファイルを指定します。

    `“SFTMIME configure package:<package name> /OverrideURL FILE://<network path to V2.sft>”`

**注**  
-   差分の SFT ファイルは、正しい順序でクライアントに適用する必要があります。 たとえば、V2 は、V3 の前に V1 アプリケーションに適用する必要があります。 dsft が適用されます。

-   Sequencer での**Microsoft Windows Installer (MSI) パッケージ**機能の生成は、差分の SFT ファイルでは使用できません。

 

## 関連トピック


[App-v Sequencer を使用して仮想アプリケーションを作成またはアップグレードする方法](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





