---
title: FOR XML Auto-Abfragen geben Verweise auf abgeleitete Tabellen im Kompatibilitätsmodus 90 oder höher zurück. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FOR XML AUTO [SQL Server]
ms.assetid: 10c32f06-f7e1-40e0-8f79-6d921f2bef1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 702cb2ca1d437dff03cee09c98d72082500709d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630505"
---
# <a name="for-xml-auto-queries-return-derived-table-references-in-90-or-later-compatibility-modes"></a><span data-ttu-id="d5ec1-102">FOR XML AUTO-Abfragen geben abgeleitete Tabellenverweise im Kompatibilitätsmodus 90 oder höher zurück</span><span class="sxs-lookup"><span data-stu-id="d5ec1-102">FOR XML AUTO queries return derived table references in 90 or later compatibility modes</span></span>
  <span data-ttu-id="d5ec1-103">Wenn der Datenbank-Kompatibilitätsgrad auf 90 oder höher festgelegt ist, geben FOR XML-Abfragen, die im AUTO-Modus ausgeführt werden, Verweise auf Aliase abgeleiteter Tabellen wieder.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-103">When the database compatibility level is set to 90 or later, FOR XML queries that execute in AUTO mode return references to derived table aliases.</span></span> <span data-ttu-id="d5ec1-104">Wenn der Datenbank-Kompatibilitätsgrad auf 80 festgelegt ist, geben FOR XML AUTO-Abfragen Verweise auf die Basistabellen wieder, die eine abgeleitete Tabelle definieren.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-104">When the compatibility level is set to 80, FOR XML AUTO queries return references to the base tables that define a derived table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d5ec1-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="d5ec1-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d5ec1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5ec1-106">Description</span></span>  
 <span data-ttu-id="d5ec1-107">Sehen Sie sich z. B. die folgende Tabelle an:</span><span class="sxs-lookup"><span data-stu-id="d5ec1-107">For example, consider the following table:</span></span>  
  
```  
CREATE TABLE Test(id int);  
INSERT INTO Test VALUES(1);  
INSERT INTO Test VALUES(2);  
```  
  
 <span data-ttu-id="d5ec1-108">Die folgende Abfrage, die eine abgeleitete Tabelle umfasst, führt bei den Kompatibilitätsgraden 80, 90 oder höher zu unterschiedlichen Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="d5ec1-108">The following query, which includes a derived table, produces different results under compatibility levels 80, 90, or later:</span></span>  
  
```  
SELECT * FROM   
   (SELECT a.id AS a, b.id AS b   
    FROM Test a JOIN Test b ON a.id=b.id)  
AS DerivedTest   
FOR XML AUTO;  
```  
  
 <span data-ttu-id="d5ec1-109">Beim Kompatibilitätsgrad 80 gibt die Abfrage die folgenden Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-109">Under compatibility level 80, the query returns the following results.</span></span> <span data-ttu-id="d5ec1-110">Die Ergebnisse verweisen auf die Basistabellenaliase `a` und `b` der abgeleiteten Tabelle anstatt auf den Alias der abgeleiteten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-110">The results reference the base table aliases `a` and `b` of the derived table instead of the derived table alias.</span></span>  
  
```  
<a a="1"><b b="1"/></a><a a="2"><b b="2"/></a>  
```  
  
 <span data-ttu-id="d5ec1-111">Beim Kompatibilitätsgrad 90 oder höher gibt die Abfrage Verweise auf den Alias `DerivedTest` der abgeleiteten Tabelle anstatt auf die Basistabellen der abgeleiteten Tabelle wieder.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-111">Under compatibility level 90 or later, the query returns references to the derived table alias `DerivedTest` instead of to the derived table's base tables.</span></span>  
  
```  
<DerivedTest a="1" b="1"/><DerivedTest a="2" b="2"/>  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="d5ec1-112">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="d5ec1-112">Corrective Action</span></span>  
 <span data-ttu-id="d5ec1-113">Ändern Sie die Anwendung nach Bedarf, um den Änderungen bei den Ergebnissen von FOR XML AUTO-Abfragen, die abgeleitete Tabellen umfassen und mit dem Kompatibilitätsgrad 90 oder höher ausgeführt werden, Rechnung zu tragen.</span><span class="sxs-lookup"><span data-stu-id="d5ec1-113">Modify your application as required to account for the changes in results of FOR XML AUTO queries that include derived tables and that run under compatibility level 90 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ec1-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5ec1-114">See Also</span></span>  
 <span data-ttu-id="d5ec1-115">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d5ec1-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="d5ec1-116">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="d5ec1-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
