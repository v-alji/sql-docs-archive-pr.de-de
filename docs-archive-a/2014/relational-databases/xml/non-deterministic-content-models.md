---
title: Nicht deterministische Inhaltsmodelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696510"
---
# <a name="non-deterministic-content-models"></a><span data-ttu-id="add54-102">Nicht deterministische Inhaltsmodelle</span><span class="sxs-lookup"><span data-stu-id="add54-102">Non-Deterministic Content Models</span></span>
  <span data-ttu-id="add54-103">Vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1) lehnte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML-Schemas ab, die nicht deterministische Inhaltsmodelle enthielten.</span><span class="sxs-lookup"><span data-stu-id="add54-103">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejected XML schemas that had non-deterministic content models.</span></span>  
  
 <span data-ttu-id="add54-104">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1 werden nicht deterministische Inhaltsmodelle jedoch akzeptiert, wenn die Vorkommenseinschränkungen „0,1“ oder „unbegrenzt“ lauten.</span><span class="sxs-lookup"><span data-stu-id="add54-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, however, non-deterministic content models are accepted if the occurrence constraints are 0,1, or unbounded.</span></span>  
  
## <a name="example-non-deterministic-content-model-rejected"></a><span data-ttu-id="add54-105">Beispiel: Nicht deterministisches Inhaltsmodell abgelehnt</span><span class="sxs-lookup"><span data-stu-id="add54-105">Example: Non-deterministic content model rejected</span></span>  
 <span data-ttu-id="add54-106">Im folgenden Beispiel wird versucht, ein XML-Schema mit einem nicht deterministischen Inhaltsmodell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="add54-106">The following example attempts to create an XML schema with a non-deterministic content model.</span></span> <span data-ttu-id="add54-107">Der Code schlägt fehl, da unklar ist, ob das `<root>` -Element eine Sequenz mit zwei `<a>` -Elementen oder ob das `<root>` -Element zwei Sequenzen mit jeweils einem `<a>` -Element haben sollte.</span><span class="sxs-lookup"><span data-stu-id="add54-107">The code fails because it is not clear whether the `<root>` element should have a sequence of two `<a>` elements or if the `<root>` element should have two sequences, each with an `<a>` element.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 <span data-ttu-id="add54-108">Das Schema kann durch Verschieben der Vorkommenseinschränkung an einen eindeutigen Speicherort korrigiert werden.</span><span class="sxs-lookup"><span data-stu-id="add54-108">The schema can be fixed by moving the occurrence constraint to a unique location.</span></span> <span data-ttu-id="add54-109">So kann z. B. die Einschränkung zum enthaltenden Sequenzpartikel verschoben werden:</span><span class="sxs-lookup"><span data-stu-id="add54-109">For example, the constraint can be moved to the containing sequence particle:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 <span data-ttu-id="add54-110">Oder die Einschränkung kann zum enthaltenen Element verschoben werden:</span><span class="sxs-lookup"><span data-stu-id="add54-110">Or the constraint can be moved to the contained element:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a><span data-ttu-id="add54-111">Beispiel: Nicht deterministisches Inhaltsmodell akzeptiert</span><span class="sxs-lookup"><span data-stu-id="add54-111">Example: Non-deterministic content model accepted</span></span>  
 <span data-ttu-id="add54-112">Das folgende Schema würde in Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die älter als [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1 sind, abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="add54-112">The following schema would be rejected in versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="add54-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="add54-113">See Also</span></span>  
 [<span data-ttu-id="add54-114">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="add54-114">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
