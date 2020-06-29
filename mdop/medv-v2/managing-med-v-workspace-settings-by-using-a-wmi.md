---
title: WMI を使用した MED-V ワークスペースの設定の管理
description: WMI を使用した MED-V ワークスペースの設定の管理
author: dansimp
ms.assetid: 05a665a3-2309-46c1-babb-a3e3bbb0b1f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e74e6fa4944ce0dacd5503baec73044b231abe83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826134"
---
# <span data-ttu-id="7c57b-103">WMI を使用した MED-V ワークスペースの設定の管理</span><span class="sxs-lookup"><span data-stu-id="7c57b-103">Managing MED-V Workspace Settings by Using a WMI</span></span>


<span data-ttu-id="7c57b-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 で Windows Management Instrumentation (WMI) を使用して、現在の構成設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-104">You can use Windows Management Instrumentation (WMI) in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 to manage your current configuration settings.</span></span>

## <span data-ttu-id="7c57b-105">WMI を使用して MED-V ワークスペースの設定を管理するには</span><span class="sxs-lookup"><span data-stu-id="7c57b-105">To manage MED-V workspace settings with a WMI</span></span>


<span data-ttu-id="7c57b-106">WMI ブラウジングツールを使用すると、MED-V ワークスペースの設定を表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-106">A WMI browsing tool lets you view and edit the settings in a MED-V workspace.</span></span> <span data-ttu-id="7c57b-107">WMI プロバイダーは、Microsoft .Net Framework 3.5 から WMI プロバイダ拡張フレームワークを使って実装されています。</span><span class="sxs-lookup"><span data-stu-id="7c57b-107">The WMI provider is implemented by using the WMI Provider Extension framework from the Microsoft .Net Framework 3.5.</span></span>

<span data-ttu-id="7c57b-108">WMI プロバイダーは、 **root\\microsoft\\medv**名前空間に実装され、クラス**設定**を実装します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-108">The WMI provider is implemented in the **root\\microsoft\\medv** namespace and implements the class **Setting**.</span></span> <span data-ttu-id="7c57b-109">[クラス]**設定**には、HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\medv レジストリキーのシステムレジストリ内の設定に対応するプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c57b-109">The class **Setting** contains properties that correspond to the settings in the system registry under the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv registry key.</span></span>

<span data-ttu-id="7c57b-110">**注意** WMI 閲覧ツールを使って、クラスやインスタンスを削除または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-110">**Caution** WMI browsing tools can be used to delete or modify classes and instances.</span></span> <span data-ttu-id="7c57b-111">特定のクラスやインスタンスを削除または変更すると、重要なデータが失われ、MED-V が予期しない動作を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7c57b-111">Deleting or modifying certain classes and instances can result in the loss of valuable data and cause MED-V to function unpredictably.</span></span>

 

<span data-ttu-id="7c57b-112">以下の手順に従って、希望の WMI ブラウジングツールを使用して、MED-V 構成設定の表示と編集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-112">You can use your preferred WMI browsing tool to view and edit MED-V configuration settings by following these steps.</span></span>

1.  <span data-ttu-id="7c57b-113">管理者権限を持つ優先 WMI 閲覧ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-113">Open your preferred WMI browsing tool with administrator permissions.</span></span>

2.  <span data-ttu-id="7c57b-114">名前空間**root\\microsoft\\medv**に接続します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-114">Connect to the namespace **root\\microsoft\\medv**.</span></span>

3.  <span data-ttu-id="7c57b-115">実行中のインスタンスに接続するインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-115">Enumerate the instances to connect to the running instance.</span></span> <span data-ttu-id="7c57b-116">クラス**設定**のインスタンスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c57b-116">You want to connect to the instance of the class **Setting**.</span></span>

    <span data-ttu-id="7c57b-117">**オブジェクトエディター**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-117">An **Object Editor** window opens.</span></span> <span data-ttu-id="7c57b-118">MED-V 構成設定は、**プロパティ**として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-118">The MED-V configuration settings are listed as **Properties**.</span></span>

<span data-ttu-id="7c57b-119">WMI で MED-V 構成設定を編集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-119">Perform the following steps to edit a MED-V configuration setting in the WMI.</span></span>

1.  <span data-ttu-id="7c57b-120">[**オブジェクトエディター** ] ウィンドウの**プロパティ**の一覧で、編集する構成設定の名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c57b-120">In the list of **Properties** on the **Object Editor** window, double-click the name of the configuration setting you want to edit.</span></span> <span data-ttu-id="7c57b-121">たとえば、MED-V URL リダイレクション情報を編集するには、プロパティ**Uxredirecturls**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c57b-121">For example, to edit MED-V URL redirection information, double-click the property **UxRedirectUrls**.</span></span>

    <span data-ttu-id="7c57b-122">**プロパティエディター**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-122">A **Property Editor** window opens.</span></span>

