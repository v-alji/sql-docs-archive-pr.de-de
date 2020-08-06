---
title: XTP-Phantom Prozessor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 0f691b3d-a8fd-4459-ad21-2cfc8574a8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14158b7097427b6704cf5e747fa998a11217ecd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698042"
---
# <a name="xtp-phantom-processor"></a><span data-ttu-id="ebd03-102">XTP-Phantomprozessor</span><span class="sxs-lookup"><span data-stu-id="ebd03-102">XTP Phantom Processor</span></span>
  <span data-ttu-id="ebd03-103">Das XTP-Leistungsobjekt "Phantomprozessor" enthält Leistungsindikatoren für das zur Phantomverarbeitung verwendete Subsystem der XTP-Engine.</span><span class="sxs-lookup"><span data-stu-id="ebd03-103">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="ebd03-104">Diese Komponente ist dafür verantwortlich, Phantomzeilen in Transaktionen zu erkennen, die auf der SERIALIZABLE-Isolationsstufe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-104">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>  
  
 <span data-ttu-id="ebd03-105">In dieser Tabelle werden die Leistungsindikatoren für **XTP-Phantom Prozessoren** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebd03-105">This table describes the **XTP Phantom Processor** counters.</span></span>  
  
|<span data-ttu-id="ebd03-106">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="ebd03-106">Counter</span></span>|<span data-ttu-id="ebd03-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ebd03-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebd03-108">**Dusty-Corner-Scanwiederholungen/s (durch Phantom ausgegeben)**</span><span class="sxs-lookup"><span data-stu-id="ebd03-108">**Dusty corner scan retries/sec (Phantom-issued)**</span></span>|<span data-ttu-id="ebd03-109">Die durchschnittliche Anzahl von Scanwiederholungen aufgrund von Schreibkonflikten während Dusty-Corner-Sweep-Vorgängen, die pro Sekunde durch den Phantomprozessor ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-109">The number of scan retries due to write conflicts during dusty corner sweeps issued by the phantom processor (on average), per second.</span></span> <span data-ttu-id="ebd03-110">Dieser Leistungsindikator befindet sich auf einer sehr niedrigen Ebene und dient nicht der Verwendung durch Kunden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-110">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="ebd03-111">**Entfernte abgelaufene Phantomzeilen/s**</span><span class="sxs-lookup"><span data-stu-id="ebd03-111">**Phantom expired rows removed/sec**</span></span>|<span data-ttu-id="ebd03-112">Die durchschnittliche Anzahl abgelaufener Zeilen, die pro Sekunde von Phantomscans entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-112">The number of expired rows removed by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="ebd03-113">**Berührte abgelaufene Phantomzeilen/s**</span><span class="sxs-lookup"><span data-stu-id="ebd03-113">**Phantom expired rows touched/sec**</span></span>|<span data-ttu-id="ebd03-114">Die durchschnittliche Anzahl abgelaufener Zeilen, die pro Sekunde von Phantomscans berührt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-114">The number of expired rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="ebd03-115">**Berührte ablaufende Phantomzeilen/s**</span><span class="sxs-lookup"><span data-stu-id="ebd03-115">**Phantom expiring rows touched/sec**</span></span>|<span data-ttu-id="ebd03-116">Die durchschnittliche Anzahl ablaufender Zeilen, die pro Sekunde von Phantomscans berührt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-116">The number of expiring rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="ebd03-117">**Berührte Phantomzeilen/s**</span><span class="sxs-lookup"><span data-stu-id="ebd03-117">**Phantom rows touched/sec**</span></span>|<span data-ttu-id="ebd03-118">Die durchschnittliche Anzahl von Zeilen, die pro Sekunde von Phantomscans berührt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd03-118">The number of rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="ebd03-119">**Gestartete Phantomscans/s**</span><span class="sxs-lookup"><span data-stu-id="ebd03-119">**Phantom scans started/sec**</span></span>|<span data-ttu-id="ebd03-120">Die durchschnittliche Anzahl der pro Sekunde gestarteten Phantomscans.</span><span class="sxs-lookup"><span data-stu-id="ebd03-120">The number of phantom scans started (on average), per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ebd03-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebd03-121">See Also</span></span>  
 [<span data-ttu-id="ebd03-122">XTP-&#40;in-Memory-OLTP&#41; Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="ebd03-122">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
