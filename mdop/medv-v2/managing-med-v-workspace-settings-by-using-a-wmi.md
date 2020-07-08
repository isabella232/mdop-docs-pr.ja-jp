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
# WMI を使用した MED-V ワークスペースの設定の管理


Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 で Windows Management Instrumentation (WMI) を使用して、現在の構成設定を管理できます。

## WMI を使用して MED-V ワークスペースの設定を管理するには


WMI ブラウジングツールを使用すると、MED-V ワークスペースの設定を表示および編集できます。 WMI プロバイダーは、Microsoft .Net Framework 3.5 から WMI プロバイダ拡張フレームワークを使って実装されています。

WMI プロバイダーは、 **root\\microsoft\\medv**名前空間に実装され、クラス**設定**を実装します。 [クラス]**設定**には、HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\medv レジストリキーのシステムレジストリ内の設定に対応するプロパティが含まれています。

**注意** WMI 閲覧ツールを使って、クラスやインスタンスを削除または変更することができます。 特定のクラスやインスタンスを削除または変更すると、重要なデータが失われ、MED-V が予期しない動作を引き起こす可能性があります。

 

以下の手順に従って、希望の WMI ブラウジングツールを使用して、MED-V 構成設定の表示と編集を行うことができます。

1.  管理者権限を持つ優先 WMI 閲覧ツールを開きます。

2.  名前空間**root\\microsoft\\medv**に接続します。

3.  実行中のインスタンスに接続するインスタンスを列挙します。 クラス**設定**のインスタンスに接続する必要があります。

    **オブジェクトエディター**ウィンドウが開きます。 MED-V 構成設定は、**プロパティ**として一覧表示されます。

WMI で MED-V 構成設定を編集するには、次の手順を実行します。

1.  [**オブジェクトエディター** ] ウィンドウの**プロパティ**の一覧で、編集する構成設定の名前をダブルクリックします。 たとえば、MED-V URL リダイレクション情報を編集するには、プロパティ**Uxredirecturls**をダブルクリックします。

    **プロパティエディター**ウィンドウが開きます。

2.  値を編集して構成情報を更新します。 たとえば、MED-V URL リダイレクション情報を編集するには、リストの web アドレスを追加または削除します。

3.  更新されたプロパティの設定を保存します。

MED-V 構成設定の表示または編集が完了したら、WMI ブラウジングツールを閉じます。

**重要** MED-V の構成設定の変更を有効にするには、MED-V ワークスペースの再起動が必要になる場合もあります。

 

次のコードは、**設定**クラスを定義するマネージオブジェクト形式 (MOF) ファイルを示しています。

``` syntax
[dynamic: ToInstance, provider("TroubleShooting, Version=2.0.392.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"), singleton: DisableOverride ToInstance ToSubClass]
class Setting : ConfigValueProvider
{
                boolean UxSmartCardLogonEnabled = TRUE;
                [read] string User;
                [implemented] void Clear([in] string propertyName);
};
```

**Setting**クラスは**configvalueprovider**クラスから継承します。 次のコードは、 **Configvalueprovider**クラスを定義するマネージオブジェクト形式 (MOF) ファイルを示しています。

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

## 関連トピック


[MED-V ワークスペースの構成設定の管理](managing-med-v-workspace-configuration-settings.md)

[MED-V ワークスペースの設定を管理する](manage-med-v-workspace-settings.md)

 

 





