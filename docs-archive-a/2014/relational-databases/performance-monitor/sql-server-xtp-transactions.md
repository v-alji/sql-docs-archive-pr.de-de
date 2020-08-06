---
title: XTP-Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698031"
---
# <a name="xtp-transactions"></a><span data-ttu-id="63ba1-102">XTP-Transaktionen</span><span class="sxs-lookup"><span data-stu-id="63ba1-102">XTP Transactions</span></span>
  <span data-ttu-id="63ba1-103">Das XTP-Leistungsobjekt für Transaktionen enthält Leistungsindikatoren für XTP-Engine-Transaktionen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ba1-103">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="63ba1-104">In dieser Tabelle werden die Leistungsindikatoren für **XTP-Transaktionen** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="63ba1-104">This table describes the **XTP Transactions** counters.</span></span>  
  
|<span data-ttu-id="63ba1-105">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="63ba1-105">Counter</span></span>|<span data-ttu-id="63ba1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="63ba1-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63ba1-107">**Abbruchweitergaben/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-107">**Cascading aborts/sec**</span></span>|<span data-ttu-id="63ba1-108">Die durchschnittliche Anzahl der Transaktionen, für die pro Sekunde aufgrund eines Commitabhängigkeits-Rollbacks ein Rollback durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="63ba1-108">The number of transactions that rolled back to due a commit dependency rollback (on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-109">**Übernommene Commitabhängigkeiten/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-109">**Commit dependencies taken/sec**</span></span>|<span data-ttu-id="63ba1-110">Die durchschnittliche Anzahl der Commitabhängigkeiten, die pro Sekunde von Transaktionen übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="63ba1-110">The number of commit dependencies taken by transactions (on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-111">**Vorbereitete schreibgeschützte Transaktionen/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-111">**Read-only transactions prepared/sec**</span></span>|<span data-ttu-id="63ba1-112">Die Anzahl der schreibgeschützten Transaktionen, die pro Sekunde für die Commitverarbeitung vorbereitet wurden.</span><span class="sxs-lookup"><span data-stu-id="63ba1-112">The number of read-only transactions that were prepared for commit processing, per second.</span></span>|  
|<span data-ttu-id="63ba1-113">**Sicherungspunktaktualisierungen/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-113">**Save point refreshes/sec**</span></span>|<span data-ttu-id="63ba1-114">Die durchschnittliche Häufigkeit pro Sekunde, mit der ein Sicherungspunkt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="63ba1-114">The number of times a savepoint was "refreshed", (on average), per second.</span></span> <span data-ttu-id="63ba1-115">Eine Sicherungspunktaktualisierung erfolgt, wenn ein vorhandener Sicherungspunkt auf den aktuellen Punkt in der Lebensdauer der Transaktion zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="63ba1-115">A savepoint refresh is when an existing savepoint is reset to the current point in the transaction's lifetime.</span></span>|  
|<span data-ttu-id="63ba1-116">**Sicherungspunkt-Rollbacks/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-116">**Save point rollbacks/sec**</span></span>|<span data-ttu-id="63ba1-117">Die durchschnittliche Häufigkeit, mit der für eine Transaktion pro Sekunde ein Rollback auf einen Sicherungspunkt ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="63ba1-117">The number of times a transaction rolled back to a save point (on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-118">**Erstellte Sicherungspunkte/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-118">**Save points created /sec**</span></span>|<span data-ttu-id="63ba1-119">Die durchschnittliche Anzahl der pro Sekunde erstellten Sicherungspunkte.</span><span class="sxs-lookup"><span data-stu-id="63ba1-119">The number of save points created (on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-120">**Transaktionsüberprüfungsfehler/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-120">**Transaction validation failure/sec**</span></span>|<span data-ttu-id="63ba1-121">Die durchschnittliche Anzahl der Transaktionen mit fehlgeschlagener Überprüfungsverarbeitung (pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="63ba1-121">The number of transactions that failed validation processing (on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-122">**Vom Benutzer abgebrochene Transaktionen/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-122">**Transactions aborted by user/sec**</span></span>|<span data-ttu-id="63ba1-123">Die durchschnittliche Anzahl der Transaktionen, die pro Sekunde vom Benutzer abgebrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="63ba1-123">The number of transactions that were aborted by the user (on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-124">**Abgebrochene Transaktionen/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-124">**Transactions aborted/sec**</span></span>|<span data-ttu-id="63ba1-125">Die durchschnittliche Anzahl der Transaktionen, die pro Sekunde vom Benutzer und vom System abgebrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="63ba1-125">The number of transactions that aborted (both by the user and the system, on average), per second.</span></span>|  
|<span data-ttu-id="63ba1-126">**Erstellte Transaktionen/s**</span><span class="sxs-lookup"><span data-stu-id="63ba1-126">**Transactions created/sec**</span></span>|<span data-ttu-id="63ba1-127">Die durchschnittliche Anzahl der pro Sekunde im System erstellten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="63ba1-127">The number of transactions created in the system (on average), per second.</span></span><br /><br /> <span data-ttu-id="63ba1-128">XTP-Transaktionen werden anders als datenträgerbasierte Transaktionen gezählt (wie aus Datenbanken:Transaktionen/Sekunde ersichtlich).</span><span class="sxs-lookup"><span data-stu-id="63ba1-128">XTP transactions are counted differently than disk-based transactions (as reflected in Databases:Transactions/sec).</span></span> <span data-ttu-id="63ba1-129">Beispielsweise zählt Erstellte Transaktionen/s schreibgeschützte Transaktionen, Datenbanken:Transaktionen/Sekunde hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="63ba1-129">For example, Transactions created/sec counts read/only transactions, while Databases:Transactions/sec does not.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63ba1-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63ba1-130">See Also</span></span>  
 [<span data-ttu-id="63ba1-131">XTP-&#40;in-Memory-OLTP&#41; Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="63ba1-131">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
