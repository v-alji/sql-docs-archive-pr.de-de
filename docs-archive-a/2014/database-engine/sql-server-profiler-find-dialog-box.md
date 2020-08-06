---
title: Dialog Feld "SQL Server Profiler suchen" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.find.f1
helpviewer_keywords:
- Find dialog box
ms.assetid: dfaeec04-93d3-4214-9fc1-38b80179b36b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cedf50930c06d211ebcee0c45a249667219f392c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721713"
---
# <a name="sql-server-profiler---find-dialog-box"></a><span data-ttu-id="15a25-102">SQL Server Profiler - Suchen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="15a25-102">SQL Server Profiler - Find Dialog Box</span></span>
  <span data-ttu-id="15a25-103">Mithilfe des Dialogfelds **Suchen** können Sie eine Ablaufverfolgung nach bestimmten Zeichen oder Wörtern durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="15a25-103">Use the **Find** dialog box to search a trace for specific characters or words.</span></span> <span data-ttu-id="15a25-104">Um einen Suchvorgang abzubrechen, drücken Sie ESC.</span><span class="sxs-lookup"><span data-stu-id="15a25-104">To cancel a search in progress, press ESC.</span></span>  
  
 <span data-ttu-id="15a25-105">Um das Dialogfeld in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]zu öffnen, klicken Sie im Menü **Bearbeiten** auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="15a25-105">To open this dialog box in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], on the **Edit** menu, click **Find**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="15a25-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="15a25-106">Options</span></span>  
 <span data-ttu-id="15a25-107">**Suchen nach**</span><span class="sxs-lookup"><span data-stu-id="15a25-107">**Find what**</span></span>  
 <span data-ttu-id="15a25-108">Geben Sie den Text ein, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="15a25-108">Enter the text that you want to search for.</span></span> <span data-ttu-id="15a25-109">Die Suche entspricht jeder Zeichenfolge, die die angegebene Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="15a25-109">The search matches any string containing the specified string.</span></span> <span data-ttu-id="15a25-110">Die Suche nach "Completed" entspricht beispielsweise "SQL:BatchCompleted".</span><span class="sxs-lookup"><span data-stu-id="15a25-110">For example, searching for "Completed" matches "SQL:BatchCompleted."</span></span> <span data-ttu-id="15a25-111">Platzhalterzeichen (\*, ? usw.) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15a25-111">Wild card characters (\*, ?, etc.) are not supported.</span></span>  
  
 <span data-ttu-id="15a25-112">**Suchen in Spalte**</span><span class="sxs-lookup"><span data-stu-id="15a25-112">**Search in column**</span></span>  
 <span data-ttu-id="15a25-113">Klicken Sie auf eine zu durchsuchende Datenspalte, oder klicken Sie **\<All columns>** auf, um alle Datenspalten in der Ablauf Verfolgung zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="15a25-113">Click a data column to search, or click **\<All columns>** to search all the data columns in the trace.</span></span>  
  
 <span data-ttu-id="15a25-114">**Groß-/Kleinschreibung beachten**</span><span class="sxs-lookup"><span data-stu-id="15a25-114">**Match case**</span></span>  
 <span data-ttu-id="15a25-115">Sucht nach Text, der die gleiche Groß-/Kleinschreibung besitzt wie der Text im Feld **Suchen nach** .</span><span class="sxs-lookup"><span data-stu-id="15a25-115">Finds text that has the same case as the **Find what** box.</span></span> <span data-ttu-id="15a25-116">Deaktivieren Sie dieses Kontrollkästchen, um in der Ablaufverfolgung nach Beispielen zu suchen, die groß oder klein geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="15a25-116">Clear this check box to find examples in the trace that are in both uppercase and lowercase text characters.</span></span>  
  
 <span data-ttu-id="15a25-117">**Nur ganzes Wort suchen**</span><span class="sxs-lookup"><span data-stu-id="15a25-117">**Match whole word**</span></span>  
 <span data-ttu-id="15a25-118">Schränkt die Suche auf ganze Wörter ein.</span><span class="sxs-lookup"><span data-stu-id="15a25-118">Restricts the search to entire words.</span></span> <span data-ttu-id="15a25-119">Deaktivieren Sie das Kontrollkästchen **Nur ganzes Wort** suchen, um nach Zeichen innerhalb eines Worts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="15a25-119">Clear the **Match whole word** check box to search for characters within a word.</span></span>  
  
 <span data-ttu-id="15a25-120">**Weitersuchen**</span><span class="sxs-lookup"><span data-stu-id="15a25-120">**Find Next**</span></span>  
 <span data-ttu-id="15a25-121">Sucht nach dem nächsten Beispiel der im Feld **Suchen nach** angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="15a25-121">Finds the next example of the characters in the **Find what** box.</span></span>  
  
 <span data-ttu-id="15a25-122">**Vorheriges suchen**</span><span class="sxs-lookup"><span data-stu-id="15a25-122">**Find Previous**</span></span>  
 <span data-ttu-id="15a25-123">Sucht in der Ablaufverfolgung rückwärts nach dem vorherigen Beispiel der im Feld **Suchen nach** angegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="15a25-123">Searches backwards in the trace, to find the previous example of the characters in the **Find what** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a25-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15a25-124">See Also</span></span>  
 <span data-ttu-id="15a25-125">[Suchen eines Werts oder einer Datenspalte während der Ablauf Verfolgung &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="15a25-125">[Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="15a25-126">[Erstellen Sie eine Ablauf Verfolgungs &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="15a25-126">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="15a25-127">[Öffnen Sie eine Ablauf Verfolgungs Tabelle &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="15a25-127">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="15a25-128">[Öffnen Sie eine Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="15a25-128">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="15a25-129">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="15a25-129">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="15a25-130">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="15a25-130">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
