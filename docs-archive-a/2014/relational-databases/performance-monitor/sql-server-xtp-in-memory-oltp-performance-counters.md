---
title: XTP-Leistungsindikatoren (in-Memory OLTP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: fe3cbaf4-65f4-44c5-acc6-7b735cda0c5d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4363a526ada3694e92d18cac0d7abe8a26f6a92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698043"
---
# <a name="xtp-in-memory-oltp-performance-counters"></a><span data-ttu-id="d21ea-102">XTP (In-Memory OLTP)-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="d21ea-102">XTP (In-Memory OLTP) Performance Counters</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d21ea-103">bietet Objekte und Leistungsindikatoren, die vom Systemmonitor zum Überwachen der In-Memory OLTP-Aktivität verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d21ea-103">provides objects and counters that can be used by Performance Monitor to monitor In-Memory OLTP activity.</span></span>  
  
##  <a name="xtp-in-memory-oltp-performance-objects"></a><a name="SQLServerPOs"></a><span data-ttu-id="d21ea-104">XTP-Leistungs Objekte (in-Memory OLTP)</span><span class="sxs-lookup"><span data-stu-id="d21ea-104">XTP (In-Memory OLTP) Performance Objects</span></span>  
 <span data-ttu-id="d21ea-105">In der folgenden Tabelle werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Objekte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d21ea-105">The following table describes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span>  
  
|<span data-ttu-id="d21ea-106">Leistungsobjekt</span><span class="sxs-lookup"><span data-stu-id="d21ea-106">Performance object</span></span>|<span data-ttu-id="d21ea-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d21ea-107">Description</span></span>|  
|------------------------|-----------------|  
|[<span data-ttu-id="d21ea-108">XTP-Cursor</span><span class="sxs-lookup"><span data-stu-id="d21ea-108">XTP Cursors</span></span>](../cursors.md)|<span data-ttu-id="d21ea-109">Das XTP-Leistungsobjekt für Cursor enthält Leistungsindikatoren für interne Cursor der XTP-Engine.</span><span class="sxs-lookup"><span data-stu-id="d21ea-109">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="d21ea-110">Cursor sind die Bausteine auf unterer Ebene, die die XTP-Engine zur Verarbeitung von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d21ea-110">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="d21ea-111">Daher können Sie diese in der Regel nicht direkt steuern.</span><span class="sxs-lookup"><span data-stu-id="d21ea-111">As such, you do not typically have direct control over them.</span></span>|  
|[<span data-ttu-id="d21ea-112">XTP Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="d21ea-112">XTP Garbage Collection</span></span>](sql-server-xtp-garbage-collection.md)|<span data-ttu-id="d21ea-113">Das XTP-Leistungsobjekt für die Garbage Collection enthält Leistungsindikatoren für die Garbage Collection der XTP-Engine.</span><span class="sxs-lookup"><span data-stu-id="d21ea-113">The XTP Garbage Collection performance object contains counters related to the XTP engine's garbage collector.</span></span>|  
|[<span data-ttu-id="d21ea-114">XTP-Phantomprozessor</span><span class="sxs-lookup"><span data-stu-id="d21ea-114">XTP Phantom Processor</span></span>](sql-server-xtp-phantom-processor.md)|<span data-ttu-id="d21ea-115">Das XTP-Leistungsobjekt "Phantomprozessor" enthält Leistungsindikatoren für das zur Phantomverarbeitung verwendete Subsystem der XTP-Engine.</span><span class="sxs-lookup"><span data-stu-id="d21ea-115">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="d21ea-116">Diese Komponente ist dafür verantwortlich, Phantomzeilen in Transaktionen zu erkennen, die auf der SERIALIZABLE-Isolationsstufe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d21ea-116">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>|  
|[<span data-ttu-id="d21ea-117">XTP-Speicher</span><span class="sxs-lookup"><span data-stu-id="d21ea-117">XTP Storage</span></span>](sql-server-xtp-storage.md)|<span data-ttu-id="d21ea-118">Das Leistungsobjekt "XTP-Speicher" enthält Leistungsindikatoren für den XTP-Speicher in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d21ea-118">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="d21ea-119">XTP-Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="d21ea-119">XTP Transaction Log</span></span>](sql-server-xtp-transaction-log.md)|<span data-ttu-id="d21ea-120">Das XTP-Leistungsobjekt für Transaktionsprotokolle enthält Leistungsindikatoren für die XTP-Transaktionsprotokollierung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d21ea-120">The XTP Transaction Log performance object contains counters related to XTP transaction logging in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="d21ea-121">XTP-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="d21ea-121">XTP Transactions</span></span>](sql-server-xtp-transactions.md)|<span data-ttu-id="d21ea-122">Das XTP-Leistungsobjekt für Transaktionen enthält Leistungsindikatoren für XTP-Engine-Transaktionen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d21ea-122">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
  
