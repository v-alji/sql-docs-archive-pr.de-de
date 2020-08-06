---
title: SQL Server, Statistiken für das Broker-TO (Objekt) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Broker Transmission Object object
- 'SQL Server: Broker Transmission Object'
ms.assetid: b5bc5dde-e540-4848-8aa3-5735c51df2fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 93d9c24a175dedfee171eccfccb34673501660ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620816"
---
# <a name="sql-server-broker-to-statistics-object"></a><span data-ttu-id="46594-102">SQL Server, Statistiken für das Broker-TO (Objekt)</span><span class="sxs-lookup"><span data-stu-id="46594-102">SQL Server, Broker TO Statistics Object</span></span>
  <span data-ttu-id="46594-103">Das Leistungsobjekt „SQLServer:Statistiken für das Broker-TO“ übermittelt Informationen darüber, wie oft [!INCLUDE[ssSB](../../includes/sssb-md.md)]-Dialoge Übertragungsobjekte anfordern, und wie oft Übertragungsobjekte in **tempdb** geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="46594-103">The SQLServer:Broker TO Statistics performance object reports information about how many times [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialogs request transmission objects, and how often transmission objects are written to **tempdb**.</span></span>  
  
 <span data-ttu-id="46594-104">Übertragungsobjekte zeichnen den Status von Nachrichtenübertragungen für einen [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Dialog auf.</span><span class="sxs-lookup"><span data-stu-id="46594-104">Transmission objects record the state of message transmissions for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialog.</span></span> <span data-ttu-id="46594-105">Sie werden im Arbeitsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46594-105">They are stored in memory.</span></span> <span data-ttu-id="46594-106">Um Arbeitsspeicher freizugeben, schreibt [!INCLUDE[ssSB](../../includes/sssb-md.md)] regelmäßig Batches inaktiver Übertragungsobjekte in Arbeitstabellen in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="46594-106">To free memory, [!INCLUDE[ssSB](../../includes/sssb-md.md)] periodically writes batches of inactive transmission objects to work tables in **tempdb**.</span></span>  
  
 <span data-ttu-id="46594-107">In der folgenden Tabelle sind die in diesem Objekt enthaltenen Indikatoren aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="46594-107">The following table lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="46594-108">Leistungsindikatoren für "Statistiken für das Broker-TO" in SQL Server</span><span class="sxs-lookup"><span data-stu-id="46594-108">SQL Server Broker TO Statistics counters</span></span>|<span data-ttu-id="46594-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="46594-109">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="46594-110">**Mittlere Länge der Batchschreibvorgänge**</span><span class="sxs-lookup"><span data-stu-id="46594-110">**Avg. Length of Batched Writes**</span></span>|<span data-ttu-id="46594-111">Die durchschnittliche Anzahl von Übertragungsobjekten, die in einem Batch gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="46594-111">The average number of transmission objects saved in a batch.</span></span>|  
|<span data-ttu-id="46594-112">**Mittlere Schreibdauer für Batch (ms)**</span><span class="sxs-lookup"><span data-stu-id="46594-112">**Avg. Time To Write Batch (ms)**</span></span>|<span data-ttu-id="46594-113">Die durchschnittliche Anzahl von Millisekunden, die zur Speicherung eines Batches von Übertragungsobjekten erforderlich waren.</span><span class="sxs-lookup"><span data-stu-id="46594-113">The average number of milliseconds required to save a batch of transmission objects.</span></span>|  
|<span data-ttu-id="46594-114">**Mittlere Zeit zwischen Batches (ms)**</span><span class="sxs-lookup"><span data-stu-id="46594-114">**Avg. Time Between Batches (ms)**</span></span>|<span data-ttu-id="46594-115">Die durchschnittliche Anzahl von Millisekunden, die zwischen Speicherungen der Batches von Übertragungsobjekten verstrichen sind.</span><span class="sxs-lookup"><span data-stu-id="46594-115">The average number of milliseconds between writes of transmission object batches.</span></span>|  
|<span data-ttu-id="46594-116">**Übertragungsobjektabrufe/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="46594-116">**Tran Object Gets/sec**</span></span>|<span data-ttu-id="46594-117">Gibt an, wie oft pro Sekunde Dialoge Übertragungsobjekte angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="46594-117">The number of times per second that dialogs requested transmission objects.</span></span>|  
|<span data-ttu-id="46594-118">**Pro Sekunde als geändert markierte Übertragungsobjekte**</span><span class="sxs-lookup"><span data-stu-id="46594-118">**Tran Objects Marked Dirty/sec**</span></span>|<span data-ttu-id="46594-119">Gibt an, wie oft pro Sekunde Übertragungsobjekte als geändert markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="46594-119">The number of times per second that transmission objects were marked as dirty.</span></span> <span data-ttu-id="46594-120">Übertragungsobjekte werden als geändert markiert, sobald eine Bearbeitung bewirkt, dass sich die Kopie im Arbeitsspeicher von der in **tempdb**gespeicherten Kopie unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="46594-120">Transmission objects are marked as dirty by the first modification that causes the in-memory copy to differ from the copy stored in **tempdb**.</span></span> <span data-ttu-id="46594-121">Übertragungsobjekte werden geändert, wenn [!INCLUDE[ssSB](../../includes/sssb-md.md)] eine Änderung des Status von Nachrichtenübertragungen für einen Dialog aufzeichnen muss.</span><span class="sxs-lookup"><span data-stu-id="46594-121">Transmission objects are modified when [!INCLUDE[ssSB](../../includes/sssb-md.md)] has to record a change in the state of message transmissions for the dialog.</span></span>|  
|<span data-ttu-id="46594-122">**Schreibvorgänge für Übertragungsobjekte/Sekunde**</span><span class="sxs-lookup"><span data-stu-id="46594-122">**Tran Object Writes/sec**</span></span>|<span data-ttu-id="46594-123">Gibt an, wie oft pro Sekunde Batches von Übertragungsobjekten in die **tempdb** -Arbeitstabellen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="46594-123">The number of times per second that a batch of transmission objects were written to **tempdb** work tables.</span></span> <span data-ttu-id="46594-124">Ein große Anzahl von Schreibvorgängen kann darauf hinweisen, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Arbeitsspeicher überbeansprucht wird.</span><span class="sxs-lookup"><span data-stu-id="46594-124">Large numbers of writes could indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory is being stressed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46594-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46594-125">See Also</span></span>  
 <span data-ttu-id="46594-126">[SQL Server, Zugriffsmethoden-Objekt](sql-server-access-methods-object.md) </span><span class="sxs-lookup"><span data-stu-id="46594-126">[SQL Server, Access Methods Object](sql-server-access-methods-object.md) </span></span>  
 <span data-ttu-id="46594-127">[SQL Server, Speicher-Manager-Objekt](sql-server-memory-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="46594-127">[SQL Server, Memory Manager Object](sql-server-memory-manager-object.md) </span></span>  
 [<span data-ttu-id="46594-128">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="46594-128">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
