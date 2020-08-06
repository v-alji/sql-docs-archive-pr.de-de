---
title: REPLACENULL (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 70db7832-b5a0-4db5-a8ad-42ad8630d8e8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f10bb6ef6102076fe7b1cc236461e2358ad96372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701420"
---
# <a name="replacenull-ssis-expression"></a><span data-ttu-id="4fb9b-102">REPLACENULL (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="4fb9b-102">REPLACENULL (SSIS Expression)</span></span>
  <span data-ttu-id="4fb9b-103">Gibt den Wert des zweiten Ausdrucksparameters zurück, wenn der erste Ausdrucksparameter NULL ist; andernfalls wird der Wert des ersten Ausdrucks zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-103">Returns the value of second expression parameter if the value of first expression parameter is NULL; otherwise, returns the value of first expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fb9b-104">Syntax</span></span>  
  
```vb  
REPLACENULL(expression 1,expression 2)  
```  
  
## <a name="arguments"></a><span data-ttu-id="4fb9b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4fb9b-105">Arguments</span></span>  
 <span data-ttu-id="4fb9b-106">*expression 1*</span><span class="sxs-lookup"><span data-stu-id="4fb9b-106">*expression 1*</span></span>  
 <span data-ttu-id="4fb9b-107">Das Ergebnis dieses Ausdrucks wird mit NULL verglichen.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-107">The result of this expression is checked against NULL.</span></span>  
  
 <span data-ttu-id="4fb9b-108">*expression 2*</span><span class="sxs-lookup"><span data-stu-id="4fb9b-108">*expression 2*</span></span>  
 <span data-ttu-id="4fb9b-109">Das Ergebnis dieses Ausdrucks wird zurückgegeben, wenn der erste Ausdruck NULL ergibt.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-109">The result of this expression is returned if the first expression evaluates to NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4fb9b-110">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="4fb9b-110">Result Types</span></span>  
 <span data-ttu-id="4fb9b-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="4fb9b-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fb9b-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4fb9b-112">Remarks</span></span>  
  
-   <span data-ttu-id="4fb9b-113">Die Länge von *expression 2* darf Null sein.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-113">The length of *expression 2* may be zero.</span></span>  
  
-   <span data-ttu-id="4fb9b-114">REPLACENULL gibt ein NULL-Ergebnis zurück, wenn eines der Argumente NULL ist.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-114">REPLACENULL returns a null result if any argument is null.</span></span>  
  
-   <span data-ttu-id="4fb9b-115">BLOB-Spalten (DT_TEXT, DT_NTEXT, DT_IMAGE) werden von keimen der beiden Parameter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-115">BLOB columns (DT_TEXT, DT_NTEXT, DT_IMAGE) are not supported for either parameter.</span></span>  
  
-   <span data-ttu-id="4fb9b-116">Es wird davon ausgegangen, dass die zwei Ausdrücke den gleichen Rückgabetyp haben.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-116">The two expressions are expected to have the same return type.</span></span> <span data-ttu-id="4fb9b-117">Andernfalls versucht die Funktion, den 2. Ausdruck in den Rückgabetyp des 1. Ausdrucks umzuwandeln, was möglicherweise zu einem Fehler führt, wenn die Datentypen nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-117">If they do not, the function attempts to cast the 2nd expression to the return type of the 1st expression, which may result in an error if the data types are incompatible.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4fb9b-118">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4fb9b-118">Expression Examples</span></span>  
 <span data-ttu-id="4fb9b-119">Im folgenden Beispiel wird ein beliebiger NULL-Wert in einer Datenbankspalte durch eine Zeichenfolge (1900-01-01) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-119">The following example replaces any NULL value in a database column with a string (1900-01-01).</span></span> <span data-ttu-id="4fb9b-120">Diese Funktion wird vor allem in häufigen Mustern für abgeleitete Spalten verwendet, in denen Sie NULL-Werte durch andere Werte ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-120">This function is especially used in common Derived Column patterns where you want to replace NULL values with something else.</span></span>  
  
```  
REPLACENULL(MyColumn, "1900-01-01")  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4fb9b-121">Im folgenden Beispiel wird gezeigt, wie in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)]vorgegangen wurde.</span><span class="sxs-lookup"><span data-stu-id="4fb9b-121">The following example shows how it was done in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span></span>  
  
```  
(DT_DBTIMESTAMP) (ISNULL(MyColumn) ? "1900-01-01" : MyColumn)   
```  
  
  
