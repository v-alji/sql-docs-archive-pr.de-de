---
title: Ausführen von Massen Kopier Vorgängen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724606"
---
# <a name="performing-bulk-copy-operations-odbc"></a><span data-ttu-id="ba07d-102">Durchführen von Massenkopiervorgängen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ba07d-102">Performing Bulk Copy Operations (ODBC)</span></span>
  <span data-ttu-id="ba07d-103">Der ODBC-Standard unterstützt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Massenkopiervorgänge nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="ba07d-103">The ODBC standard does not directly support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="ba07d-104">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Version 7.0 oder höher verbunden ist, unterstützt er die DB-Library-Funktionen, die die Massenkopiervorgänge in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchführen.</span><span class="sxs-lookup"><span data-stu-id="ba07d-104">When connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the DB-Library functions that perform [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="ba07d-105">Diese treiberspezifische Erweiterung stellt eine einfache Möglichkeit dar, bestehende DB-Library-Anwendungen zu aktualisieren, die Funktionen zum Massenkopieren verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba07d-105">This driver-specific extension provides an easy upgrade path for existing DB-Library applications that use bulk copy functions.</span></span> <span data-ttu-id="ba07d-106">Die spezialisierte Unterstützung für Massenkopiervorgänge befindet sich in den folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="ba07d-106">The specialized bulk copy support is in the following files:</span></span>  
  
-   <span data-ttu-id="ba07d-107">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="ba07d-107">sqlncli.h</span></span>  
  
     <span data-ttu-id="ba07d-108">Enthält Funktionsprototypen und Konstantendefinitionen für Funktionen zum Massenkopieren.</span><span class="sxs-lookup"><span data-stu-id="ba07d-108">Includes function prototypes and constant definitions for bulk copy functions.</span></span> <span data-ttu-id="ba07d-109">sqlncli.h muss in der ODBC-Anwendung, die Massenkopiervorgänge ausführt, enthalten sein und im Includepfad der Anwendung angegeben werden, wenn die Anwendung kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ba07d-109">sqlncli.h must be included in the ODBC application performing bulk copy operations and must be in the application's include path when it is compiled.</span></span>  
  
-   <span data-ttu-id="ba07d-110">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="ba07d-110">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="ba07d-111">Muss im Bibliothekspfad des Linkers enthalten sein und als zu verknüpfende Datei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ba07d-111">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="ba07d-112">sqlncli11.lib wird zusammen mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ba07d-112">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="ba07d-113">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="ba07d-113">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="ba07d-114">Muss zur Ausführungszeit verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="ba07d-114">Must be present at execution time.</span></span> <span data-ttu-id="ba07d-115">sqlncli11.dll wird mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC-Treiber von Native Client verteilt.</span><span class="sxs-lookup"><span data-stu-id="ba07d-115">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba07d-116">Die ODBC-Funktion **SQLBulkOperations** hat keine Beziehung zu den Funktionen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Massen Kopiervorgang.</span><span class="sxs-lookup"><span data-stu-id="ba07d-116">The ODBC **SQLBulkOperations** function has no relationship to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy functions.</span></span> <span data-ttu-id="ba07d-117">Anwendungen müssen die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifischen Massenkopierfunktionen verwenden, um Massenkopiervorgänge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ba07d-117">Applications must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy functions to perform bulk copy operations.</span></span>  
  
## <a name="minimally-logging-bulk-copies"></a><span data-ttu-id="ba07d-118">Minimales Protokollieren von Massenkopiervorgängen</span><span class="sxs-lookup"><span data-stu-id="ba07d-118">Minimally Logging Bulk Copies</span></span>  
 <span data-ttu-id="ba07d-119">Beim vollständigen Wiederherstellungsmodell werden alle beim Massenladen ausgeführten Vorgänge für das Einfügen von Zeilen vollständig im Transaktionsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="ba07d-119">With the Full Recovery model, all row-insert operations performed by bulk load are fully logged in the transaction log.</span></span> <span data-ttu-id="ba07d-120">Bei umfangreichen Datenladevorgängen kann dies dazu führen, dass das Transaktionsprotokoll schnell aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="ba07d-120">For large data loads, this can cause the transaction log to fill rapidly.</span></span> <span data-ttu-id="ba07d-121">Unter bestimmten Umständen ist die minimale Protokollierung möglich.</span><span class="sxs-lookup"><span data-stu-id="ba07d-121">Under certain conditions, minimally logging is possible.</span></span> <span data-ttu-id="ba07d-122">Bei der minimalen Protokollierung wird das Risiko verkleinert, dass ein Massenladevorgang das Protokoll auffüllt. Außerdem ist sie effizienter als die vollständige Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="ba07d-122">Minimal logging reduces the possibility of a bulk load operation filling the log space and is also more efficient than full logging.</span></span>  
  
 <span data-ttu-id="ba07d-123">Informationen zur Verwendung der minimalen Protokollierung finden Sie unter [Voraussetzungen für die minimale Protokollierung beim Massen Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span><span class="sxs-lookup"><span data-stu-id="ba07d-123">For information on using minimal logging, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba07d-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ba07d-124">Remarks</span></span>  
 <span data-ttu-id="ba07d-125">Bei der Verwendung von bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höher erhalten Sie unter Umständen Fehler in Situationen, die in Versionen vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] keine Fehler hervorriefen.</span><span class="sxs-lookup"><span data-stu-id="ba07d-125">When using bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, you might see errors in situations where there were no errors prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="ba07d-126">Das liegt daran, dass bcp.exe in höheren Versionen keine implizite Datentypkonvertierung mehr vornimmt.</span><span class="sxs-lookup"><span data-stu-id="ba07d-126">This is because in the later versions, bcp.exe no longer performs implicit data type conversion.</span></span> <span data-ttu-id="ba07d-127">Vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] wurden numerische Daten von bcp.exe in den money-Datentyp konvertiert, wenn die Zieltabelle einen money-Datentyp aufwies.</span><span class="sxs-lookup"><span data-stu-id="ba07d-127">Prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe converted numeric data to a money data type, if the target table had a money data type.</span></span> <span data-ttu-id="ba07d-128">Allerdings wurden in dieser Situation zusätzliche Felder von bcp.exe einfach abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="ba07d-128">However, in that situation, bcp.exe simply truncated extra fields.</span></span> <span data-ttu-id="ba07d-129">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] gibt bcp.exe einen Fehler aus, wenn die Datentypen von Datei und Zieltabelle nicht übereinstimmen, und dadurch Daten abgeschnitten werden müssten, um in die Zieltabelle zu passen.</span><span class="sxs-lookup"><span data-stu-id="ba07d-129">Beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if data types do not match between the file and the target table, bcp.exe will raise an error if there is any data that would have to be truncated to fit into the target table.</span></span> <span data-ttu-id="ba07d-130">Um diesen Fehler zu beheben, korrigieren Sie die Daten so, dass sie zum Zieldatentyp passen.</span><span class="sxs-lookup"><span data-stu-id="ba07d-130">To resolve this error, fix the data to match the target data type.</span></span> <span data-ttu-id="ba07d-131">Optional können Sie die Datei bcp.exe aus einer Version vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba07d-131">Optionally, use bcp.exe from a release prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba07d-132">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba07d-132">In This Section</span></span>  
  
