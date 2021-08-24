---
title: はじめに - MBAM と Configuration Manager の使用
description: はじめに - MBAM と Configuration Manager の使用
author: dansimp
ms.assetid: b0a1d3cc-0b01-4b69-a2cd-fd09fb3beda4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f23a0eba923608fb6e25e44ee2843f3cde4c2dc
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910812"
---
# <a name="getting-started---using-mbam-with-configuration-manager"></a>はじめに - MBAM と Configuration Manager の使用


Microsoft BitLocker Administration and Monitoring (MBAM) をインストールする場合は、MBAM を Configuration Manager 2007 または System Center 2012 Configuration Manager と統合するトポロジを選択できます。 MBAM がサポートする構成マネージャーのサポートされているバージョンの一覧については、「Configuration Manager を使用して [MBAM を展開する計画」を参照してください](planning-to-deploy-mbam-with-configuration-manager-2.md)。 統合トポロジでは、ハードウェアコンプライアンスとレポート機能は MBAM から削除され、Configuration Manager からアクセスされます。

**重要**  
WindowsTo Go は、Configuration Manager 2007 を使用して MBAM の統合トポロジをインストールする場合はサポートされません。

 

## <a name="using-mbam-with-configuration-manager"></a>Configuration Manager での MBAM の使用


MBAM の統合は、Configuration Manager 2007 または System Center 2012 Configuration Manager に次の 3 つのアイテムをインストールする新しい構成パックに基づいており、次のセクションで詳しく説明します。

構成項目と構成基準で構成される構成データ

コレクション

レポート

### <a name="configuration-data"></a>構成データ

構成データには、"BitLocker オペレーティング システム ドライブ保護" と "BitLocker 固定データ ドライブ保護" の 2 つの構成項目が含まれる構成基準 "BitLocker Protection" がインストールされます。 構成基準はコレクションに展開され、MBAM のインストール時にも作成されます。 2 つの構成項目は、クライアント コンピューターのコンプライアンス状態を評価するための基礎となります。 この情報は、Configuration Manager でキャプチャ、保存、および評価されます。 構成項目は、オペレーティング システム ドライブ (OSD) と固定データ ドライブ (FDD) のコンプライアンス要件に基づいて行います。 展開されたコンピューターに必要な詳細が収集され、それらのドライブの種類に対するコンプライアンスを評価できます。 既定では、構成基準は 12 時間ごとにコンプライアンス状態を評価し、コンプライアンス データを Configuration Manager に送信します。

### <a name="collection"></a>コレクション

MBAM は、MBAM サポートされているコンピューターと呼ばれるコレクションを作成します。 構成基準は、このコレクション内のクライアント コンピューターを対象とします。 これは、既定では 12 時間ごとに実行され、メンバーシップを評価する動的コレクションです。 メンバーシップは、次の 3 つの条件に基づいて行います。

-   これは、サポートされているバージョンのオペレーティング システムWindowsです。 現在、MBAM は Windows Enterprise と Windows 7 Ultimate、Windows 8 Enterprise、Windows To Go の Windows To Go が Windows 8 Enterprise で実行されている場合のみサポートしています。

-   これは物理コンピューターです。 仮想マシンはサポートされていません。

-   信頼できるプラットフォーム モジュール (TPM) を使用できます。 互換性のあるバージョンの TPM 1.2 以降は、7 以降Windowsです。 Windows 8と Windows移動には TPM は必要ではありません。

コレクションは、すべてのコンピューターに対して評価され、MBAM 統合のコンプライアンス評価とレポートの基礎となる互換性のあるコンピューターのサブセットを作成します。

### <a name="reports"></a>レポート

コンプライアンスの表示に使用できるレポートは 4 種類です。 以下のとおりです。

-   **BitLocker エンタープライズ ダッシュボード**– IT 管理者は、1 つのレポートに関する 3 つの異なる情報ビュー (コンプライアンス状態の配布、非準拠 – エラーの配布、およびドライブの種類別のコンプライアンス状態の配布) を提供します。 レポートのドリルダウン オプションを使用すると、IT 管理者はデータをクリックし、選択した状態に一致するコンピューターの一覧を表示できます。

-   **BitLocker エンタープライズコンプライアンスの詳細**– IT 管理者は、企業の BitLocker 暗号化コンプライアンス状態に関する情報を表示し、各コンピューターのコンプライアンス状態を含めます。 レポートのドリルダウン オプションを使用すると、IT 管理者はデータをクリックし、選択した状態に一致するコンピューターの一覧を表示できます。

