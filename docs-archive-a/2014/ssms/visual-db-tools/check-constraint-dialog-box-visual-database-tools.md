---
title: CHECK-Einschränkung (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraint
ms.assetid: ad0bbf7f-b0de-406a-bd0a-cb779816b101
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7244984b869a1c68e597984a1cd03e16e53d0306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607494"
---
# <a name="check-constraint-dialog-box-visual-database-tools"></a><span data-ttu-id="129a9-102">CHECK-Einschränkung (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="129a9-102">Check Constraint Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="129a9-103">Dieses Dialogfeld wird angezeigt, wenn Sie im Tabellen-Designer mit der rechten Maustaste auf ein Tabellendefinitions-Datenblatt klicken und auf **Einschränkungen überprüfen**klicken.</span><span class="sxs-lookup"><span data-stu-id="129a9-103">This dialog box appears when you right-click a table definition grid in Table Designer and click **Check Constraints**.</span></span> <span data-ttu-id="129a9-104">Dieses Dialogfeld enthält eine Reihe von Eigenschaften für Einschränkungen (außer für Unique-Einschränkungen), die den Tabellen in der Datenbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="129a9-104">The dialog box contains a set of properties for non-unique constraints attached to the tables in your database.</span></span> <span data-ttu-id="129a9-105">Eigenschaften für Unique-Einschränkungen werden im Dialogfeld **Indizes/Schlüssel** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="129a9-105">Properties applying to unique constraints appear in the **Indexes/Keys** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="129a9-106">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="129a9-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="129a9-107">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="129a9-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="129a9-108">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="129a9-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="129a9-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="129a9-109">Options</span></span>  
 <span data-ttu-id="129a9-110">**Ausgewählte CHECK-Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="129a9-110">**Selected Check Constraints**</span></span>  
 <span data-ttu-id="129a9-111">Listet verfügbare CHECK-Einschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="129a9-111">Lists available check constraints.</span></span> <span data-ttu-id="129a9-112">Um die Eigenschaften einer Einschränkung anzuzeigen, wählen Sie sie in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="129a9-112">To view the properties of a constraint, select it in the list.</span></span>  
  
 <span data-ttu-id="129a9-113">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="129a9-113">**Add**</span></span>  
 <span data-ttu-id="129a9-114">Erstellt eine neue Einschränkung für die ausgewählte Datenbanktabelle und stellt den Standardnamen sowie weitere Werte für die Einschränkung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="129a9-114">Create a new constraint for the selected database table and provide a default name and other values for the constraint.</span></span> <span data-ttu-id="129a9-115">Die Einschränkung wird erst dann gültig, wenn ein Ausdruck für die Einschränkung eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="129a9-115">The constraint will not become valid until an expression is entered for the constraint.</span></span>  
  
 <span data-ttu-id="129a9-116">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="129a9-116">**Delete**</span></span>  
 <span data-ttu-id="129a9-117">Entfernt die ausgewählte Einschränkung aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="129a9-117">Remove the selected constraint from the table.</span></span> <span data-ttu-id="129a9-118">Verwenden Sie diese Schaltfläche zum Entfernen der Einschränkung, um das Hinzufügen einer CHECK-Einschränkung abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="129a9-118">To cancel the addition of a check constraint, use this button to remove the constraint.</span></span>  
  
 <span data-ttu-id="129a9-119">**Kategorie Allgemein**</span><span class="sxs-lookup"><span data-stu-id="129a9-119">**General Category**</span></span>  
 <span data-ttu-id="129a9-120">Wenn die Kategorie erweitert ist, wird das Eigenschaftenfeld **Ausdruck** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="129a9-120">Expand to show the **Expression** property field.</span></span>  
  
 <span data-ttu-id="129a9-121">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="129a9-121">**Expression**</span></span>  
 <span data-ttu-id="129a9-122">Zeigt den Ausdruck für die ausgewählte CHECK-Einschränkung an.</span><span class="sxs-lookup"><span data-stu-id="129a9-122">Displays the expression for the selected check constraint.</span></span> <span data-ttu-id="129a9-123">Bei neuen Einschränkungen müssen Sie den Ausdruck vor dem Verlassen dieses Felds eingeben.</span><span class="sxs-lookup"><span data-stu-id="129a9-123">For new constraints, you must enter the expression before exiting this box.</span></span> <span data-ttu-id="129a9-124">Sie können auch vorhandene CHECK-Einschränkungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="129a9-124">You can also edit existing check constraints.</span></span> <span data-ttu-id="129a9-125">Weitere Informationen finden Sie unter [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="129a9-125">For more information, see [Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="129a9-126">**Kategorie Identität**</span><span class="sxs-lookup"><span data-stu-id="129a9-126">**Identity Category**</span></span>  
 <span data-ttu-id="129a9-127">Wenn die Kategorie erweitert ist, wird die Eigenschaften für **Name** und **Beschreibung**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="129a9-127">Expand to show properties for **Name** and **Description**.</span></span>  
  
 <span data-ttu-id="129a9-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="129a9-128">**Name**</span></span>  
 <span data-ttu-id="129a9-129">Zeigt den Namen der ausgewählten CHECK-Einschränkung an.</span><span class="sxs-lookup"><span data-stu-id="129a9-129">Shows the name of the selected check constraint.</span></span> <span data-ttu-id="129a9-130">Um den Namen dieser Einschränkung zu ändern, geben Sie den Text direkt in das Eigenschaftenfeld ein.</span><span class="sxs-lookup"><span data-stu-id="129a9-130">To change the name of this constraint, type the text directly in the property field.</span></span>  
  
 <span data-ttu-id="129a9-131">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="129a9-131">**Description**</span></span>  
 <span data-ttu-id="129a9-132">Beschreibt die CHECK-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="129a9-132">Describing this check constraint.</span></span> <span data-ttu-id="129a9-133">Sie können die Beschreibung bearbeiten, indem Sie Änderungen in das Eigenschaftenfeld eingeben. Alternativ können Sie rechts neben dem Eigenschaftenfeld auf die Auslassungspunkte ( **...** ) klicken und die Beschreibung im Dialogfeld **Description-Eigenschaft** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="129a9-133">You can edit the description by typing into the property field or you can click the ellipsis button (**...**) that appears to the right of the property field and edit the description in the **Description Property** dialog box.</span></span>  
  
 <span data-ttu-id="129a9-134">**Kategorie Tabellen-Designer**</span><span class="sxs-lookup"><span data-stu-id="129a9-134">**Table Designer Category**</span></span>  
 <span data-ttu-id="129a9-135">Wenn die Kategorie erweitert ist, werden Eigenschaften für **Vorhandene Daten bei Erstellung oder Reaktivierung überprüfen**, **Für INSERTs und UPDATEs erzwingen**und **Für Replikation erzwingen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="129a9-135">Expand to show properties for **Check Existing Data on Creation or Re-enabling**, **Enforce For Inserts And Updates**, and **Enforce Replication**.</span></span>  
  
 <span data-ttu-id="129a9-136">**Check Existing Data On Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="129a9-136">**Check Existing Data On Creation or Re-Enabling**</span></span>  
 <span data-ttu-id="129a9-137">Gibt an, ob alle vorhandenen Daten (Daten, die vor Erstellen der Einschränkung in der Tabelle vorhanden sind) mit der Einschränkung überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="129a9-137">Specify whether all pre-existing data (data existing in the table before the constraint is created) is verified against the constraint.</span></span>  
  
 <span data-ttu-id="129a9-138">**Für INSERTs und UPDATEs erzwingen**</span><span class="sxs-lookup"><span data-stu-id="129a9-138">**Enforce For Inserts And Updates**</span></span>  
 <span data-ttu-id="129a9-139">Gibt an, ob die Einschränkung erzwungen wird, wenn die Daten in die Tabelle eingefügt oder in der Tabelle aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="129a9-139">Specify whether the constraint is enforced when data is inserted into or updated in the table.</span></span>  
  
 <span data-ttu-id="129a9-140">**Für Replikation erzwingen**</span><span class="sxs-lookup"><span data-stu-id="129a9-140">**Enforce For Replication**</span></span>  
 <span data-ttu-id="129a9-141">Gibt an, ob die Einschränkung erzwungen wird, wenn durch einen Replikations-Agent in der Tabelle ein INSERT oder ein UPDATE ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="129a9-141">Indicates whether to enforce the constraint when a replication agent performs an insert or update on this table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="129a9-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="129a9-142">See Also</span></span>  
 <span data-ttu-id="129a9-143">[Unique-Einschränkungen und Check-Einschränkungen](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="129a9-143">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="129a9-144">Dialog Feld "Indizes und Schlüssel" &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="129a9-144">Indexes and Keys Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
