---
title: Ausblenden oder Löschen von Ebenen in einer abgeleiteten Hierarchie (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, hiding levels
- derived hierarchies, deleting levels
ms.assetid: e00582b9-9415-4b66-b4a7-9f590d83875f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 039b05633bcd1fdc69d226e565b3dc5211e9734f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619183"
---
# <a name="hide-or-delete-levels-in-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="1164e-102">Ausblenden oder Löschen von Ebenen in einer abgeleiteten Hierarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1164e-102">Hide or Delete Levels in a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="1164e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie eine Ebene in einer abgeleiteten Hierarchie ausblenden, wenn die Ebene zur Gruppierung benötigt wird, aber nicht angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1164e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hide a level in a derived hierarchy when you require the level for grouping but you do not need to show the level.</span></span> <span data-ttu-id="1164e-104">Löschen Sie eine Ebene, wenn Sie sie nicht zur Gruppierung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1164e-104">Delete a level when you do not want to use it for grouping.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1164e-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1164e-105">Prerequisites</span></span>  
 <span data-ttu-id="1164e-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="1164e-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="1164e-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1164e-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="1164e-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="1164e-108">You must be a model administrator.</span></span> <span data-ttu-id="1164e-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1164e-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-hide-or-delete-levels-in-a-derived-hierarchy"></a><span data-ttu-id="1164e-110">So löschen oder blenden Sie Ebenen in einer abgeleiteten Hierarchie aus</span><span class="sxs-lookup"><span data-stu-id="1164e-110">To hide or delete levels in a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="1164e-111">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1164e-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="1164e-112">Zeigen Sie auf der Seite **Modell Ansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **abgeleitete Hierarchien**.</span><span class="sxs-lookup"><span data-stu-id="1164e-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="1164e-113">Wählen Sie auf der Seite **Verwaltung abgeleiteter Hierarchien** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="1164e-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="1164e-114">Wählen Sie die Zeile der abgeleiteten Hierarchie aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="1164e-114">Select the row for the derived hierarchy you want to edit.</span></span>  
  
5.  <span data-ttu-id="1164e-115">Klicken Sie auf **ausgewählte abgeleitete Hierarchie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1164e-115">Click **Edit selected derived hierarchy**.</span></span>  
  
6.  <span data-ttu-id="1164e-116">Im Bereich **Aktuelle Ebenen** :</span><span class="sxs-lookup"><span data-stu-id="1164e-116">In the **Current Levels** pane:</span></span>  
  
    -   <span data-ttu-id="1164e-117">Um eine Ebene auszublenden, klicken Sie auf eine andere als die oberste oder unterste Ebene.</span><span class="sxs-lookup"><span data-stu-id="1164e-117">To hide a level, click a level other than the top or bottom.</span></span> <span data-ttu-id="1164e-118">Wählen Sie aus der Liste **Sichtbar** den Eintrag **Nein**aus.</span><span class="sxs-lookup"><span data-stu-id="1164e-118">From the **Visible** list, select **No**.</span></span> <span data-ttu-id="1164e-119">Klicken Sie dann auf **Ausgewähltes Hierarchieelement speichern**.</span><span class="sxs-lookup"><span data-stu-id="1164e-119">Then click **Save selected hierarchy item**.</span></span>  
  
    -   <span data-ttu-id="1164e-120">Um die oberste Ebene zu löschen, klicken Sie auf **Ausgewähltes Hierarchieelement löschen**.</span><span class="sxs-lookup"><span data-stu-id="1164e-120">To delete the top level, click **Delete selected hierarchy item**.</span></span> <span data-ttu-id="1164e-121">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1164e-121">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="1164e-122">Sie können nur die oberste Ebene löschen.</span><span class="sxs-lookup"><span data-stu-id="1164e-122">You can delete the top level only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1164e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1164e-123">See Also</span></span>  
 <span data-ttu-id="1164e-124">[Verschieben von Elementen innerhalb einer Hierarchie &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1164e-124">[Move Members within a Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="1164e-125">Abgeleitete Hierarchien &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1164e-125">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
