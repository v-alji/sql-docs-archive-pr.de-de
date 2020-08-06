---
title: Arbeitsspeicher Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LowMemoryLimit property
- MinimumAllocatedMemory property
- MidMemoryPrice property
- MemoryHeapType property
- memory [Analysis Services]
- DefaultPagesCountToReuse property
- TotalMemoryLimit property
- SessionMemoryLimit property
- VirtualMemoryLimit property
- WaitCountIfHighMemory property
- HighMemoryPrice property
- HeapTypeForObjects property
ms.assetid: 085f5195-7b2c-411a-9813-0ff5c6066d13
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f2d2e56c9a951cee27752bd57d55d185a9b6618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727162"
---
# <a name="memory-properties"></a><span data-ttu-id="50c72-102">Speichereigenschaften</span><span class="sxs-lookup"><span data-stu-id="50c72-102">Memory Properties</span></span>
  <span data-ttu-id="50c72-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] werden die in der folgenden Tabelle aufgeführten Serverarbeitsspeichereigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50c72-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports the server memory properties listed in the following table.</span></span> <span data-ttu-id="50c72-104">Einen Leitfaden zum Festlegen dieser Eigenschaften finden Sie im [SQL Server 2008 R2 Analysis Services-Betriebshandbuch](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="50c72-104">For guidance in setting these properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="50c72-105">Werte zwischen 1 und 100 stellen Prozentsätze von **Gesamter physischer Speicher** bzw. **Virtueller Adressraum**dar, je nachdem, welcher geringer ist.</span><span class="sxs-lookup"><span data-stu-id="50c72-105">Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less.</span></span> <span data-ttu-id="50c72-106">Werte über 100 stellen Arbeitsspeichergrenzwerte in Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="50c72-106">Values over 100 represent memory limits in bytes.</span></span>  
  
 <span data-ttu-id="50c72-107">**Gilt für:** Mehrdimensionaler und tabellarischer Servermodus, sofern nichts anderes angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="50c72-107">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="50c72-108">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="50c72-108">Properties</span></span>  
 `LowMemoryLimit`  
 <span data-ttu-id="50c72-109">Eine 64-Bit-Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen, die den Punkt definiert, ab dem der Server als knapp an Arbeitsspeicher gilt, ausgedrückt als Prozentsatz des gesamten physischen Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="50c72-109">A signed 64-bit double-precision floating-point number property that defines the point at which the server is low on memory, expressed as percentage of total physical memory.</span></span> <span data-ttu-id="50c72-110">Wenn dieser Grenzwert erreicht wird, beginnt die Instanz langsam, Arbeitsspeicher in Caches zu bereinigen, indem abgelaufene Sitzungen geschlossen und nicht verwendete Berechnungen entladen werden.</span><span class="sxs-lookup"><span data-stu-id="50c72-110">When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations.</span></span> <span data-ttu-id="50c72-111">Der Server gibt keinen Arbeitsspeicher unter diesem Grenzwert frei.</span><span class="sxs-lookup"><span data-stu-id="50c72-111">The server will not release memory below this limit.</span></span> <span data-ttu-id="50c72-112">Der Standardwert ist 65. Dieser Wert besagt, dass der Grenzwert für ungenügenden Arbeitsspeicher 65 % des physischen Speichers bzw. virtuellen Adressraums entspricht, je nachdem, welcher dieser Werte niedriger ist.</span><span class="sxs-lookup"><span data-stu-id="50c72-112">The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 `TotalMemoryLimit`  
 <span data-ttu-id="50c72-113">Definiert einen Schwellenwert, ab dem der Server Arbeitsspeicher aggressiver freigibt.</span><span class="sxs-lookup"><span data-stu-id="50c72-113">Defines a threshold that when reached, causes the server to deallocate memory more aggressively.</span></span> <span data-ttu-id="50c72-114">Der Standardwert ist 80 % des physischen Speichers oder des virtuellen Adressraums, je nachdem, welcher dieser Werte niedriger ist.</span><span class="sxs-lookup"><span data-stu-id="50c72-114">The default value 80% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 <span data-ttu-id="50c72-115">Beachten Sie, dass `TotalMemoryLimit` immer kleiner als `HardMemoryLimit` sein muss.</span><span class="sxs-lookup"><span data-stu-id="50c72-115">Note that `TotalMemoryLimit` must always be less than `HardMemoryLimit`</span></span>  
  
 `HardMemoryLimit`  
 <span data-ttu-id="50c72-116">Gibt einen Arbeitsspeicherschwellenwert an, ab dem die Instanz aktive Benutzersitzungen aggressiv beendet, um die Speicherauslastung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="50c72-116">Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage.</span></span> <span data-ttu-id="50c72-117">Alle beendeten Sitzungen empfangen eine Fehlermeldung, dass der Abbruch der Sitzung durch ungenügenden Arbeitsspeicher bedingt ist.</span><span class="sxs-lookup"><span data-stu-id="50c72-117">All terminated sessions will receive an error about being cancelled by memory pressure.</span></span> <span data-ttu-id="50c72-118">Der Standardwert 0 bedeutet, dass `HardMemoryLimit` auf einen mittleren Wert zwischen `TotalMemoryLimit` und dem gesamten physischen Speicher des Systems festgelegt wird; wenn der physische Speicher größer als der virtuelle Adressraum des Prozesses ist, dann wird anstelle der Berechnung von `HardMemoryLimit` der virtuelle Adressraum verwendet.</span><span class="sxs-lookup"><span data-stu-id="50c72-118">The default value, zero (0), means the `HardMemoryLimit` will be set to a midway value between `TotalMemoryLimit` and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate `HardMemoryLimit`.</span></span>  
  
 `VirtualMemoryLimit`  
 <span data-ttu-id="50c72-119">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-119">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `VertiPaqPagingPolicy`  
 <span data-ttu-id="50c72-120">Gibt das Auslagerungsverhalten an, das bei ungenügendem Arbeitsspeicher des Servers angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="50c72-120">Specifies the paging behavior in the event the server runs low on memory.</span></span> <span data-ttu-id="50c72-121">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="50c72-121">Valid values are as follows:</span></span>  
  
 <span data-ttu-id="50c72-122">NULL (**0**) deaktiviert das Paging.</span><span class="sxs-lookup"><span data-stu-id="50c72-122">Zero (**0**) disables paging.</span></span> <span data-ttu-id="50c72-123">Wenn der Arbeitsspeicher nicht ausreicht, schlägt die Verarbeitung mit dem Fehler "Nicht genügend Arbeitsspeicher" fehl.</span><span class="sxs-lookup"><span data-stu-id="50c72-123">If memory is insufficient, processing fails with an out-of-memory error.</span></span> <span data-ttu-id="50c72-124">Wenn Sie die Auslagerung deaktivieren, müssen Sie für das Dienstkonto Windows-Berechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="50c72-124">If you disable paging, you must grant Windows privileges to the service account.</span></span> <span data-ttu-id="50c72-125">Anweisungen finden Sie unter [Konfigurieren von Dienstkonten &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="50c72-125">See [Configure Service Accounts &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) for instructions.</span></span>  
  
 <span data-ttu-id="50c72-126">Der Standardwert ist**1** .</span><span class="sxs-lookup"><span data-stu-id="50c72-126">**1** is the default.</span></span> <span data-ttu-id="50c72-127">Diese Eigenschaft ermöglicht die Auslagerung auf Datenträger unter Verwendung der Auslagerungsdatei des Betriebssystems (pagefile.sys).</span><span class="sxs-lookup"><span data-stu-id="50c72-127">This property enables paging to disk using the operating system page file (pagefile.sys).</span></span>  
  
 <span data-ttu-id="50c72-128">Wenn `VertiPaqPagingPolicy` auf 1 festgelegt wird, ist es weniger wahrscheinlich, dass die Verarbeitung aufgrund von Arbeitsspeicherbeschränkungen fehlschlägt, da der Server versucht, Daten anhand der von Ihnen angegebenen Methode auf den Datenträger auszulagern.</span><span class="sxs-lookup"><span data-stu-id="50c72-128">When `VertiPaqPagingPolicy` is set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified.</span></span> <span data-ttu-id="50c72-129">Das Festlegen der `VertiPaqPagingPolicy`-Eigenschaft ist keine Garantie dafür, dass niemals Arbeitsspeicherfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="50c72-129">Setting the `VertiPaqPagingPolicy` property does not guarantee that memory errors will never happen.</span></span> <span data-ttu-id="50c72-130">Unter folgenden Bedingungen können weiterhin Fehler aufgrund von unzureichendem Arbeitsspeicher auftreten:</span><span class="sxs-lookup"><span data-stu-id="50c72-130">Out of memory errors can still occur under the following conditions:</span></span>  
  
-   <span data-ttu-id="50c72-131">Es ist nicht genügend Arbeitsspeicher für alle Wörterbücher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50c72-131">There is not enough memory for all dictionaries.</span></span> <span data-ttu-id="50c72-132">Die Wörterbücher werden während der Verarbeitung von Analysis Services für jede Spalte im Arbeitsspeicher gesperrt, und diese dürfen in der Gesamtheit den für `VertiPaqMemoryLimit` angegebenen Wert nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="50c72-132">During processing, Analysis Services locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for `VertiPaqMemoryLimit`.</span></span>  
  
-   <span data-ttu-id="50c72-133">Der virtuelle Adressraum reicht nicht aus, um den Prozess aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="50c72-133">There is insufficient virtual address space to accommodate the process.</span></span>  
  
 <span data-ttu-id="50c72-134">Um wiederholte Fehler aufgrund von unzureichendem Arbeitsspeicher zu vermeiden, können Sie das Modell umgestalten, um die verarbeitete Datenmenge zu reduzieren, oder den physischen Arbeitsspeicher des Computers erweitern.</span><span class="sxs-lookup"><span data-stu-id="50c72-134">To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.</span></span>  
  
 <span data-ttu-id="50c72-135">Gilt nur für den tabellarischen Servermodus.</span><span class="sxs-lookup"><span data-stu-id="50c72-135">Applies to tabular server mode only.</span></span>  
  
 `VertiPaqMemoryLimit`  
 <span data-ttu-id="50c72-136">Wenn die Auslagerung auf Datenträger zulässig ist, gibt diese Eigenschaft die Arbeitsspeichernutzung (als Prozentsatz des gesamten Arbeitsspeichers) beim Start der Auslagerung an.</span><span class="sxs-lookup"><span data-stu-id="50c72-136">If paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts.</span></span> <span data-ttu-id="50c72-137">Der Standardwert ist 60.</span><span class="sxs-lookup"><span data-stu-id="50c72-137">The default is 60.</span></span> <span data-ttu-id="50c72-138">Wenn die Arbeitsspeichernutzung weniger als 60 Prozent beträgt, führt der Server keine Auslagerung auf Datenträger aus.</span><span class="sxs-lookup"><span data-stu-id="50c72-138">If memory consumption is less than 60 percent, the server will not page to disk.</span></span>  
  
 <span data-ttu-id="50c72-139">Diese Eigenschaft hängt von `VertiPaqPagingPolicyProperty` ab, die auf 1 festgelegt werden muss, damit Auslagerungen stattfinden.</span><span class="sxs-lookup"><span data-stu-id="50c72-139">This property depends on the `VertiPaqPagingPolicyProperty`, which must be set to 1 in order for paging to occur.</span></span>  
  
 <span data-ttu-id="50c72-140">Gilt nur für den tabellarischen Servermodus.</span><span class="sxs-lookup"><span data-stu-id="50c72-140">Applies to tabular server mode only.</span></span>  
  
 `HighMemoryPrice`  
 <span data-ttu-id="50c72-141">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryHeapType`  
 <span data-ttu-id="50c72-142">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="50c72-143">Gilt nur für den mehrdimensionalen Servermodus.</span><span class="sxs-lookup"><span data-stu-id="50c72-143">Applies to multidimensional server mode only.</span></span>  
  
 `HeapTypeForObjects`  
 <span data-ttu-id="50c72-144">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="50c72-145">Gilt nur für den mehrdimensionalen Servermodus.</span><span class="sxs-lookup"><span data-stu-id="50c72-145">Applies to multidimensional server mode only.</span></span>  
  
 `DefaultPagesCountToReuse`  
 <span data-ttu-id="50c72-146">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `HandleIA64AlignmentFaults`  
 <span data-ttu-id="50c72-147">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MidMemoryPrice`  
 <span data-ttu-id="50c72-148">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinimumAllocatedMemory`  
 <span data-ttu-id="50c72-149">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PreAllocate`  
 <span data-ttu-id="50c72-150">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SessionMemoryLimit`  
 <span data-ttu-id="50c72-151">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `WaitCountIfHighMemory`  
 <span data-ttu-id="50c72-152">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50c72-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c72-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50c72-153">See Also</span></span>  
 <span data-ttu-id="50c72-154">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="50c72-154">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="50c72-155">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="50c72-155">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
