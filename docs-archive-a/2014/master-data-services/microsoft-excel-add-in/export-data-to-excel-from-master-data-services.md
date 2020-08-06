---
title: Laden von Daten aus MDS in Excel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: dd29389b-928c-4e50-995c-c6af27f97805
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35672807d5bb108e9386f892aea1847d45ebeb33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699891"
---
# <a name="load-data-from-mds-into-excel"></a><span data-ttu-id="76de0-102">Laden von Daten aus MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="76de0-102">Load Data from MDS into Excel</span></span>
  <span data-ttu-id="76de0-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] müssen Sie Daten aus dem MDS-Repository laden, um damit zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="76de0-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must load data from the MDS repository in order to work with it.</span></span>  
  
 <span data-ttu-id="76de0-104">Wenn Sie das Dataset vor dem Laden filtern möchten, finden Sie weitere Informationen unter [Filtern von Daten vor dem Laden &#40;MDS-Add-in für Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="76de0-104">If you want to filter the dataset before loading, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) instead.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="76de0-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="76de0-105">Prerequisites</span></span>  
 <span data-ttu-id="76de0-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="76de0-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="76de0-107">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="76de0-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-load-data-from-mds-into-excel"></a><span data-ttu-id="76de0-108">So laden Sie Daten aus MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="76de0-108">To load data from MDS into Excel</span></span>  
  
1.  <span data-ttu-id="76de0-109">Öffnen Sie Excel, und stellen Sie auf der Registerkarte **Masterdaten** eine Verbindung mit einem MDS-Repository her.</span><span class="sxs-lookup"><span data-stu-id="76de0-109">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="76de0-110">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einem MDS-Repository &#40;MDS-Add-In für Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="76de0-110">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="76de0-111">Wählen Sie im Bereich **Master Data Explorer** ein Modell und eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="76de0-111">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="76de0-112">Die Liste der Entitäten wird aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="76de0-112">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="76de0-113">Wenn der Bereich **Master Data Explorer** nicht sichtbar ist, klicken Sie in der Gruppe **Verbinden und Laden** auf **Explorer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="76de0-113">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="76de0-114">Wenn der Bereich **Master Data Explorer** deaktiviert ist, liegt dies daran, dass das vorhandene Blatt bereits von MDS verwaltete Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="76de0-114">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="76de0-115">Um den Bereich zu aktivieren, öffnen Sie ein neues Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="76de0-115">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="76de0-116">Doppelklicken Sie im Bereich **Master Data Explorer** in der Liste der Entitäten auf die Entität, die Sie laden möchten.</span><span class="sxs-lookup"><span data-stu-id="76de0-116">In the **Master Data Explorer** pane, in the list of entities, double-click the entity you want to load.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="76de0-117">Nur die erste eine Million von Elementen wird in Excel geladen.</span><span class="sxs-lookup"><span data-stu-id="76de0-117">Only the first one million members are loaded into Excel.</span></span> <span data-ttu-id="76de0-118">Klicken Sie zum Filtern der Liste vor dem Laden im Menüband in der Gruppe **Verbinden und Laden** auf **Filtern**.</span><span class="sxs-lookup"><span data-stu-id="76de0-118">To filter the list before loading, on the ribbon in the **Connect and Load** group, click **Filter**.</span></span>  
    > -   <span data-ttu-id="76de0-119">In Spalten, die beschränkte Listen (domänenbasierte Attribute) sind, werden nur die ersten 25.000 Werte geladen.</span><span class="sxs-lookup"><span data-stu-id="76de0-119">In columns that are constrained lists (domain-based attributes), only the first 25,000 values are loaded.</span></span> <span data-ttu-id="76de0-120">Sie können diese Zahl in der Eigenschaft "MaximumDbaEntitySize" der Datei "excelusersettings.config" ändern, die sich auf dem Computer befindet, auf dem Excel installiert ist.</span><span class="sxs-lookup"><span data-stu-id="76de0-120">You can change this number in the MaximumDbaEntitySize property in the excelusersettings.config file located on the computer that Excel is installed on.</span></span> <span data-ttu-id="76de0-121">Diese Datei befindet sich im Ordner c:\Users \\<User \> \appdata\local\microsoft\microsoft SQL server\120\masterdataservices \\ .</span><span class="sxs-lookup"><span data-stu-id="76de0-121">This file is located in C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices\\.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76de0-122">Es wird ein Fehler über unzureichenden Arbeitsspeicher angezeigt, wenn Sie textgetrennte Daten mithilfe des Add-Ins für Microsoft Excel in einer 32-Bit-Version von Excel laden und die Eigenschaften **Cell Count to Load** und **Cell Count to Publish** auf das Maximum von „1000“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="76de0-122">When you load text-delimited data using the Add-in for Microsoft Excel with 32-bit Excel, and the settings for the **Cell Count to Load** and **Cell Count to Publish** properties are both set to the maximum of 1000, an out-of-memory error will occur.</span></span> <span data-ttu-id="76de0-123">Sie müssen die 64-Bit-Version von Excel verwenden, um die Maximaleinstellungen für **Cell Count to Load** und **Cell Count to Publish**verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="76de0-123">You have to use 64-bit Excel to use the maximum settings for **Cell Count to Load** and **Cell Count to Publish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="76de0-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="76de0-124">Next Steps</span></span>  
 [<span data-ttu-id="76de0-125">Daten aus Excel in MDS &#40;MDS-Add-in für Excel veröffentlichen&#41;</span><span class="sxs-lookup"><span data-stu-id="76de0-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="76de0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76de0-126">See Also</span></span>  
 <span data-ttu-id="76de0-127">[Daten &#40;MDS-Add-in für Excel werden geladen&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="76de0-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="76de0-128">[Dialog Feld "Filter" &#40;MDS-Add-in für Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="76de0-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="76de0-129">Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="76de0-129">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
