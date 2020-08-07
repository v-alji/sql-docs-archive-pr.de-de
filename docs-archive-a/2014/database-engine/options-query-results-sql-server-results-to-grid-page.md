---
title: Optionen (Abfrageergebnisse-SQL Server-auf Raster Seite Ergebnisse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToGrid
ms.assetid: f88a0f5c-e800-473b-ae23-c3943de5ed63
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f9cec7e544c295420a9ae2a25e96ea9aa82030b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718646"
---
# <a name="options-query-results-sql-server-results-to-grid-page"></a><span data-ttu-id="45905-102">Optionen (Abfrageergebnisse-SQL Server-auf Raster Seite Ergebnisse)</span><span class="sxs-lookup"><span data-stu-id="45905-102">Options (Query Results-SQL Server-Results to Grid Page)</span></span>
  <span data-ttu-id="45905-103">Mithilfe dieser Seite können Sie die Anzeigeoptionen für Abfrageresultsets angeben, die im Rasterformat ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="45905-103">Use this page to specify the options for displaying a query result set in grid format.</span></span> <span data-ttu-id="45905-104">Die an diesen Optionen vorgenommenen Änderungen werden nur für neue Abfragen in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="45905-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="45905-105">Um die Optionen für die aktuellen Abfragen zu ändern, klicken Sie im Menü **Abfrage** auf **Abfrage Optionen** , oder klicken Sie mit der rechten Maustaste in das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Abfragefenster, und wählen Sie **Abfrage Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="45905-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window and select **Query Options**.</span></span> <span data-ttu-id="45905-106">Klicken Sie im linken Bereich des Dialogfelds **Abfrageoptionen** unter **Ergebnisse**auf **Raster**.</span><span class="sxs-lookup"><span data-stu-id="45905-106">In the left pane of the **Query Options** dialog box, under **Results**, click **Grid**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="45905-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="45905-107">UI element list</span></span>  
 <span data-ttu-id="45905-108">**Abfrage in das Resultset einschließen**</span><span class="sxs-lookup"><span data-stu-id="45905-108">**Include the query in the result set**</span></span>  
 <span data-ttu-id="45905-109">Gibt den Text der Abfrage als Teil der Abfrageausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="45905-109">Returns the text of the query as part of the query output.</span></span>  
  
 <span data-ttu-id="45905-110">**Spaltenheader beim Kopieren oder Speichern der Ergebnisse einschließen**</span><span class="sxs-lookup"><span data-stu-id="45905-110">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="45905-111">Aktivieren Sie dieses Kontrollkästchen, um Spaltenheader beim Kopieren von Ergebnissen in die Zwischenablage oder beim Speichern in einer Datei einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="45905-111">Select this check box to include column headers when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="45905-112">Deaktivieren Sie dieses Kontrollkästchen, wenn Sie nur die Ergebnisdaten und nicht die Spaltenheader speichern oder kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="45905-112">Clear this check box if you want saved or copied result data to have only the data and not the column headings.</span></span>  
  
 <span data-ttu-id="45905-113">**Ergebnisse nach der Ausführung verwerfen**</span><span class="sxs-lookup"><span data-stu-id="45905-113">**Discard results after execution**</span></span>  
 <span data-ttu-id="45905-114">Verhindert, dass Abfrageergebnisse im Überprüfungsbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="45905-114">Prevents query results from being displayed in the reviewing pane.</span></span> <span data-ttu-id="45905-115">Die Ergebnisse werden unmittelbar nach der Ausführung verworfen.</span><span class="sxs-lookup"><span data-stu-id="45905-115">The results are discarded immediately after execution.</span></span> <span data-ttu-id="45905-116">Durch Aktivieren dieser Option können Sie Speicherplatz einsparen.</span><span class="sxs-lookup"><span data-stu-id="45905-116">Specifying this option helps save memory.</span></span>  
  
 <span data-ttu-id="45905-117">**Ergebnisse auf separater Registerkarte anzeigen**</span><span class="sxs-lookup"><span data-stu-id="45905-117">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="45905-118">Aktivieren Sie dieses Kontrollkästchen, wenn das Resultset nicht im unteren Bereich des Dokumentfensters der Abfrage, sondern in einer neuen Registerkarte angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="45905-118">Select this check box to display the result set in a new tab, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="45905-119">**Nach Ausführung der Abfrage zur Ergebnisregisterkarte wechseln**</span><span class="sxs-lookup"><span data-stu-id="45905-119">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="45905-120">Wählen Sie diese Option, um nach der Ausführung einer Abfrage mit der Anzeige automatisch zum Ergebnisbereich zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="45905-120">Click to automatically set the screen focus to the results pane upon execution of a query.</span></span>  
  
 <span data-ttu-id="45905-121">**Maximale Anzahl von abgerufenen Zeichen**</span><span class="sxs-lookup"><span data-stu-id="45905-121">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="45905-122">**Nicht-XML-Daten**:</span><span class="sxs-lookup"><span data-stu-id="45905-122">**Non XML data**:</span></span>  
  
 <span data-ttu-id="45905-123">Geben Sie eine Zahl zwischen 1 und 65.535 ein, um die maximale Anzahl der in einer Zelle angezeigten Zeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="45905-123">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45905-124">Wenn Sie eine große Anzahl von Zeichen angeben, werden die Daten im Resultset unter Umständen abgeschnitten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45905-124">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="45905-125">Die maximale Anzahl der pro Zelle angezeigten Zeichen ist von der Schriftgröße abhängig.</span><span class="sxs-lookup"><span data-stu-id="45905-125">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="45905-126">Wenn große Resultsets zurückgegeben werden, kann ein großer Wert in diesem Feld dazu führen, dass [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] viel Arbeitsspeicher beansprucht und die Systemleistung beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="45905-126">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="45905-127">**XML-Daten**:</span><span class="sxs-lookup"><span data-stu-id="45905-127">**XML data**:</span></span>  
  
 <span data-ttu-id="45905-128">Wählen Sie **1 MB**, **2 MB**oder **5 MB**aus.</span><span class="sxs-lookup"><span data-stu-id="45905-128">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="45905-129">Wählen Sie **Unbegrenzt** aus, um alle Zeichen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45905-129">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="45905-130">**Standard wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="45905-130">**Reset to Default**</span></span>  
 <span data-ttu-id="45905-131">Setzt alle auf dieser Seite verfügbaren Werte auf die ursprünglichen Standardwerte zurück.</span><span class="sxs-lookup"><span data-stu-id="45905-131">Resets all values on this page to the original default values.</span></span>  
  
  
