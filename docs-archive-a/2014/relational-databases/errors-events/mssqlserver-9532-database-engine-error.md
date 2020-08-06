---
title: MSSQLSERVER_9532 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34ebc7c682d2ffe8bc0205565f5dfd44fdd5b66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617035"
---
# <a name="mssqlserver_9532"></a><span data-ttu-id="4bb6c-102">MSSQLSERVER_9532</span><span class="sxs-lookup"><span data-stu-id="4bb6c-102">MSSQLSERVER_9532</span></span>
    
## <a name="details"></a><span data-ttu-id="4bb6c-103">Details</span><span class="sxs-lookup"><span data-stu-id="4bb6c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bb6c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4bb6c-104">Product Name</span></span>|<span data-ttu-id="4bb6c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4bb6c-105">SQL Server</span></span>|  
|<span data-ttu-id="4bb6c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4bb6c-106">Event ID</span></span>|<span data-ttu-id="4bb6c-107">9532</span><span class="sxs-lookup"><span data-stu-id="4bb6c-107">9532</span></span>|  
|<span data-ttu-id="4bb6c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4bb6c-108">Event Source</span></span>|<span data-ttu-id="4bb6c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4bb6c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4bb6c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4bb6c-110">Component</span></span>|<span data-ttu-id="4bb6c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4bb6c-111">SQLEngine</span></span>|  
|<span data-ttu-id="4bb6c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4bb6c-112">Symbolic Name</span></span>|<span data-ttu-id="4bb6c-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span><span class="sxs-lookup"><span data-stu-id="4bb6c-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span></span>|  
|<span data-ttu-id="4bb6c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4bb6c-114">Message Text</span></span>|<span data-ttu-id="4bb6c-115">Konvertierungsfehler während des Abfrage-/DML-Vorgangs mit dem Spaltensatz '%.\*ls' beim Versuch, den '%ls'-Datentyp für die '%.\*ls'-Spalte in den '%ls'-Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-115">In the query/DML operation involving  column set '%.\*ls', conversion failed when converting from the data type '%ls' to the data type '%ls' for the column '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4bb6c-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4bb6c-116">Explanation</span></span>  
 <span data-ttu-id="4bb6c-117">Bei einem Spaltensatz handelt es sich um eine nicht typisierte XML-Darstellung, die einige Tabellenspalten mit geringer Dichte in einer strukturierten Ausgabe kombiniert.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-117">A column set is an untyped XML representation that combines some of the columns of a table into a structured output.</span></span> <span data-ttu-id="4bb6c-118">Wenn Sie die Sparsespalten mit dem XML-Spaltensatz einfügen bzw. aktualisieren, werden die Werte, die in die zugrunde liegenden Sparsespalten eingefügt werden, automatisch vom `xml`-Datentyp konvertiert.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-118">When you are inserting or updating sparse column values through the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="4bb6c-119">Es wurde ein Wert angegeben, der nicht in den Datentyp der Spalte konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-119">A value was provided that cannot be converted to the data type of the column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4bb6c-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4bb6c-120">User Action</span></span>  
 <span data-ttu-id="4bb6c-121">Da der bereitgestellte Wert nicht implizit konvertiert werden konnte, könnte es sich um einen ungültigen Eintrag handeln.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-121">Because the value provided could not be implicitly converted, it might be an invalid entry.</span></span> <span data-ttu-id="4bb6c-122">Beheben Sie den Fehler, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-122">Correct the error and retry.</span></span> <span data-ttu-id="4bb6c-123">Wenn der Wert korrekt ist, bearbeiten Sie die Anweisung so, dass die einzelnen Spalten anstelle des gesamten Spaltensatzes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-123">If the value is correct, modify the statement to use the individual columns instead of the column set.</span></span> <span data-ttu-id="4bb6c-124">Dadurch können Sie den Wert explizit in den richtigen Datentyp umwandeln.</span><span class="sxs-lookup"><span data-stu-id="4bb6c-124">This will allow you to explicitly cast the value into the correct data type.</span></span>  
  
  
