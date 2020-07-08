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
# HTTP によるクライアント レポートの送信のサポート


App-v クライアントのバージョン4.6 では、クライアントのレポートデータを発行サーバーに送信するときの HTTP 通信の使用がサポートされるようになりました。 この機能は、顧客がクライアントデータを収集して処理するように構成されているカスタム HTTP (S) 発行サーバーを実装しているシナリオをサポートします。

HTTP 発行サーバーの詳細については、 <https://go.microsoft.com/fwlink/?LinkId=157426>

## HTTP 経由のクライアントレポート


クライアントは、発行サーバーから発行された更新応答 XML で "REPORTING =" TRUE "属性を受け取ると、データの収集を開始します。 この属性を受け取ると、クライアントは、公開の更新を送信した発行サーバーに蓄積されたデータを送信します。 このプロセスの詳細は次のとおりです。

-   クライアントは発行サーバーに HTTP GET 要求を送信して、公開の更新を行います。 このメッセージのヘッダーには、カスタム HTTP (S) がメッセージの種類を識別するために使用する "AppV-Op: Refresh" カスタムヘッダーが含まれています。

-   発行サーバーは、"REPORTING =" TRUE "という値を含む発行の更新応答 XML を送信します。

-   次に、クライアントは、前回の更新以降に収集されたレポートデータと共に、HTTP POST 要求を発行サーバーに送信します。 このメッセージのヘッダーには、カスタム HTTP (S) がメッセージの種類を識別するために使用する "AppV-Op: Report" というカスタムヘッダーが含まれています。

次のスキーマは、サーバーに送信されるパッケージとアプリケーションデータの具体的な詳細を示しています。

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

 

 