2.  <span data-ttu-id="7c57b-123">値を編集して構成情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-123">Edit the value to update the configuration information.</span></span> <span data-ttu-id="7c57b-124">たとえば、MED-V URL リダイレクション情報を編集するには、リストの web アドレスを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-124">For example, to edit MED-V URL redirection information, add or remove a web address in the list.</span></span>

3.  <span data-ttu-id="7c57b-125">更新されたプロパティの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-125">Save the updated property settings.</span></span>

<span data-ttu-id="7c57b-126">MED-V 構成設定の表示または編集が完了したら、WMI ブラウジングツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7c57b-126">After you have finished viewing or editing MED-V configuration settings, close the WMI browsing tool.</span></span>

<span data-ttu-id="7c57b-127">**重要** MED-V の構成設定の変更を有効にするには、MED-V ワークスペースの再起動が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7c57b-127">**Important** In some cases, a restart of the MED-V workspace is required for changes to MED-V configuration settings to take effect.</span></span>

 

<span data-ttu-id="7c57b-128">次のコードは、**設定**クラスを定義するマネージオブジェクト形式 (MOF) ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c57b-128">The following code shows the Managed Object Format (MOF) file that defines the **Setting** class.</span></span>

``` syntax
[dynamic: ToInstance, provider("TroubleShooting, Version=2.0.392.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"), singleton: DisableOverride ToInstance ToSubClass]
class Setting : ConfigValueProvider
{
                boolean UxSmartCardLogonEnabled = TRUE;
                [read] string User;
                [implemented] void Clear([in] string propertyName);
};
```

<span data-ttu-id="7c57b-129">**Setting**クラスは**configvalueprovider**クラスから継承します。</span><span class="sxs-lookup"><span data-stu-id="7c57b-129">The **Setting** class inherits from the **ConfigValueProvider** class.</span></span> <span data-ttu-id="7c57b-130">次のコードは、 **Configvalueprovider**クラスを定義するマネージオブジェクト形式 (MOF) ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c57b-130">The following code shows the Managed Object Format (MOF) file that defines the **ConfigValueProvider** class.</span></span>

``` syntax
[abstract]
class ConfigValueProvider
{
                [write] string DiagEventLogLevel;
                [write] boolean FtsAddUserToAdminGroupEnabled;
                [write] string FtsComputerNameMask;
                [write] sint32 FtsDeleteVMStateTimeout;
                [write] sint32 FtsDetachVfdTimeout;
                [write] string FtsDialogUrl;
                [write] sint32 FtsExplorerTimeout;
                [write] string FtsFailureDialogMsg;
                [write] string FtsLogFilePaths[];
                [write] sint32 FtsMaxPostponeTime;
                [write] sint32 FtsMaxRetryCount;
                [write] string FtsMode;
                [write] sint32 FtsNonInteractiveRetryTimeoutInc;
                [write] sint32 FtsNonInteractiveTimeout;
                [write] string FtsPostponeUtcDateTimeLimit;
                [write] string FtsRetryDialogMsg;
                [write] boolean FtsSetComputerNameEnabled;
                [write] boolean FtsSetJoinDomainEnabled;
                [write] boolean FtsSetMachineObjectOUEnabled;
                [write] boolean FtsSetRegionalSettingsEnabled;
                [write] boolean FtsSetUserDataEnabled;
                [write] string FtsStartDialogMsg;
                [write] sint32 FtsTaskCancelTimeout;
                [write] sint32 FtsTaskVMTurnOffTimeout;
                [write] sint32 FtsUpgradeTimeout;
                [write] boolean UxAppPublishingEnabled;
                [write] boolean UxAudioSharingEnabled;
                [write] boolean UxClipboardSharingEnabled;
                [write] boolean UxCredentialCacheEnabled;
                [write] sint32 UxDialogTimeout;
                [write] sint32 UxHideVmTimeout;
                [write] boolean UxLogonStartEnabled;
                [write] boolean UxPrinterSharingEnabled;
                [write] sint32 UxRebootAbsoluteDelayTimeout;
                [write] string UxRedirectUrls[];
                [write] boolean UxShowExit;
                [write] boolean UxSmartCardLogonEnabled;
                [write] boolean UxSmartCardSharingEnabled;
                [write] boolean UxUSBDeviceSharingEnabled;
                [write] string VmCloseAction;
                [write] sint32 VmGuestMemFromHostMem[];
                [write] sint32 VmGuestUpdateDuration;
                [write] string VmGuestUpdateTime;
                [write] sint32 VmHostMemToGuestMem[];
                [write] boolean VmHostMemToGuestMemCalcEnabled;
                [write] sint32 VmMemory;
                [write] boolean VmMultiUserEnabled;
                [write] string VmNetworkingMode;
                [write] sint32 VmTaskTimeout;
};
```

## <span data-ttu-id="7c57b-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7c57b-131">Related topics</span></span>


[<span data-ttu-id="7c57b-132">MED-V ワークスペースの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="7c57b-132">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="7c57b-133">MED-V ワークスペースの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="7c57b-133">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





