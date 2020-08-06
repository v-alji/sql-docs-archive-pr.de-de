---
title: Spaltenzuordnungen (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.columnmapandtransform.f1
ms.assetid: eadc54a6-f936-4ffc-91d7-fbfd2bdcab93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7994de1292677421447d441c1ac5aeb2b6fbc618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619939"
---
# <a name="column-mappings-sql-server-import-and-export-wizard"></a><span data-ttu-id="c86b9-102">Spaltenzuordnungen (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="c86b9-102">Column Mappings (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="c86b9-103">Verwenden Sie das Dialogfeld **Spalten** Zuordnungen, um Transformationsparameter zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c86b9-103">Use the **Column Mappings** dialog box to edit transformation parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c86b9-104">Sie müssen nicht alle Spalten in einer Tabelle kopieren, wenn Sie die Option zum Kopieren von Tabellen auswählen.</span><span class="sxs-lookup"><span data-stu-id="c86b9-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="c86b9-105">Wählen Sie **\<ignore>** in der **Ziel** Spalte dieses Dialog Felds für Spalten aus, die Sie überspringen möchten.</span><span class="sxs-lookup"><span data-stu-id="c86b9-105">Select **\<ignore>** in the **Destination** column of this dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="c86b9-106">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c86b9-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="c86b9-107">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c86b9-107">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="c86b9-108">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="c86b9-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="c86b9-109">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c86b9-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="c86b9-110">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="c86b9-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="c86b9-111">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c86b9-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c86b9-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c86b9-112">Options</span></span>  
 <span data-ttu-id="c86b9-113">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="c86b9-113">**Source**</span></span>  
 <span data-ttu-id="c86b9-114">Identifiziert die ausgewählte Quelltabelle, -sicht oder -abfrage.</span><span class="sxs-lookup"><span data-stu-id="c86b9-114">Identifies the selected source table, view, or query.</span></span>  
  
 <span data-ttu-id="c86b9-115">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="c86b9-115">**Destination**</span></span>  
 <span data-ttu-id="c86b9-116">Identifiziert die ausgewählte Zieltabelle, -sicht oder -abfrage.</span><span class="sxs-lookup"><span data-stu-id="c86b9-116">Identifies the selected destination table, view, or query.</span></span>  
  
 <span data-ttu-id="c86b9-117">**Zieltabelle erstellen**</span><span class="sxs-lookup"><span data-stu-id="c86b9-117">**Create destination table/file**</span></span>  
 <span data-ttu-id="c86b9-118">Geben Sie an, ob eine Zieltabelle erstellt werden soll, falls noch keine solche Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c86b9-118">Specify whether to create the destination table if it does not already exist.</span></span>  
  
 <span data-ttu-id="c86b9-119">**Zeilen in Zieltabelle löschen**</span><span class="sxs-lookup"><span data-stu-id="c86b9-119">**Delete rows in destination table/file**</span></span>  
 <span data-ttu-id="c86b9-120">Geben Sie an, ob die Daten aus einer vorhandenen Tabelle gelöscht werden sollen, bevor neue Daten geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c86b9-120">Specify whether to clear the data from an existing table before loading new data.</span></span>  
  
 <span data-ttu-id="c86b9-121">**Append rows to destination table/file**</span><span class="sxs-lookup"><span data-stu-id="c86b9-121">**Append rows to destination table/file**</span></span>  
 <span data-ttu-id="c86b9-122">Geben Sie an, ob die neuen Daten an die in der Tabelle bereits enthaltenen Daten angefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c86b9-122">Specify whether to append the new data to the data already present in an existing table.</span></span>  
  
 <span data-ttu-id="c86b9-123">**SQL bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="c86b9-123">**Edit SQL**</span></span>  
 <span data-ttu-id="c86b9-124">Verwenden Sie die default-Anweisung im Dialogfeld **SQL-Anweisung CREATE TABLE** , oder ändern Sie Sie für Ihre Zwecke.</span><span class="sxs-lookup"><span data-stu-id="c86b9-124">Use the default statement in the **Create Table SQL Statement** dialog box, or modify it for your purposes.</span></span> <span data-ttu-id="c86b9-125">Wenn die Anweisung geändert wird, müssen Sie auch für die Tabellenzuordnung die entsprechenden Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c86b9-125">If you modify this statement, you must also make associated changes to table mapping.</span></span>  
  
 <span data-ttu-id="c86b9-126">**Zieltabelle löschen und erneut erstellen**</span><span class="sxs-lookup"><span data-stu-id="c86b9-126">**Drop and re-create destination table**</span></span>  
 <span data-ttu-id="c86b9-127">Wählen Sie diese Option aus, um die Zieltabelle zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c86b9-127">Choose this option to overwrite the destination table.</span></span> <span data-ttu-id="c86b9-128">Diese Option ist nur verfügbar, wenn Sie den Assistenten verwenden, um die Zieltabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c86b9-128">This option is only available when you use the wizard to create the destination table.</span></span> <span data-ttu-id="c86b9-129">Die Zieltabelle wird nur gelöscht und erneut erstellt, wenn Sie das vom Assistenten erstellte Paket speichern und anschließend erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c86b9-129">The destination table is only dropped and re-created if you save the package that the wizard creates, and then run the package again.</span></span>  
  
 <span data-ttu-id="c86b9-130">**IDENTITY_INSERT aktivieren**</span><span class="sxs-lookup"><span data-stu-id="c86b9-130">**Enable identity insert**</span></span>  
 <span data-ttu-id="c86b9-131">Wählen Sie diese Option aus, damit vorhandene IDENTITY-Werte in den Quelldaten in eine IDENTITY-Spalte in der Zieltabelle eingefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="c86b9-131">Choose this option to allow existing identity values in the source data to be inserted into an identity column in the destination table.</span></span> <span data-ttu-id="c86b9-132">Standardmäßig ist dies für die Identity-Zielspalte nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c86b9-132">By default, the destination identity column does not allow this.</span></span>  
  
 <span data-ttu-id="c86b9-133">**Zuordnungen**</span><span class="sxs-lookup"><span data-stu-id="c86b9-133">**Mappings**</span></span>  
 <span data-ttu-id="c86b9-134">Zeigt an wie jede Spalte in der Datenquelle einer Spalte im Ziel zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c86b9-134">Displays how each column in the data source maps to a column in the destination.</span></span>  
  
 <span data-ttu-id="c86b9-135">Diese Liste weist die folgenden Spalten auf:</span><span class="sxs-lookup"><span data-stu-id="c86b9-135">This list has the following columns:</span></span>  
  
 <span data-ttu-id="c86b9-136">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="c86b9-136">**Source**</span></span>  
 <span data-ttu-id="c86b9-137">Zeigen Sie die einzelnen Quellspalten an, für die Transformationsparameter festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="c86b9-137">View each source column for which you can set transformation parameters.</span></span>  
  
 <span data-ttu-id="c86b9-138">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="c86b9-138">**Destination**</span></span>  
 <span data-ttu-id="c86b9-139">Geben Sie an, ob eine Spalte während des Kopiervorgangs ignoriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c86b9-139">Specify whether you want to ignore a column during the copy operation.</span></span> <span data-ttu-id="c86b9-140">Sie können nur eine Teilmenge von Spalten kopieren, indem Sie **\<ignore>** in dieser Spalte für Spalten auswählen, die Sie überspringen möchten.</span><span class="sxs-lookup"><span data-stu-id="c86b9-140">You can copy only a subset of columns by selecting **\<ignore>** in this column for columns that you want to skip.</span></span> <span data-ttu-id="c86b9-141">Bevor Sie Spalten zuordnen, müssen Sie alle Spalten ignorieren, die nicht zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c86b9-141">Before you map columns, you must ignore all columns that will not be mapped.</span></span>  
  
 <span data-ttu-id="c86b9-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="c86b9-142">**Type**</span></span>  
 <span data-ttu-id="c86b9-143">Wählen Sie einen Datentyp für die Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="c86b9-143">Select a data type for the column.</span></span>  
  
 <span data-ttu-id="c86b9-144">**NULL zulassen**</span><span class="sxs-lookup"><span data-stu-id="c86b9-144">**Nullable**</span></span>  
 <span data-ttu-id="c86b9-145">Geben Sie an, ob der NULL-Wert in der Spalte zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="c86b9-145">Specify whether a column will allow a null value.</span></span>  
  
 <span data-ttu-id="c86b9-146">**Größe**</span><span class="sxs-lookup"><span data-stu-id="c86b9-146">**Size**</span></span>  
 <span data-ttu-id="c86b9-147">Geben Sie die Anzahl der Zeichen in der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="c86b9-147">Specify the number of characters in the column.</span></span>  
  
 <span data-ttu-id="c86b9-148">**Genauigkeit**</span><span class="sxs-lookup"><span data-stu-id="c86b9-148">**Precision**</span></span>  
 <span data-ttu-id="c86b9-149">Geben Sie die Genauigkeit der angezeigten Daten in der Anzahl der Ziffern an.</span><span class="sxs-lookup"><span data-stu-id="c86b9-149">Specify the precision of displayed data, referring to the number of digits.</span></span>  
  
 <span data-ttu-id="c86b9-150">**Skalierung**</span><span class="sxs-lookup"><span data-stu-id="c86b9-150">**Scale**</span></span>  
 <span data-ttu-id="c86b9-151">Geben Sie die Anzahl der Dezimalstellen der angezeigten Daten an.</span><span class="sxs-lookup"><span data-stu-id="c86b9-151">Specify the scale of displayed data, referring to the number of decimal places.</span></span>  
  
  
