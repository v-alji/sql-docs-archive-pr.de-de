---
title: Auftrags Eigenschaften und neuer Auftrag (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a5d2ab84ed211a03a3c217bd5f4cd54453a4dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699183"
---
# <a name="job-properties-and-new-job-general-page"></a><span data-ttu-id="8ae14-102">Auftragseigenschaften und „Neuer Auftrag“ (Seite „Allgemein“)</span><span class="sxs-lookup"><span data-stu-id="8ae14-102">Job Properties and New Job (General Page)</span></span>
  <span data-ttu-id="8ae14-103">Verwenden Sie diese Seite, um die allgemeinen Eigenschaften eines-Agent-Auftrags anzuzeigen und zu ändern [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ae14-103">Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8ae14-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8ae14-104">Options</span></span>  
 <span data-ttu-id="8ae14-105">**Name**</span><span class="sxs-lookup"><span data-stu-id="8ae14-105">**Name**</span></span>  
 <span data-ttu-id="8ae14-106">Ändern Sie den Namen des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="8ae14-106">Change the name of the job.</span></span>  
  
 <span data-ttu-id="8ae14-107">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="8ae14-107">**Owner**</span></span>  
 <span data-ttu-id="8ae14-108">Wählen Sie den Besitzer für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="8ae14-108">Select the owner for the job.</span></span>  
  
 <span data-ttu-id="8ae14-109">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="8ae14-109">**Category**</span></span>  
 <span data-ttu-id="8ae14-110">Wählen Sie die Auftragskategorie für den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="8ae14-110">Select the job category for the job.</span></span>  
  
 <span data-ttu-id="8ae14-111">**...**</span><span class="sxs-lookup"><span data-stu-id="8ae14-111">**...**</span></span>  
 <span data-ttu-id="8ae14-112">Zeigt die Aufträge in der ausgewählten Kategorie an.</span><span class="sxs-lookup"><span data-stu-id="8ae14-112">View the jobs in the selected category.</span></span>  
  
 <span data-ttu-id="8ae14-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8ae14-113">**Description**</span></span>  
 <span data-ttu-id="8ae14-114">Ändern Sie die Beschreibung des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="8ae14-114">Change the description of the job.</span></span>  
  
 <span data-ttu-id="8ae14-115">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="8ae14-115">**Enabled**</span></span>  
 <span data-ttu-id="8ae14-116">Aktivieren Sie den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="8ae14-116">Enable the job.</span></span> <span data-ttu-id="8ae14-117">Wenn der Auftrag nicht aktiviert ist, wird er nicht als Antwort auf einen Zeitplan oder eine Warnung ausgeführt. Sie können den Auftrag jedoch weiterhin mithilfe der gespeicherten Prozedur **sp_start_job** starten.</span><span class="sxs-lookup"><span data-stu-id="8ae14-117">When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.</span></span>  
  
 <span data-ttu-id="8ae14-118">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="8ae14-118">**Source**</span></span>  
 <span data-ttu-id="8ae14-119">Zeigt den Masterserver für den Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="8ae14-119">Displays the master server for the job.</span></span> <span data-ttu-id="8ae14-120">Nur auf der Seite **Auftragseigenschaften– Allgemein** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ae14-120">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="8ae14-121">**Erstellt**</span><span class="sxs-lookup"><span data-stu-id="8ae14-121">**Created**</span></span>  
 <span data-ttu-id="8ae14-122">Zeigt das Datum und die Uhrzeit der Auftragserstellung an.</span><span class="sxs-lookup"><span data-stu-id="8ae14-122">Displays the date and time that the job was created.</span></span> <span data-ttu-id="8ae14-123">Nur auf der Seite **Auftragseigenschaften– Allgemein** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ae14-123">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="8ae14-124">**Zuletzt geändert**</span><span class="sxs-lookup"><span data-stu-id="8ae14-124">**Last modified**</span></span>  
 <span data-ttu-id="8ae14-125">Zeigt das Datum und die Uhrzeit der letzten Änderung des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="8ae14-125">Displays the date and time that the job was last modified.</span></span> <span data-ttu-id="8ae14-126">Nur auf der Seite **Auftragseigenschaften– Allgemein** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ae14-126">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="8ae14-127">**Zuletzt ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="8ae14-127">**Last executed**</span></span>  
 <span data-ttu-id="8ae14-128">Zeigt das Datum und die Uhrzeit des Starts der letzten Ausführung des Auftrags an.</span><span class="sxs-lookup"><span data-stu-id="8ae14-128">Displays the date and time that the job last started running.</span></span> <span data-ttu-id="8ae14-129">Nur auf der Seite **Auftragseigenschaften– Allgemein** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ae14-129">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="8ae14-130">**Anzeigen des Auftragsverlaufs**</span><span class="sxs-lookup"><span data-stu-id="8ae14-130">**View Job History**</span></span>  
 <span data-ttu-id="8ae14-131">Zeigt den Auftragsverlauf für den Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="8ae14-131">View the job history for the job.</span></span> <span data-ttu-id="8ae14-132">Nur auf der Seite **Auftragseigenschaften– Allgemein** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ae14-132">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae14-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ae14-133">See Also</span></span>  
 <span data-ttu-id="8ae14-134">[Implementieren von Aufträgen](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="8ae14-134">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="8ae14-135">Auftragskategorien: Verwalten von Auftragskategorien</span><span class="sxs-lookup"><span data-stu-id="8ae14-135">Job Categories: Manage Job Categories</span></span>](job-categories-manage-job-categories.md)  
  
  
