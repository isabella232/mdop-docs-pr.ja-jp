---
title: アーキテクチャの概要
description: アーキテクチャの概要
author: dansimp
ms.assetid: a00edb9f-207b-4f32-9e8f-522ea2739d2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a5db4a56b2abfb0df19b0d6d86f4bf88380c2bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827294"
---
# アーキテクチャの概要


このセクションでは、Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 の上位レベルのシステムアーキテクチャとコンポーネント設計について説明します。

## システムアーキテクチャ


MED-V は、1つのデバイスで2つのオペレーティングシステムを実行する、仮想イメージの配信、グループポリシーベースのプロビジョニング、一元管理を実行するために、Windows 仮想 PC を拡張します。 MED-V を使用することで、windows 7 Professional、Enterprise、または Windows 7 Ultimate を実行している Windows ベースのデスクトップで、企業の Windows 仮想 PC のイメージの構成、展開、管理を簡単に行うことができます。 MED-V ソリューションには、次のコンポーネントが含まれています。

<a href="" id="---------------med-v-host"></a> **MED-V ホスト**  
MED-V Host Agent、電子ソフトウェア配布 (ESD) システム、レジストリ管理システム、および MED-V ゲストが含まれている Windows 7 環境。 MED-V ホストは、特定のセットアップ機能とシステム情報を処理できるように、MED-V ゲストと通信します。

<a href="" id="-------------------med-v-host-agent"></a> **MED-V ホストエージェント**  
チャネルを提供して、MED-V ゲストと通信する med-v ホストに含まれている med-v ソフトウェア。 また、初回のセットアップやアプリケーションの公開などの機能も提供されます。

**注** MED-V とその必須コンポーネントがインストールされた後、med-v を構成する必要があります。 MED-V の構成は、初回のセットアップとして参照されます。

 

<a href="" id="esd-system"></a>**ESD システム**  
MED-V で作成される MED-V ワークスペースパッケージファイルを展開してインストールできる既存のソフトウェア配布方法。

<a href="" id="registry-management-system"></a>**レジストリ管理システム**  
既存のグループポリシー設定と基本設定の管理方法。

<a href="" id="windows-virtual-pc-image"></a>**Windows 仮想 PC のイメージ**  
次のコンポーネントが含まれている管理者が定義した仮想マシン。

<a href="" id="corporate-operating-system"></a>**企業のオペレーティングシステム**  
標準の企業オペレーティングシステム。

<a href="" id="management-and-security-tools"></a>**管理とセキュリティツール**  
ウイルス対策など、標準の管理およびセキュリティツール。

<a href="" id="-----------------------med-v-guest"></a> **MED ゲスト**  
Windows XP SP3 環境。 windows 7 上で実行されている windows 仮想 PC の一部として、次のコンポーネントが含まれています。

<a href="" id="---------------------------med-v-guest-agent"></a> **MED-Hyper-v ゲストエージェント**  
Med-v ホストと通信するためのチャネルを提供する、MED-V ゲストに含まれている MED-V ソフトウェア。 また、初回のセットアップの実行などの機能を備えた MED-V Host Agent もサポートされています。

**注** MED-V ゲストエージェントは、初回セットアップ時に自動的にインストールされます。

 

<a href="" id="esd-client"></a>**ESD クライアント**  
Esd システムの省略可能な部分で、ソフトウェアパッケージをインストールし、ステータスを ESD システムに報告します。

## 関連トピック


[アプリケーションのオペレーティング システムの互換性の計画](planning-for-application-operating-system-compatibility.md)

[MED-V の展開環境を準備する](prepare-the-deployment-environment-for-med-v.md)

 

 





