---
title: Dateispeicher Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Income property
- InitialBonus property
- PercentScanPerPrice property
- FileStore properties
- BackgroundTrimCost property
- Tax property
- PerformanceTrace property
- MinimumBalance property
- UnbufferedThreshold property
- BackgroundTrimAmount property
- MaximumBalance property
- MemoryLimitMin property
- MemoryLimit property
ms.assetid: 580cf0aa-7425-4d48-aa8d-128f5b488fcd
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc81273b55dea5820ef80f34c22d293492eb8055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727181"
---
# <a name="filestore-properties"></a><span data-ttu-id="ceaae-102">FileStore (Eigenschaften)</span><span class="sxs-lookup"><span data-stu-id="ceaae-102">Filestore Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="ceaae-103">werden die in den folgenden Tabellen aufgeführten Dateispeicher-Servereigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ceaae-103">supports the filestore server properties listed in the following tables.</span></span> <span data-ttu-id="ceaae-104">Hierbei handelt es sich um erweiterte Eigenschaften, die nicht ohne die Unterstützung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="ceaae-104">These are all advanced properties that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span> <span data-ttu-id="ceaae-105">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceaae-105">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="ceaae-106">**Gilt für:** mehrdimensionalen und Tabellenservermodus</span><span class="sxs-lookup"><span data-stu-id="ceaae-106">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ceaae-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ceaae-107">Properties</span></span>  
 `MemoryLimit`  
 <span data-ttu-id="ceaae-108">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-108">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryLimitMin`  
 <span data-ttu-id="ceaae-109">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PercentScanPerPrice`  
 <span data-ttu-id="ceaae-110">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PerformanceTrace`  
 <span data-ttu-id="ceaae-111">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-111">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RandomFileAccessMode`  
 <span data-ttu-id="ceaae-112">Eine boolesche Eigenschaft, die angibt, ob auf Datenbankdateien und zwischengespeicherte Dateien im zufälligen Dateizugriffsmodus zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="ceaae-112">A Boolean property that indicates whether database files and cached files are accessed in random file access mode.</span></span> <span data-ttu-id="ceaae-113">Diese Eigenschaft ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ceaae-113">This property is off by default.</span></span> <span data-ttu-id="ceaae-114">Beim Öffnen von Partitionsdatendateien für den Lesezugriff wird das Flag für den zufälligen Dateizugriff von Analysis Services standardmäßig nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ceaae-114">By default, Analysis Services does not set the random file access flag when opening partition data files for read access.</span></span>  
  
 <span data-ttu-id="ceaae-115">In High-End-Systemen, insbesondere solchen mit umfangreichen Speicherressourcen und mehreren NUMA-Knoten, kann es vorteilhaft sein, zufälligen Dateizugriff zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ceaae-115">On high-end systems, particularly those with large memory resources and multiple NUMA nodes, it can be advantageous to use random file access.</span></span> <span data-ttu-id="ceaae-116">Zur Konfliktverringerung im Cache umgeht Windows im zufälligen Zugriffsmodus Seitenzuordnungsvorgänge, bei denen Daten vom Datenträger in den Systemdateicache eingelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ceaae-116">In random access mode, Windows bypasses page mapping operations that read data from disk into the system file cache, thereby lowering contention on the cache.</span></span>  
  
 <span data-ttu-id="ceaae-117">Sie müssen Vergleichstests ausführen, um zu bestimmen, ob die Abfrageleistung durch Ändern dieser Eigenschaft verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="ceaae-117">You will need to run comparison tests to determine whether query performance is improved as the result of changing this property.</span></span> <span data-ttu-id="ceaae-118">Best Practices zum Ausführen von Vergleichstests, einschließlich des Löschens des Caches und des Vermeidens von häufigen Fehlern, finden Sie im [SQL Server 2008 R2 Analysis Services-Vorgangshandbuch](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="ceaae-118">For best practices on running comparison tests, including clearing the cache and avoiding common mistakes, see the [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span> <span data-ttu-id="ceaae-119">Weitere Informationen zu den vor-und Nachteile der Verwendung dieser Eigenschaft finden Sie unter [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369) .</span><span class="sxs-lookup"><span data-stu-id="ceaae-119">For additional information on the tradeoffs of using this property, see [https://support.microsoft.com/kb/2549369](https://support.microsoft.com/kb/2549369).</span></span>  
  
 <span data-ttu-id="ceaae-120">Um diese Eigenschaft in Management Studio anzuzeigen oder zu ändern, aktivieren Sie Liste der erweiterten Eigenschaften in der Servereigenschaftenseite.</span><span class="sxs-lookup"><span data-stu-id="ceaae-120">To view or modify this property in Management Studio, enable the advanced properties list in the server properties page.</span></span> <span data-ttu-id="ceaae-121">Sie können die Eigenschaft auch in der Datei "msmdsrv.ini" ändern.</span><span class="sxs-lookup"><span data-stu-id="ceaae-121">You can also change the property in the msmdsrv.ini file.</span></span> <span data-ttu-id="ceaae-122">Nach dem Festlegen dieser Eigenschaft wird empfohlen, den Server erneut zu starten. Andernfalls wird auf bereits geöffnete Dateien weiterhin im bisherigen Modus zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="ceaae-122">Restarting the server is recommended after setting this property; otherwise files that are already open will continue to be accessed in the previous mode.</span></span>  
  
 `UnbufferedThreshold`  
 <span data-ttu-id="ceaae-123">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-123">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="memory-model-category"></a><span data-ttu-id="ceaae-124">Arbeitsspeichermodell-Kategorie</span><span class="sxs-lookup"><span data-stu-id="ceaae-124">Memory Model Category</span></span>  
 `MemoryModel\Tax`  
 <span data-ttu-id="ceaae-125">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-125">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\Income`  
 <span data-ttu-id="ceaae-126">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\MaximumBalance`  
 <span data-ttu-id="ceaae-127">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-127">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\MinimumBalance`  
 <span data-ttu-id="ceaae-128">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-128">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryModel\InitialBonus`  
 <span data-ttu-id="ceaae-129">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ceaae-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceaae-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ceaae-130">See Also</span></span>  
 <span data-ttu-id="ceaae-131">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ceaae-131">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="ceaae-132">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="ceaae-132">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
