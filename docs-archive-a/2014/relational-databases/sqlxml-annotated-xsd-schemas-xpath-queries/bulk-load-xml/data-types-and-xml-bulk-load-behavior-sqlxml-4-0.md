---
title: Datentypen und XML-Massen Ladeverhalten (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- bulk load [SQLXML], data types
- data types [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], data types
ms.assetid: d1ac1939-1f6c-4398-b7a7-a79ca608a4f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b03423f3bb88166d0d9ce5b0df450d4455e7ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619750"
---
# <a name="data-types-and-xml-bulk-load-behavior-sqlxml-40"></a><span data-ttu-id="e6b7b-102">Datentypen und XML-Massenladenverhalten (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e6b7b-102">Data Types and XML Bulk Load Behavior (SQLXML 4.0)</span></span>
  <span data-ttu-id="e6b7b-103">Die Datentypen, die im Zuordnungsschema (XSD- oder XDR-Schema und `sql:datatype`) angegeben werden, werden mit Ausnahme der folgenden Fälle immer ignoriert:</span><span class="sxs-lookup"><span data-stu-id="e6b7b-103">The data types that are specified in the mapping schema (XSD or XDR type and `sql:datatype`) are generally ignored, except in the following cases:</span></span>  
  
 <span data-ttu-id="e6b7b-104">Bei XSD:</span><span class="sxs-lookup"><span data-stu-id="e6b7b-104">In XSD:</span></span>  
  
-   <span data-ttu-id="e6b7b-105">Bei den Typen `dateTime` oder `time` müssen Sie die `sql:datatype`-Anmerkung angeben, da XML-Massenladen vor dem Senden der Daten an Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] eine Datenkonvertierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="e6b7b-105">If the type is `dateTime` or `time`, you must specify the `sql:datatype` because XML Bulk Load performs data conversion before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e6b7b-106">Wenn Sie ein Massen laden in eine Spalte vom `uniqueidentifier` Typ in Ausführen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] und der XSD-Wert eine GUID mit geschweiften Klammern ({und}) ist, müssen Sie **SQL: datatype = "uniqueidentifier"** angeben, um die geschweiften Klammern zu entfernen, bevor der Wert in die Spalte eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e6b7b-106">When you are bulk loading into a column of `uniqueidentifier` type in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and the XSD value is a GUID that includes braces ({ and }), you must specify **sql:datatype="uniqueidentifier"** to remove the braces before the value is inserted into the column.</span></span> <span data-ttu-id="e6b7b-107">Wenn `sql:datatype` nicht angegeben wird, wird der Wert mit Klammern gesendet, und beim Einfügen tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="e6b7b-107">If `sql:datatype` is not specified, the value is sent with the braces and the insert fails.</span></span>  
  
 <span data-ttu-id="e6b7b-108">Weitere Informationen zu `sql:datatype` finden Sie unter [Datentyp Umwandlungen und die SQL: datatype-Anmerkung &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e6b7b-108">For more information about `sql:datatype`, see [Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="e6b7b-109">Bei XDR:</span><span class="sxs-lookup"><span data-stu-id="e6b7b-109">In XDR:</span></span>  
  
-   <span data-ttu-id="e6b7b-110">Wenn der `dt:type``datetime`, `time`, `dateTime.tz` oder `time.tz` lautet, müssen Sie die Datentypen `dt:type` und `sql:datatype` angeben, da XML-Massenladen vor dem Senden der Daten an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] eine Datenkonvertierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="e6b7b-110">If the `dt:type` is `datetime`, `time`, `dateTime.tz`, or `time.tz`, you must specify both the `dt:type` and `sql:datatype` data types because XML Bulk Load performs data conversion before it sends the data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e6b7b-111">Wenn die XML-Daten vom Typ sind `uuid` , `sql:datatype` muss angegeben werden. **dt: Type = "uuid"** ist auch erforderlich, es sei denn, die Daten sind Zeichen folgen Daten.</span><span class="sxs-lookup"><span data-stu-id="e6b7b-111">If your XML data is of type `uuid`, `sql:datatype` must be specified; **dt:type="uuid"** is also required, unless the data is string data.</span></span> <span data-ttu-id="e6b7b-112">Wenn `dt:uuid` nicht angegeben wird, akzeptiert XML-Massenladen Zeichenfolgen mit Klammern (und entfernt diese ggf.).</span><span class="sxs-lookup"><span data-stu-id="e6b7b-112">If you do not specify `dt:uuid`, XML Bulk Load accepts strings with braces (and removes them if needed).</span></span>  
  
-   <span data-ttu-id="e6b7b-113">Wenn es sich bei den XML-Daten um Daten vom Typ `bin.base64` oder `bin.hex` handelt, müssen Sie den XML-Datentyp mit `dt:type` angeben.</span><span class="sxs-lookup"><span data-stu-id="e6b7b-113">If the XML data is `bin.base64` or `bin.hex`, you must specify the XML data type with `dt:type`.</span></span> <span data-ttu-id="e6b7b-114">XML-Massenladen lädt die Daten dann als Hexadezimaldarstellung der Daten in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b7b-114">XML Bulk Load then loads the data into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a hexadecimal representation of the data.</span></span>  
  
  
