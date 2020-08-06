---
title: Namespaceunterstützung im PATH-Modus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, namespace support
- namespaces [XML in SQL Server]
ms.assetid: 5f128ea2-0ceb-4b23-bce7-c8b3fd615466
author: rothja
ms.author: jroth
ms.openlocfilehash: abd6cd1f5590bffcd841b07897c9685faed4726f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696513"
---
# <a name="namespace-support-in-path-mode"></a><span data-ttu-id="c8598-102">Namespaceunterstützung im PATH-Modus</span><span class="sxs-lookup"><span data-stu-id="c8598-102">Namespace Support in PATH Mode</span></span>
  <span data-ttu-id="c8598-103">Die Unterstützung von Namespaces im PATH-Modus wird durch den Einsatz von WITH NAMESPACES bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c8598-103">Namespace support in the PATH mode is provided by using WITH NAMESPACES.</span></span> <span data-ttu-id="c8598-104">Beispielsweise zeigt die folgende Abfrage die Syntax von WITH NAMESPACES, um einen Namespace ("a:") zu deklarieren, der in der nachfolgenden SELECT-Anweisung verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="c8598-104">For example, the following query demonstrates the WITH NAMESPACES syntax to declare a namespace ("a:") that can then be used in the subsequent SELECT statement:</span></span>  
  
```  
WITH XMLNAMESPACES('a' as a)  
SELECT 1 as 'a:b'  
FOR XML PATH  
```  
  
## <a name="examples"></a><span data-ttu-id="c8598-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c8598-105">Examples</span></span>  
 <span data-ttu-id="c8598-106">Diese Beispiele veranschaulichen die Verwendung des PATH-Modus beim Generieren von XML-Code aus einer SELECT-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="c8598-106">These samples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="c8598-107">Viele dieser Abfragen beziehen sich auf die XML-Dokumente mit den Fahrradfertigungsanweisungen, die in der Instructions-Spalte der ProductModel-Tabelle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c8598-107">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8598-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8598-108">See Also</span></span>  
 [<span data-ttu-id="c8598-109">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="c8598-109">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
