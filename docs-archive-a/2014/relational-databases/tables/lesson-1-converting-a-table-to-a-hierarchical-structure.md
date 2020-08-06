---
title: 'Lektion 1: Konvertieren einer Tabelle in eine hierarchische Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 196a546093786f9be4b88536763b3150ae750f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724474"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a><span data-ttu-id="36207-102">Lektion 1: Konvertieren einer Tabelle in eine hierarchische Struktur</span><span class="sxs-lookup"><span data-stu-id="36207-102">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>
  <span data-ttu-id="36207-103">Kunden mit Tabellen, die hierarchische Beziehungen mithilfe von Selbstjoins darstellen, können diese Tabellen in eine hierarchische Struktur konvertieren, indem Sie diese Lektion als Richtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="36207-103">Customers who have tables using self joins to express hierarchical relationships can convert their tables to a hierarchical structure using this lesson as a guide.</span></span> <span data-ttu-id="36207-104">Es ist relativ leicht, von dieser Darstellung zu einer mit `hierarchyid` zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="36207-104">It is relatively easy to migrate from this representation to one using `hierarchyid`.</span></span> <span data-ttu-id="36207-105">Nach der Migration verfügen die Benutzer über ein grundlegendes Verständnis hierarchischer Darstellungen, die für effizientere Abfragen auf verschiedene Weise indiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="36207-105">After migration, users will have a compact and easy to understand hierarchical representation, which can be indexed in several ways for efficient queries.</span></span>  
  
 <span data-ttu-id="36207-106">In dieser Lektion wird eine vorhandene Tabelle untersucht und eine neue Tabelle mit einer `hierarchyid`-Spalte erstellt. Daraufhin wird diese Tabelle mit den Daten der Quelltabelle gefüllt, und schließlich werden drei Indizierungsstrategien dargestellt.</span><span class="sxs-lookup"><span data-stu-id="36207-106">This lesson, examines an existing table, creates a new table containing a `hierarchyid` column, populates the table with the data from the source table, and then demonstrates three indexing strategies.</span></span> <span data-ttu-id="36207-107">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="36207-107">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="36207-108">Untersuchen der aktuellen Struktur der Mitarbeitertabelle</span><span class="sxs-lookup"><span data-stu-id="36207-108">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [<span data-ttu-id="36207-109">Auffüllen einer Tabelle mit vorhandenen hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="36207-109">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [<span data-ttu-id="36207-110">Optimieren der NewOrg-Tabelle</span><span class="sxs-lookup"><span data-stu-id="36207-110">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [<span data-ttu-id="36207-111">Zusammenfassung: Konvertieren einer Tabelle in eine hierarchische Struktur</span><span class="sxs-lookup"><span data-stu-id="36207-111">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a><span data-ttu-id="36207-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="36207-112">Prerequisites</span></span>  
 <span data-ttu-id="36207-113">Für diese Lektion benötigen Sie die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="36207-113">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="36207-114">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="36207-114">Next Task in Lesson</span></span>  
 [<span data-ttu-id="36207-115">Untersuchen der aktuellen Struktur der Mitarbeitertabelle</span><span class="sxs-lookup"><span data-stu-id="36207-115">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="36207-116">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="36207-116">Next Lesson</span></span>  
 [<span data-ttu-id="36207-117">Lektion 2: Erstellen und Verwalten von Daten in einer hierarchischen Tabelle</span><span class="sxs-lookup"><span data-stu-id="36207-117">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  
