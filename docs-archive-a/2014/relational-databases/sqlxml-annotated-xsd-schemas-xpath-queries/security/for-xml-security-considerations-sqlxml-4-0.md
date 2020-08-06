---
title: FOR XML-Sicherheitsüberlegungen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- client-side XML formatting
- FOR XML clause, security
- server-side XML formatting
- AUTO mode
- security [SQLXML], FOR XML
ms.assetid: facba279-df93-475b-ad43-0043dc5bae03
author: rothja
ms.author: jroth
ms.openlocfilehash: 9a64fa61848e4b5435b2aa944c53953a8c083ab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620778"
---
# <a name="for-xml-security-considerations-sqlxml-40"></a><span data-ttu-id="aadf0-102">FOR XML-Sicherheitsüberlegungen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="aadf0-102">FOR XML Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="aadf0-103">Der FOR XML AUTO-Modus erstellt eine XML-Hierarchie, in der Elementnamen Tabellennamen und Attributnamen Spaltennamen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="aadf0-103">The FOR XML AUTO mode generates an XML hierarchy in which element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="aadf0-104">Somit werden die Datenbanktabelle und die Spalteninformationen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="aadf0-104">This exposes the database table and column information.</span></span> <span data-ttu-id="aadf0-105">Sie können die Datenbankinformationen ausblenden, wenn Sie den AUTO-Modus (serverseitige Formatierung) verwenden, indem Sie Tabellen- und Spaltenaliasse in der Abfrage angeben.</span><span class="sxs-lookup"><span data-stu-id="aadf0-105">You can hide the database information when you use AUTO mode (server-side formatting) by specifying table and column aliases in the query.</span></span> <span data-ttu-id="aadf0-106">Diese Aliasse werden in dem resultierenden XML-Dokument als Element- und Attributsnamen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aadf0-106">These aliases are returned in the resulting XML document as element and attribute names.</span></span>  
  
 <span data-ttu-id="aadf0-107">Die folgende Abfrage gibt beispielsweise den AUTO-Modus an, daher wird die XML-Formatierung auf dem Server durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="aadf0-107">For example, the following query specifies AUTO mode; therefore, the XML formatting is done on the server:</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="aadf0-108">Im resultierenden XML-Dokument werden die Aliasse für Element- und Attributsnamen verwendet:</span><span class="sxs-lookup"><span data-stu-id="aadf0-108">In the resulting XML document, the aliases are used for element and attribute names:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <C F="Nancy" L="Fuller" />   
  <CE F="Andrew" L="Peacock" />   
  <C F="Janet" L="Leverling" />   
  ...  
</root>  
```  
  
 <span data-ttu-id="aadf0-109">Wenn Sie den NESTED-Modus (clientseitige Formatierung) verwenden, werden Aliasse nur für Attribute im resultierenden XML-Dokument zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aadf0-109">When you use NESTED mode (client-side formatting), aliases are returned only for attributes in the resulting XML document.</span></span> <span data-ttu-id="aadf0-110">Die Namen der Basistabellen werden immer als Elementnamen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aadf0-110">The names of the base tables are always returned as element names.</span></span> <span data-ttu-id="aadf0-111">Die folgende Abfrage gibt beispielsweise den NESTED-Modus an.</span><span class="sxs-lookup"><span data-stu-id="aadf0-111">For example, the following query specifies NESTED mode.</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="aadf0-112">Im resultierenden XML-Dokument werden die Namen der Basistabellen als Elementnamen zurückgegeben; Tabellenaliasse werden nicht verwendet:</span><span class="sxs-lookup"><span data-stu-id="aadf0-112">In the resulting XML document, the names of the base tables are returned as element names and table aliases are not used:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Person.Contact F="Nancy" L="Fuller" />   
  <Person.Contact F="Andrew" L="Peacock" />   
  <Person.Contact F="Janet" L="Leverling" />   
       ...  
</root>  
```  
  
  
