---
title: Tabelle hinzufügen (Dialog Feld) (Abfrage-und Sicht-Designer) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.query.addtable
- vdtsql.chm:65565
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d7bf30cbdd37927735c36f184208a1ded957763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615754"
---
# <a name="add-table-dialog-box-query-and-view-designers-visual-database-tools"></a><span data-ttu-id="0c13d-102">Tabelle hinzufügen (Dialogfeld) (Abfrage- und Sicht-Designer) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0c13d-102">Add Table Dialog Box (Query and View Designers) (Visual Database Tools)</span></span>
  <span data-ttu-id="0c13d-103">Mit diesem Dialogfeld können Sie einer Abfrage oder Sicht Tabellen, Sichten, benutzerdefinierte Funktionen oder Synonyme hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c13d-103">This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c13d-104">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c13d-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="0c13d-105">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c13d-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="0c13d-106">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="0c13d-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c13d-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0c13d-107">Options</span></span>  
 <span data-ttu-id="0c13d-108">**Tabellen**</span><span class="sxs-lookup"><span data-stu-id="0c13d-108">**Tables**</span></span>  
 <span data-ttu-id="0c13d-109">Listet die Tabellen auf, die dem Bereich **Diagramm** hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c13d-109">Lists the tables you can add to the **Diagram** pane.</span></span> <span data-ttu-id="0c13d-110">Um eine Tabelle hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-110">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="0c13d-111">Um mehrere Tabellen gleichzeitig hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-111">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="0c13d-112">**Ansichten**</span><span class="sxs-lookup"><span data-stu-id="0c13d-112">**Views**</span></span>  
 <span data-ttu-id="0c13d-113">Listet die Sichten auf, die dem Bereich **Diagramm** hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c13d-113">Lists the views you can add to the **Diagram** pane.</span></span> <span data-ttu-id="0c13d-114">Um eine Sicht hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-114">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="0c13d-115">Um mehrere Sichten gleichzeitig hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-115">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="0c13d-116">**Funktionen**</span><span class="sxs-lookup"><span data-stu-id="0c13d-116">**Functions**</span></span>  
 <span data-ttu-id="0c13d-117">Listet die benutzerdefinierten Funktionen auf, die dem Bereich **Diagramm** hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c13d-117">Lists the user-defined functions you can add to the **Diagram** pane.</span></span> <span data-ttu-id="0c13d-118">Um eine Funktion hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-118">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="0c13d-119">Um mehrere Funktionen gleichzeitig hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-119">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="0c13d-120">**Synonyme**</span><span class="sxs-lookup"><span data-stu-id="0c13d-120">**Synonyms**</span></span>  
 <span data-ttu-id="0c13d-121">Listet die Synonyme auf, die dem Bereich **Diagramm** hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c13d-121">Lists the synonyms you can add to the **Diagram** pane.</span></span> <span data-ttu-id="0c13d-122">Um ein Synonym hinzuzufügen, wählen Sie es aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-122">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="0c13d-123">Um mehrere Synonyme gleichzeitig hinzuzufügen, wählen Sie sie aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0c13d-123">To add several synonyms at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="0c13d-124">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="0c13d-124">**Refresh**</span></span>  
 <span data-ttu-id="0c13d-125">Aktualisieren Sie die Liste, sodass alle Änderungen an der Datenbank in die Liste aufgenommen werden, die seit dem letzten Abrufen der Liste vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0c13d-125">Update the list to include any changes made to the database since the list was last retrieved.</span></span>  
  
 <span data-ttu-id="0c13d-126">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="0c13d-126">**Add**</span></span>  
 <span data-ttu-id="0c13d-127">Fügen Sie die jeweils ausgewählten Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c13d-127">Add the selected item or items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c13d-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c13d-128">See Also</span></span>  
 [<span data-ttu-id="0c13d-129">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0c13d-129">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
