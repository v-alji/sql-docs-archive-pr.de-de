---
title: Dialogfeld „XML-Indizes“ (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.xmlindexes
ms.assetid: eef38310-4498-4ccc-bb77-5bbd1c7cc477
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1fb23a801a9129611c032fa1d659caf624088aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619487"
---
# <a name="xml-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="1a159-102">XML-Indizes (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1a159-102">XML Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="1a159-103">Verwenden Sie das Dialogfeld **XML-Indizes** , um Indizes für Spalten vom Datentyp XML zu erstellen, denn diese können nicht mithilfe des Dialogfelds **Index/Schlüssel** indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1a159-103">Use the **XML Indexes** dialog box to create indexes for columns of the data type XML, which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="1a159-104">Jede XML-Spalte kann mehrere XML-Indizes aufweisen, aber der zuerst erstellte Index (der primäre Index) bildet die Basis für alle weiteren Indizes (die sekundären Indizes).</span><span class="sxs-lookup"><span data-stu-id="1a159-104">Each XML column can have more than one XML Index, but the first one created (primary) will be the basis of the others (secondary).</span></span> <span data-ttu-id="1a159-105">Wenn Sie den primären XML-Index löschen, werden auch die sekundären Indizes gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1a159-105">If you delete the primary XML index, the secondary indexes will also be deleted.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a159-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1a159-106">Options</span></span>  
 <span data-ttu-id="1a159-107">**Ausgewählter XML-Index**</span><span class="sxs-lookup"><span data-stu-id="1a159-107">**Selected XML Index**</span></span>  
 <span data-ttu-id="1a159-108">Listet vorhandene XML-Indizes auf.</span><span class="sxs-lookup"><span data-stu-id="1a159-108">Lists existing XML indexes.</span></span> <span data-ttu-id="1a159-109">Wird ausgewählt, um die zugehörigen Eigenschaften im rechten Datenblatt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a159-109">Select to show its properties in the grid to the right.</span></span> <span data-ttu-id="1a159-110">Falls die Liste leer ist, sind für die Tabelle Indizes definiert worden.</span><span class="sxs-lookup"><span data-stu-id="1a159-110">If the list is empty, none have been defined for the table.</span></span>  
  
 <span data-ttu-id="1a159-111">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="1a159-111">**Add**</span></span>  
 <span data-ttu-id="1a159-112">Erstellen Sie einen neuen XML-Index.</span><span class="sxs-lookup"><span data-stu-id="1a159-112">Create a new XML index.</span></span>  
  
 <span data-ttu-id="1a159-113">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="1a159-113">**Delete**</span></span>  
 <span data-ttu-id="1a159-114">Löschen Sie den in der Liste **Ausgewählter XML-Index** ausgewählten XML-Index.</span><span class="sxs-lookup"><span data-stu-id="1a159-114">Delete XML index selected in the **Selected XML Index** list.</span></span> <span data-ttu-id="1a159-115">Beim Löschen des primären XML-Indexes wird eine Meldung ausgegeben, dass dadurch auch alle sekundären Indizes gelöscht werden, und Sie können entweder den Vorgang fortsetzen oder die Aktion abbrechen.</span><span class="sxs-lookup"><span data-stu-id="1a159-115">If you delete the primary XML index, you will be notified that this will delete all secondary ones as well, and you can either continue or cancel the action.</span></span>  
  
 <span data-ttu-id="1a159-116">**Kategorie Allgemein**</span><span class="sxs-lookup"><span data-stu-id="1a159-116">**General Category**</span></span>  
 <span data-ttu-id="1a159-117">Wenn die Kategorie erweitert ist, werden die Eigenschaftenfelder für **Spalten**, **Ist Primary**und **Typ**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a159-117">When expanded, shows the property fields for **Columns**, **Is Primary**, and **Type**.</span></span>  
  
 <span data-ttu-id="1a159-118">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="1a159-118">**Columns**</span></span>  
 <span data-ttu-id="1a159-119">Zeigt an, dass dieser Index in aufsteigender Reihenfolge sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="1a159-119">Shows that this index is sorted in ascending order.</span></span>  
  
 <span data-ttu-id="1a159-120">**Ist Primary**</span><span class="sxs-lookup"><span data-stu-id="1a159-120">**Is Primary**</span></span>  
 <span data-ttu-id="1a159-121">Gibt an, ob dies der primäre Index ist.</span><span class="sxs-lookup"><span data-stu-id="1a159-121">Indicates whether this is the primary index.</span></span> <span data-ttu-id="1a159-122">Der erste für die Spalte erstellte XML-Index stellt die Basis für die anderen Indizes dar.</span><span class="sxs-lookup"><span data-stu-id="1a159-122">The first XML index created on the column will be the basis of the others.</span></span>  
  
 <span data-ttu-id="1a159-123">**Primärverweisname**</span><span class="sxs-lookup"><span data-stu-id="1a159-123">**Primary reference name**</span></span>  
 <span data-ttu-id="1a159-124">Zeigt für einen sekundären Index den Namen des primären Indexes an.</span><span class="sxs-lookup"><span data-stu-id="1a159-124">Shows the name of the primary index if this is a secondary index.</span></span> <span data-ttu-id="1a159-125">Nur verfügbar, wenn es sich um einen sekundären Index handelt.</span><span class="sxs-lookup"><span data-stu-id="1a159-125">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="1a159-126">**Sekundärer Typ**</span><span class="sxs-lookup"><span data-stu-id="1a159-126">**Secondary type**</span></span>  
 <span data-ttu-id="1a159-127">Zeigt den Typ des sekundären Indexes an.</span><span class="sxs-lookup"><span data-stu-id="1a159-127">Shows the type of secondary index.</span></span> <span data-ttu-id="1a159-128">Nur verfügbar, wenn es sich um einen sekundären Index handelt.</span><span class="sxs-lookup"><span data-stu-id="1a159-128">Only available if this is a secondary index.</span></span>  
  
 <span data-ttu-id="1a159-129">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1a159-129">**Type**</span></span>  
 <span data-ttu-id="1a159-130">Zeigt an, dass dies ein XML-Index ist.</span><span class="sxs-lookup"><span data-stu-id="1a159-130">Shows that this is an XML index.</span></span>  
  
 <span data-ttu-id="1a159-131">**Kategorie Identität**</span><span class="sxs-lookup"><span data-stu-id="1a159-131">**Identity Category**</span></span>  
 <span data-ttu-id="1a159-132">Wenn die Kategorie erweitert ist, werden die Eigenschaftenfelder für **Name** und **Beschreibung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a159-132">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="1a159-133">**Name**</span><span class="sxs-lookup"><span data-stu-id="1a159-133">**Name**</span></span>  
 <span data-ttu-id="1a159-134">Zeigt den Namen des XML-Indexes an.</span><span class="sxs-lookup"><span data-stu-id="1a159-134">Shows the name of the XML index.</span></span> <span data-ttu-id="1a159-135">Wenn ein neuer Index erstellt wird, erhält dieser einen Standardnamen, der auf der Tabelle im aktiven Fenster des Tabellen-Designers basiert.</span><span class="sxs-lookup"><span data-stu-id="1a159-135">When a new one is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="1a159-136">Sie können den Namen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="1a159-136">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="1a159-137">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1a159-137">**Description**</span></span>  
 <span data-ttu-id="1a159-138">Beschreiben Sie den Index.</span><span class="sxs-lookup"><span data-stu-id="1a159-138">Describe the index.</span></span> <span data-ttu-id="1a159-139">Klicken Sie zum Erstellen einer detaillierteren Beschreibung auf **Beschreibung**, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten ( **…** ) rechts neben dem Eigenschaftenfeld.</span><span class="sxs-lookup"><span data-stu-id="1a159-139">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="1a159-140">Dadurch wird ein größerer Bereich verfügbar, in den Sie Text eingeben können.</span><span class="sxs-lookup"><span data-stu-id="1a159-140">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="1a159-141">**Kategorie Tabellen-Designer**</span><span class="sxs-lookup"><span data-stu-id="1a159-141">**Table Designer Category**</span></span>  
 <span data-ttu-id="1a159-142">Wenn die Kategorie erweitert ist, werden Informationen zu den Eigenschaften dieses XML-Indexes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a159-142">When expanded, shows information about the properties of this XML index.</span></span>  
  
 <span data-ttu-id="1a159-143">**Füllspezifikation**</span><span class="sxs-lookup"><span data-stu-id="1a159-143">**Fill Specification**</span></span>  
 <span data-ttu-id="1a159-144">Wenn dieses Element erweitert ist, werden Informationen für **Füllfaktor** und **Index mit Leerstellen auffüllen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a159-144">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="1a159-145">**Füllfaktor**</span><span class="sxs-lookup"><span data-stu-id="1a159-145">**Fill Factor**</span></span>  
 <span data-ttu-id="1a159-146">Geben Sie an, zu welchem Prozentsatz die Indexseite vom System gefüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a159-146">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="1a159-147">Sobald eine Seite gefüllt ist, müssen beim Hinzufügen neuer Daten die Seite vom System geteilt werden, wobei die Leistung beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a159-147">Once a page is full, the system must split the page if new data is added, which impairs performance.</span></span>  
  
-   <span data-ttu-id="1a159-148">Ein Wert von 100 bedeutet, dass die Seiten gefüllt werden. Diese Einstellung erfordert den geringsten Aufwand an Speicherplatz, ist aber auch am wenigsten effektiv.</span><span class="sxs-lookup"><span data-stu-id="1a159-148">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="1a159-149">Diese Einstellung sollte nur verwendet werden, wenn keine Änderungen an den Daten vorgenommen werden, zum Beispiel in einer schreibgeschützten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1a159-149">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="1a159-150">Durch einen niedrigeren Wert bleibt auf den Datenseiten ein größerer Bereich leer. Dadurch müssen die Datenseiten seltener geteilt werden, wenn Indizes größer werden.</span><span class="sxs-lookup"><span data-stu-id="1a159-150">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="1a159-151">Dies erfordert allerdings mehr Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="1a159-151">However, it requires more storage space.</span></span> <span data-ttu-id="1a159-152">Diese Einstellung empfiehlt sich eher, wenn Änderungen an den Daten in der Tabelle vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="1a159-152">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="1a159-153">**Index mit Leerstellen auffüllen**</span><span class="sxs-lookup"><span data-stu-id="1a159-153">**Pad Index**</span></span>  
 <span data-ttu-id="1a159-154">Stellen Sie Seiten in diesem Index mit demselben Prozentsatz leeren Platzes (Auffüllung) zur Verfügung, wie in **Füllfaktor**angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a159-154">Provide pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="1a159-155">**Ist deaktiviert**</span><span class="sxs-lookup"><span data-stu-id="1a159-155">**Is Disabled**</span></span>  
 <span data-ttu-id="1a159-156">Geben Sie an, ob der Index deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a159-156">Specify whether this index is disabled.</span></span> <span data-ttu-id="1a159-157">Deaktivierte Indizes unterstützen weder Suchvorgänge noch werden sie aktualisiert, wenn der Tabelle neue Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1a159-157">Disabled indexes do not support searches, nor do they get updated when new items are added to the table.</span></span> <span data-ttu-id="1a159-158">Sie können die Leistung für Masseneinfügungen und -updates verbessern, indem Sie einen Index deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a159-158">You can improve performance for bulk inserts and updates by disabling an index.</span></span>  
  
 <span data-ttu-id="1a159-159">**Seitensperren sind zulässig**</span><span class="sxs-lookup"><span data-stu-id="1a159-159">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="1a159-160">Geben Sie an, ob Sperren auf Seitenebene für diesen Index zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="1a159-160">Specify whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="1a159-161">Das Zulassen oder Untersagen von Sperren auf Seitenebene wirkt sich auf die Datenbankleistung aus.</span><span class="sxs-lookup"><span data-stu-id="1a159-161">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="1a159-162">**Statistiken neu berechnen**</span><span class="sxs-lookup"><span data-stu-id="1a159-162">**Re-compute Statistics**</span></span>  
 <span data-ttu-id="1a159-163">Berechnen Sie beim Erstellen des Indexes neue Statistiken.</span><span class="sxs-lookup"><span data-stu-id="1a159-163">Compute new statistics when the index is created.</span></span> <span data-ttu-id="1a159-164">Durch das Neuberechnen von Statistiken wird die Erstellung der Indizes verlangsamt, die Abfrageleistungen werden allerdings verbessert.</span><span class="sxs-lookup"><span data-stu-id="1a159-164">Re-computing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="1a159-165">**Zeilensperren sind zulässig**</span><span class="sxs-lookup"><span data-stu-id="1a159-165">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="1a159-166">Geben Sie an, ob das Sperren auf Zeilenebene für diesen Index zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="1a159-166">Specify whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="1a159-167">Das Zulassen oder Untersagen von Sperren auf Zeilenebene wirkt sich auf die Datenbankleistung aus.</span><span class="sxs-lookup"><span data-stu-id="1a159-167">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a159-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a159-168">See Also</span></span>  
 [<span data-ttu-id="1a159-169">Erstellen von XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="1a159-169">Create XML Indexes</span></span>](../../relational-databases/xml/create-xml-indexes.md)  
  
  
