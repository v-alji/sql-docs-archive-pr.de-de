---
title: 'Die folgenden Funktionen werden von Excel Services nicht unterstützt und möglicherweise nur teilweise angezeigt: Kommentare, Formen oder andere Objekte | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ade92e15-dfbf-496b-9378-a00bd83ba750
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67c2989ab89f242fdce2ca64f3c2f361e17d49ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700316"
---
# <a name="the-following-features-are-not-supported-by-excel-services-and-may-not-display-or-may-display-only-partially-comments-shapes-or-other-objects"></a><span data-ttu-id="5fd5b-102">Die folgenden Funktionen werden von Excel Services nicht unterstützt und möglicherweise nur teilweise oder überhaupt nicht angezeigt: Kommentare, Formen oder andere Objekte</span><span class="sxs-lookup"><span data-stu-id="5fd5b-102">The following features are not supported by Excel Services and may not display or may display only partially: Comments, Shapes, or other objects</span></span>
  <span data-ttu-id="5fd5b-103">Dieser Fehler tritt auf, wenn Sie einer PowerPivot-Arbeitsmappe Slicer aus einer PowerPivot-Feldliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-103">This error occurs when you add Slicers to a PowerPivot workbook from a PowerPivot Field List.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5fd5b-104">Details</span><span class="sxs-lookup"><span data-stu-id="5fd5b-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fd5b-105">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="5fd5b-105">Applies to</span></span>|<span data-ttu-id="5fd5b-106">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="5fd5b-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="5fd5b-107">Produktversion</span><span class="sxs-lookup"><span data-stu-id="5fd5b-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="5fd5b-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd5b-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="5fd5b-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="5fd5b-109">Cause</span></span>|<span data-ttu-id="5fd5b-110">Das Shape-Objekt, mit dem die Positionierung und Formatierung von Slicern gesteuert wird, die einer Arbeitsmappe aus der PowerPivot-Feldliste hinzugefügt wurden, kann von Excel Web Access nicht gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-110">Excel Web Access cannot render the Shape object used to control positioning and formatting of Slicers added to a workbook from the PowerPivot Field List.</span></span>|  
|<span data-ttu-id="5fd5b-111">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5fd5b-111">Message Text</span></span>|<span data-ttu-id="5fd5b-112">Die folgenden Funktionen werden von Excel Services nicht unterstützt und möglicherweise nur teilweise oder überhaupt nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5fd5b-112">The following features are not supported by Excel Services and may not display or may display only partially:</span></span><br /><br /> <span data-ttu-id="5fd5b-113">Kommentare, Formen oder andere Objekte</span><span class="sxs-lookup"><span data-stu-id="5fd5b-113">Comments, Shapes, or other objects</span></span><br /><br /> <span data-ttu-id="5fd5b-114">Einige Funktionen z. B. externe Datenabfragen, zeigen zwischengespeicherte Daten an, die nur in Microsoft Excel aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-114">Some features, such as external data queries, display cached data which can only be refreshed in Microsoft Excel.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5fd5b-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5fd5b-115">Explanation</span></span>  
 <span data-ttu-id="5fd5b-116">Excel Webzugriff zeigt diesen Fehler an, wenn Sie eine Power Pivot-Arbeitsmappe in einem Browser öffnen und auf die Schaltfläche **Details** für die Meldung, **nicht unterstützte Funktionen, die diese Arbeitsmappe möglicherweise nicht wie vorgesehen anzeigt**.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-116">Excel Web Access shows this error when you open a PowerPivot workbook in a browser and you click the **Details** button for the message, **Unsupported Features This workbook may not display as intended**.</span></span>  
  
 <span data-ttu-id="5fd5b-117">Dieser Fehler tritt auf, weil die PowerPivot-Arbeitsmappe Slicer enthält, deren Layout über ein ausgeblendetes Shape-Objekt in Excel gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-117">This error occurs because the PowerPivot workbook contains Slicers whose layout is controlled by a hidden Shape object in Excel.</span></span> <span data-ttu-id="5fd5b-118">Das Shape-Objekt steuert die Formatierung und Positionierung der Slicer in horizontalen und vertikalen Platzierungen.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-118">The Shape object controls the formatting and positioning of the Slicers in horizontal and vertical placements.</span></span>  
  
 <span data-ttu-id="5fd5b-119">Shape-Objekte können von Excel Services nicht gerendert werden, dies ist jedoch kein Problem, weil es sich um ein ausgeblendetes Objekt handelt.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-119">Excel Services cannot render a Shape object, but because the object is hidden, the fact that it does not render is not an issue.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5fd5b-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5fd5b-120">User Action</span></span>  
 <span data-ttu-id="5fd5b-121">Dieser Fehler kann ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-121">This error can be ignored.</span></span> <span data-ttu-id="5fd5b-122">Klicken Sie auf **OK** , um die Fehlermeldung zu schließen und die Verwendung von Arbeitsmappe und Slicern ohne Probleme fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5fd5b-122">Click **OK** to close the error message and proceed to use the workbook and Slicers with no problem.</span></span>  
  
  
