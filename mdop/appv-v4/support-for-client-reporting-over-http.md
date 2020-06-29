---
title: HTTP によるクライアント レポートの送信のサポート
description: HTTP によるクライアント レポートの送信のサポート
author: dansimp
ms.assetid: 4a26ac80-1fb5-4c05-83de-4d06793f7bf2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4e1759bb4df39ac403e2837c4083275a8b3436f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815287"
---
# <span data-ttu-id="8d565-103">HTTP によるクライアント レポートの送信のサポート</span><span class="sxs-lookup"><span data-stu-id="8d565-103">Support for Client Reporting over HTTP</span></span>


<span data-ttu-id="8d565-104">App-v クライアントのバージョン4.6 では、クライアントのレポートデータを発行サーバーに送信するときの HTTP 通信の使用がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8d565-104">Version 4.6 of the App-V client now supports the use of HTTP communication when sending client reporting data to the publishing server.</span></span> <span data-ttu-id="8d565-105">この機能は、顧客がクライアントデータを収集して処理するように構成されているカスタム HTTP (S) 発行サーバーを実装しているシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8d565-105">This feature supports scenarios where a customer has implemented a custom HTTP(S) publishing server that is configured to collect and process client data.</span></span>

<span data-ttu-id="8d565-106">HTTP 発行サーバーの詳細については、</span><span class="sxs-lookup"><span data-stu-id="8d565-106">For more information on HTTP publishing servers, see</span></span> <https://go.microsoft.com/fwlink/?LinkId=157426>

## <span data-ttu-id="8d565-107">HTTP 経由のクライアントレポート</span><span class="sxs-lookup"><span data-stu-id="8d565-107">Client Reporting over HTTP</span></span>


<span data-ttu-id="8d565-108">クライアントは、発行サーバーから発行された更新応答 XML で "REPORTING =" TRUE "属性を受け取ると、データの収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="8d565-108">The client starts collecting data when it receives a “REPORTING=”TRUE””attribute in the publishing refresh response XML from the publishing server.</span></span> <span data-ttu-id="8d565-109">この属性を受け取ると、クライアントは、公開の更新を送信した発行サーバーに蓄積されたデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="8d565-109">When this attribute is received, the client sends any accumulated data to the publishing server that sent the publishing refresh.</span></span> <span data-ttu-id="8d565-110">このプロセスの詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d565-110">The details of this process are as follows:</span></span>

-   <span data-ttu-id="8d565-111">クライアントは発行サーバーに HTTP GET 要求を送信して、公開の更新を行います。</span><span class="sxs-lookup"><span data-stu-id="8d565-111">The client sends an HTTP GET request to the publishing server for a publishing refresh.</span></span> <span data-ttu-id="8d565-112">このメッセージのヘッダーには、カスタム HTTP (S) がメッセージの種類を識別するために使用する "AppV-Op: Refresh" カスタムヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d565-112">The header of this message contains an “AppV-Op:Refresh” custom header that the custom HTTP(S) publishing server uses to identify the message type.</span></span>

-   <span data-ttu-id="8d565-113">発行サーバーは、"REPORTING =" TRUE "という値を含む発行の更新応答 XML を送信します。</span><span class="sxs-lookup"><span data-stu-id="8d565-113">The publishing server then sends the publishing refresh response XML that contains a “REPORTING=”TRUE”” value.</span></span>

-   <span data-ttu-id="8d565-114">次に、クライアントは、前回の更新以降に収集されたレポートデータと共に、HTTP POST 要求を発行サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="8d565-114">The client then sends an HTTP POST request to the publishing server along with the reporting data that has been gathered since the previous refresh.</span></span> <span data-ttu-id="8d565-115">このメッセージのヘッダーには、カスタム HTTP (S) がメッセージの種類を識別するために使用する "AppV-Op: Report" というカスタムヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d565-115">The header of this message contains an “AppV-Op:Report” custom header that the custom HTTP(S) publishing server uses to identify the message type.</span></span>

<span data-ttu-id="8d565-116">次のスキーマは、サーバーに送信されるパッケージとアプリケーションデータの具体的な詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d565-116">The following schema gives specific details of the package and the application data that is sent to the server.</span></span>

```xml
<?xml version="1.0"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:element name="CLIENT_DATA">
        <xs:complexType>
            <xs:all>
                <xs:element ref="PKG_LIST" minOccurs="1" maxOccurs="1"/>
                <xs:element ref="APP_RECORDS" minOccurs="1" maxOccurs="1"/>
            </xs:all>
            <!-- no regex for Ver because we want to allow tags like "Beta" -->
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Host" type="xs:token" use="required"/>
            <xs:attribute name="CacheSize" type="xs:nonNegativeInteger" use="required"/>
            <xs:attribute name="CacheUsed" type="xs:nonNegativeInteger" use="required"/>
        </xs:complexType>
    </xs:element>

    <xs:element name="PKG_LIST">
        <xs:complexType>
            <xs:choice>
                <xs:element ref="PKG_DATA" minOccurs="0" maxOccurs="unbounded"/>
            </xs:choice>
        </xs:complexType>
    </xs:element>

    <xs:element name="PKG_DATA">
        <xs:complexType>
            <xs:attribute name="Name" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Guid" type="xs:token" use="required"/>
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="VerGuid" type="xs:token" use="required"/>
            <xs:attribute name="Source" type="xs:normalizedString" use="required"/>
            <xs:attribute name="PctCached" use="required">
                <xs:simpleType>
                    <xs:restriction base="xs:nonNegativeInteger">
                        <xs:minInclusive value="0"/>
                        <xs:maxInclusive value="100"/>
                    </xs:restriction>
                </xs:simpleType>
            </xs:attribute>
        </xs:complexType>
    </xs:element>

    <xs:element name="APP_RECORDS">
         <xs:complexType>
            <xs:choice>
                <xs:element ref="APP_RECORD" minOccurs="0" maxOccurs="unbounded"/>
            </xs:choice>
        </xs:complexType>
   </xs:element>

    <xs:element name="APP_RECORD">
            <xs:attribute name="Name" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Server" type="xs:normalizedString" use="required"/>
            <xs:attribute name="User" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Launched" type="xs:dateTime" use="required"/>
            <xs:attribute name="Shutdown" type="xs:dateTime" use="optional"/>
    </xs:element>

</xs:schema>
```

 

 





