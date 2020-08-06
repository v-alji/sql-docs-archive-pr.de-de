---
title: Festlegen des Synchronisierungsbereichs (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6f4a11e6-6151-47be-a43f-e3dbf6c0e737
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3efbb7774d5116c9b3a18457291434f2a05aac7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608286"
---
# <a name="set-synchronization-scope-report-builder-and-ssrs"></a><span data-ttu-id="de109-102">Festlegen des Synchronisierungsbereichs (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="de109-102">Set Synchronization Scope (Report Builder and SSRS)</span></span>
  <span data-ttu-id="de109-103">Indikatoren übermitteln Datenwerte, indem sie Indikatorwerte innerhalb eines angegebenen Bereichs synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="de109-103">Indicators convey data values by synchronizing across the range of indicator values within a specified scope.</span></span> <span data-ttu-id="de109-104">Standardmäßig ist der Bereich der übergeordnete Container des Indikators, z. B. die Tabelle oder die Matrix mit dem Indikator.</span><span class="sxs-lookup"><span data-stu-id="de109-104">By default, the scope is the parent container of the indicator such as the table or matrix that contains the indicator.</span></span> <span data-ttu-id="de109-105">Sie können die Synchronisierung des Indikators abhängig vom Layout des Berichts ändern.</span><span class="sxs-lookup"><span data-stu-id="de109-105">You can change the synchronization of the indicator depending on the layout of your report.</span></span> <span data-ttu-id="de109-106">Wenn ein Datenbereich wie eine Tabelle z. B. über eine Zeilengruppe verfügt, können Sie die Gruppe als Indikatorbereich angeben.</span><span class="sxs-lookup"><span data-stu-id="de109-106">For example, if a data region such as a table has a row group, you can specify the group as the indicator scope.</span></span> <span data-ttu-id="de109-107">Der Indikator kann die Synchronisierung auch überspringen.</span><span class="sxs-lookup"><span data-stu-id="de109-107">The indicator can also omit synchronization.</span></span>  
  
 <span data-ttu-id="de109-108">Optionen wie Maßeinheiten können mithilfe von Ausdrücken festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="de109-108">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="de109-109">Weitere Informationen finden Sie unter [Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de109-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="de109-110">Allgemeine Informationen zum Verständnis und zum Festlegen von Bereichen in Berichten finden Sie unter [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Sammlungen (Berichts-Generator und SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="de109-110">For general information about understanding and setting scope within reports, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-synchronization-scope-of-an-indicator"></a><span data-ttu-id="de109-111">So ändern Sie den Synchronisierungsbereich eines Indikators</span><span class="sxs-lookup"><span data-stu-id="de109-111">To change the synchronization scope of an indicator</span></span>  
  
1.  <span data-ttu-id="de109-112">Klicken Sie mit der rechten Maustaste auf den Indikator, der geändert werden soll, und klicken Sie auf **Indikatoreigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="de109-112">Right click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="de109-113">Klicken Sie im linken Bereich auf **Wert und Status** .</span><span class="sxs-lookup"><span data-stu-id="de109-113">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="de109-114">Klicken Sie in der Liste **Synchronisierungsbereich** auf den Bereich, den Sie übernehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="de109-114">In the **Synchronization scope** list, click the scope that you want to apply.</span></span>  
  
     <span data-ttu-id="de109-115">Die Option **(Keine)** ist immer verfügbar. Mit ihr wird der Synchronisierungsbereich aus dem Indikator entfernt.</span><span class="sxs-lookup"><span data-stu-id="de109-115">The **(None)** option, which removes synchronization scope from the indicator, is always available.</span></span> <span data-ttu-id="de109-116">Andere Optionen hängen vom Layout des Berichts ab.</span><span class="sxs-lookup"><span data-stu-id="de109-116">Other options depend on the layout of your report.</span></span>  
  
     <span data-ttu-id="de109-117">Klicken Sie optional auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Bereich festlegt.</span><span class="sxs-lookup"><span data-stu-id="de109-117">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the scope.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de109-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de109-118">See Also</span></span>  
 [<span data-ttu-id="de109-119">Indikatoren &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="de109-119">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
