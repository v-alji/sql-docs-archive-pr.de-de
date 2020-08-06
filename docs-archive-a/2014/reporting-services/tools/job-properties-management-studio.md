---
title: Auftragseigenschaften (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.jobproperties.f1
ms.assetid: 807ffd0e-9363-4f8f-9c36-c5d746ad19fd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4d309ba78a21114cf51c48f0a5c5b3b2f7c2500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700707"
---
# <a name="job-properties-management-studio"></a><span data-ttu-id="29146-102">Auftragseigenschaften (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="29146-102">Job Properties (Management Studio)</span></span>
  <span data-ttu-id="29146-103">Verwenden Sie das Fenster **Auftragseigenschaften** , um Informationen zu einem ausgeführten Bericht oder Abonnement anzuzeigen, bevor Sie den Vorgang abbrechen.</span><span class="sxs-lookup"><span data-stu-id="29146-103">Use the **Job Properties** page to view information about an in-progress report or subscription before you cancel it.</span></span>  
  
 <span data-ttu-id="29146-104">Starten Sie, um diese Seite zu öffnen, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], stellen Sie eine Verbindung mit einem Berichtsserver her, und öffnen Sie den Ordner **Aufträge** .</span><span class="sxs-lookup"><span data-stu-id="29146-104">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, and open the **Jobs** folder.</span></span> <span data-ttu-id="29146-105">Klicken Sie mit der rechten Maustaste auf einen gerade ausgeführten Auftrag, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="29146-105">Right-click a job that is running, and then click **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29146-106">Diese Funktion wird in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="29146-106">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="29146-107">Die Seite wird nicht angezeigt, wenn Sie [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="29146-107">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="29146-108">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="29146-108">Tasks</span></span>  
 <span data-ttu-id="29146-109">Bevor Sie Informationen zu einem Auftrag anzeigen können, müssen Sie die Seite aktualisieren, damit die Informationen über die gerade auf dem Berichtsserver ausgeführten Aufträge abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="29146-109">Before you can view information about a job, refresh the page to retrieve information about jobs that are currently running on the report server:</span></span>  
  
1.  <span data-ttu-id="29146-110">Öffnen Sie den Berichtsserverordner.</span><span class="sxs-lookup"><span data-stu-id="29146-110">Open the report server folder.</span></span>  
  
