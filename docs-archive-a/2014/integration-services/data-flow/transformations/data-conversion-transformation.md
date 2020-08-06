---
title: Transformation für Datenkonvertierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57b1f70c070cdf81dc0bc899ed365d048db26cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608773"
---
# <a name="data-conversion-transformation"></a><span data-ttu-id="f335c-102">Transformation für Datenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="f335c-102">Data Conversion Transformation</span></span>
  <span data-ttu-id="f335c-103">Die Transformation für Datenkonvertierung konvertiert die Daten in einer Eingabespalte in einen anderen Datentyp und kopiert sie dann in eine neue Ausgabespalte.</span><span class="sxs-lookup"><span data-stu-id="f335c-103">The Data Conversion transformation converts the data in an input column to a different data type and then copies it to a new output column.</span></span> <span data-ttu-id="f335c-104">Beispielsweise kann ein Paket Daten aus mehreren Quellen extrahieren und anschließend mithilfe dieser Transformation Spalten in den für den Zieldatenspeicher erforderlichen Datentyp konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f335c-104">For example, a package can extract data from multiple sources, and then use this transformation to convert columns to the data type required by the destination data store.</span></span> <span data-ttu-id="f335c-105">Für eine einzelne Eingabespalte können mehrere Konvertierungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f335c-105">You can apply multiple conversions to a single input column.</span></span>  
  
 <span data-ttu-id="f335c-106">Mithilfe dieser Transformation kann ein Paket die folgenden Datenkonvertierungstypen ausführen:</span><span class="sxs-lookup"><span data-stu-id="f335c-106">Using this transformation, a package can perform the following types of data conversions:</span></span>  
  
-   <span data-ttu-id="f335c-107">Ändern des Datentyps.</span><span class="sxs-lookup"><span data-stu-id="f335c-107">Change the data type.</span></span> <span data-ttu-id="f335c-108">Weitere Informationen finden Sie unter [Integration Services Datentypen](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f335c-108">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f335c-109">Falls Sie Daten in einen date- oder datetime-Datentyp konvertieren, weist das Datum in der Ausgabespalte das ISO-Format auf, auch wenn für das Gebietsschema ein anderes Format angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f335c-109">If you are converting data to a date or a datetime data type, the date in the output column is in the ISO format, although the locale preference may specify a different format.</span></span>  
  
-   <span data-ttu-id="f335c-110">Festlegen der Spaltenlänge der Zeichenfolgendaten sowie der Genauigkeit und der Dezimalstellenanzahl für numerische Daten.</span><span class="sxs-lookup"><span data-stu-id="f335c-110">Set the column length of string data and the precision and scale on numeric data.</span></span> <span data-ttu-id="f335c-111">Weitere Informationen finden Sie unter [Genauigkeit, Dezimalstellen und Länge &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f335c-111">For more information, see [Precision, Scale, and Length &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span></span>  
  
-   <span data-ttu-id="f335c-112">Eingeben einer Codepage.</span><span class="sxs-lookup"><span data-stu-id="f335c-112">Specify a code page.</span></span> <span data-ttu-id="f335c-113">Weitere Informationen finden Sie unter [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="f335c-113">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f335c-114">Beim Kopieren zwischen Spalten mit einem Zeichenfolgen-Datentyp müssen die beiden Spalten die gleiche Codepage verwenden.</span><span class="sxs-lookup"><span data-stu-id="f335c-114">When copying between columns with a string data type, the two columns must use the same code page.</span></span>  
  
 <span data-ttu-id="f335c-115">Falls die Länge einer Ausgabespalte von Zeichenfolgendaten kürzer als die Länge der entsprechenden Eingabespalte ist, werden die Ausgabedaten abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="f335c-115">If the length of an output column of string data is shorter than the length of its corresponding input column, the output data is truncated.</span></span> <span data-ttu-id="f335c-116">Weitere Informationen finden Sie unter [Fehlerbehandlung in Daten](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="f335c-116">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="f335c-117">Diese Transformation weist eine Eingabe, eine Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="f335c-117">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f335c-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f335c-118">Related Tasks</span></span>  
 <span data-ttu-id="f335c-119">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="f335c-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="f335c-120">Weitere Informationen zum Verwenden der Transformation für Datenkonvertierung im SSIS-Designer finden Sie unter [Konvertieren von Daten in einen anderen Datentyp mithilfe der Transformation für Datenkonvertierung](data-conversion-transformation.md) und [Transformations-Editor für Datenkonvertierung](../../data-conversion-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f335c-120">For information about using the Data Conversion Transformation in the SSIS Designer, see [Convert Data to a Different Data Type by Using the Data Conversion Transformation](data-conversion-transformation.md) and [Data Conversion Transformation Editor](../../data-conversion-transformation-editor.md).</span></span> <span data-ttu-id="f335c-121">Weitere Informationen zum programmgesteuerten Festlegen der Eigenschaften dieser Transformation finden Sie unter [Allgemeine Eigenschaften](../../common-properties.md) und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f335c-121">For information about setting properties of this transformation programmatically, see [Common Properties](../../common-properties.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f335c-122">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f335c-122">Related Content</span></span>  
 <span data-ttu-id="f335c-123">Blogeintrag, [Leistungsvergleich zwischen Datentypkonvertierungstechniken in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), auf blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f335c-123">Blog entry, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f335c-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f335c-124">See Also</span></span>  
 <span data-ttu-id="f335c-125">[Schnelle Analyse](../../fast-parse.md) </span><span class="sxs-lookup"><span data-stu-id="f335c-125">[Fast Parse](../../fast-parse.md) </span></span>  
 <span data-ttu-id="f335c-126">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="f335c-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="f335c-127">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="f335c-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
