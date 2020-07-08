---
title: Sequencer のインストール方法 (App-v 4.6 SP1)
description: Sequencer のインストール方法 (App-v 4.6 SP1)
author: dansimp
ms.assetid: fe8eb876-28fb-46ae-b592-da055107e639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 611564e861d65dcd357c58732fb60dab21c05abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817274"
---
# Sequencer のインストール方法 (App-v 4.6 SP1)


Microsoft Application Virtualization (App-v) Sequencer は、アプリケーションを仮想アプリケーションとして実行できるように、アプリケーションのインストールとセットアップのプロセスを監視および記録します。 オペレーティングシステムのみがインストールされているコンピューターに、App-v Sequencer をインストールする必要があります。 または、仮想コンピューターなどの仮想環境で実行されているコンピューターに Sequencer をインストールすることもできます。 この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが容易であるために役立ちます。

アプリケーションのシーケンスに使用しているコンピューターの管理者資格情報を持っている必要があります。また、コンピューターは、どのバージョンの App-v クライアントも実行していない必要があります。 App-v Sequencer を使用して仮想アプリケーションを作成するには、複数の操作が必要であるため、 [Application Virtualization Sequencer ハードウェアとソフトウェアの要件](application-virtualization-sequencer-hardware-and-software-requirements.md)を満たしているか超えているコンピューターに Sequencer をインストールすることが重要です。

**注**  
セーフモードでの App-v sequencer の実行はサポートされていません。



**Microsoft Application Virtualization Sequencer をインストールするには**

1.  Microsoft Application Virtualization Sequencer インストールファイルをインストールするコンピューターにコピーします。

2.  Microsoft Application Virtualization Sequencer のインストールウィザードを開始するには、[ **Setup.exe**] をダブルクリックします。 **Microsoft Visual C++ SP1 再頒布可能パッケージ (x86)** がインストール前に検出されない場合は、[**インストール**] をクリックして必要な前提条件をインストールします。

3.  インストールを続行するには、[**ようこそ**] ページで [**次へ**] をクリックします。

4.  [**使用**許諾契約書] ページで、使用許諾契約書に同意し、[**使用許諾契約書に同意**します] をクリックして、[**次へ**] をクリックします。

5.  [**インポート先のフォルダー** ] ページで、既定のインストールフォルダーを承認するには、[**次へ**] をクリックします。 別の保存先フォルダーを指定するには、[**変更**] をクリックし、インストールに使用するインストールフォルダーを指定します。 **[次へ]** をクリックします。

6.  [**仮想ドライブ**] ページで、アプリケーションの仮想化の既定のドライブ**Q:\\** (既定) を、すべてのシーケンスされたアプリケーションの実行元のドライブとして構成するには、[**次へ**] をクリックします。 別のドライブ文字を指定する場合は、一覧を使用し、適切なドライブ文字を選択して使用するドライブ文字を選び、[**次へ**] をクリックします。

    **重要**  
    この手順で指定した Application Virtualization のドライブ文字は、仮想アプリケーションがターゲットコンピューター上で実行されるドライブ文字です。 指定されたドライブ文字は、使用可能であり、App-v クライアントを実行しているコンピューターで現在使用されていないものである必要があります。 指定したドライブが既に使われている場合、仮想アプリケーションはターゲットコンピューターで失敗します。



7.  [**プログラムをインストールする準備ができ**ました] ページで、インストールを開始するには、[**インストール**] をクリックします。

8.  **InstallShield ウィザード**の [完了] ページで、インストールウィザードを終了して app-v Sequencer を開くには、[**完了**] をクリックします。 Sequencer を開かずにインストールウィザードを閉じるには、[**プログラムの起動**] をオフにして、[**完了**] をクリックします。

    **注**  
    仮想環境を実行しているコンピューター (たとえば仮想マシン) に app-v Sequencer をインストールした場合は、スナップショットを取得する必要があります。 アプリケーションをシーケンスした後は、この画像に戻すことができます。そのため、次のアプリケーションをシーケンスできます。



~~~
When you uninstall the Sequencer, the following registry keys are not removed from the computer that the Sequencer was installed on. Additionally, you must restart the computer after you have uninstalled the Sequencer so that all associated drivers can be stopped and the operation can be completed.

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey**
~~~

## 関連トピック


[Application Virtualization Sequencer の構成 (App-V 4.6 SP1)](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)









