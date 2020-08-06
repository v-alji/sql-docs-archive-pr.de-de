---
title: Tabelleneigenschaften (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.tabledesigner
- vdt.designers.properties.Table
ms.assetid: cc392987-1aab-45f5-b5af-a26be53409bf
author: stevestein
ms.author: sstein
ms.openlocfilehash: df4a0332ebc622b069c468e51c461b7cba20aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720701"
---
# <a name="table-properties-visual-database-tools"></a><span data-ttu-id="1871c-102">Tabelleneigenschaften (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1871c-102">Table Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="1871c-103">Diese Eigenschaften werden im Eigenschaftenfenster angezeigt, wenn Sie mit der rechten Maustaste in den Tabellen-Designer klicken und Eigenschaften auswählen.</span><span class="sxs-lookup"><span data-stu-id="1871c-103">These properties appear in the Properties window when you right click in Table Designer and select Properties.</span></span> <span data-ttu-id="1871c-104">Wenn nicht anders beschrieben, können Sie diese Eigenschaften im Eigenschaftenfenster bearbeiten, wenn die Tabelle markiert ist.</span><span class="sxs-lookup"><span data-stu-id="1871c-104">Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1871c-105">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="1871c-105">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="1871c-106">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1871c-106">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="1871c-107">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="1871c-107">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="show-table-properties-in-table-designer"></a><span data-ttu-id="1871c-108">Anzeigen von Tabelleneigenschaften im Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="1871c-108">Show Table Properties in Table Designer</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1871c-109">Die in diesem Thema behandelten Eigenschaften sind nicht alphabetisch, sondern nach Kategorie angeordnet.</span><span class="sxs-lookup"><span data-stu-id="1871c-109">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
 <span data-ttu-id="1871c-110">**Kategorie Identität**</span><span class="sxs-lookup"><span data-stu-id="1871c-110">**Identity Category**</span></span>  
 <span data-ttu-id="1871c-111">Wenn die Kategorie erweitert ist, werden die Eigenschaften für **Name**, **Beschreibung**und **Schema**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1871c-111">Expands to show properties for **Name**, **Description**, and **Schema**.</span></span>  
  
 <span data-ttu-id="1871c-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="1871c-112">**Name**</span></span>  
 <span data-ttu-id="1871c-113">Zeigt den Namen der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="1871c-113">Displays the name of the table.</span></span> <span data-ttu-id="1871c-114">Bearbeiten Sie das Textfeld, um den Namen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1871c-114">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1871c-115">Alle Abfragen, Sichten, benutzerdefinierten Funktionen, gespeicherten Prozeduren und Programme, die auf die Tabelle verweisen, werden durch die Namensänderung ungültig.</span><span class="sxs-lookup"><span data-stu-id="1871c-115">If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="1871c-116">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="1871c-116">**Database Name**</span></span>  
 <span data-ttu-id="1871c-117">Zeigt den Namen der Datenquelle der ausgewählten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="1871c-117">Shows the name of the data source of the selected table.</span></span>  
  
 <span data-ttu-id="1871c-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1871c-118">**Description**</span></span>  
 <span data-ttu-id="1871c-119">Zeigt eine Beschreibung der ausgewählten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="1871c-119">Shows a description of the selected table.</span></span> <span data-ttu-id="1871c-120">Klicken Sie auf die Beschreibung, und klicken Sie anschließend auf die Auslassungspunkte **(...)** rechts neben der Eigenschaft, um die ganze Beschreibung anzuzeigen oder sie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1871c-120">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="1871c-121">**Schema**</span><span class="sxs-lookup"><span data-stu-id="1871c-121">**Schema**</span></span>  
 <span data-ttu-id="1871c-122">Zeigt den Namen des Schemas an, zu dem die Tabelle gehört.</span><span class="sxs-lookup"><span data-stu-id="1871c-122">Shows the name of the schema to which this table belongs.</span></span> <span data-ttu-id="1871c-123">(Gilt nur für Microsoft SQL Server.)</span><span class="sxs-lookup"><span data-stu-id="1871c-123">(Applies only to Microsoft SQL Server.)</span></span>  
  
 <span data-ttu-id="1871c-124">**Servername**</span><span class="sxs-lookup"><span data-stu-id="1871c-124">**Server Name**</span></span>  
 <span data-ttu-id="1871c-125">Zeigt den Namen des Servers für diese Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="1871c-125">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="1871c-126">**Kategorie Tabellen-Designer**</span><span class="sxs-lookup"><span data-stu-id="1871c-126">**Table Designer Category**</span></span>  
 <span data-ttu-id="1871c-127">Wenn die Kategorie erweitert ist, werden Eigenschaften für **Identitätsspalte**, **Ist indizierbar**und **Ist repliziert**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1871c-127">Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.</span></span>  
  
 <span data-ttu-id="1871c-128">**Identitätsspalte**</span><span class="sxs-lookup"><span data-stu-id="1871c-128">**Identity Column**</span></span>  
 <span data-ttu-id="1871c-129">Zeigt die Spalte an, die als Identitätsspalte der Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1871c-129">Shows the column used as the table's identity column.</span></span> <span data-ttu-id="1871c-130">Wenn Sie die Identitätsspalte ändern möchten, wählen Sie einen Eintrag in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="1871c-130">To change the identity column, choose from the drop-down list.</span></span> <span data-ttu-id="1871c-131">In der Liste werden nur Spalten mit einem numerischen Datentyp aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1871c-131">Only columns of a numeric data type will show in the list.</span></span>  
  
 <span data-ttu-id="1871c-132">**Ist indizierbar**</span><span class="sxs-lookup"><span data-stu-id="1871c-132">**Is Indexable**</span></span>  
 <span data-ttu-id="1871c-133">Zeigt an, ob die Tabelle indiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1871c-133">Shows whether the table can be indexed.</span></span> <span data-ttu-id="1871c-134">Wenn die Tabelle nicht indiziert werden kann, liegt dies unter Umständen daran, dass Sie nicht der Besitzer der Tabelle sind, oder dass die Tabelle Spalten mit den Datentypen text, ntext oder image enthält.</span><span class="sxs-lookup"><span data-stu-id="1871c-134">If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.</span></span>  
  
 <span data-ttu-id="1871c-135">**Ist repliziert**</span><span class="sxs-lookup"><span data-stu-id="1871c-135">**Is Replicated**</span></span>  
 <span data-ttu-id="1871c-136">Zeigt an, ob die Tabelle in einem anderen Speicherort repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="1871c-136">Shows whether the table is replicated in another location.</span></span>  
  
 <span data-ttu-id="1871c-137">**Kategorie Reguläre Datenbereichsspezifikation**</span><span class="sxs-lookup"><span data-stu-id="1871c-137">**Regular Data Space Specification Category**</span></span>  
 <span data-ttu-id="1871c-138">Wenn die Kategorie erweitert ist, werden Eigenschaften für **(Datenbereichstyp)** , **Schemaname der Dateigruppe oder Partition**und **Partitionsspaltenliste**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1871c-138">Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.</span></span>  
  
 <span data-ttu-id="1871c-139">**(Datenbereichstyp)**</span><span class="sxs-lookup"><span data-stu-id="1871c-139">**(Data Space Type)**</span></span>  
 <span data-ttu-id="1871c-140">Zeigt an, ob die Tabelle mit einem Dateigruppen- oder einem Partitionsschema gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1871c-140">Shows whether this table is stored using a filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="1871c-141">**Schemaname der Dateigruppe oder Partition**</span><span class="sxs-lookup"><span data-stu-id="1871c-141">**Filegroup or Partition Scheme Name**</span></span>  
 <span data-ttu-id="1871c-142">Zeigt den Namen des Dateigruppen- oder Partitionsschemas an.</span><span class="sxs-lookup"><span data-stu-id="1871c-142">Shows the name of the filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="1871c-143">**Partitionsspaltenliste**</span><span class="sxs-lookup"><span data-stu-id="1871c-143">**Partition Column List**</span></span>  
 <span data-ttu-id="1871c-144">Ermöglicht den Zugriff auf das Dialogfeld **Partitionsspaltenliste** .</span><span class="sxs-lookup"><span data-stu-id="1871c-144">Provides access to the **Partition Column List** dialog box.</span></span>  
  
 <span data-ttu-id="1871c-145">**Zeilen-GUID-Spalte**</span><span class="sxs-lookup"><span data-stu-id="1871c-145">**Row GUID Column**</span></span>  
 <span data-ttu-id="1871c-146">Zeigt die Spalte an, die von Microsoft SQL Server als ROWGUID-Spalte der Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1871c-146">Shows the column used by Microsoft SQL Server as the table's ROWGUID column.</span></span> <span data-ttu-id="1871c-147">Wenn Sie die ROWGUID-Spalte ändern möchten, wählen Sie einen Eintrag in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="1871c-147">To change the ROWGUID column, choose from the drop-down list.</span></span> <span data-ttu-id="1871c-148">(Gilt nur für SQL Server 7.0 oder höher.)</span><span class="sxs-lookup"><span data-stu-id="1871c-148">(Applies only to SQL Server 7.0 or higher.)</span></span>  
  
 <span data-ttu-id="1871c-149">**Text/Image-Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="1871c-149">**Text/Image Filegroup**</span></span>  
 <span data-ttu-id="1871c-150">Stellt eine Dropdownliste bereit, in der die Dateigruppe für Spalten mit dem Datentyp text oder image ausgewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1871c-150">Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types.</span></span> <span data-ttu-id="1871c-151">Wenn die Tabelle mit einem Partitionsschema gespeichert wird, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="1871c-151">If the table is stored using a partition scheme, leave this field blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1871c-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1871c-152">See Also</span></span>  
 [<span data-ttu-id="1871c-153">Entwerfen von Tabellen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1871c-153">Design Tables &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