-   **BitLocker コンピューターコンプライアンス** – IT 管理者は、個々のコンピューターを表示し、特定の状態の準拠または準拠していない状態で報告された理由を特定できます。 このレポートには、オペレーティング システム ドライブ (OSD) と固定データ ドライブ (FDD) の暗号化状態も表示されます。

-   **BitLocker エンタープライズ概要**– IT 管理者は、MBAM ポリシーを使用して企業のコンプライアンスの状態を表示できます。 各コンピューターの状態が評価され、ポリシーに対する企業内のすべてのコンピューターのコンプライアンスの概要がレポートに表示されます。 レポートのドリルダウン オプションを使用すると、IT 管理者はデータをクリックし、選択した状態に一致するコンピューターの一覧を表示できます。

## <a name="high-level-architecture-of-mbam-with-configuration-manager"></a>High-Levelマネージャーを使用した MBAM のアーキテクチャ


次の図は、Configuration Manager トポロジを使用した MBAM アーキテクチャを示しています。 この構成は、実稼働環境で最大 200,000 MBAM のクライアントをサポートします。

![構成マネージャーを使用した mbam アーキテクチャ。](images/mbam2-cmserver.gif)

このアーキテクチャのサーバー、データベース、および機能の説明は次のとおりです。 アーキテクチャ イメージ内のサーバー機能とデータベースは、コンピューターまたはサーバーの下に一覧表示され、インストールすることをお勧めします。

-   **データベース サーバー** – 回復**データベース、********監査データベース**、および監査レポートは、Windows サーバーにインストールされ、SQL Serverされます。 Recovery データベースには、MBAM クライアント コンピューターから収集された回復データが格納されます。 Audit Database には、回復データにアクセスしたクライアント コンピューターから収集された監査アクティビティ データが格納されます。 監査レポートは、企業内のクライアント コンピューターのコンプライアンス状態に関するデータを提供します。

-   **Configuration Manager プライマリ サイト サーバー** – Configuration Manager サーバーには、configuration Manager プライマリ サイト サーバーにインストールする必要がある System Center Configuration Manager 統合トポロジを含む MBAM サーバー のインストールが含まれる。 Configuration Manager Server は、クライアント コンピューターからハードウェア インベントリ情報を収集し、クライアント コンピューターの BitLocker 準拠を報告するために使用されます。 MBAM セットアップ サーバーのインストールを実行すると、コレクションと構成データが Configuration Manager プライマリ サイト サーバーにインストールされます。

-   **管理および監視サーバー** -**管理および**監視サーバーは、Windows サーバーにインストールされ、管理と監視の Web サイトと監視 Web サービスで構成されます。 管理および監視 Web サイトは、アクティビティを監査し、回復データ (BitLocker 回復キーなど) にアクセスするために使用されます。 セルフサービス **ポータルは、** 管理および監視サーバーにもインストールされます。 ポータルを使用すると、クライアント コンピューター上のエンド ユーザーは、BitLocker パスワードを紛失または忘れた場合に、Web サイトに個別にログオンして回復キーを取得できます。 監査レポートは、管理および監視サーバーにもインストールされます。

-   **管理ワークステーション** - ポリシー テンプレート **は** 、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループ ポリシー オブジェクトで構成されます。 ポリシー テンプレートは、任意のサーバーまたはワークステーションにインストールできますが、通常は、サーバーまたはクライアント コンピューターでサポートされている管理ワークステーションWindowsインストールされます。 ワークステーションは専用のコンピューターである必要はない。

-   **MBAM クライアント** および **Configuration Manager クライアント** コンピューター

    -   **MBAM クライアントは、** 次のタスクを実行します。

        -   グループ ポリシー オブジェクトを使用して、エンタープライズ内のクライアント コンピューターの BitLocker 暗号化を適用します。

        -   オペレーティング システム ドライブ、固定データ ドライブ、およびリムーバブル データ (USB) ドライブの 3 つの BitLocker データ ドライブの種類の回復キーを収集します。

        -   クライアント コンピューターに関する回復情報とコンピューター情報を収集します。

    -   **Configuration Manager クライアント** – Configuration Manager クライアントを使用すると、Configuration Manager はクライアント コンピューターに関するハードウェア互換性データを収集し、Configuration Manager はコンプライアンス情報を報告できます。

## <a name="related-topics"></a>関連トピック


[Configuration Manager での MBAM の使用](using-mbam-with-configuration-manager.md)

 

 





