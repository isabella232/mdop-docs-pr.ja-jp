---
title: MED-V の Windows 仮想 PC イメージの構成
description: MED-V の Windows 仮想 PC イメージの構成
author: dansimp
ms.assetid: d87a0df8-9e08-4d1e-bfb0-9dc3cebf0d28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 340754b33576651c8ba89c85f369c48c0a0ab957
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826817"
---
# MED-V の Windows 仮想 PC イメージの構成


MED-V イメージに含めるすべての項目をインストールしたら、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 で使用するようにイメージを構成できます。 このセクションのトピックでは、med-v ワークスペースパッケージを作成する前に、初回のセットアップを実行するように MED-V イメージを設定する方法について説明します。

初回は、セットアップでエンドユーザー用の MED-V ワークスペースを準備します。 このプロセスでは、MED-V ワークスペースにパッケージ化されたイメージから仮想マシンを作成し、仮想マシン上で Windows ミニセットアップを実行します。 これには、カスタムセットアップスクリプトと、セットアップ完了アプリケーションの1回目の実行 (FtsCompletion.exe) が含まれます。

次の手順に従って、初回のセットアップを実行するために MED-V イメージを構成します。

1. オプションとして、仮想ハードディスク (VHD) を最適化して、Windows 仮想 PC イメージの構成を続行する前に、空のディスク領域を再利用し、VHD のサイズを小さくすることができます。 詳細については、「 [Med-v 仮想ハードディスクの最適化](compacting-the-med-v-virtual-hard-disk.md)」を参照してください。

2. 仮想マシンのセットアッププロセスをカスタマイズします。

3. Sysprep を使用して、MED-V イメージを封印します。

   **仮想マシンのセットアッププロセスをカスタマイズする**

4. MED-V で使用する画像の準備の一部として、Windows Update を実行するための設定の指定など、仮想マシンのさまざまな設定を構成できます。 MED-V ワークスペースパッケージを作成する前に、必要な仮想マシンの設定をすべて指定します。

