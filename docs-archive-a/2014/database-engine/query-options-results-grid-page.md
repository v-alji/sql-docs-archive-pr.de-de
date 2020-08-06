---
title: Ergebnisse der Abfrage Optionen (Raster Seite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.grid.f1
ms.assetid: 764bf435-3aab-4c62-b4e0-64fe020a5a95
author: rothja
ms.author: jroth
ms.openlocfilehash: bf300dd5071128b0259230ae788a27595bd8d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621163"
---
# <a name="query-options-results-grid-page"></a><span data-ttu-id="656e9-102">Abfrageergebnis (Seite Ergebnisse in Raster)</span><span class="sxs-lookup"><span data-stu-id="656e9-102">Query Options Results (Grid Page)</span></span>
  <span data-ttu-id="656e9-103">Mithilfe dieser Seite können Sie die Anzeigeoptionen für Abfrageresultsets angeben, die im Rasterformat ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="656e9-103">Use this page to specify the options for displaying a query result set in grid format.</span></span>  
  
## <a name="options"></a><span data-ttu-id="656e9-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="656e9-104">Options</span></span>  
 <span data-ttu-id="656e9-105">**Abfrage in das Resultset einschließen**</span><span class="sxs-lookup"><span data-stu-id="656e9-105">**Include the query in the result set**</span></span>  
 <span data-ttu-id="656e9-106">Gibt den Text der Abfrage als Teil des Resultsets zurück.</span><span class="sxs-lookup"><span data-stu-id="656e9-106">Returns the text of the query as part of the result set.</span></span>  
  
 <span data-ttu-id="656e9-107">**Spaltenheader beim Kopieren oder Speichern der Ergebnisse einschließen**</span><span class="sxs-lookup"><span data-stu-id="656e9-107">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="656e9-108">Schließt Spaltenheader (Titel) ein, wenn Ergebnisse in die Zwischenablage kopiert oder in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="656e9-108">Include column headers (titles) when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="656e9-109">Deaktivieren Sie dieses Kontrollkästchen, wenn Sie nur die Ergebnisdaten und nicht die Spaltenheader speichern oder kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="656e9-109">Clear this check box if you do not want saved or copied result data to have only the data, and not the column headings.</span></span>  
  
 <span data-ttu-id="656e9-110">**Ergebnisse nach der Ausführung verwerfen**</span><span class="sxs-lookup"><span data-stu-id="656e9-110">**Discard results after execution**</span></span>  
 <span data-ttu-id="656e9-111">Gibt Arbeitsspeicher frei, indem die Abfrageergebnisse nach der Anzeige auf dem Bildschirm verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="656e9-111">Free memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="656e9-112">**Ergebnisse auf separater Registerkarte anzeigen**</span><span class="sxs-lookup"><span data-stu-id="656e9-112">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="656e9-113">Zeigt das Resultset statt unten im Dokumentfenster der Abfrage in einem neuen Dokumentfenster an.</span><span class="sxs-lookup"><span data-stu-id="656e9-113">Display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="656e9-114">**Nach Ausführung der Abfrage zur Ergebnisregisterkarte wechseln**</span><span class="sxs-lookup"><span data-stu-id="656e9-114">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="656e9-115">Verschiebt den Fokus automatisch auf das Resultset.</span><span class="sxs-lookup"><span data-stu-id="656e9-115">Automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="656e9-116">**Maximale Anzahl von abgerufenen Zeichen**</span><span class="sxs-lookup"><span data-stu-id="656e9-116">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="656e9-117">**Nicht-XML-Daten**:</span><span class="sxs-lookup"><span data-stu-id="656e9-117">**Non XML data**:</span></span>  
  
 <span data-ttu-id="656e9-118">Geben Sie eine Zahl zwischen 1 und 65.535 ein, um die maximale Anzahl der in einer Zelle angezeigten Zeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="656e9-118">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="656e9-119">Wenn Sie eine große Anzahl von Zeichen angeben, werden die Daten im Resultset unter Umständen abgeschnitten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="656e9-119">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="656e9-120">Die maximale Anzahl der pro Zelle angezeigten Zeichen ist von der Schriftgröße abhängig.</span><span class="sxs-lookup"><span data-stu-id="656e9-120">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="656e9-121">Wenn große Resultsets zurückgegeben werden, kann ein großer Wert in diesem Feld dazu führen, dass [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] viel Arbeitsspeicher beansprucht und die Systemleistung beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="656e9-121">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="656e9-122">**XML-Daten**:</span><span class="sxs-lookup"><span data-stu-id="656e9-122">**XML data**:</span></span>  
  
 <span data-ttu-id="656e9-123">Wählen Sie **1 MB**, **2 MB**oder **5 MB**aus.</span><span class="sxs-lookup"><span data-stu-id="656e9-123">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="656e9-124">Wählen Sie **Unbegrenzt** aus, um alle Zeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="656e9-124">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="656e9-125">**Standard wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="656e9-125">**Reset to Default**</span></span>  
 <span data-ttu-id="656e9-126">Setzt alle auf dieser Seite verfügbaren Werte auf die ursprünglichen Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="656e9-126">Resets all values on this page to the original default values.</span></span>  
  
  
