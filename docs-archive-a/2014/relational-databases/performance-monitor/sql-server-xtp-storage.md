---
title: XTP-Speicher | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 4070580b-880d-4f4c-abcc-626a4fe0c9a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: efd4a9eba36060d3d4bab9b371678ab2b2c409ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618672"
---
# <a name="xtp-storage"></a><span data-ttu-id="8738d-102">XTP-Speicher</span><span class="sxs-lookup"><span data-stu-id="8738d-102">XTP Storage</span></span>
  <span data-ttu-id="8738d-103">Das Leistungsobjekt "XTP-Speicher" enthält Leistungsindikatoren für den XTP-Speicher in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8738d-103">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8738d-104">In dieser Tabelle werden die **XTP-Speicher** Indikatoren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8738d-104">This table describes the **XTP Storage** counters.</span></span>  
  
|<span data-ttu-id="8738d-105">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="8738d-105">Counter</span></span>|<span data-ttu-id="8738d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8738d-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8738d-107">**Geschlossene Prüfpunkte**</span><span class="sxs-lookup"><span data-stu-id="8738d-107">**Checkpoints Closed**</span></span>|<span data-ttu-id="8738d-108">Die Anzahl der vom Online-Agent geschlossenen Prüfpunkte.</span><span class="sxs-lookup"><span data-stu-id="8738d-108">Count of checkpoints closed done by online agent.</span></span>|  
|<span data-ttu-id="8738d-109">**Verarbeitete Prüfpunkte**</span><span class="sxs-lookup"><span data-stu-id="8738d-109">**Checkpoints Completed**</span></span>|<span data-ttu-id="8738d-110">Die Anzahl der vom Offline-Prüfpunktthread verarbeiteten Prüfpunkte.</span><span class="sxs-lookup"><span data-stu-id="8738d-110">Count of checkpoints processed by offline checkpoint thread.</span></span>|  
|<span data-ttu-id="8738d-111">**Abgeschlossene Kernzusammenführungen**</span><span class="sxs-lookup"><span data-stu-id="8738d-111">**Core Merges Completed**</span></span>|<span data-ttu-id="8738d-112">Die Anzahl der vom Zusammenführungsarbeitsthread abgeschlossenen Kernzusammenführungen.</span><span class="sxs-lookup"><span data-stu-id="8738d-112">The number of core merges completed by the merge worker thread.</span></span> <span data-ttu-id="8738d-113">Diese Zusammenführungen müssen noch installiert werden.</span><span class="sxs-lookup"><span data-stu-id="8738d-113">These merges still need to be installed.</span></span>|  
|<span data-ttu-id="8738d-114">**Auswertungen der Zusammenführungsrichtlinie**</span><span class="sxs-lookup"><span data-stu-id="8738d-114">**Merge Policy Evaluations**</span></span>|<span data-ttu-id="8738d-115">Die Anzahl der Auswertungen für die Zusammenführungsrichtlinie, seit der Server gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="8738d-115">The number of merge policy evaluations since the server started.</span></span>|  
|<span data-ttu-id="8738d-116">**Ausstehende Zusammenführungsanforderungen**</span><span class="sxs-lookup"><span data-stu-id="8738d-116">**Merge Requests Outstanding**</span></span>|<span data-ttu-id="8738d-117">Die Anzahl der ausstehenden Zusammenführungsanforderungen, seit der Server gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="8738d-117">The number of merge requests outstanding since the server started.</span></span>|  
|<span data-ttu-id="8738d-118">**Abgebrochene Zusammenführungen**</span><span class="sxs-lookup"><span data-stu-id="8738d-118">**Merges Abandoned**</span></span>|<span data-ttu-id="8738d-119">Die Anzahl der aufgrund eines Fehlers abgebrochenen Zusammenführungen.</span><span class="sxs-lookup"><span data-stu-id="8738d-119">The number of merges abandoned due to failure.</span></span>|  
|<span data-ttu-id="8738d-120">**Installierte Zusammenführungen**</span><span class="sxs-lookup"><span data-stu-id="8738d-120">**Merges Installed**</span></span>|<span data-ttu-id="8738d-121">Die Anzahl der erfolgreich installierten Zusammenführungen.</span><span class="sxs-lookup"><span data-stu-id="8738d-121">The number of merges successfully installed.</span></span>|  
|<span data-ttu-id="8738d-122">**Gesamtanzahl zusammengeführter Dateien**</span><span class="sxs-lookup"><span data-stu-id="8738d-122">**Total Files Merged**</span></span>|<span data-ttu-id="8738d-123">Die Gesamtanzahl der zusammengeführten Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="8738d-123">The total number of source files merged.</span></span> <span data-ttu-id="8738d-124">Diese Anzahl kann verwendet werden, um die durchschnittliche Anzahl von Quelldateien in der Zusammenführung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8738d-124">This count can be used to find the average number of source files in the merge.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8738d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8738d-125">See Also</span></span>  
 [<span data-ttu-id="8738d-126">XTP-&#40;in-Memory-OLTP&#41; Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="8738d-126">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
