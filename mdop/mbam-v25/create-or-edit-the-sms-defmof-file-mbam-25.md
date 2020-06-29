---
title: Sms \ _def ファイルを作成または編集する
description: Sms \ _def ファイルを作成または編集する
author: dansimp
ms.assetid: 0bc5e7d8-9747-4da6-a1b3-38d8f27ba121
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 272f597974e96efa0c742fecfe9488a4899fc695
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823197"
---
# <span data-ttu-id="24502-103">Sms \ _def ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="24502-103">Create or Edit the Sms\_def.mof File</span></span>


<span data-ttu-id="24502-104">MBAM Configuration Manager レポートを使って、クライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、Sms \ _def .mof ファイルを作成または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24502-104">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to create or edit the Sms\_def.mof file.</span></span>

<span data-ttu-id="24502-105">SystemCenter2012 ConfigurationManager を使用している場合は、ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24502-105">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span> <span data-ttu-id="24502-106">トップレベルサイトにファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="24502-106">Create the file on the top-tier site.</span></span> <span data-ttu-id="24502-107">変更はインフラストラクチャ内の他のサイトに複製されます。</span><span class="sxs-lookup"><span data-stu-id="24502-107">The changes will be replicated to the other sites in your infrastructure.</span></span>

<span data-ttu-id="24502-108">Configuration Manager 2007 では、ファイルは既に存在しているので、編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24502-108">In Configuration Manager 2007, the file already exists, so you only have to edit it.</span></span> **<span data-ttu-id="24502-109">既存のファイルは上書きしないでください。</span><span class="sxs-lookup"><span data-stu-id="24502-109">Do not overwrite the existing file.</span></span>**

<span data-ttu-id="24502-110">以下のセクションで、使用している Configuration Manager のバージョンに対応する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="24502-110">In the following sections, complete the instructions that correspond to the version of Configuration Manager that you are using.</span></span>

**<span data-ttu-id="24502-111">SystemCenter2012 ConfigurationManager の Sms \ _def ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="24502-111">To create the Sms\_def.mof file for SystemCenter2012 ConfigurationManager</span></span>**

1.  <span data-ttu-id="24502-112">Configuration Manager サーバーで、Sms \ _def のファイル (デスクトップなど) を作成する場所に移動します (例)。</span><span class="sxs-lookup"><span data-stu-id="24502-112">On the Configuration Manager Server, browse to the location where you have to create the Sms\_def.mof file, for example, the Desktop.</span></span>

