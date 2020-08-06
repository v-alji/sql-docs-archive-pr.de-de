---
title: MSSQLSERVER_2570 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 79137d0f70c05c6aa7b758f7e073d152681a14b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696869"
---
# <a name="mssqlserver_2570"></a><span data-ttu-id="6168a-102">MSSQLSERVER_2570</span><span class="sxs-lookup"><span data-stu-id="6168a-102">MSSQLSERVER_2570</span></span>
    
## <a name="details"></a><span data-ttu-id="6168a-103">Details</span><span class="sxs-lookup"><span data-stu-id="6168a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6168a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6168a-104">Product Name</span></span>|<span data-ttu-id="6168a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6168a-105">SQL Server</span></span>|  
|<span data-ttu-id="6168a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6168a-106">Event ID</span></span>|<span data-ttu-id="6168a-107">2570</span><span class="sxs-lookup"><span data-stu-id="6168a-107">2570</span></span>|  
|<span data-ttu-id="6168a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6168a-108">Event Source</span></span>|<span data-ttu-id="6168a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6168a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6168a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6168a-110">Component</span></span>|<span data-ttu-id="6168a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6168a-111">SQLEngine</span></span>|  
|<span data-ttu-id="6168a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6168a-112">Symbolic Name</span></span>|<span data-ttu-id="6168a-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="6168a-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="6168a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6168a-114">Message Text</span></span>|<span data-ttu-id="6168a-115">Seite P_ID, Slot S_ID in Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ).</span><span class="sxs-lookup"><span data-stu-id="6168a-115">Page P_ID, slot S_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="6168a-116">Der Wert der COLUMN_NAME-Spalte liegt für den "DATATYPE"-Datentyp außerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="6168a-116">Column COLUMN_NAME value is out of range for data type "DATATYPE".</span></span> <span data-ttu-id="6168a-117">Aktualisieren Sie die Spalte auf einen gültigen Wert.</span><span class="sxs-lookup"><span data-stu-id="6168a-117">Update column to a legal value.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6168a-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6168a-118">Explanation</span></span>  
 <span data-ttu-id="6168a-119">Der Spaltenwert, der in der angegebenen Spalte enthalten ist, liegt außerhalb des Bereichs der möglichen Werte für den Spaltendatentyp.</span><span class="sxs-lookup"><span data-stu-id="6168a-119">The column value that is contained in the specified column is outside the range of possible values for the column data type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6168a-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6168a-120">User Action</span></span>  
 <span data-ttu-id="6168a-121">Der Fehler kann nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="6168a-121">The error is not repairable.</span></span> <span data-ttu-id="6168a-122">Aktualisieren Sie die Spalte auf einen Wert innerhalb des Bereichs für den Datentyp der Spalte, und führen Sie den Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="6168a-122">Update the column to a value within the range for the data type of the column and run the command again.</span></span>  <span data-ttu-id="6168a-123">Weitere Informationen finden Sie im KB-Artikel [923247](https://support.microsoft.com/kb/923247).</span><span class="sxs-lookup"><span data-stu-id="6168a-123">For more information, see this KB article [923247](https://support.microsoft.com/kb/923247).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6168a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6168a-124">See Also</span></span>  
 <span data-ttu-id="6168a-125">[UPDATE (Transact-SQL)](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6168a-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 [<span data-ttu-id="6168a-126">Datentypen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6168a-126">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
