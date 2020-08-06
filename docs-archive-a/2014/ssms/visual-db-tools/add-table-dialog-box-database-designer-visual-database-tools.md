---
title: Tabelle hinzufügen (Dialogfeld) (Datenbank-Designer) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65555
- vdt.dlgbox.schema.addtable
ms.assetid: 3c0b1b30-795c-4240-91d6-890b8348014a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ae9d3763ef66c0a7580cc516169c2f273f36528
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615755"
---
# <a name="add-table-dialog-box-database-designer-visual-database-tools"></a><span data-ttu-id="8a10f-102">Tabelle hinzufügen (Dialogfeld) (Database Designer) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8a10f-102">Add Table Dialog Box (Database Designer) (Visual Database Tools)</span></span>
  <span data-ttu-id="8a10f-103">Mit diesem Dialogfeld können Sie Tabellen im Datenbank-Designer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8a10f-103">Lets you add tables in Database Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a10f-104">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="8a10f-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="8a10f-105">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a10f-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="8a10f-106">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="8a10f-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8a10f-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="8a10f-107">UI element list</span></span>  
 <span data-ttu-id="8a10f-108">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="8a10f-108">**Refresh**</span></span>  
 <span data-ttu-id="8a10f-109">Aktualisiert die Liste der Tabellen, sodass sie mit dem aktuellen Stand der Datenbank übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8a10f-109">Refreshed the list of tables to match the current state of the database.</span></span>  
  
 <span data-ttu-id="8a10f-110">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="8a10f-110">**Add**</span></span>  
 <span data-ttu-id="8a10f-111">Fügt die ausgewählten Tabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a10f-111">Adds the selected table or tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a10f-112">Wenn Sie dem Diagramm mehrere Tabellen hinzufügen möchten, können Sie alle auswählen und dann auf **Hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="8a10f-112">If you want to add several tables to the diagram, you can select them all before clicking **Add**.</span></span> <span data-ttu-id="8a10f-113">Sie können auch auf jede hinzuzufügende Tabelle doppelklicken und anschließend auf **Schließen** klicken.</span><span class="sxs-lookup"><span data-stu-id="8a10f-113">Alternatively, you can double-click each table you want to add, then click **Close** when you are finished.</span></span>  
  
 <span data-ttu-id="8a10f-114">**Close**</span><span class="sxs-lookup"><span data-stu-id="8a10f-114">**Close**</span></span>  
 <span data-ttu-id="8a10f-115">Schließt das Dialogfeld, ohne dass weitere Tabellen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8a10f-115">Closes the dialog box without adding further tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a10f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a10f-116">See Also</span></span>  
 [<span data-ttu-id="8a10f-117">Hinzufügen von Tabellen zu Diagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8a10f-117">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