2.  <span data-ttu-id="24502-113">**Sms \ _def .mof**というテキストファイルを作成し、次のコードをコピーして、次の sms \ _def の「.mof (.mof)」クラスでファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="24502-113">Create a text file called **Sms\_def.mof** and copy the following code to populate the file with the following Sms\_def.mof MBAM classes:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL)
    [ SMS_Report (TRUE),
      SMS_Group_Name ("BitLocker Encryption Details"),
      SMS_Class_ID ("MICROSOFT|BITLOCKER_DETAILS|1.0")]
    class Win32_BitLockerEncryptionDetails : SMS_Class_Template
    {
        [ SMS_Report (TRUE), key ]
        String     DeviceId;
        [ SMS_Report (TRUE) ]
        String     BitlockerPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        String     MbamPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        SInt32     MbamVolumeType;
        [ SMS_Report (TRUE) ]
        String     DriveLetter;
        [ SMS_Report (TRUE) ]
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        SInt32     Compliant;
        [ SMS_Report (TRUE) ]
        SInt32     ReasonsForNonCompliance[];
        [ SMS_Report (TRUE) ]
        SInt32     KeyProtectorTypes[];
        [ SMS_Report (TRUE) ]
        SInt32     EncryptionMethod;
        [ SMS_Report (TRUE) ]
        SInt32     ConversionStatus;
        [ SMS_Report (TRUE) ]
        SInt32     ProtectionStatus;
        [ SMS_Report (TRUE) ]
        Boolean     IsAutoUnlockEnabled;
        [ SMS_Report (TRUE) ]
        String     NoncomplianceDetectedDate;
        [ SMS_Report (TRUE) ]
        String     EnforcePolicyDate;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0")]
    Class Win32Reg_MBAMPolicy: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;
        
        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;
        
        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser; 
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    //Read Win32_OperatingSystem.SKU WMI property in a new class - because SKU is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Operating System Ex"),
      SMS_Class_ID   ("MICROSOFT|OPERATING_SYSTEM_EXT|1.0") ]
    class CCM_OperatingSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
            string     Name;
        [SMS_Report (TRUE) ]
            uint32     SKU;
    };

    //Read Win32_ComputerSystem.PCSystemType WMI property in a new class - because PCSystemType is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Computer System Ex"),
      SMS_Class_ID   ("MICROSOFT|COMPUTER_SYSTEM_EXT|1.0") ]
    class CCM_ComputerSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
        string     Name;
        [SMS_Report (TRUE) ]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================
    ```

3.  <span data-ttu-id="24502-114">**Sms \ _def**ファイルをインポートするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="24502-114">Import the **Sms\_def.mof** file by doing the following:</span></span>

    1.  <span data-ttu-id="24502-115">**SystemCenter2012 ConfigurationManager コンソール**を開いて、[**管理**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="24502-115">Open the **SystemCenter2012 ConfigurationManager console** and select the **Administration** tab.</span></span>

    2.  <span data-ttu-id="24502-116">[**管理**] タブで、[**クライアントの設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="24502-116">On the **Administration** tab, select **Client Settings**.</span></span>

    3.  <span data-ttu-id="24502-117">[既定の**クライアント設定**] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24502-117">Right-click **Default Client Settings**, and then select **Properties**.</span></span>

    4.  <span data-ttu-id="24502-118">[**既定の設定**] ウィンドウで、[**ハードウェアインベントリ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="24502-118">In the **Default Settings** window, select **Hardware Inventory**.</span></span>

    5.  <span data-ttu-id="24502-119">[**クラスの設定**] をクリックし、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24502-119">Click **Set Classes**, and then click **Import**.</span></span>

    6.  <span data-ttu-id="24502-120">表示されたブラウザーで、使用**し**ている .mof ファイルを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24502-120">In the browser that opens, select your **.mof** file, and then click **Open**.</span></span> <span data-ttu-id="24502-121">[**インポートの概要**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="24502-121">The **Import Summary** window opens.</span></span>

    7.  <span data-ttu-id="24502-122">[**インポートの概要**] ウィンドウで、[ハードウェアインベントリクラスとクラス設定の両方をインポートする] オプションが選択されていることを確認し、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24502-122">In the **Import Summary** window, ensure that the option to import both hardware inventory classes and class settings is selected, and then click **Import**.</span></span>

    8.  <span data-ttu-id="24502-123">[**ハードウェアインベントリクラス**] ウィンドウと [**既定の設定**] ウィンドウの両方で、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24502-123">In both the **Hardware Inventory Classes** window and the **Default Settings** window, click **OK**.</span></span>

4.  <span data-ttu-id="24502-124">次のようにして**Win32 \ _Tpm**クラスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="24502-124">Enable the **Win32\_Tpm** class as follows:</span></span>

    1.  <span data-ttu-id="24502-125">**SystemCenter2012 ConfigurationManager コンソール**を開いて、[**管理**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="24502-125">Open the **SystemCenter2012 ConfigurationManager console** and select the **Administration** tab.</span></span>

    2.  <span data-ttu-id="24502-126">[**管理**] タブで、[**クライアントの設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="24502-126">On the **Administration** tab, select **Client Settings**.</span></span>

    3.  <span data-ttu-id="24502-127">[既定の**クライアント設定**] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24502-127">Right-click **Default Client Settings**, and then select **Properties**.</span></span>

    4.  <span data-ttu-id="24502-128">[**既定の設定**] ウィンドウで、[**ハードウェアインベントリ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="24502-128">In the **Default Settings** window, select **Hardware Inventory**.</span></span>

    5.  <span data-ttu-id="24502-129">[**クラスの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24502-129">Click **Set Classes**.</span></span>

    6.  <span data-ttu-id="24502-130">メインウィンドウで下にスクロールし、 **TPM (Win32 \ _Tpm)** クラスを選択します。</span><span class="sxs-lookup"><span data-stu-id="24502-130">In the main window, scroll down, and then select the **TPM (Win32\_Tpm)** class.</span></span>

    7.  <span data-ttu-id="24502-131">[ **TPM**] で、 **specversion**プロパティが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24502-131">Under **TPM**, ensure that the **SpecVersion** property is selected.</span></span>

    8.  <span data-ttu-id="24502-132">[**ハードウェアインベントリクラス**] ウィンドウと [**既定の設定**] ウィンドウの両方で、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24502-132">In both the **Hardware Inventory Classes** window and the **Default Settings** window, click **OK**.</span></span>

**<span data-ttu-id="24502-133">Configuration Manager 2007 用の sms \ _def ファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="24502-133">To edit the sms\_def.mof file for Configuration Manager 2007</span></span>**

1.  <span data-ttu-id="24502-134">Configuration Manager サーバーで、 **sms \ _def**ファイルが保存されている場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="24502-134">On the Configuration Manager Server, browse to the location of the **sms\_def.mof** file:</span></span>

    <span data-ttu-id="24502-135">&lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv</span><span class="sxs-lookup"><span data-stu-id="24502-135">&lt;CMInstallLocation&gt;\\Inboxes\\clifiles.src\\hinv</span></span>\\

    <span data-ttu-id="24502-136">既定のインストールの場合、インストール場所は% systemdrive% \\ Program Files (x86) ¥ Microsoft Configuration Manager です。</span><span class="sxs-lookup"><span data-stu-id="24502-136">On a default installation, the installation location is %systemdrive% \\Program Files (x86)\\Microsoft Configuration Manager.</span></span>

2.  <span data-ttu-id="24502-137">次のコードをコピーし、 **Sms \ _def**ファイルに追加して、次の必要な mbam クラスをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="24502-137">Copy the following code, and then append it to **Sms\_def.mof** file to add the following required MBAM classes to the file:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL)
    [ SMS_Report (TRUE),
      SMS_Group_Name ("BitLocker Encryption Details"),
      SMS_Class_ID ("MICROSOFT|BITLOCKER_DETAILS|1.0")]
    class Win32_BitLockerEncryptionDetails : SMS_Class_Template
    {
        [ SMS_Report (TRUE), key ]
        String     DeviceId;
        [ SMS_Report (TRUE) ]
        String     BitlockerPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        String     MbamPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        SInt32     MbamVolumeType;
        [ SMS_Report (TRUE) ]
        String     DriveLetter;
        [ SMS_Report (TRUE) ]
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        SInt32     Compliant;
        [ SMS_Report (TRUE) ]
        SInt32     ReasonsForNonCompliance[];
        [ SMS_Report (TRUE) ]
        SInt32     KeyProtectorTypes[];
        [ SMS_Report (TRUE) ]
        SInt32     EncryptionMethod;
        [ SMS_Report (TRUE) ]
        SInt32     ConversionStatus;
        [ SMS_Report (TRUE) ]
        SInt32     ProtectionStatus;
        [ SMS_Report (TRUE) ]
        Boolean     IsAutoUnlockEnabled;
        [ SMS_Report (TRUE) ]
        String     NoncomplianceDetectedDate;
        [ SMS_Report (TRUE) ]
        String     EnforcePolicyDate;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0"),
      SMS_Context_1("__ProviderArchitecture=32|uint32"),
      SMS_Context_2("__RequiredArchitecture=true|boolean")]
    Class Win32Reg_MBAMPolicy: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;
        
        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;
        
        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser; 
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        // Encoded Computer Name
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0"),
      SMS_Context_1("__ProviderArchitecture=64|uint32"),
      SMS_Context_2("__RequiredArchitecture=true|boolean")]
    Class Win32Reg_MBAMPolicy_64: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;
        
        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;
        
        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser; 
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        // Encoded Computer Name
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    //Read Win32_OperatingSystem.SKU WMI property in a new class - because SKU is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Operating System Ex"),
      SMS_Class_ID   ("MICROSOFT|OPERATING_SYSTEM_EXT|1.0") ]
    class CCM_OperatingSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
            string     Name;
        [SMS_Report (TRUE) ]
            uint32     SKU;
    };

    //Read Win32_ComputerSystem.PCSystemType WMI property in a new class - because PCSystemType is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Computer System Ex"),
      SMS_Class_ID   ("MICROSOFT|COMPUTER_SYSTEM_EXT|1.0") ]
    class CCM_ComputerSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
        string     Name;
        [SMS_Report (TRUE) ]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================
    ```