5. MED-V ワークスペースパッケージを作成する前に、仮想マシン上の復元ポイントを無効にして差分ディスクの拡張を禁止することをお勧めします。 詳細については、「 [WINDOWS XP でシステムの復元を有効または無効にする方法](https://go.microsoft.com/fwlink/?LinkId=195927)」を参照してください ( https://go.microsoft.com/fwlink/?LinkId=195927) .

   **注**  
   初回セットアップの実行時に、復元ポイントを無効にするように Sysprep.inf ファイルを設定することができます。 この GuiRunOnce キーを設定する例については、このセクションで後述するサンプルの Sysprep.inf ファイルを参照してください。



6. 既定の Windows Welcome ではなく、ミニセットアップを実行するようにセットアッププロセスを構成します。 Sysprep ツールは、 **-ミニ**スイッチを使用して実行するか、グラフィカルユーザーインターフェイスで [**ミニセットアップ**] チェックボックスをオンにする必要があります。 詳細については、「 [Sysprep でイメージを封印する方法](#bkmk-seal)」を参照してください。

   **初回のセットアップ完了時のファイルの呼び出し**

   1.  FtsCompletion.exe という名前の実行可能ファイルは、MED-V ゲストエージェントのインストールの一部として含まれています。 既定では、[ **Program Files – Microsoft Enterprise デスクトップ仮想化**] の下にある med-v イメージのシステムドライブにあります。

       **重要**  
       初回のセットアッププロセスでの最終手順として、この実行可能プログラムを実行する必要があります。 実行可能プログラムが呼び出されるユーザーは、ゲストのローカル管理者グループのメンバーである必要があります。



   2.  たとえば、MED-V ワークスペースと共に展開されるスクリプトを使用して、この実行可能プログラムを呼び出す方法を決定することができます。 この実行可能ファイルは、Sysprep.inf ファイルの最後の行として呼び出すことができます。 Sysprep.inf ファイルでこの実行可能プログラムを呼び出す方法の例については、このセクションで後述するサンプルファイルを参照してください。

MED-V イメージのカスタマイズを完了したら、Sysprep を使用してイメージを封印することができます。

<a href="" id="bkmk-seal"></a>**Sysprep を使用した MED-V イメージの封印**

1.  システム準備ツール (Sysprep) は、管理者または IT プロフェッショナルによるネットワーク全体でイメージベースのインストールを実行するために使用できるテクノロジです。

2.  MED-V 環境では、Sysprep を使って、一意のセキュリティ Id (SID) とその他の設定を、最初に起動したときに各 MED-V ワークスペースに割り当てることができます。

    **注**  
    Sysprep の使い方の詳細については、「 [Sysprep テクニカルリファレンス](https://go.microsoft.com/fwlink/?LinkId=195930)(」) を参照してください https://go.microsoft.com/fwlink/?LinkId=195930) 。



~~~
**Caution**  
When you use non-ASCII characters in the Sysprep.inf file, you must save the file by using the encoding appropriate for the characters entered. Windows XP expects the Sysprep.inf file to be encoded by using the code page for the language that you are targeting.

You must also make sure that the System Locale of the computers to which the MED-V workspace is deployed is set to handle the language specific characters that might be present in the Sysprep.inf file. To change the settings for the System Locale, follow these steps:

1.  To open Region and Language, click **Start**, click **Control Panel**, and then click **Region and Language**.

2.  Click the **Administrative** tab, and then click **Change System Locale** under **Language for non-Unicode programs**.

    If you are prompted for an administrator password or confirmation, type the administrator password or provide confirmation.

3.  Select your preferred language and then click **OK**.



**To configure Sysprep on the MED-V Guest Computer**

1.  Create a folder named *Sysprep* in the root of the MED-V image system drive.

2.  Download the deploy.cab file. For more information, see [Windows XP Service Pack 3 Deployment Tools](https://go.microsoft.com/fwlink/?LinkId=195928) From the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195928).

3.  From the deploy.cab file, copy or extract the Setupmgr.exe, Sysprep.exe, and Setupcl.exe files to the Sysprep folder.

4.  In the Sysprep folder, run **Setup Manager** (Setupmgr.exe) to create a Sysprep.inf answer file.

    Or, you can create this file manually or use your company’s existing file. For more information, see [How to use the Sysprep tool to automate successful deployment of Windows XP](https://go.microsoft.com/fwlink/?LinkId=195929) (https://go.microsoft.com/fwlink/?LinkId=195929).

5.  Follow the **Setup Manager** wizard.

    **Important**  
    You must configure the MED-V guest to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.



    **Caution**  
    When you configure a proxy account for joining virtual machines to the domain, know that it is possible for an end user to obtain the proxy account credentials. Take all the necessary security precautions to minimize risk, such as limiting account user rights. For more information about security concerns when you configure a Windows Virtual PC image for MED-V, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).



    If end users must provide information during the first time setup process based on the parameters specified in the Sysprep.inf file, you must also specify that first time setup is run in **Attended** mode when you are creating your MED-V workspace package. If no information will be required from the end user, you can specify that first time setup is run in **Unattended** mode when you are creating your MED-V workspace package. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode. This requires that you provide all of the required settings information as you continue through the **Setup Manager** wizard.

    **Caution**  
    If you have set a local policy or registry entry to include a service level agreement (SLA) in your image (VHD), you must specify that first time setup is run in **Attended** mode or first time setup will fail. Or, a MED-V best practice is to enforce the SLA through Group Policy later so that the SLA is displayed to the end user after first time setup is finished.



    **Note**  
    You can configure the MED-V workspace to set certain Sysprep.inf settings based on the configuration of the host and the identity of the end user. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).



6.  Seal the MED-V image.

    **Important**  
    We recommend that you make a backup copy of the MED-V image before sealing it.



    After you have completed all the steps in the **Setup Manager** wizard, you are ready to run Sysprep to seal the MED-V image.

**To run Sysprep**

1.  Run the System Preparation Tool (Sysprep.exe) from the *Sysprep* folder that you created when you configured Sysprep in the MED-V virtual machine.

2.  In the warning message box that appears, click **OK**.

3.  In the **Options** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes. Also, make sure that the **Shutdown mode** box is set to **Shut down**.

4.  Click **Reseal**. This removes identity information and clears event logs to prepare for first time setup.

5.  If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and then change the selections.

6.  Click **OK** to complete the system preparation process.

After you have run Sysprep on your MED-V image, the virtual machine shuts down and is ready for use in creating a MED-V workspace.
~~~

## 例


Sysprep.inf ファイルの例を次に示します。

``` syntax
;SetupMgrTag
[GuiUnattended]
    EncryptedAdminPassword=NO
    TimeZone=10
    OEMDuplicatorstring="MED_V v2 Host"
    AdminPassword="administrator"
    AutoLogon=Yes
    AutoLogonCount=1
    OEMSkipRegional=1
    OemSkipWelcome=1

[UserData]
    ProductKey=
    FullName="MED-V User"
    OrgName="Contoso"
    ComputerName=*

[Identification]
    JoinDomain=domain.corp.contoso.com
    DomainAdmin=UserName
    DomainAdminPassword=Password

[Networking]
    InstallDefaultComponents=Yes

[Branding]
    BrandIEUsingUnattended=Yes

[Proxy]
    Proxy_Enable=0
    Use_Same_Proxy=0

[Unattended]
    InstallFilesPath=C:\sysprep\i386
    TargetPath=\WINDOWS
    UpdateServerProfileDirectory=1
    OemSkipEula=Yes

[RegionalSettings]
    LanguageGroup=1
    Language=00000409

[GuiRunOnce]
    Command0="wmic /namespace:\\root\default path SystemRestore call Disable %SystemDrive%\"
    Command1="c:\Program Files\Microsoft Enterprise Desktop Virtualization\FtsCompletion.exe"

[sysprepcleanup]
```

## 関連トピック


[MED-V ワークスペース パッケージを作成する](create-a-med-v-workspace-package.md)

[MED-V イメージを準備する](prepare-a-med-v-image.md)









