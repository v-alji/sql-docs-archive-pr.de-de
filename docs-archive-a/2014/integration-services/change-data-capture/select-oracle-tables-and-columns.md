---
title: Auswählen von Oracle-Tabellen und -Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selTabCol
ms.assetid: bf73f80e-a954-4c5f-874e-17fdd4082715
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d51e597f1210643b1543ed981045ade7b2fc2b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616128"
---
# <a name="select-oracle-tables-and-columns"></a><span data-ttu-id="8df6e-102">Auswählen von Oracle-Tabellen und -Spalten</span><span class="sxs-lookup"><span data-stu-id="8df6e-102">Select Oracle Tables and Columns</span></span>
  <span data-ttu-id="8df6e-103">Verwenden Sie die Seite Select Oracle Tables and Columns, um die Tabellen aus der Oracle-Quelldatenbank auszuwählen, in der die Änderungen aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="8df6e-103">Use the Select Oracle Tables and Columns page to select the tables from the Oracle source database where changes are captured.</span></span> <span data-ttu-id="8df6e-104">Diese Seite verfügt über die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="8df6e-104">This page has the following elements:</span></span>  
  
## <a name="options"></a><span data-ttu-id="8df6e-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8df6e-105">Options</span></span>  
 <span data-ttu-id="8df6e-106">**Liste 'Tabelle'**</span><span class="sxs-lookup"><span data-stu-id="8df6e-106">**Table list**</span></span>  
 <span data-ttu-id="8df6e-107">Die Tabellenliste enthält drei Spalten:</span><span class="sxs-lookup"><span data-stu-id="8df6e-107">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="8df6e-108">**Oracle Table Name**: Der Name der Tabelle, einschließlich des Tabellenschemas.</span><span class="sxs-lookup"><span data-stu-id="8df6e-108">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="8df6e-109">**Capture Instance:** Der Name der Aufzeichnungsinstanz, die für die Benennung der instanzspezifischen Change Data Capture-Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8df6e-109">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="8df6e-110">Die Aufzeichnungsinstanz darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="8df6e-110">The capture instance cannot be NULL.</span></span>  
  
     <span data-ttu-id="8df6e-111">Wenn kein Name angegeben wird, wird der Name aus dem Quellschemanamen und dem Quelltabellennamen im Format `<schema-name>_<table-name>`abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8df6e-111">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>`.</span></span> <span data-ttu-id="8df6e-112">Der Name der Aufzeichnungsinstanz darf nicht länger als 100 Zeichen sein und muss innerhalb der Datenbank eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="8df6e-112">The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span>  
  
     <span data-ttu-id="8df6e-113">Sie können in dieser Spalte in jede Zelle klicken, um die **capture_instance**manuell zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8df6e-113">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="8df6e-114">**Security Role**: Der Name der Datenbank-Gatingrolle, mit deren Hilfe der Zugriff auf die Änderungsdaten gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="8df6e-114">**Security Role**: The name of the database gating role used to control access to change data.</span></span>  
  
     <span data-ttu-id="8df6e-115">Sie können in dieser Spalte in jede Zelle klicken, um die **security_role**manuell zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8df6e-115">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="8df6e-116">**Tabellen hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="8df6e-116">**Add Tables**</span></span>  
 <span data-ttu-id="8df6e-117">Klicken Sie auf **Tabellen hinzufügen** , um das Dialogfeld „Tabellenauswahl“ zu öffnen und den Schritt [Auswählen von Oracle-Tabellen zum Aufzeichnen von Änderungen](select-oracle-tables-for-capturing-changes.md)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8df6e-117">Click **Add Tables** to open the Table Selection dialog box where you can [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="8df6e-118">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="8df6e-118">**Edit**</span></span>  
 <span data-ttu-id="8df6e-119">Wählen Sie in der Liste eine Tabelle aus, und wählen Sie **Bearbeiten** aus, um das Dialogfeld **Eigenschaften** für die Tabelle zu öffnen, in dem Sie den Schritt [Vornehmen von Änderungen an den zum Aufzeichnen von Änderungen ausgewählten Tabellen](make-changes-to-the-tables-selected-for-capturing-changes.md)ausführen können.</span><span class="sxs-lookup"><span data-stu-id="8df6e-119">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="8df6e-120">**Remove**</span><span class="sxs-lookup"><span data-stu-id="8df6e-120">**Remove**</span></span>  
 <span data-ttu-id="8df6e-121">Wählen Sie in der Liste eine Tabelle aus, und klicken Sie auf **Entfernen** , um die Tabelle aus der CDC-Instanz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8df6e-121">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
 <span data-ttu-id="8df6e-122">Klicken Sie nach dem [Auswählen von Oracle-Tabellen zum Aufzeichnen von Änderungen](select-oracle-tables-for-capturing-changes.md) und/oder dem [Vornehmen von Änderungen an den zum Aufzeichnen von Änderungen ausgewählten Tabellen](make-changes-to-the-tables-selected-for-capturing-changes.md) in den entsprechenden Dialogfeldern auf **Weiter** , um den Schritt [Generieren und Ausführen des ergänzenden Protokollierungsskripts](generate-and-run-the-supplemental-logging-script.md)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8df6e-122">After you [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md) and/or [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md) using the correct dialog boxes, click **Next** to [Generate and Run the Supplemental Logging Script](generate-and-run-the-supplemental-logging-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df6e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8df6e-123">See Also</span></span>  
 <span data-ttu-id="8df6e-124">[Erstellen der Instanz für die SQL Server-Änderungsdatenbank](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="8df6e-124">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="8df6e-125">[Bearbeiten von Tabellen](edit-tables.md) </span><span class="sxs-lookup"><span data-stu-id="8df6e-125">[Edit Tables](edit-tables.md) </span></span>  
 <span data-ttu-id="8df6e-126">[Hinzufügen von Tabellen zu einer CDC-Instanz](add-tables-to-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="8df6e-126">[Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="8df6e-127">Bearbeiten der Tabelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8df6e-127">Edit the Table Properties</span></span>](edit-the-table-properties.md)  
  
  