3.  <span data-ttu-id="24502-138">**Win32 \ _Tpm**クラスを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="24502-138">Modify the **Win32\_Tpm** class as follows:</span></span>

    -   <span data-ttu-id="24502-139">Class 属性で**SMS \ _REPORT**を**TRUE**に設定します。</span><span class="sxs-lookup"><span data-stu-id="24502-139">Set **SMS\_REPORT** to **TRUE** in the class attributes.</span></span>

    -   <span data-ttu-id="24502-140">**Specversion**プロパティ属性で**SMS \ _REPORT**を**TRUE**に設定します。</span><span class="sxs-lookup"><span data-stu-id="24502-140">Set **SMS\_REPORT** to **TRUE** in the **SpecVersion** property attribute.</span></span>

    <span data-ttu-id="24502-141">**MBAM の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="24502-141">**Got a suggestion for MBAM**?</span></span> <span data-ttu-id="24502-142">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="24502-142">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> <span data-ttu-id="24502-143">**MBAM の問題が発生した場合**</span><span class="sxs-lookup"><span data-stu-id="24502-143">**Got a MBAM issue**?</span></span> <span data-ttu-id="24502-144">[Mbam TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)を使用します。</span><span class="sxs-lookup"><span data-stu-id="24502-144">Use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="24502-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="24502-145">Related topics</span></span>


[<span data-ttu-id="24502-146">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="24502-146">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)

[<span data-ttu-id="24502-147">Configuration.mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="24502-147">Edit the Configuration.mof File</span></span>](edit-the-configurationmof-file-mbam-25.md)

[<span data-ttu-id="24502-148">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="24502-148">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

 

 
## <span data-ttu-id="24502-149">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="24502-149">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="24502-150">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="24502-150">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="24502-151">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="24502-151">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




