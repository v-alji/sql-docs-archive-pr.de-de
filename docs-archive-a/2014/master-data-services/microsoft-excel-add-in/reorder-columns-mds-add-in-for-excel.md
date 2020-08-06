---
title: Neuanordnen von Spalten (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ac00462e-c0f7-4b8d-86f2-d9eda2598a15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f0c47a631ffe699936a8d45bcc4e47e0b6f0a985
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698373"
---
# <a name="reorder-columns-mds-add-in-for-excel"></a><span data-ttu-id="5613b-102">Neuanordnen von Spalten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="5613b-102">Reorder Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5613b-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]können Sie Spalten durch das Filtern der Liste vor dem Laden neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="5613b-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you can reorder columns by filtering the list before loading.</span></span>  
  
 <span data-ttu-id="5613b-104">Wenn Sie Attribute im Dialogfeld **Filter** neu anordnen, werden die Daten mit der neuen Reihenfolge in Excel geladen.</span><span class="sxs-lookup"><span data-stu-id="5613b-104">When you reorder attributes in the **Filter** dialog box, the data is loaded into Excel with the new order.</span></span> <span data-ttu-id="5613b-105">Wenn Sie jedoch die Attributdaten das nächste Mal filtern, wird die Reihenfolge des ursprünglichen Entwurfs wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="5613b-105">However, the next time that you filter the attribute data, the order will revert to the order in the original design.</span></span> <span data-ttu-id="5613b-106">Um die Reihenfolge permanent zu ändern, sollte ein Administrator die Reihenfolge im Bereich **Systemverwaltung** von Master Data Manager ändern.</span><span class="sxs-lookup"><span data-stu-id="5613b-106">To change the order permanently, an administrator should change the order in the **System Administration** area of Master Data Manager.</span></span> <span data-ttu-id="5613b-107">Weitere Informationen finden Sie unter [Change the Order of Attributes](../change-the-order-of-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="5613b-107">For more information, see [Change the Order of Attributes](../change-the-order-of-attributes.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5613b-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5613b-108">Prerequisites</span></span>  
 <span data-ttu-id="5613b-109">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="5613b-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5613b-110">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="5613b-110">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-reorder-mds-managed-columns"></a><span data-ttu-id="5613b-111">So ordnen Sie von MDS verwaltete Spalten neu an</span><span class="sxs-lookup"><span data-stu-id="5613b-111">To reorder MDS-managed columns</span></span>  
  
1.  <span data-ttu-id="5613b-112">Öffnen Sie Excel, und stellen Sie auf der Registerkarte **Masterdaten** eine Verbindung mit einem MDS-Repository her.</span><span class="sxs-lookup"><span data-stu-id="5613b-112">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="5613b-113">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einem MDS-Repository &#40;MDS-Add-In für Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5613b-113">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="5613b-114">Wählen Sie im Bereich **Master Data Explorer** ein Modell und eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="5613b-114">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="5613b-115">Die Liste der Entitäten wird aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="5613b-115">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="5613b-116">Wenn der Bereich **Master Data Explorer** nicht sichtbar ist, klicken Sie in der Gruppe **Verbinden und Laden** auf **Explorer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5613b-116">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="5613b-117">Wenn der Bereich **Master Data Explorer** deaktiviert ist, liegt dies daran, dass das vorhandene Blatt bereits von MDS verwaltete Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="5613b-117">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="5613b-118">Um den Bereich zu aktivieren, öffnen Sie ein neues Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="5613b-118">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="5613b-119">Klicken Sie im Bereich **Master Data Explorer** auf eine Entität.</span><span class="sxs-lookup"><span data-stu-id="5613b-119">In the **Master Data Explorer** pane, click an entity.</span></span>  
  
4.  <span data-ttu-id="5613b-120">Klicken Sie in der Gruppe **Verbinden und Laden** auf **Filtern**.</span><span class="sxs-lookup"><span data-stu-id="5613b-120">In the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="5613b-121">Klicken Sie im Dialogfeld **Filtern** im Abschnitt **Spalten** in der Liste der Attribute auf das Attribut, das Sie bewegen möchten.</span><span class="sxs-lookup"><span data-stu-id="5613b-121">In the **Filter** dialog box, in the **Columns** section, in the list of attributes, click the attribute you want to move.</span></span>  
  
6.  <span data-ttu-id="5613b-122">Klicken Sie rechts von der Liste auf den **Nach oben** - oder **Nach unten** -Pfeil, um das Attribut im Arbeitsblatt nach links und rechts zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="5613b-122">To the right of the list, click the **Up** or **Down** arrow to move the attribute left and right in the worksheet.</span></span>  
  
7.  <span data-ttu-id="5613b-123">Wiederholen Sie Schritt 7 für jedes Attribut, bis die Reihenfolge von oben nach unten die Reihenfolge von links nach rechts darstellt, die Sie im Arbeitsblatt wünschen.</span><span class="sxs-lookup"><span data-stu-id="5613b-123">Repeat step 7 for each attribute until the top-to-bottom order represents the left-to-right order you want in the worksheet.</span></span>  
  
8.  <span data-ttu-id="5613b-124">Klicken Sie auf **Daten laden**.</span><span class="sxs-lookup"><span data-stu-id="5613b-124">Click **Load Data**.</span></span> <span data-ttu-id="5613b-125">Das Blatt wird mit von MDS verwalteten Daten aufgefüllt, und die Spalten werden in der angegebenen Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5613b-125">The sheet is populated with MDS-managed data and the columns are displayed in the order you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5613b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5613b-126">See Also</span></span>  
 [<span data-ttu-id="5613b-127">Daten &#40;MDS-Add-in für Excel werden geladen&#41;</span><span class="sxs-lookup"><span data-stu-id="5613b-127">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  