2.  <span data-ttu-id="29146-111">Klicken Sie mit der rechten Maustaste auf **Aufträge**, und klicken Sie dann auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="29146-111">Right-click **Jobs**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="29146-112">Wird ein Auftrag aufgeführt, dann klicken Sie mit der rechten Maustaste auf den Auftrag, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="29146-112">If a job is listed, right-click the job, and then click **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29146-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="29146-113">Options</span></span>  
 <span data-ttu-id="29146-114">**Auftrags-ID**</span><span class="sxs-lookup"><span data-stu-id="29146-114">**Job ID**</span></span>  
 <span data-ttu-id="29146-115">Dem Auftrag wird während seiner Verarbeitung ein GUID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="29146-115">A GUID that is assigned to a job while it is processing.</span></span> <span data-ttu-id="29146-116">Dieser Zufallswert wird jedes Mal generiert, wenn ein Bericht oder Abonnement ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="29146-116">The value is randomly generated each time a report or subscription runs.</span></span>  
  
 <span data-ttu-id="29146-117">**Auftragsstatus**</span><span class="sxs-lookup"><span data-stu-id="29146-117">**Job Status**</span></span>  
 <span data-ttu-id="29146-118">Gültige Werte sind **Neu** und **Wird ausgeführt**.</span><span class="sxs-lookup"><span data-stu-id="29146-118">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="29146-119">Bei Beginn des Auftrags ist der Status immer **Neu** .</span><span class="sxs-lookup"><span data-stu-id="29146-119">Status is always **New** when the job begins.</span></span> <span data-ttu-id="29146-120">Nach 60 Sekunden ändert sich der Status in **Wird ausgeführt**.</span><span class="sxs-lookup"><span data-stu-id="29146-120">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="29146-121">Sie müssen die Seite aktualisieren, damit die Änderung übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="29146-121">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="29146-122">**Auftragstyp**</span><span class="sxs-lookup"><span data-stu-id="29146-122">**Job Type**</span></span>  
 <span data-ttu-id="29146-123">Die gültigen Werte sind **Benutzer** und **System**.</span><span class="sxs-lookup"><span data-stu-id="29146-123">Valid values are **User** and **System**.</span></span> <span data-ttu-id="29146-124">Als Benutzerauftrag wird ein Auftrag bezeichnet, der durch einen einzelnen Benutzer initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="29146-124">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="29146-125">Dazu zählt das Ausführen eines Berichts bei Bedarf, die manuelle Generierung einer Momentaufnahme zum Berichtsverlauf oder das manuelle Erstellen einer Momentaufnahme zur Berichtsausführung.</span><span class="sxs-lookup"><span data-stu-id="29146-125">This includes running a report on-demand, manually generating a report history snapshot, or manually creating a report execution snapshot.</span></span> <span data-ttu-id="29146-126">Ein ausgeführtes Standardabonnement wird ebenfalls als Benutzerauftrag bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="29146-126">An in-progress standard subscription is also a user job.</span></span> <span data-ttu-id="29146-127">Als Systemauftrag wird ein Auftrag bezeichnet, der durch den Berichtsserver initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="29146-127">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="29146-128">Systemaufträge schließen die Berichtsverarbeitung ein, die von einem Zeitplan ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="29146-128">System jobs include report processing that is triggered by a schedule.</span></span>  
  
 <span data-ttu-id="29146-129">**Auftragsaktion**</span><span class="sxs-lookup"><span data-stu-id="29146-129">**Job Action**</span></span>  
 <span data-ttu-id="29146-130">Für Berichte zeigt diese Spalte die ausgeführten Berichtsausführungsprozesse an.</span><span class="sxs-lookup"><span data-stu-id="29146-130">For reports, this column shows which report execution processes are underway.</span></span> <span data-ttu-id="29146-131">Dieser Wert ist immer **Rendern**.</span><span class="sxs-lookup"><span data-stu-id="29146-131">This value is always **Render**.</span></span>  
  
 <span data-ttu-id="29146-132">**Auftragsbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="29146-132">**Job Description**</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="29146-133">stellt standardmäßig keine Auftragsbeschreibungen bereit.</span><span class="sxs-lookup"><span data-stu-id="29146-133">does not provide job descriptions by default.</span></span>  
  
 <span data-ttu-id="29146-134">**Servername**</span><span class="sxs-lookup"><span data-stu-id="29146-134">**Server Name**</span></span>  
 <span data-ttu-id="29146-135">Zeigt den Namen des Berichtsservers an, der den Auftrag verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="29146-135">Shows the name of the report server that is processing the job.</span></span> <span data-ttu-id="29146-136">Wenn Sie eine Bereitstellung für horizontales Skalieren konfiguriert haben, zeigt dieser Wert an, welcher Server den Auftrag verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="29146-136">If you configured a scale-out deployment, this value will show which server is processing the job.</span></span>  
  
 <span data-ttu-id="29146-137">**Berichtsname**</span><span class="sxs-lookup"><span data-stu-id="29146-137">**Report Name**</span></span>  
 <span data-ttu-id="29146-138">Zeigt den Berichtsnamen an.</span><span class="sxs-lookup"><span data-stu-id="29146-138">Shows the name of the report.</span></span> <span data-ttu-id="29146-139">Abonnements werden durch ihre Beschreibung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="29146-139">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="29146-140">**Berichtspfad**</span><span class="sxs-lookup"><span data-stu-id="29146-140">**Report Path**</span></span>  
 <span data-ttu-id="29146-141">Zeigt den Pfad des Berichts in der Ordnerhierarchie des Berichtsservers an.</span><span class="sxs-lookup"><span data-stu-id="29146-141">Shows the path of the report in the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="29146-142">**Startzeit**</span><span class="sxs-lookup"><span data-stu-id="29146-142">**Start Time**</span></span>  
 <span data-ttu-id="29146-143">Zeigt den Zeitpunkt des Prozessstarts an.</span><span class="sxs-lookup"><span data-stu-id="29146-143">Shows when the process started.</span></span>  
  
 <span data-ttu-id="29146-144">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="29146-144">**User Name**</span></span>  
 <span data-ttu-id="29146-145">Für Prozesse, die durch einen Benutzer initiiert wurden, zeigt diese Spalte den Namen des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="29146-145">For processes initiated by a user, this column shows the name of the user.</span></span> <span data-ttu-id="29146-146">Bei Systemaufträgen ist dies der Name des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="29146-146">For system jobs, this is the name of the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29146-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29146-147">See Also</span></span>  
 <span data-ttu-id="29146-148">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="29146-148">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="29146-149">[Vorgehensweise: Herstellen einer Verbindung mit einem Berichtsserver in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="29146-149">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="29146-150">Verwalten eines ausgeführten Prozesses</span><span class="sxs-lookup"><span data-stu-id="29146-150">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
