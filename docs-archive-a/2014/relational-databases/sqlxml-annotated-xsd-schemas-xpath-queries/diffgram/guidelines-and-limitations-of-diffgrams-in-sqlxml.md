---
title: Richtlinien und Einschränkungen von DiffGrams in SQLXML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f2901f02f8b4a8fc7b77dcb6c1cb166cb6af6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618601"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a><span data-ttu-id="346ca-102">Richtlinien und Einschränkungen von DiffGrams für SQLXML</span><span class="sxs-lookup"><span data-stu-id="346ca-102">Guidelines and Limitations of DiffGrams in SQLXML</span></span>
  <span data-ttu-id="346ca-103">Bei der Verwendung von DiffGrams mit SQLXML 4.0 gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="346ca-103">Remember the following when using DiffGrams with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="346ca-104">BLOB-Typen (Binary Large Object), wie zum Beispiel `text/ntext`, und Images sollten nicht im `<diffgr:before>`-Block verwendet werden, wenn Sie mit DiffGrams arbeiten, da sie auf diese Weise für die Verwendung in der Parallelitätssteuerung eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="346ca-104">Binary large object (BLOB) types like `text/ntext` and images should not be used in the `<diffgr:before>` block in when working with DiffGrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="346ca-105">Dies kann wegen der Einschränkungen auf Vergleich für BLOB-Typen Probleme mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verursachen.</span><span class="sxs-lookup"><span data-stu-id="346ca-105">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="346ca-106">Das gilt zum Beispiel für das LIKE-Schlüsselwort in der WHERE-Klausel zwischen Spalten des `text`-Datentyps. Vergleiche schlagen allerdings für BLOB-Typen fehl, deren Datengröße 8 K übersteigt.</span><span class="sxs-lookup"><span data-stu-id="346ca-106">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="346ca-107">Sonderzeichen in `ntext`-Daten können aufgrund der Einschränkungen beim Vergleich von BLOB-Typen Probleme mit SQLXML 4.0 verursachen.</span><span class="sxs-lookup"><span data-stu-id="346ca-107">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="346ca-108">Die Verwendung von "[Serializable]" im `<diffgr:before>`-Block eines DiffGrams, das in der Parallelitätsprüfung einer Spalte vom Typ `ntext` verwendet wird, schlägt beispielsweise mit der folgenden SQLOLEDB-Fehlerbeschreibung fehl:</span><span class="sxs-lookup"><span data-stu-id="346ca-108">For example, the use of "[Serializable]" in the `<diffgr:before>` block of a DiffGram when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  
