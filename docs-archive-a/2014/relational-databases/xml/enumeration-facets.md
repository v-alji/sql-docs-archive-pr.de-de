---
title: Enumerationsfacets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- enumeration facets
ms.assetid: dec23a79-ddd6-4701-9721-55a2c435a34d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e06598890d9b652879327e0351db5113cc17e6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608432"
---
# <a name="enumeration-facets"></a>Enumerationsfacets
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weist XML-Schemas mit Typen zurück, die Musterfacets besitzen, oder Enumerationen, die diese Facets verletzen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Schema würde zurückgewiesen, weil der enthaltene Enumerationswert einen Wert mit einer Mischung aus Groß- und Kleinschreibung umfasst. Ein weiterer Grund für die Zurückweisung besteht darin, dass dieser Wert den Musterwert verletzt, der Werte ausschließlich auf Kleinbuchstaben beschränkt.  
  
```  
CREATE XML SCHEMA COLLECTION MySampleCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" xmlns:ns="http://ns">  
    <simpleType name="MyST">  
       <restriction base="string">  
          <pattern value="[a-z]*"/>  
       </restriction>  
    </simpleType>  
  
    <simpleType name="MyST2">  
       <restriction base="ns:MyST">  
           <enumeration value="mYstring"/>  
       </restriction>  
    </simpleType>  
</schema>'  
GO  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
