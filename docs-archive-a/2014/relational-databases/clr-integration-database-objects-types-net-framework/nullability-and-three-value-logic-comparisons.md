---
title: NULL-Zulässigkeit und dreiwertige Logik Vergleiche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- precision [CLR integration]
- overflow detections [CLR integration]
- null values [CLR integration]
- three-value logic comparisons [CLR integration]
- data types [CLR integration]
- SqlBoolean data type
ms.assetid: 13da4c7f-1010-4b2d-a63c-c69b6bfd96f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b8000c1c28d5a1d3d129b6e8d01c4ab2fbbbc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725953"
---
# <a name="nullability-and-three-value-logic-comparisons"></a><span data-ttu-id="ced43-102">Zulässigkeit von NULL-Werten und Vergleiche mit dreiwertiger Logik</span><span class="sxs-lookup"><span data-stu-id="ced43-102">Nullability and Three-Value Logic Comparisons</span></span>
  <span data-ttu-id="ced43-103">Wenn Sie mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen vertraut sind, finden Sie eine ähnliche Semantik und Genauigkeit im `System.Data.SqlTypes`-Namespace in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ced43-103">If you are familiar with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, you will find similar semantics and precision in the `System.Data.SqlTypes` namespace in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ced43-104">Es gibt jedoch einige Unterschiede, und die wichtigsten dieser Unterschiede werden in diesem Thema behandelt.</span><span class="sxs-lookup"><span data-stu-id="ced43-104">There are some differences, however, and this topic covers the most important of these differences.</span></span>  
  
## <a name="null-values"></a><span data-ttu-id="ced43-105">NULL-Werte</span><span class="sxs-lookup"><span data-stu-id="ced43-105">NULL Values</span></span>  
 <span data-ttu-id="ced43-106">Ein Hauptunterschied zwischen den systemeigenen CLR (Common Language Runtime)-Datentypen und den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentypen besteht darin, dass Erstere keine NULL-Werte zulassen, Letztere dagegen die uneingeschränkte NULL-Semantik bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ced43-106">A primary difference between native common language runtime (CLR) data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types is that the former do not allow for NULL values, while the latter provide full NULL semantics.</span></span>  
  
 <span data-ttu-id="ced43-107">Vergleiche werden durch NULL-Werte beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="ced43-107">Comparisons are affected by NULL values.</span></span> <span data-ttu-id="ced43-108">Wenn die beiden Werte x und y verglichen werden und x oder y NULL ist, dann ergeben einige logische Vergleiche den Wert UNKNOWN statt true oder false.</span><span class="sxs-lookup"><span data-stu-id="ced43-108">When comparing two values x and y, if either x or y is NULL, then some logical comparisons evaluate to an UNKNOWN value rather than true or false.</span></span>  
  
## <a name="sqlboolean-data-type"></a><span data-ttu-id="ced43-109">SqlBoolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="ced43-109">SqlBoolean Data Type</span></span>  
 <span data-ttu-id="ced43-110">Zur Darstellung dieser dreiwertigen Logik wurde im `System.Data.SqlTypes`-Namespace der `SqlBoolean`-Typ eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ced43-110">The `System.Data.SqlTypes` namespace introduces a `SqlBoolean` type to represent this 3-value logic.</span></span> <span data-ttu-id="ced43-111">Vergleiche zwischen beliebigen Werten des Typs `SqlTypes` ergeben einen Wert des `SqlBoolean`-Typs.</span><span class="sxs-lookup"><span data-stu-id="ced43-111">Comparisons between any `SqlTypes` return a `SqlBoolean` value type.</span></span> <span data-ttu-id="ced43-112">Der UNKNOWN-Wert wird durch den NULL-Wert des `SqlBoolean`-Typs dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ced43-112">The UNKNOWN value is represented by the null value of the `SqlBoolean` type.</span></span> <span data-ttu-id="ced43-113">Die Eigenschaften `IsTrue`, `IsFalse` und `IsNull` dienen zur Überprüfung des Werts eines `SqlBoolean`-Typs.</span><span class="sxs-lookup"><span data-stu-id="ced43-113">The properties `IsTrue`, `IsFalse`, and `IsNull` are provided to check the value of a `SqlBoolean` type.</span></span>  
  
## <a name="operations-functions-and-null-values"></a><span data-ttu-id="ced43-114">Vorgänge, Funktionen und NULL-Werte</span><span class="sxs-lookup"><span data-stu-id="ced43-114">Operations, Functions, and NULL Values</span></span>  
 <span data-ttu-id="ced43-115">Alle arithmetischen Operatoren (+,-, \* ,/,%), bitweise Operatoren (~, & und |) und die meisten Funktionen geben NULL zurück, wenn einer der Operanden oder Argumente von `SqlTypes` NULL ist.</span><span class="sxs-lookup"><span data-stu-id="ced43-115">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, and |), and most functions return NULL if any of the operands or arguments of `SqlTypes` are NULL.</span></span> <span data-ttu-id="ced43-116">Die `IsNull`-Eigenschaft gibt stets den Wert true oder false zurück.</span><span class="sxs-lookup"><span data-stu-id="ced43-116">The `IsNull` property always returns a true or false value.</span></span>  
  
## <a name="precision"></a><span data-ttu-id="ced43-117">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="ced43-117">Precision</span></span>  
 <span data-ttu-id="ced43-118">Für Dezimaldatentypen in der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -CLR gelten andere Maximalwerte als für die numerischen Datentypen und Dezimaldatentypen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ced43-118">Decimal data types in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR have different maximum values than those of the numeric and decimal data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ced43-119">Außerdem wird bei den Dezimaldatentypen der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -CLR die maximale Genauigkeit angenommen.</span><span class="sxs-lookup"><span data-stu-id="ced43-119">In addition, in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR decimal data types assume the maximum precision.</span></span> <span data-ttu-id="ced43-120">In der CLR für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]bietet `SqlDecimal` jedoch die gleiche maximale Genauigkeit und Dezimalstellenanzahl sowie die gleiche Semantik wie die Dezimaldatentypen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ced43-120">In the CLR for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], however, `SqlDecimal` provides the same maximum precision and scale, and the same semantics as the decimal data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="overflow-detection"></a><span data-ttu-id="ced43-121">Überlauferkennung</span><span class="sxs-lookup"><span data-stu-id="ced43-121">Overflow Detection</span></span>  
 <span data-ttu-id="ced43-122">In der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] -CLR wird durch die Addition von zwei sehr großen Zahlen möglicherweise keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ced43-122">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] CLR, the addition of two very large numbers may not throw an exception.</span></span> <span data-ttu-id="ced43-123">Wenn kein Prüfvorgang verwendet wurde, dann wird das zurückgegebene Ergebnis möglicherweise als negative Ganzzahl dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ced43-123">Instead, if no check operator has been used, the returned result may "wrap around" as a negative integer.</span></span> <span data-ttu-id="ced43-124">In `System.Data.SqlTypes` werden Ausnahmen für alle Überlauf- und Unterlauffehler sowie Fehler aufgrund einer Division durch 0 ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ced43-124">In `System.Data.SqlTypes`, exceptions are thrown for all overflow and underflow errors, and divide-by-zero errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced43-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ced43-125">See Also</span></span>  
 [<span data-ttu-id="ced43-126">SQL Server-Datentypen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ced43-126">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
