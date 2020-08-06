---
title: Erstellen von Beziehungen zwischen Tabellen in einem Diagramm (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7d627a37f84dcb66b2129bb9c7dbc5890ccd46c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724358"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a><span data-ttu-id="d670a-102">Erstellen von Beziehungen zwischen Tabellen in einem Diagramm (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d670a-102">Create Relationships Between Tables on a Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="d670a-103">Sie können im Datenbank-Designer Beziehungen zwischen den Spalten in verschiedenen Tabellen erstellen, indem Sie Spalten zwischen Tabellen ziehen.</span><span class="sxs-lookup"><span data-stu-id="d670a-103">You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.</span></span>  
  
### <a name="to-create-a-relationship-graphically"></a><span data-ttu-id="d670a-104">So erstellen Sie eine Beziehung grafisch</span><span class="sxs-lookup"><span data-stu-id="d670a-104">To create a relationship graphically</span></span>  
  
1.  <span data-ttu-id="d670a-105">Klicken Sie im Datenbank-Designer auf die Zeilenauswahl, um eine oder mehrere Datenbankspalten auszuwählen, für die Sie eine Beziehung mit einer Spalte in einer anderen Tabelle erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d670a-105">In Database Designer, click the row selector for one or more database columns that you want to relate to a column in another table.</span></span>  
  
2.  <span data-ttu-id="d670a-106">Ziehen Sie die Spalte(n) auf die zugehörige Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d670a-106">Drag the selected column(s) to the related table.</span></span>  
  
3.  <span data-ttu-id="d670a-107">Es werden zwei Dialogfelder angezeigt: **Fremdschlüsselbeziehung** und **Tabellen und Spalten**, wobei letzteres im Vordergrund angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d670a-107">Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.</span></span>  
  
4.  <span data-ttu-id="d670a-108">Unter**Beziehungsname** wird ein vom System bereitgestellter Name im Format FK_*localtable*_*foreigntable*angegeben.</span><span class="sxs-lookup"><span data-stu-id="d670a-108">**Relationship name** has a system-provided name in the format FK_*localtable*_*foreigntable*.</span></span> <span data-ttu-id="d670a-109">Sie können diesen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="d670a-109">You may change this value.</span></span>  
  
5.  <span data-ttu-id="d670a-110">Stellen Sie sicher, dass für **Primärschlüsseltabelle** die richtige Tabelle angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d670a-110">Verify that **Primary key table** specifies the correct table.</span></span>  
  
6.  <span data-ttu-id="d670a-111">Im Raster sind alle lokalen Spalten und die entsprechenden Fremdspalten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d670a-111">The grid lists the local columns and their matching foreign columns.</span></span> <span data-ttu-id="d670a-112">Sie können Spalten hinzufügen oder entfernen bzw. die Zuordnungen ändern.</span><span class="sxs-lookup"><span data-stu-id="d670a-112">You can add or remove table columns or change mappings.</span></span>  
  
7.  <span data-ttu-id="d670a-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d670a-113">Choose **OK**.</span></span>  
  
     <span data-ttu-id="d670a-114">Das Dialogfeld **Fremdschlüsselbeziehung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d670a-114">The **Foreign Key Relationship** dialog box appears.</span></span> <span data-ttu-id="d670a-115">Unter**Ausgewählte Beziehung** wird die von Ihnen erstellte Beziehung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d670a-115">**Selected Relationship** shows the relationship you have created.</span></span>  
  
8.  <span data-ttu-id="d670a-116">Sie können die Eigenschaften der Beziehung im Raster ändern.</span><span class="sxs-lookup"><span data-stu-id="d670a-116">Change properties for the relationship in the grid.</span></span>  
  
9. <span data-ttu-id="d670a-117">Klicken Sie auf **OK** , um die Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d670a-117">Choose **OK** to create the relationship.</span></span>  
  
     <span data-ttu-id="d670a-118">Im Datenbank-Designer wird eine Beziehung zwischen von Ihnen ausgewählten Spalten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d670a-118">Database Designer shows a relationship between the columns you chose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d670a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d670a-119">See Also</span></span>  
 <span data-ttu-id="d670a-120">[Tabellen und Spalten (Dialog Feld) &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d670a-120">[Tables and Columns Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="d670a-121">[Unique-Einschränkungen und Check-Einschränkungen](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="d670a-121">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="d670a-122">Verwenden von Tabellen in Datenbankdiagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d670a-122">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
