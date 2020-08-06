---
title: Tabelle aktualisieren (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.updatetable
- vdtsql.chm:69643
ms.assetid: 174c7275-5b15-42a9-b172-5ff30de575a1
author: stevestein
ms.author: sstein
ms.openlocfilehash: 426c842b85d6404ba101b57a9b572107dbc76bb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619489"
---
# <a name="update-table-dialog-box-visual-database-tools"></a><span data-ttu-id="f6039-102">Tabelle aktualisieren (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f6039-102">Update Table Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="f6039-103">Mit diesem Dialogfeld können Sie die Tabelle angeben, die aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f6039-103">This dialog box allows you to specify the table to be updated.</span></span>  
  
 <span data-ttu-id="f6039-104">Dieses Dialogfeld wird angezeigt, wenn beim Ändern eines Abfragetyps in eine Updateabfrage mehr als eine Tabelle im Diagrammbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f6039-104">This dialog box appears if more than one table is displayed in the Diagram pane when you change a query's type to be an Update query.</span></span>  
  
 <span data-ttu-id="f6039-105">Wählen Sie die zu aktualisierbare Tabelle aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="f6039-105">Select the table to update, and then choose **OK**.\</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6039-106">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f6039-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="f6039-107">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6039-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="f6039-108">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="f6039-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6039-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6039-109">See Also</span></span>  
 [<span data-ttu-id="f6039-110">Erstellen von Updateabfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f6039-110">Create Update Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
