---
title: Problembehandlung bei Diagrammen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b931b50545ba2b8d7c4c06cc5c48d6415a05470a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717446"
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a><span data-ttu-id="85887-102">Problembehandlung bei Diagrammen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="85887-102">Troubleshoot Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="85887-103">Beim Arbeiten mit Diagrammen können diese Punkte hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="85887-103">These issues can be helpful when working with charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a><span data-ttu-id="85887-104">Warum zählt das Diagramm die Werte auf der Wertachse, statt sie zu addieren?</span><span class="sxs-lookup"><span data-stu-id="85887-104">Why does my chart count, not sum, the values on the value axis?</span></span>  
 <span data-ttu-id="85887-105">Die meisten Diagrammtypen erfordern numerische Werte an der Wertachse (normalerweise der y-Achse), damit sie ordnungsgemäß gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="85887-105">Most chart types require numeric values along the value axis, which is typically the y-axis, in order to draw correctly.</span></span> <span data-ttu-id="85887-106">Wenn der Datentyp des Wertfelds `String` lautet, kann das Diagramm keinen numerischen Wert anzeigen, selbst wenn sich in den Feldern Zahlen befinden.</span><span class="sxs-lookup"><span data-stu-id="85887-106">If the data type of your value field is `String`, the chart cannot display a numeric value, even if there are numerals in the fields.</span></span> <span data-ttu-id="85887-107">Stattdessen zeigt das Diagramm die Anzahl der Zeilen an, die in diesem Feld einen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="85887-107">Instead, the chart displays a count of the total number of rows that contain a value in that field.</span></span> <span data-ttu-id="85887-108">Zur Vermeidung dieses Verhaltens sollten Sie sicherstellen, dass die Felder, die Sie für Wertereihen verwenden, numerische Datentypen und keine Zeichenfolgen mit formatierten Zahlen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="85887-108">To avoid this behavior, make sure that the fields that you use for value series have numeric data types, as opposed to strings that contain formatted numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85887-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85887-109">See Also</span></span>  
 [<span data-ttu-id="85887-110">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="85887-110">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
