---
title: PreConnect:Starting-Ereignisklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Starting Event Class
ms.assetid: d43ed0ad-3dbd-42e0-9cef-8320b8d87497
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b642d369c73cc144af31f835786613766045f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619809"
---
# <a name="preconnectstarting-event-class"></a><span data-ttu-id="9a0c9-102">PreConnect:Starting-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="9a0c9-102">PreConnect:Starting Event Class</span></span>
  <span data-ttu-id="9a0c9-103">Die PreConnect:Starting-Ereignisklasse zeigt an, dass die Ausführung eines LOGON-Triggers oder der Klassifizierungsfunktion der Ressourcenkontrolle beginnt.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-103">The PreConnect:Starting event class indicates when a LOGON trigger or the Resource Governor classifier function starts execution.</span></span>  
  
## <a name="preconnectstarting-event-class-data-columns"></a><span data-ttu-id="9a0c9-104">Datenspalten der PreConnect:Starting-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="9a0c9-104">PreConnect:Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="9a0c9-105">Datenspaltenname</span><span class="sxs-lookup"><span data-stu-id="9a0c9-105">Data column name</span></span>|<span data-ttu-id="9a0c9-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9a0c9-106">Data type</span></span>|<span data-ttu-id="9a0c9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a0c9-107">Description</span></span>|<span data-ttu-id="9a0c9-108">Column ID</span><span class="sxs-lookup"><span data-stu-id="9a0c9-108">Column ID</span></span>|<span data-ttu-id="9a0c9-109">Filterbar</span><span class="sxs-lookup"><span data-stu-id="9a0c9-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="9a0c9-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="9a0c9-110">EventClass</span></span>|`int`|<span data-ttu-id="9a0c9-111">215</span><span class="sxs-lookup"><span data-stu-id="9a0c9-111">215</span></span>|<span data-ttu-id="9a0c9-112">27</span><span class="sxs-lookup"><span data-stu-id="9a0c9-112">27</span></span>|<span data-ttu-id="9a0c9-113">Nein</span><span class="sxs-lookup"><span data-stu-id="9a0c9-113">No</span></span>|  
|<span data-ttu-id="9a0c9-114">SPID</span><span class="sxs-lookup"><span data-stu-id="9a0c9-114">SPID</span></span>|`int`|<span data-ttu-id="9a0c9-115">Die ID des Serverprozesses, von dem das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="9a0c9-116">12</span><span class="sxs-lookup"><span data-stu-id="9a0c9-116">12</span></span>|<span data-ttu-id="9a0c9-117">Ja</span><span class="sxs-lookup"><span data-stu-id="9a0c9-117">Yes</span></span>|  
|<span data-ttu-id="9a0c9-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="9a0c9-118">EventSubClass</span></span>|`int`|<span data-ttu-id="9a0c9-119">1 für die benutzerdefinierte Klassifizierungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="9a0c9-120">21</span><span class="sxs-lookup"><span data-stu-id="9a0c9-120">21</span></span>|<span data-ttu-id="9a0c9-121">Ja</span><span class="sxs-lookup"><span data-stu-id="9a0c9-121">Yes</span></span>|  
|<span data-ttu-id="9a0c9-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="9a0c9-122">StartTime</span></span>|`datetime`|<span data-ttu-id="9a0c9-123">Der Zeitpunkt, an dem die benutzerdefinierte Klassifizierungsfunktion beginnt.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="9a0c9-124">14</span><span class="sxs-lookup"><span data-stu-id="9a0c9-124">14</span></span>|<span data-ttu-id="9a0c9-125">Ja</span><span class="sxs-lookup"><span data-stu-id="9a0c9-125">Yes</span></span>|  
|<span data-ttu-id="9a0c9-126">ObjectID</span><span class="sxs-lookup"><span data-stu-id="9a0c9-126">ObjectID</span></span>|`int`|<span data-ttu-id="9a0c9-127">Die ID des benutzerdefinierten Klassifizierungsobjekts.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-127">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="9a0c9-128">22</span><span class="sxs-lookup"><span data-stu-id="9a0c9-128">22</span></span>|<span data-ttu-id="9a0c9-129">Ja</span><span class="sxs-lookup"><span data-stu-id="9a0c9-129">Yes</span></span>|  
|<span data-ttu-id="9a0c9-130">ObjectName</span><span class="sxs-lookup"><span data-stu-id="9a0c9-130">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="9a0c9-131">Der zweiteilige Name der benutzerdefinierten Klassifizierungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-131">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="9a0c9-132">Beispiel: dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="9a0c9-132">For example, dbo.classifier.</span></span>|<span data-ttu-id="9a0c9-133">34</span><span class="sxs-lookup"><span data-stu-id="9a0c9-133">34</span></span>|<span data-ttu-id="9a0c9-134">Ja</span><span class="sxs-lookup"><span data-stu-id="9a0c9-134">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a0c9-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a0c9-135">See Also</span></span>  
 <span data-ttu-id="9a0c9-136">[Erweiterte Ereignisse](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="9a0c9-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="9a0c9-137">[PreConnect: Abgeschlossene Ereignisklasse](preconnect-completed-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="9a0c9-137">[PreConnect:Completed Event Class](preconnect-completed-event-class.md) </span></span>  
 [<span data-ttu-id="9a0c9-138">Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="9a0c9-138">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
