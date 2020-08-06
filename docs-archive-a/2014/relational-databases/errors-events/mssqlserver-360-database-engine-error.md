---
title: MSSQLSERVER_360 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 360 (Database Engine error)
ms.assetid: e2b7c1b2-3679-4206-9b25-6bd55ef96a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b30311d7f55231c1e7a6d5969d49c5d1bc07a848
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616576"
---
# <a name="mssqlserver_360"></a><span data-ttu-id="33db3-102">MSSQLSERVER_360</span><span class="sxs-lookup"><span data-stu-id="33db3-102">MSSQLSERVER_360</span></span>
    
## <a name="details"></a><span data-ttu-id="33db3-103">Details</span><span class="sxs-lookup"><span data-stu-id="33db3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33db3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="33db3-104">Product Name</span></span>|<span data-ttu-id="33db3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="33db3-105">SQL Server</span></span>|  
|<span data-ttu-id="33db3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="33db3-106">Event ID</span></span>|<span data-ttu-id="33db3-107">360</span><span class="sxs-lookup"><span data-stu-id="33db3-107">360</span></span>|  
|<span data-ttu-id="33db3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="33db3-108">Event Source</span></span>|<span data-ttu-id="33db3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="33db3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="33db3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="33db3-110">Component</span></span>|<span data-ttu-id="33db3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="33db3-111">SQLEngine</span></span>|  
|<span data-ttu-id="33db3-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="33db3-112">Symbolic Name</span></span>|<span data-ttu-id="33db3-113">DML_UPDATE_SPARSE_AND_COLSET</span><span class="sxs-lookup"><span data-stu-id="33db3-113">DML_UPDATE_SPARSE_AND_COLSET</span></span>|  
|<span data-ttu-id="33db3-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="33db3-114">Message Text</span></span>|<span data-ttu-id="33db3-115">Die Zielspaltenliste einer INSERT-, UPDATE- oder MERGE-Anweisung kann nicht sowohl eine Sparsespalte als auch den Spaltensatz enthalten, in dem sich die Sparsespalte befindet.</span><span class="sxs-lookup"><span data-stu-id="33db3-115">The target column list of an INSERT, UPDATE, or MERGE statement cannot contain both a sparse column and the column set that contains the sparse column.</span></span> <span data-ttu-id="33db3-116">Schreiben Sie die Anweisung um, sodass entweder nur die Sparsespalte oder nur der Spaltensatz enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="33db3-116">Rewrite the statement to include either the sparse column or the column set, but not both.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33db3-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="33db3-117">Explanation</span></span>  
 <span data-ttu-id="33db3-118">Ein Spaltensatz ist eine nicht typisierte XML-Darstellung, in der einige Spalten einer Tabelle zu einer strukturierten Ausgabe zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="33db3-118">A column set is an untyped XML representation that combines some columns of a table into a structured output.</span></span> <span data-ttu-id="33db3-119">Es wurde versucht, sowohl den Spaltensatz als auch eine Spalte aus dem Spaltensatz zu ändern, sodass zwei Verweise auf die gleiche Spalte entstanden.</span><span class="sxs-lookup"><span data-stu-id="33db3-119">An attempt was made to modify both the column set and a column that is included in the column set, causing two references to the same column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33db3-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="33db3-120">User Action</span></span>  
 <span data-ttu-id="33db3-121">Schreiben Sie die Anweisung um, sodass Verweise auf entweder die Spalte mit geringer Dichte oder auf den Spaltensatz enthalten sind. Schließen Sie jedoch keinesfalls beide in die Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="33db3-121">Rewrite the statement to include references to either the column or the column set, but do not include both in the statement.</span></span>  
  
  
