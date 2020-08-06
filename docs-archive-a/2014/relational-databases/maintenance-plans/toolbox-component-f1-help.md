---
title: Toolboxkomponente (F1-Hilfe) |Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Toolbox [SQL Server Management Studio]
ms.assetid: d8401ecc-7d47-49df-aae5-22a148eeb23f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f3b4c94ef1c4690af2a333fcdbdef88b475219e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622637"
---
# <a name="toolbox-component-f1-help"></a><span data-ttu-id="1b3f1-102">Toolboxkomponente (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="1b3f1-102">Toolbox Component F1 Help</span></span>

<span data-ttu-id="1b3f1-103">In der **Toolbox** wird eine Vielzahl von Elementen angezeigt, die in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Projekten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-103">**Toolbox** displays a variety of items for use in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects.</span></span> <span data-ttu-id="1b3f1-104">Die **Toolbox** können Sie über das Menü **Ansicht** öffnen. Bei Bedarf können Sie das Fenster der Toolbox verankern.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-104">You can open the **Toolbox** from the **View** menu, and dock this window as you wish.</span></span> <span data-ttu-id="1b3f1-105">Eine verankerte **Toolbox** kann in geöffnetem Zustand fixiert werden oder für die Zeit, in der sie nicht verwendet wird, auf **Automatisch ausblenden** gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-105">While docked, the **Toolbox** can either be pinned open or set to **Auto Hide** when not in use.</span></span>  
  
<span data-ttu-id="1b3f1-106">**Toolbox** Symbole können per Drag und Drop abgelegt, kopiert und in Code-Editoren eingefügt werden oder auf Oberflächen in der Entwurfs Ansicht eingefügt werden [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b3f1-106">**Toolbox** icons can be dragged and dropped or copied and pasted into code editors or onto design view surfaces within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="using-the-toolbox"></a><span data-ttu-id="1b3f1-107">Verwenden der Toolbox</span><span class="sxs-lookup"><span data-stu-id="1b3f1-107">Using the Toolbox</span></span>  
 <span data-ttu-id="1b3f1-108">Die Toolbox ist eine verschiebbare Strukturansicht, die in ihrem Verhalten [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer ähnelt, aber nicht über ein Raster oder Verbindungslinien verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-108">The Toolbox is a sliding tree control that behaves much like [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer, but without grid or connection lines.</span></span> <span data-ttu-id="1b3f1-109">Mehrere Segmente der **Toolbox** (als „Registerkarten“ bezeichnet) können gleichzeitig erweitert werden, und die gesamte Struktur kann innerhalb des Fensters **Toolbox** per Bildlauf verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-109">Multiple segments of the **Toolbox** (called "tabs") can be expanded simultaneously, and the entire tree scrolls inside the **Toolbox** window.</span></span> <span data-ttu-id="1b3f1-110">Um eine der Registerkarten der **Toolbox**zu erweitern, klicken Sie auf das Pluszeichen ( **+** ) neben ihrem Namen.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-110">To expand any tab of the **Toolbox**, click the plus (**+**) sign next to its name.</span></span> <span data-ttu-id="1b3f1-111">Um eine erweiterte Registerkarte zu reduzieren, klicken Sie auf das Minuszeichen ( **-** ) neben ihrem Namen.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-111">To collapse an expanded tab, click the minus (**-**) sign next to its name.</span></span>  
  
 <span data-ttu-id="1b3f1-112">Jedes Mal, wenn Sie in einen Editor oder Designer zurückkehren, führt die **Toolbox** automatisch einen Bildlauf zur zuletzt verwendeten Registerkarte und zum zuletzt ausgewählten Element durch.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-112">Each time you return to an editor or designer, the **Toolbox** automatically scrolls to the most recent tab and item selected.</span></span> <span data-ttu-id="1b3f1-113">Wenn Sie den Fokus auf einen anderen Editor oder Designer verlagern, wandert die aktuelle Auswahl in der **Toolbox** mit Ihnen mit.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-113">As you shift focus to a different editor or designer, the current selection in the **Toolbox** shifts with you.</span></span>  
  
## <a name="customizing-the-toolbox"></a><span data-ttu-id="1b3f1-114">Anpassen der Toolbox</span><span class="sxs-lookup"><span data-stu-id="1b3f1-114">Customizing the Toolbox</span></span>  
 <span data-ttu-id="1b3f1-115">Die Elemente innerhalb einer Registerkarte lassen sich problemlos neu anordnen. Auch das Hinzufügen benutzerdefinierter Registerkarten und Elemente zur **Toolbox**ist einfach.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-115">It is easy to rearrange items within a tab, and to add custom tabs and items to the **Toolbox**.</span></span>  
  
 <span data-ttu-id="1b3f1-116">Um der **Toolbox** Elemente hinzuzufügen bzw. diese von ihr zu entfernen, klicken Sie im Menü **Extras** auf **Toolboxelemente auswählen**.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-116">To add or remove **Toolbox** items, on the **Tools** menu, click **Choose Toolbox Items**.</span></span> <span data-ttu-id="1b3f1-117">Nur **Wartungstasks** können in der **Toolbox** als Symbole verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-117">Only **Maintenance Tasks** can be made available as **Toolbox** icons.</span></span> <span data-ttu-id="1b3f1-118">Es sind nicht immer alle Komponenten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-118">All components are not always available.</span></span> <span data-ttu-id="1b3f1-119">Wartungstasks beispielsweise sind nur beim Erstellen eines Wartungsplans verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b3f1-119">For instance, maintenance tasks are only available when creating a maintenance plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3f1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b3f1-120">See Also</span></span>  
 <span data-ttu-id="1b3f1-121">[Verwenden der Toolbox](../../ssms/use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="1b3f1-121">[Use the Toolbox](../../ssms/use-the-toolbox.md) </span></span>  
 [<span data-ttu-id="1b3f1-122">Auswählen von Toolboxelementen &#40;Seite „Wartungstasks“&#41;</span><span class="sxs-lookup"><span data-stu-id="1b3f1-122">Choose Toolbox Items &#40;Maintenance Tasks Page&#41;</span></span>](../../ssms/menu-help/choose-toolbox-items-maintenance-tasks-page.md)  
