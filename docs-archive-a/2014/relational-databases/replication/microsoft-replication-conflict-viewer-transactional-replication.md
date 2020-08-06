---
title: Replikationskonflikt-Viewer von Microsoft (Transaktionsreplikation) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.cvqueued.f1
ms.assetid: eec59d8e-cadb-4623-a31f-9f42ec09c97f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cc3f2ea3d1d2b29fba9c9d9121e23bf4bcd88bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607682"
---
# <a name="microsoft-replication-conflict-viewer-transactional-replication"></a><span data-ttu-id="ee0e1-102">Replikationskonflikt-Viewer von Microsoft (Transaktionsreplikation)</span><span class="sxs-lookup"><span data-stu-id="ee0e1-102">Microsoft Replication Conflict Viewer (Transactional Replication)</span></span>
  <span data-ttu-id="ee0e1-103">Mit dem Replikationskonflikt-Viewer können Sie Konflikte anzeigen, die bei der Synchronisierung für die Peer-zu-Peer-Transaktionsreplikation und die Transaktionsreplikation mit Abonnements mit verzögertem Update über eine Warteschlange aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-103">The Replication Conflict Viewer enables you to view conflicts that have occurred during synchronization for peer-to-peer transactional replication and transactional replication with queued updating subscriptions.</span></span> <span data-ttu-id="ee0e1-104">Weitere Informationen finden Sie unter [Anzeigen von Datenkonflikten für Transaktionsveröffentlichungen &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ee0e1-104">For more information, see [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee0e1-105">Der Replikationskonflikt-Viewer zeigt Konflikte an, die bei der Mergereplikation und der Transaktionsreplikation auftreten.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-105">The Replication Conflict Viewer displays conflicts that occur in merge replication and in transactional replication.</span></span> <span data-ttu-id="ee0e1-106">Bei der Transaktionsreplikation können Sie den Replikationskonflikt-Viewer verwenden, um Konfliktdaten anzuzeigen, aber Sie können keine andere Lösung für den Konflikt auswählen.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-106">For transactional replication, you can use Replication Conflict Viewer to view conflict data, but you cannot choose a different resolution for the conflict.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ee0e1-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ee0e1-107">Options</span></span>  
 <span data-ttu-id="ee0e1-108">Der Replikationskonflikt-Viewer ist in zwei Abschnitte unterteilt.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-108">The Replication Conflict Viewer is divided into two sections.</span></span> <span data-ttu-id="ee0e1-109">Der obere Abschnitt des Dialogfelds zeigt die Konfliktliste für die ausgewählte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-109">The upper section of the dialog box shows the conflict list for the selected table.</span></span> <span data-ttu-id="ee0e1-110">Wenn Sie auf ein Element in der Konfliktliste klicken, werden die Details des Konflikts im unteren Abschnitt des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-110">When you click an item in the conflict list, the details of the conflict are displayed in the lower section of the dialog box.</span></span>  
  
 <span data-ttu-id="ee0e1-111">Die Konfliktdaten im unteren Abschnitt werden in zwei entsprechenden Spalten angezeigt (**Konfliktgewinner** und **Konfliktverlierer**).</span><span class="sxs-lookup"><span data-stu-id="ee0e1-111">The conflict data in the lower section is displayed in two corresponding columns (**Conflict Winner** and **Conflict Loser**).</span></span> <span data-ttu-id="ee0e1-112">Wenn ein Konflikt zwischen aktualisierten und gelöschten Daten vorhanden ist, können möglicherweise keine Daten für die gelöschte Seite des Konflikts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-112">If the conflict is between updated and deleted data, there may be no data to show for the deleted side of the conflict.</span></span> <span data-ttu-id="ee0e1-113">In diesem Fall zeigt der Replikationskonflikt-Viewer eine Meldung in einer der beiden Spalten an, die die Zeile angibt, die an einem Speicherort gelöscht und an einem anderen aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-113">In this case, the Replication Conflict Viewer displays a message in one of the columns, indicating the row was deleted at one location and updated at another.</span></span> <span data-ttu-id="ee0e1-114">Sie gibt außerdem die vorgeschlagene Lösung an.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-114">It also indicates the suggested resolution.</span></span>  
  
 <span data-ttu-id="ee0e1-115">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-115">**Database**</span></span>  
 <span data-ttu-id="ee0e1-116">Wählen Sie eine Datenbank aus, die Veröffentlichungen mit Konflikten enthält.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-116">Choose a database that includes publications with conflicts.</span></span>  
  
 <span data-ttu-id="ee0e1-117">**Veröffentlichung**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-117">**Publication**</span></span>  
 <span data-ttu-id="ee0e1-118">Wählen Sie eine Veröffentlichung aus, die Tabellen mit Konflikten enthält.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-118">Choose a publication that includes tables with conflicts.</span></span>  
  
 <span data-ttu-id="ee0e1-119">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-119">**Table**</span></span>  
 <span data-ttu-id="ee0e1-120">Wählen Sie eine Tabelle aus, die Konflikte enthält.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-120">Choose a table that includes conflicts.</span></span>  
  
 <span data-ttu-id="ee0e1-121">**Filter definieren**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-121">**Define Filter**</span></span>  
 <span data-ttu-id="ee0e1-122">Klicken Sie auf diese Option, um das Dialogfeld **Filter definieren** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-122">Click to open the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="ee0e1-123">**Filter anwenden oder entfernen**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-123">**Apply or Remove Filter**</span></span>  
 <span data-ttu-id="ee0e1-124">Klicken Sie auf diese Option, um einen Filter anzuwenden oder zu entfernen, der im Dialogfeld **Filter definieren** definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-124">Click to apply or remove a filter that has been defined in the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="ee0e1-125">**Alles markieren**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-125">**Select All**</span></span>  
 <span data-ttu-id="ee0e1-126">Wählt alle Konflikte aus, die im Raster aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-126">Click to select all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="ee0e1-127">**Keine auswählen**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-127">**Select None**</span></span>  
 <span data-ttu-id="ee0e1-128">Macht die Auswahl für alle Konflikte rückgängig, die im Raster aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-128">Click to deselect all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="ee0e1-129">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-129">**Remove**</span></span>  
 <span data-ttu-id="ee0e1-130">Entfernt die ausgewählten Konflikte aus dem Viewer und die zugeordneten Metadaten aus den Replikationssystemtabellen.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-130">Click to remove selected conflicts from the viewer and their associated metadata from the replication system tables.</span></span>  
  
 <span data-ttu-id="ee0e1-131">**Alle Spalten anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-131">**Show all columns**</span></span>  
 <span data-ttu-id="ee0e1-132">Zeigt alle Spalten der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-132">Select to show all columns of the table.</span></span>  
  
 <span data-ttu-id="ee0e1-133">**Die ersten fünf Spalten und Spalten mit Konfliktdaten anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-133">**Show first five columns and other columns with conflicting data**</span></span>  
 <span data-ttu-id="ee0e1-134">Zeigt die ersten fünf Spalten und alle Spalten mit Konflikten an.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-134">Select to display the first five columns and any columns that have conflicts.</span></span> <span data-ttu-id="ee0e1-135">Diese Option ist hilfreich, wenn die Tabelle über eine große Anzahl von Spalten verfügt, Sie aber nur diejenigen anzeigen möchten, die für die Konfliktlösung am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-135">This is helpful when the table has a large number of columns, but you want to see only the columns most relevant to resolving the conflict.</span></span> <span data-ttu-id="ee0e1-136">Die ersten fünf Spalten sind in diese Sicht immer einbezogen, da Felder zum Kennzeichnen einer Zeile, z. B. der Primärschlüssel oder Namensfelder, sich oft in den ersten Spalten einer Tabelle befinden.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-136">The first five columns are always included in this view, as fields that identify a row, such as the primary key or name fields, are often among the first columns of the table.</span></span>  
  
 <span data-ttu-id="ee0e1-137">**Spalteninformationen anzeigen** (**…**)</span><span class="sxs-lookup"><span data-stu-id="ee0e1-137">**Display Column Information** (**...**)</span></span>  
 <span data-ttu-id="ee0e1-138">Zeigt die Spalteninformationen an: **Tabellenname**, **Spaltenname**, **Datentyp**und **Spaltenwert**.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-138">Click to view column information: **Table Name**, **Column Name**, **Data Type**, and **Column Value**.</span></span>  
  
 <span data-ttu-id="ee0e1-139">**Details dieses Konflikts protokollieren**</span><span class="sxs-lookup"><span data-stu-id="ee0e1-139">**Log the details of the conflict**</span></span>  
 <span data-ttu-id="ee0e1-140">Aktivieren Sie dieses Kontrollkästchen, um die Details eines Konflikts in eine Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-140">Check this box to log the details of the conflict to a file.</span></span> <span data-ttu-id="ee0e1-141">Zeigen Sie auf das Menü **Ansicht** , und klicken Sie auf **Optionen**, um einen Speicherort für die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-141">To specify a location for the file, point to the **View** menu and click **Options**.</span></span> <span data-ttu-id="ee0e1-142">Geben Sie einen Wert ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen (**...**), und navigieren Sie zur entsprechenden Datei.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-142">Enter a value, or click the browse (**...**) and navigate to the appropriate file.</span></span> <span data-ttu-id="ee0e1-143">Klicken Sie auf **OK** , um das Dialogfeld **Optionen** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ee0e1-143">Click **OK** to exit the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0e1-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee0e1-144">See Also</span></span>  
 <span data-ttu-id="ee0e1-145">[Konflikterkennung bei der Peer-zu-Peer-Replikation](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ee0e1-145">[Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span></span>  
 [<span data-ttu-id="ee0e1-146">Anzeigen von Datenkonflikten für Transaktionsveröffentlichungen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ee0e1-146">View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;</span></span>](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
  
