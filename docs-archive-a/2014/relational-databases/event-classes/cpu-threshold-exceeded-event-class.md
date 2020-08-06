---
title: CPU Threshold Exceeded (Ereignisklasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07b51e1a6f08f48c601b00d2dcb67bc6d09006f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609254"
---
# <a name="cpu-threshold-exceeded-event-class"></a><span data-ttu-id="d0f9a-102">CPU Threshold Exceeded (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="d0f9a-102">CPU Threshold Exceeded Event Class</span></span>
  <span data-ttu-id="d0f9a-103">Die CPU Threshold Exceeded-Ereignisklasse zeigt an, dass die Ressourcenkontrolle eine Abfrage entdeckt hat, die den für REQUEST_MAX_CPU_TIME_SEC festgelegten CPU-Grenzwert überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-103">The CPU Threshold Exceeded event class indicates that Resource Governor detects a query that exceeds the CPU threshold specified for REQUEST_MAX_CPU_TIME_SEC.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0f9a-104">Das Erkennungsintervall für dieses Ereignis beträgt fünf Sekunden.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-104">The detection interval for this event is five seconds.</span></span> <span data-ttu-id="d0f9a-105">Es wird auf jeden Fall ein Ereignis erzeugt, wenn eine Abfrage den festgelegten Grenzwert um mindestens fünf Sekunden überschreitet.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-105">It is guaranteed that an event will be generated if a query exceeds the specified limit by at least five seconds.</span></span> <span data-ttu-id="d0f9a-106">Falls jedoch eine Abfrage den festgelegten Grenzwert um weniger als fünf Sekunden überschreitet, kann es sein, dass die Überschreitung je nach Zeitpunkt der Abfrage und dem Zeitpunkt des letzten Erkennungslaufs nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-106">However, if a query exceeds the specified threshold by less than five seconds, its detection might be missed depending on the timing of the query and the time of last detection sweep.</span></span>  
  
## <a name="cpu-threshold-exceeded-data-columns"></a><span data-ttu-id="d0f9a-107">Datenspalten der CPU Threshold Exceeded-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="d0f9a-107">CPU Threshold Exceeded Data Columns</span></span>  
  
|<span data-ttu-id="d0f9a-108">Datenspaltenname</span><span class="sxs-lookup"><span data-stu-id="d0f9a-108">Data column name</span></span>|<span data-ttu-id="d0f9a-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d0f9a-109">Data type</span></span>|<span data-ttu-id="d0f9a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0f9a-110">Description</span></span>|<span data-ttu-id="d0f9a-111">Column ID</span><span class="sxs-lookup"><span data-stu-id="d0f9a-111">Column ID</span></span>|<span data-ttu-id="d0f9a-112">Filterbar</span><span class="sxs-lookup"><span data-stu-id="d0f9a-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="d0f9a-113">CPU</span><span class="sxs-lookup"><span data-stu-id="d0f9a-113">CPU</span></span>|`int`|<span data-ttu-id="d0f9a-114">CPU-Verwendung in Millisekunden</span><span class="sxs-lookup"><span data-stu-id="d0f9a-114">CPU usage in milliseconds.</span></span>|<span data-ttu-id="d0f9a-115">18</span><span class="sxs-lookup"><span data-stu-id="d0f9a-115">18</span></span>|<span data-ttu-id="d0f9a-116">Ja</span><span class="sxs-lookup"><span data-stu-id="d0f9a-116">Yes</span></span>|  
|<span data-ttu-id="d0f9a-117">EventClass</span><span class="sxs-lookup"><span data-stu-id="d0f9a-117">EventClass</span></span>|`int`|<span data-ttu-id="d0f9a-118">214</span><span class="sxs-lookup"><span data-stu-id="d0f9a-118">214</span></span>|<span data-ttu-id="d0f9a-119">27</span><span class="sxs-lookup"><span data-stu-id="d0f9a-119">27</span></span>|<span data-ttu-id="d0f9a-120">Nein</span><span class="sxs-lookup"><span data-stu-id="d0f9a-120">No</span></span>|  
|<span data-ttu-id="d0f9a-121">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="d0f9a-121">EventSubClass</span></span>|`int`|<span data-ttu-id="d0f9a-122">CPU-Grenzwertüberschreitung</span><span class="sxs-lookup"><span data-stu-id="d0f9a-122">CPU limit violation.</span></span>|<span data-ttu-id="d0f9a-123">21</span><span class="sxs-lookup"><span data-stu-id="d0f9a-123">21</span></span>|<span data-ttu-id="d0f9a-124">Ja</span><span class="sxs-lookup"><span data-stu-id="d0f9a-124">Yes</span></span>|  
|<span data-ttu-id="d0f9a-125">GroupID</span><span class="sxs-lookup"><span data-stu-id="d0f9a-125">GroupID</span></span>|`int`|<span data-ttu-id="d0f9a-126">ID der Gruppe, in der die Überschreitung aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="d0f9a-126">Group ID where the violation occurred.</span></span>|<span data-ttu-id="d0f9a-127">66</span><span class="sxs-lookup"><span data-stu-id="d0f9a-127">66</span></span>|<span data-ttu-id="d0f9a-128">Ja</span><span class="sxs-lookup"><span data-stu-id="d0f9a-128">Yes</span></span>|  
|<span data-ttu-id="d0f9a-129">OwnerID</span><span class="sxs-lookup"><span data-stu-id="d0f9a-129">OwnerID</span></span>|`int`|<span data-ttu-id="d0f9a-130">SPID des Prozesses, der die Überschreitung verursacht hat</span><span class="sxs-lookup"><span data-stu-id="d0f9a-130">SPID of the process that caused the violation.</span></span>|<span data-ttu-id="d0f9a-131">58</span><span class="sxs-lookup"><span data-stu-id="d0f9a-131">58</span></span>|<span data-ttu-id="d0f9a-132">Ja</span><span class="sxs-lookup"><span data-stu-id="d0f9a-132">Yes</span></span>|  
|<span data-ttu-id="d0f9a-133">SPID</span><span class="sxs-lookup"><span data-stu-id="d0f9a-133">SPID</span></span>|`int`|<span data-ttu-id="d0f9a-134">ID des Serverprozesses, von dem das Ereignis ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="d0f9a-134">ID of the server process that fires this event.</span></span><br /><br /> <span data-ttu-id="d0f9a-135">Hinweis: Diese SPID kann sich von der tatsächlichen Benutzer-SPID unterscheiden, wenn die CPU-Verwendung von einem Systemthread als Hintergrundaufgabe überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="d0f9a-135">Note: This can differ from the actual user SPID if a system thread validates CPU usage as a background task.</span></span>|<span data-ttu-id="d0f9a-136">12</span><span class="sxs-lookup"><span data-stu-id="d0f9a-136">12</span></span>|<span data-ttu-id="d0f9a-137">Ja</span><span class="sxs-lookup"><span data-stu-id="d0f9a-137">Yes</span></span>|  
|<span data-ttu-id="d0f9a-138">StartTime</span><span class="sxs-lookup"><span data-stu-id="d0f9a-138">StartTime</span></span>|`datetime`|<span data-ttu-id="d0f9a-139">Zeitpunkt, zu dem das Ereignis ausgelöst wurde</span><span class="sxs-lookup"><span data-stu-id="d0f9a-139">The time when this event fired.</span></span>|<span data-ttu-id="d0f9a-140">14</span><span class="sxs-lookup"><span data-stu-id="d0f9a-140">14</span></span>|<span data-ttu-id="d0f9a-141">Ja</span><span class="sxs-lookup"><span data-stu-id="d0f9a-141">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0f9a-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0f9a-142">See Also</span></span>  
 [<span data-ttu-id="d0f9a-143">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d0f9a-143">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
