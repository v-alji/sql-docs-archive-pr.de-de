---
title: 'Tutorial: Verwenden des hierarchyid-Datentyps | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tutorials [hierarchyid]
- hierarchyid [Database Engine], tutorial
ms.assetid: 5a7f7cfd-7faf-439f-8085-8fd6bf7db355
author: stevestein
ms.author: sstein
ms.openlocfilehash: a735b4c2b51e1c680c8129647733ce1efd9f9984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615911"
---
# <a name="tutorial-using-the-hierarchyid-data-type"></a><span data-ttu-id="46fe2-102">Lernprogramm: Verwenden des hierarchyid-Datentyps</span><span class="sxs-lookup"><span data-stu-id="46fe2-102">Tutorial: Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="46fe2-103">Dieses Lernprogramm richtet sich an Benutzer, die mit [!INCLUDE[tsql](../../includes/tsql-md.md)] vertraut sind, aber noch keine Erfahrung mit dem `hierarchyid`-Datentyp haben.</span><span class="sxs-lookup"><span data-stu-id="46fe2-103">This tutorial is intended for users who are experienced with [!INCLUDE[tsql](../../includes/tsql-md.md)], but are new to the `hierarchyid` data type.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="46fe2-104">Lernziele</span><span class="sxs-lookup"><span data-stu-id="46fe2-104">What You Will Learn</span></span>  
 <span data-ttu-id="46fe2-105">Dieses Lernprogramm ist in zwei Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="46fe2-105">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="46fe2-106">Lektion 1: Konvertieren einer Tabelle in eine hierarchische Struktur</span><span class="sxs-lookup"><span data-stu-id="46fe2-106">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-converting-a-table-to-a-hierarchical-structure.md)  
 <span data-ttu-id="46fe2-107">In dieser Lektion verschieben Sie die Daten einer vorhandenen Angestelltentabelle, die als Über-/Unterordnungshierarchie strukturiert ist, in eine neue Tabelle, welche die Hierarchie mithilfe des `hierarchyid`-Datentyps darstellt.</span><span class="sxs-lookup"><span data-stu-id="46fe2-107">In this lesson, you take an existing employee table that is structured as a parent/child hierarchy and move the data into a new table that represents the hierarchy by using the `hierarchyid` data type.</span></span> <span data-ttu-id="46fe2-108">Für diese Lektion benötigen Sie die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="46fe2-108">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [<span data-ttu-id="46fe2-109">Lektion 2: Erstellen und Verwalten von Daten in einer hierarchischen Tabelle</span><span class="sxs-lookup"><span data-stu-id="46fe2-109">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
 <span data-ttu-id="46fe2-110">In dieser Lektion erstellen Sie eine Tabelle, in der die Hierarchie mithilfe des `hierarchyid`-Datentyps dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="46fe2-110">In this lesson, you create a table by using the `hierarchyid` data type to represent the hierarchy structure.</span></span> <span data-ttu-id="46fe2-111">Dann bearbeiten Sie die Daten in der Tabelle, indem Sie hierarchische Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="46fe2-111">Then, you manipulate the data in the table by using the hierarchical methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46fe2-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="46fe2-112">Requirements</span></span>  
 <span data-ttu-id="46fe2-113">Auf dem System muss Folgendes installiert sein:</span><span class="sxs-lookup"><span data-stu-id="46fe2-113">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="46fe2-114">Eine beliebige Edition von [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder höher.</span><span class="sxs-lookup"><span data-stu-id="46fe2-114">Any edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
-   <span data-ttu-id="46fe2-115">Entweder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="46fe2-115">Either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Express.</span></span>  
  
-   <span data-ttu-id="46fe2-116">Internet Explorer 6 oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="46fe2-116">Internet Explorer 6 or a later version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46fe2-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46fe2-117">See Also</span></span>  
 <span data-ttu-id="46fe2-118">[Tutorial: Einstieg in die Datenbank-Engine](../tutorial-getting-started-with-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="46fe2-118">[Tutorial: Getting Started with the Database Engine](../tutorial-getting-started-with-the-database-engine.md) </span></span>  
 <span data-ttu-id="46fe2-119">[Tutorial: Schreiben von Transact-SQL-Anweisungen](../../t-sql/tutorial-writing-transact-sql-statements.md) </span><span class="sxs-lookup"><span data-stu-id="46fe2-119">[Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md) </span></span>  
 <span data-ttu-id="46fe2-120">[hierarchyid-Datentyp-Methoden Verweis](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="46fe2-120">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="46fe2-121">[SQL Server der hierarchischen Daten &#40;&#41;](../hierarchical-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="46fe2-121">[Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md) </span></span>  
 [<span data-ttu-id="46fe2-122">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="46fe2-122">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
