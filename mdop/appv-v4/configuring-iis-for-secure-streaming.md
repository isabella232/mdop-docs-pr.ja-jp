---
title: セキュリティで保護されたストリーミング用の IIS の構成
description: セキュリティで保護されたストリーミング用の IIS の構成
author: dansimp
ms.assetid: 9a80a703-4642-4bec-b7af-dc7cb6b76925
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 724fd247d98c265421cea13f4b91c97049a2b4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821884"
---
# セキュリティで保護されたストリーミング用の IIS の構成


Microsoft Application Virtualization (App-v) バージョン4.5 のリリースでは、HTTP と HTTPS を、ストリーミングアプリケーションパッケージのプロトコルとして使うことができます。 このオプションを使用すると、IIS が通常提供する追加のスケーラビリティを組織が活用できます。 ストリーミングサーバーとして IIS を使う場合は、HTTP の代わりに HTTPS を使用して、クライアントとサーバー間の通信をセキュリティで保護することができます。

**注** ファイルサーバーからアプリケーションをストリーミングする場合は、アプリケーションパッケージへの通信のセキュリティを強化する必要があります。 これは IPsec を使って実現できます。 詳細については、TechNet ライブラリの次のトピックを参照してください。

-   Windows Server2003 の場合は、 <https://go.microsoft.com/fwlink/?LinkId=133226>

-   Windows Server 2008 の場合は、 <https://go.microsoft.com/fwlink/?LinkId=133227>

 

## MIME の種類


IIS を使って HTTP または HTTPS で仮想アプリケーションをストリーミングする場合、App-v をサポートするには、次の MIME の種類を IIS サーバーに追加する必要があります。

-   .OSD = TXT

-   .SFT = バイナリ

MIME の種類を追加するためのガイダンスとして、次のサポート技術情報の記事を使用します。

IIS 6.0: <https://go.microsoft.com/fwlink/?LinkId=151973>

IIS 7.0: <https://go.microsoft.com/fwlink/?LinkId=151977>

## Kerberos 認証


HTTP または HTTPS と Kerberos 認証を使用して、ICO、OSD、または SFT の各ファイルをストリーミングする場合、環境のセキュリティが強化されます。 ただし、IIS で Kerberos 認証をサポートするには、適切なサービスプリンシパル名 (SPN) を構成する必要があります。 この `setspn.exe` ツールは、インストール CD のサポートツールから Windows Server2003 で利用でき、Windows Server2008 に組み込まれています。

SPN を作成するには、 `setspn.exe` ドメイン管理者のメンバーとしてログインしているときに、コマンドプロンプトから実行します (例:) `setspn.exe –A HTTP/FQDN of Server ServerName` 。

## 関連トピック


[インストール後の安全な通信のための Management Server または Streaming Server の構成](configuring-management-or-streaming-server-for-secure-communications-post-installation.md)

 

 





