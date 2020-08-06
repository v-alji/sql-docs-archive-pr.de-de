---
title: Verwenden von Tabellen in Datenbankdiagrammen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], tables
- Table Designer, database diagrams
- tables [SQL Server], database diagrams
- database diagrams [SQL Server], Table Designer
ms.assetid: ee2c5d84-22bf-4597-ac70-a27ed8cc94f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: f648cd5fd08ed47c6670491ad5b7f3d75b7ead47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619490"
---
# <a name="work-with-tables-in-database-diagram-visual-database-tools"></a><span data-ttu-id="74cb4-102">Verwenden von Tabellen in Datenbankdiagrammen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="74cb4-102">Work with Tables in Database Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="74cb4-103">Sie können Datenbanktabellen sowohl im Tabellen-Designer als auch im Datenbankdiagramm-Designer erstellen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="74cb4-103">You can modify and create database tables in either Table Designer or Database Diagram Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74cb4-104">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="74cb4-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="74cb4-105">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74cb4-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="74cb4-106">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="74cb4-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74cb4-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="74cb4-107">In This Section</span></span>  
 [<span data-ttu-id="74cb4-108">Hinzufügen von Tabellen zu Diagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-108">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
 [<span data-ttu-id="74cb4-109">Hinzufügen verknüpfter Tabellen zu Diagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-109">Add Related Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-related-tables-to-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="74cb4-110">Speichern ausgewählter Tabellen in einem Diagramm &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-110">Save Selected Tables on a Diagram &#40;Visual Database Tools&#41;</span></span>](save-selected-tables-on-a-diagram-visual-database-tools.md)  
  
 [<span data-ttu-id="74cb4-111">Kopieren von Tabellen von einem Datenbankdiagramm in ein anderes Datenbankdiagramm &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-111">Copy Tables from One Database Diagrams to Another &#40;Visual Database Tools&#41;</span></span>](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)  
  
 [<span data-ttu-id="74cb4-112">Entfernen von Tabellen aus Datenbankdiagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-112">Remove Tables from Database Diagrams &#40;Visual Database Tools&#41;</span></span>](remove-tables-from-database-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="74cb4-113">Zuordnen von m:n-Beziehungen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-113">Map Many-to-Many Relationships &#40;Visual Database Tools&#41;</span></span>](map-many-to-many-relationships-visual-database-tools.md)  
  
 [<span data-ttu-id="74cb4-114">Zeichnen reflexiver Beziehungen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-114">Draw Reflexive Relationships &#40;Visual Database Tools&#41;</span></span>](draw-reflexive-relationships-visual-database-tools.md)  
  
## <a name="reference"></a><span data-ttu-id="74cb4-115">Verweis</span><span class="sxs-lookup"><span data-stu-id="74cb4-115">Reference</span></span>  
 [<span data-ttu-id="74cb4-116">Tabelle hinzufügen (Dialogfeld) &#40;Datenbank-Designer&#41; &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb4-116">Add Table Dialog Box &#40;Database Designer&#41; &#40;Visual Database Tools&#41;</span></span>](add-table-dialog-box-database-designer-visual-database-tools.md)  
  
## <a name="related-sections"></a><span data-ttu-id="74cb4-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="74cb4-117">Related Sections</span></span>  
  
