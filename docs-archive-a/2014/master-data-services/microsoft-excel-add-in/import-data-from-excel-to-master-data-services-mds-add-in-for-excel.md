---
title: Veröffentlichen von Daten aus Excel in MDS (MDS-Add-in für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 597a954760816d8938628974998fe8f6daad1af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621034"
---
# <a name="publish-data-from-excel-to-mds-mds-add-in-for-excel"></a><span data-ttu-id="7e5d5-102">Veröffentlichen von Daten von Excel nach MDS (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="7e5d5-102">Publish Data from Excel to MDS (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="7e5d5-103">Veröffentlichen Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]Daten an das MDS-Repository, wenn Sie mit der Arbeit in Excel fertig sind und die Änderungen speichern möchten, damit andere Benutzer Zugriff auf sie haben.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you are finished working in Excel and want to save your changes so other users have access to them.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="7e5d5-104">Wenn Sie Änderungen veröffentlichen, werden die Kommentare zu von MDS verwalteten Zellen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-104">When you publish changes, comments on MDS-managed cells are deleted.</span></span>  
> -   <span data-ttu-id="7e5d5-105">Eine Formel wird in einer von MDS verwalteten Zelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-105">A formula is not supported in an MDS-managed cell.</span></span> <span data-ttu-id="7e5d5-106">Eine Formel in einer von MDS verwalteten Zelle wird als Textwert behandelt.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-106">A formula in an MDS-managed cell is handled as a text value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7e5d5-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7e5d5-107">Prerequisites</span></span>  
 <span data-ttu-id="7e5d5-108">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="7e5d5-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="7e5d5-109">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="7e5d5-110">Das aktive Arbeitsblatt muss von MDS verwaltete Daten enthalten, und Sie müssen Änderungen oder Hinzufügungen zu den von MDS verwalteten Daten vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-110">The active worksheet must contain MDS-managed data and you must have made changes or additions to the MDS-managed data.</span></span>  
  
-   <span data-ttu-id="7e5d5-111">Wenn Sie Elemente hinzufügen, müssen Sie keinen **Code** -Wert angeben, wenn Codes für die Entität automatisch generiert werden.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-111">If you are adding members, you do not have to specify a **Code** value if codes for the entity are being automatically generated.</span></span> <span data-ttu-id="7e5d5-112">Weitere Informationen finden Sie unter [automatische Code Erstellung &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7e5d5-112">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span></span>  
  
### <a name="to-publish-data-to-the-mds-repository"></a><span data-ttu-id="7e5d5-113">So veröffentlichen Sie Daten im MDS-Repository</span><span class="sxs-lookup"><span data-stu-id="7e5d5-113">To publish data to the MDS repository</span></span>  
  
1.  <span data-ttu-id="7e5d5-114">Klicken Sie in der Gruppe **Veröffentlichen und Validieren** auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-114">In the **Publish and Validate** group, click **Publish**.</span></span>  
  
2.  <span data-ttu-id="7e5d5-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-115">Optional.</span></span> <span data-ttu-id="7e5d5-116">Wenn das Dialogfeld **Veröffentlichen und mit Anmerkung versehen** angezeigt wird, wählen Sie die Freigabe der gleichen Anmerkung (Kommentar) für alle Updates oder die Kommentierung jeder Änderung einzeln.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-116">If the **Publish and Annotate** dialog box is displayed, choose to share the same annotation (comment) for all updates, or to annotate each change individually.</span></span>  
  
3.  <span data-ttu-id="7e5d5-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-117">Optional.</span></span> <span data-ttu-id="7e5d5-118">Aktivieren Sie das Kontrollkästchen **Dieses Dialogfeld nicht mehr anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="7e5d5-118">Select the **Do not show this dialog box again** check box.</span></span> <span data-ttu-id="7e5d5-119">Sie können das Dialogfeld zukünftig immer anzeigen, indem Sie **Einstellungen** auswählen und das Kontrollkästchen **Dialogfeld 'Veröffentlichen und mit Anmerkung versehen' beim Veröffentlichen anzeigen** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-119">You can always show the dialog box in the future by choosing **Settings** and selecting the **Show Publish and Annotate dialog box when publishing** check box.</span></span>  
  
4.  <span data-ttu-id="7e5d5-120">Klicken Sie auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-120">Click **Publish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e5d5-121">Wenn Sie dem Arbeitsblatt neue Elemente (Zeilen) hinzufügen, sie aber nicht erfolgreich im MDS-Repository veröffentlichen können, verfügen Sie möglicherweise nicht für alle Attribute im Arbeitsblatt über die Berechtigung **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="7e5d5-121">If you are adding new members (rows) to your worksheet and you cannot successfully publish them to the MDS repository, you may not have **Update** permission to all of the attributes in the worksheet.</span></span> <span data-ttu-id="7e5d5-122">Klicken Sie auf der Registerkarte **Überprüfen** in der Gruppe **Änderungen** auf **Blattschutz aufheben** , und versuchen Sie, erneut zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="7e5d5-122">On the **Review** tab, in the **Changes** group, click **Unprotect Sheet** and try to publish again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7e5d5-123">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7e5d5-123">Next Steps</span></span>  
 [<span data-ttu-id="7e5d5-124">Anwenden von Geschäftsregeln &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7e5d5-124">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="7e5d5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e5d5-125">See Also</span></span>  
 <span data-ttu-id="7e5d5-126">[Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7e5d5-126">[Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="7e5d5-127">Überprüfen von Daten &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7e5d5-127">Validating Data &#40;MDS Add-in for Excel&#41;</span></span>](validating-data-mds-add-in-for-excel.md)  
  
  
