---
title: Definieren einer referenzierten Beziehung und Eigenschaften der referenzierten Beziehung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
author: minewiskan
ms.author: owend
ms.openlocfilehash: a84cf2ed95ab3660c5a6b3c039dc58351dc43264
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700382"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a><span data-ttu-id="8419e-102">Definieren einer Beziehung, auf die verwiesen wird, und deren Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8419e-102">Define a Referenced Relationship and Referenced Relationship Properties</span></span>
  <span data-ttu-id="8419e-103">Eine Bezugsdimensionsbeziehung wird im Cube-Designer auf der Registerkarte **Dimensionsverwendung** definiert.</span><span class="sxs-lookup"><span data-stu-id="8419e-103">A reference dimension relationship is defined on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="8419e-104">Die Bezugsdimensionsbeziehung wird definiert, indem Folgendes angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="8419e-104">The reference dimension relationship is defined by specifying the following:</span></span>  
  
-   <span data-ttu-id="8419e-105">Die Zwischendimension, mit der ein Join hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8419e-105">The intermediate dimension to which to join.</span></span> <span data-ttu-id="8419e-106">Hierbei kann es sich um eine reguläre Dimension oder eine andere Bezugsdimension handeln.</span><span class="sxs-lookup"><span data-stu-id="8419e-106">This can be a regular dimension or another reference dimension.</span></span>  
  
-   <span data-ttu-id="8419e-107">Ein Bezugsdimensionsattribut, das die niedrigste verfügbare Stufe für die Aggregation der Dimension im Hinblick auf die Measuregruppe definiert.</span><span class="sxs-lookup"><span data-stu-id="8419e-107">A reference dimension attribute that defines the lowest level that the dimension is available for aggregation with regard to the measure group.</span></span>  
  
-   <span data-ttu-id="8419e-108">Das (Fremdschlüssel-)Attribut in der Zwischendimension, das dem Bezugsdimensionsattribut entspricht.</span><span class="sxs-lookup"><span data-stu-id="8419e-108">The (foreign key) attribute in the intermediate dimension that corresponds to the reference dimension attribute.</span></span>  
  
 <span data-ttu-id="8419e-109">Beachten Sie, dass die Spalte, die die Bezugsdimension mit der Faktentabelle verknüpft und bei der es sich im Allgemeinen um das Schlüsselattribut in der Bezugsdimension handelt, auch als ein Attribut in der Zwischendimension definiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="8419e-109">Notice that the column that links the reference dimension to the fact table, which is generally the key attribute in the reference dimension, must also be defined as an attribute in the intermediate dimension.</span></span> <span data-ttu-id="8419e-110">Wenn Sie eine Kette von Bezugsdimensionen erstellen, beginnen Sie mit dem Erstellen der regulären Beziehung zwischen der ersten Dimension in der Kette und der Measuregruppe.</span><span class="sxs-lookup"><span data-stu-id="8419e-110">When you create a chain of reference dimensions, start by creating the regular relationship between the first dimension in the chain and the measure group.</span></span> <span data-ttu-id="8419e-111">Erstellen Sie anschließend jede weitere referenzierte Beziehung in der entsprechenden Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="8419e-111">Then create each additional referenced relationship in order.</span></span> <span data-ttu-id="8419e-112">Eine referenzierte Beziehung kann nur zu einer Dimension mit einer vorhandenen Beziehung zu der Measuregruppe erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8419e-112">A referenced relationship can only be made to a dimension that has an existing relationship to the measure group.</span></span>  
  
 <span data-ttu-id="8419e-113">Wenn Sie eine Bezugsdimensionsbeziehung erstellen, wird der Dimensionsattributlink standardmäßig materialisiert.</span><span class="sxs-lookup"><span data-stu-id="8419e-113">When you create a reference dimension relationship, the dimension attribute link is materialized by default.</span></span> <span data-ttu-id="8419e-114">Durch das Materialisieren eines Dimensionsattributlinks wird bewirkt, dass der Wert des Links zwischen der Faktentabelle und der Bezugsdimension für jede Zeile während der Verarbeitung in der MOLAP-Struktur für die Dimension materialisiert, d. h. gespeichert, wird.</span><span class="sxs-lookup"><span data-stu-id="8419e-114">Materializing a dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the MOLAP structure for the dimension during processing.</span></span> <span data-ttu-id="8419e-115">Dies hat eine geringe Auswirkung auf die Verarbeitungsleistung und die Speicheranforderungen, verbessert jedoch die Abfrageleistung.</span><span class="sxs-lookup"><span data-stu-id="8419e-115">This will have a minor effect on processing performance and storage requirements, but will improve query performance.</span></span>  
  
 <span data-ttu-id="8419e-116">In einer Bezugsdimension wird die Granularität durch Identifizieren des Attributs angegeben, das die Beziehung zwischen einer Bezugsdimension und der Measuregruppe, die der Haupttabelle der Dimension entspricht, definiert.</span><span class="sxs-lookup"><span data-stu-id="8419e-116">In a reference dimension, granularity is specified by identifying the attribute that defines the relationship between a reference dimension and the measure group corresponding to the main table of the dimension.</span></span> <span data-ttu-id="8419e-117">Wenn mehrere Bezugsdimensionen miteinander verkettet werden, definieren die Verweise die Beziehung von der äußersten Dimension bis zur Measuregruppe.</span><span class="sxs-lookup"><span data-stu-id="8419e-117">When multiple reference dimensions are chained together, the references define the relationship from the outermost dimension to the measure group.</span></span>  
  
  