-   [<span data-ttu-id="ba07d-133">Verwenden von Datendateien und Formatdateien</span><span class="sxs-lookup"><span data-stu-id="ba07d-133">Using Data Files and Format Files</span></span>](using-data-files-and-format-files.md)  
  
-   [<span data-ttu-id="ba07d-134">Massenkopieren aus Programmvariablen</span><span class="sxs-lookup"><span data-stu-id="ba07d-134">Bulk Copying from Program Variables</span></span>](bulk-copying-from-program-variables.md)  
  
-   [<span data-ttu-id="ba07d-135">Verwalten von Batchgrößen für das Massenkopieren</span><span class="sxs-lookup"><span data-stu-id="ba07d-135">Managing Bulk Copy Batch Sizes</span></span>](managing-bulk-copy-batch-sizes.md)  
  
-   [<span data-ttu-id="ba07d-136">Massenkopieren von Text- und Bilddaten</span><span class="sxs-lookup"><span data-stu-id="ba07d-136">Bulk Copying Text and Image Data</span></span>](bulk-copying-text-and-image-data.md)  
  
-   [<span data-ttu-id="ba07d-137">Konvertieren von DB-Library-Programmen zum Massenkopieren in ODBC-Programme</span><span class="sxs-lookup"><span data-stu-id="ba07d-137">Converting from DB-Library to ODBC Bulk Copy</span></span>](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba07d-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba07d-138">See Also</span></span>  
 <span data-ttu-id="ba07d-139">[SQL Server Native Client &#40;ODBC-&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="ba07d-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="ba07d-140">Massenimport und -export von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba07d-140">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
