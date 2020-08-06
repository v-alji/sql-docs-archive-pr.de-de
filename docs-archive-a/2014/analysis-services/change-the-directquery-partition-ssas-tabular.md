---
title: Ändern der directquery-Partition (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615707"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a><span data-ttu-id="7a9fd-102">Ändern der DirectQuery-Partition (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="7a9fd-102">Change the DirectQuery Partition (SSAS Tabular)</span></span>
  <span data-ttu-id="7a9fd-103">Da nur eine Partition in einer Tabelle als DirectQuery-Partition festgelegt werden kann, verwendet Analysis Services standardmäßig die erste Partition, die in der Tabelle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-103">Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table.</span></span> <span data-ttu-id="7a9fd-104">Während der Modellprojekterstellung können Sie die DirectQuery-Partition im Dialogfeld Partitions-Manager in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-104">During model project authoring, you can change the DirectQuery partition by using the Partition Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="7a9fd-105">Für bereitgestellte Modelle können Sie die DirectQuery-Partition mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-105">For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a><span data-ttu-id="7a9fd-106">Ändern der DirectQuery-Partition für ein tabellarisches Modellprojekt</span><span class="sxs-lookup"><span data-stu-id="7a9fd-106">Change the DirectQuery partition for a tabular model project</span></span>  
  
1.  <span data-ttu-id="7a9fd-107">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]im Modell-Designer auf die Tabelle (Registerkarte), die die partitionierte Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in the model designer, click on the table (tab) that contains the partitioned table.</span></span>  
  
2.  <span data-ttu-id="7a9fd-108">Klicken Sie auf das Menü **Tabelle** und dann auf **Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-108">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="7a9fd-109">Im **Partitions-Manager**wird die Partition, die die aktuelle Partition für direkte Abfragen ist, durch das Präfix **(DirectQuery)** für den Partitionsnamen angegeben.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-109">In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.</span></span>  
  
     <span data-ttu-id="7a9fd-110">Wählen Sie eine andere Partition in der Liste **Partitionen** aus, und klicken Sie dann auf **Als DirectQuery festlegen**.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-110">Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**.</span></span> <span data-ttu-id="7a9fd-111">Die Schaltfläche **Als DirectQuery festlegen** wird bei Auswahl der aktuellen DirectQuery-Partition nicht aktiviert, und sie ist nicht sichtbar, wenn das Modell nicht für den DirectQuery-Modus aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-111">The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="7a9fd-112">Ändern Sie bei Bedarf die Verarbeitungsoptionen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-112">If necessary, change the processing options, and then click **OK**.</span></span>  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a><span data-ttu-id="7a9fd-113">Ändern der DirectQuery-Partition für ein bereitgestelltes tabellarisches Modell</span><span class="sxs-lookup"><span data-stu-id="7a9fd-113">Change the DirectQuery partition for a deployed tabular model</span></span>  
  
1.  <span data-ttu-id="7a9fd-114">Öffnen Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]die Modelldatenbank in Objekt-Explorer.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="7a9fd-115">Erweitern Sie den Knoten **Tabellen** , klicken Sie mit der rechten Maustaste auf die partitionierte Tabelle, und wählen Sie **Partitionen**aus.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-115">Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.</span></span>  
  
     <span data-ttu-id="7a9fd-116">Die Partition, die für die Verwendung mit dem DirectQuery-Modus festgelegt ist, besitzt das Präfix (DirectQuery) für den Partitionsnamen.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-116">The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.</span></span>  
  
3.  <span data-ttu-id="7a9fd-117">Um zu einer anderen Partition zu wechseln, klicken Sie auf der Symbolleiste auf das Symbol für **DirectQuery** , um das Dialogfeld **DirectQuery-Partition festlegen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-117">To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box.</span></span> <span data-ttu-id="7a9fd-118">Das Symbol für DirectQuery auf der Symbolleiste ist nicht verfügbar für Modelle, für die DirectQuery nicht aktiviert wurde.)</span><span class="sxs-lookup"><span data-stu-id="7a9fd-118">The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.</span></span>  
  
4.  <span data-ttu-id="7a9fd-119">Wählen Sie eine andere Partition in der Dropdownliste **Partitionsname** aus, und ändern Sie ggf. die Verarbeitungsoptionen für die Partition.</span><span class="sxs-lookup"><span data-stu-id="7a9fd-119">Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9fd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a9fd-120">See Also</span></span>  
 [<span data-ttu-id="7a9fd-121">Partitionen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="7a9fd-121">Partitions &#40;SSAS Tabular&#41;</span></span>](tabular-models/partitions-ssas-tabular.md)  
  
  
