---
title: NULL (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- NULL function
- null values [Integration Services]
ms.assetid: df144237-3fbb-41ac-8624-efd92b6522b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14cd51b4e245ca6984a4c62eae2b9d5536ab1f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608760"
---
# <a name="null-ssis-expression"></a><span data-ttu-id="346ed-102">NULL (SSIS-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="346ed-102">NULL (SSIS Expression)</span></span>
  <span data-ttu-id="346ed-103">Gibt einen NULL-Wert eines angeforderten Datentyps zurück.</span><span class="sxs-lookup"><span data-stu-id="346ed-103">Returns a null value of a requested data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="346ed-104">Syntax</span></span>  
  
```  
  
NULL(typespec)  
```  
  
## <a name="arguments"></a><span data-ttu-id="346ed-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="346ed-105">Arguments</span></span>  
 <span data-ttu-id="346ed-106">*typespec*</span><span class="sxs-lookup"><span data-stu-id="346ed-106">*typespec*</span></span>  
 <span data-ttu-id="346ed-107">Ein gültiger Datentyp.</span><span class="sxs-lookup"><span data-stu-id="346ed-107">Is a valid data type.</span></span> <span data-ttu-id="346ed-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="346ed-108">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="346ed-109">Ergebnistypen</span><span class="sxs-lookup"><span data-stu-id="346ed-109">Result Types</span></span>  
 <span data-ttu-id="346ed-110">Ein beliebiger gültiger Datentyp mit einem NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="346ed-110">Any valid data type with a null value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="346ed-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="346ed-111">Remarks</span></span>  
 <span data-ttu-id="346ed-112">NULL gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.</span><span class="sxs-lookup"><span data-stu-id="346ed-112">NULL returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="346ed-113">Parameter sind erforderlich, um einen NULL-Wert für bestimmte Datentypen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="346ed-113">Parameters are required to request a null value for some data types.</span></span> <span data-ttu-id="346ed-114">In der folgenden Tabelle sind diese Datentypen und die zugehörigen Parameter aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="346ed-114">The following table lists these data types and their parameters.</span></span>  
  
|<span data-ttu-id="346ed-115">Datentyp</span><span class="sxs-lookup"><span data-stu-id="346ed-115">Data type</span></span>|<span data-ttu-id="346ed-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="346ed-116">Parameter</span></span>|<span data-ttu-id="346ed-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="346ed-117">Example</span></span>|  
|---------------|---------------|-------------|  
|<span data-ttu-id="346ed-118">DT_STR</span><span class="sxs-lookup"><span data-stu-id="346ed-118">DT_STR</span></span>|<span data-ttu-id="346ed-119">*charcount*</span><span class="sxs-lookup"><span data-stu-id="346ed-119">*charcount*</span></span><br /><br /> <span data-ttu-id="346ed-120">*codepage*</span><span class="sxs-lookup"><span data-stu-id="346ed-120">*codepage*</span></span>|<span data-ttu-id="346ed-121">(DT_STR,30,1252) wandelt 30 Zeichen mithilfe der 1252-Codepage in den DT_STR-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="346ed-121">(DT_STR,30,1252) casts 30 characters to the DT_STR data type using the 1252 code page.</span></span>|  
|<span data-ttu-id="346ed-122">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="346ed-122">DT_WSTR</span></span>|<span data-ttu-id="346ed-123">*charcount*</span><span class="sxs-lookup"><span data-stu-id="346ed-123">*charcount*</span></span>|<span data-ttu-id="346ed-124">(DT_WSTR,20) wandelt 20 Zeichen in den DT_WSTR-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="346ed-124">(DT_WSTR,20) casts 20 characters to the DT_WSTR data type.</span></span>|  
|<span data-ttu-id="346ed-125">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="346ed-125">DT_BYTES</span></span>|<span data-ttu-id="346ed-126">*bytecount*</span><span class="sxs-lookup"><span data-stu-id="346ed-126">*bytecount*</span></span>|<span data-ttu-id="346ed-127">(DT_BYTES,50) wandelt 50 Bytes in den DT_BYTES-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="346ed-127">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|  
|<span data-ttu-id="346ed-128">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="346ed-128">DT_DECIMAL</span></span>|<span data-ttu-id="346ed-129">*scale*</span><span class="sxs-lookup"><span data-stu-id="346ed-129">*scale*</span></span>|<span data-ttu-id="346ed-130">(DT_DECIMAL,2) wandelt einen numerischen Wert mithilfe von 2 Dezimalstellen in den DT_DECIMAL-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="346ed-130">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|  
|<span data-ttu-id="346ed-131">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="346ed-131">DT_NUMERIC</span></span>|<span data-ttu-id="346ed-132">*precision*</span><span class="sxs-lookup"><span data-stu-id="346ed-132">*precision*</span></span><br /><br /> <span data-ttu-id="346ed-133">*scale*</span><span class="sxs-lookup"><span data-stu-id="346ed-133">*scale*</span></span>|<span data-ttu-id="346ed-134">(DT_NUMERIC,10,3) wandelt einen numerischen Wert mithilfe einer Genauigkeit von 10 und 3 Dezimalstellen in den DT_NUMERIC-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="346ed-134">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|  
|<span data-ttu-id="346ed-135">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="346ed-135">DT_TEXT</span></span>|<span data-ttu-id="346ed-136">*codepage*</span><span class="sxs-lookup"><span data-stu-id="346ed-136">*codepage*</span></span>|<span data-ttu-id="346ed-137">(DT_TEXT,1252) wandelt einen Wert mithilfe der 1252-Codepage in den DT_TEXT-Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="346ed-137">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|  
  
## <a name="expression-examples"></a><span data-ttu-id="346ed-138">Beispiele für Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="346ed-138">Expression Examples</span></span>  
 <span data-ttu-id="346ed-139">In diesen Beispielen wird der NULL-Wert der Datentypen zurückgegeben: DT_STR, DT_DATE und DT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="346ed-139">These examples return the null value of the data types: DT_STR, DT_DATE, and DT_BOOL.</span></span>  
  
```  
NULL(DT_STR,10,1252)  
NULL(DT_DATE)  
NULL(DT_BOOL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="346ed-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="346ed-140">See Also</span></span>  
 <span data-ttu-id="346ed-141">[ISNULL &#40;SSIS-Ausdruck&#41;](null-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="346ed-141">[ISNULL &#40;SSIS Expression&#41;](null-ssis-expression.md) </span></span>  
 [<span data-ttu-id="346ed-142">Funktionen &#40;SSIS-Ausdruck&#41;</span><span class="sxs-lookup"><span data-stu-id="346ed-142">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
