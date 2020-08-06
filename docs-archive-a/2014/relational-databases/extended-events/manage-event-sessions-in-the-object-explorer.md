---
title: Verwalten von Ereignissitzungen im Objekt-Explorer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 16849e38-d3fb-414d-8dcb-797b5ffce6ee
author: rothja
ms.author: jroth
ms.openlocfilehash: 1aa33a97137f63348898e6b1fcb7b19b2d218573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608665"
---
# <a name="manage-event-sessions-in-the-object-explorer"></a><span data-ttu-id="7f4ed-102">Verwalten von Ereignissitzungen im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="7f4ed-102">Manage Event Sessions in the Object Explorer</span></span>
  <span data-ttu-id="7f4ed-103">In diesem Thema werden die Aktionen erläutert, die Sie im **Objekt-Explorer** ausführen können und die sich auf erweiterte Ereignisse auswirken:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-103">This topic discusses the actions you can take in **Object Explorer** that affect Extended Events:</span></span>  
  
-   <span data-ttu-id="7f4ed-104">Erstellen einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-104">Create an Extended Events Session</span></span>  
  
-   <span data-ttu-id="7f4ed-105">Starten oder Beenden einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-105">Starting or Stopping an Extended Events Session</span></span>  
  
-   <span data-ttu-id="7f4ed-106">Exportieren einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-106">Export an Extended Events Session</span></span>  
  
-   <span data-ttu-id="7f4ed-107">Importieren einer Sitzungsvorlage für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-107">Import an Extended Events Session Template</span></span>  
  
-   <span data-ttu-id="7f4ed-108">Bearbeiten einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-108">Edit an Extended Events Session</span></span>  
  
-   <span data-ttu-id="7f4ed-109">Löschen einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-109">Delete an Extended Events Session</span></span>  
  
## <a name="create-an-extended-events-session"></a><span data-ttu-id="7f4ed-110">Erstellen einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-110">Create an Extended Events Session</span></span>  
 <span data-ttu-id="7f4ed-111">Weitere Informationen zum Erstellen einer Sitzung für erweiterte Ereignisse finden Sie unter [Erstellen einer Sitzung für erweiterte Ereignisse](../../database-engine/create-an-extended-events-session.md).</span><span class="sxs-lookup"><span data-stu-id="7f4ed-111">For more information about creating an Extended Events session, see [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span></span>  
  
## <a name="starting-or-stopping-an-extended-events-session"></a><span data-ttu-id="7f4ed-112">Starten oder Beenden einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-112">Starting or Stopping an Extended Events Session</span></span>  
 <span data-ttu-id="7f4ed-113">Sie können eine Sitzung für erweiterte Ereignisse mithilfe des Abfrage- **Editors** starten oder beenden, indem Sie die- `ALTER EVENT SESSION` Anweisung oder den Knoten **Erweiterte Ereignisse** von **Objekt-Explorer**verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-113">You can start or stop an Extended Events session through the **Query Editor** using the `ALTER EVENT SESSION` statement, or by using the **Extended Events** node of **Object Explorer**.</span></span>  
  
 <span data-ttu-id="7f4ed-114">Wenn Sie eine Ereignissitzung beenden, wird die Sitzung in der dynamischen Verwaltungssicht (dynamic management view; DMV) von „sys.dm_xe_sessions“ nicht mehr als aktive Sitzung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-114">When you stop an event session, the session is no longer listed as an active session in the sys.dm_xe_sessions dynamic management view (DMV).</span></span> <span data-ttu-id="7f4ed-115">Die Sitzungsdefinition bleibt jedoch intakt, und Sie können die Sitzung neu starten.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-115">However, the session definition remains intact, and you can restart the session.</span></span> <span data-ttu-id="7f4ed-116">Um eine Sitzungsdefinition vollständig zu entfernen, müssen Sie die Sitzung löschen.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-116">To completely remove a session definition, you must delete the session.</span></span>  
  
 <span data-ttu-id="7f4ed-117">Zum Starten oder Beenden einer Sitzung für erweiterte Ereignisse müssen Sie über die ALTER ANY EVENT SESSION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-117">To start or stop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="7f4ed-118">Beim Beenden einer Sitzung, die ein Arbeitsspeicherziel verwendet, z.B. den Ringpuffer, Buckets, Ereignispaarung oder synchrone Ereigniszählerziele, gehen die gesamten im Puffer der Sitzung gespeicherten Informationen (die target_data-Spalte der „sys.dm_xe_session_targets“-DMV) verloren.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-118">When you stop a session that uses an in-memory target, such as the ring buffer, bucketing, event pairing, or synchronous event counter targets, all the information stored in the session's buffer (the target_data column of the sys.dm_xe_session_targets DMV) will be lost.</span></span> <span data-ttu-id="7f4ed-119">Um auch nach dem Beenden der Sitzung auf die Ereignisdaten zugreifen zu können, sollten Sie die Daten speichern, bevor Sie die Sitzung beenden, oder die Sitzung so konfigurieren, dass sie das Dateiziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-119">To access event data after you stop the session, you should either save the data before you stop the session, or configure the session to use the file target.</span></span>  
  
### <a name="start-or-stop-an-extended-events-session-using-query-editor"></a><span data-ttu-id="7f4ed-120">Starten oder Beenden einer Sitzung für erweiterte Ereignisse mithilfe des Abfrage-Editors</span><span class="sxs-lookup"><span data-stu-id="7f4ed-120">Start or Stop an Extended Events Session Using Query Editor</span></span>  
 <span data-ttu-id="7f4ed-121">Geben Sie die folgenden Anweisungen aus, und ersetzen Sie dabei *Sitzungsname* durch den Namen der Sitzung für erweiterte Ereignisse, um eine Sitzung zu starten:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-121">To start a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = START  
```  
  
 <span data-ttu-id="7f4ed-122">Um eine Sitzung zu beenden, geben Sie die folgenden Anweisungen aus, und ersetzen Sie dabei *Sitzungsname* durch den Namen der Sitzung für erweiterte Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-122">To stop a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = STOP  
```  
  
### <a name="start-or-stop-an-extended-events-session-in-object-explorer"></a><span data-ttu-id="7f4ed-123">Starten oder Beenden einer Sitzung für erweiterte Ereignisse mittels Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="7f4ed-123">Start or Stop an Extended Events Session in Object Explorer</span></span>  
 <span data-ttu-id="7f4ed-124">Erweitern Sie die Knoten **Verwaltung**, **Erweiterte Ereignisse**und **Sitzungen**, klicken mit der rechten Maustaste auf eine Sitzung und klicken anschließend auf **Sitzung starten** oder **Sitzung beenden** , um im **Objekt-Explorer**eine Sitzung für erweiterte Ereignisse zu starten oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-124">To start or stop an Extended Events session in **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes and right click on a session and then click **Start Session** or **Stop Session**.</span></span>  
  
## <a name="export-an-extended-events-session-template"></a><span data-ttu-id="7f4ed-125">Exportieren einer Sitzungsvorlage für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-125">Export an Extended Events Session Template</span></span>  
 <span data-ttu-id="7f4ed-126">Sie können mit dem **Objekt-Explorer**eine Sitzung für erweiterte Ereignisse exportieren und diese als XML-Vorlage speichern.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-126">You can export an Extended Events session using **Object Explorer**, and save it as an .xml template file.</span></span> <span data-ttu-id="7f4ed-127">Beispielsweise können Sie eine Sitzung exportieren und anschließend mithilfe des **Assistenten für neue Sitzungen** die Vorlage auf eine **neue Ereignissitzung** anwenden.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-127">For example, you may want to export a session and then apply the template to a new event session using the **New Session Wizard** or the **New Session** wizard.</span></span>  
  
 <span data-ttu-id="7f4ed-128">Stellen Sie beim Exportieren einer Sitzung sicher, dass Sie die Vorlagendatei an einem Speicherort speichern, der das NTFS-Dateisystem verwendet. Schränken Sie zudem den Zugriff auf Benutzer ein, die zum Anzeigen der Informationen autorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-128">When you export a session, make sure that you save the template file to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="7f4ed-129">So exportieren Sie mit dem **Objekt-Explorer**eine Sitzung für erweiterte Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-129">To export an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="7f4ed-130">Erweitern Sie die Knoten **Verwaltung**, **Erweiterte Ereignisse**und anschließend **Sitzungen** .</span><span class="sxs-lookup"><span data-stu-id="7f4ed-130">Expand the **Management**, **Extended Events**, and then **Sessions** nodes</span></span>  
  
2.  <span data-ttu-id="7f4ed-131">Klicken Sie mit der rechten Maustaste auf die zu exportierende Sitzung, und wählen Sie anschließend **Sitzung exportieren**aus.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-131">Right-click the session that you want to export, and select **Export Session**.</span></span>  
  
3.  <span data-ttu-id="7f4ed-132">Wählen Sie im Dialogfeld **Speichern unter** einen Speicherort zum Speichern der Datei aus, geben Sie den Dateinamen in das Feld **Dateiname** ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-132">In the **Save As** dialog box, select a location to save the file, type the file name in the **File name** box, and then click **Save**.</span></span>  
  
     <span data-ttu-id="7f4ed-133">Wenn Sie die Datei am Standardspeicherort für [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Vorlagen speichern, wird die Vorlage in der Dropdownliste vordefinierter Vorlagen angezeigt, wenn Sie das Dialogfeld **Assistent für neue Sitzungen** und **Neue Sitzung** verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-133">If you save the file to the default [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] template location, the template will appear in the dropdown list of predefined templates when you use the **New Session Wizard** and **New Session** dialog.</span></span>  
  
## <a name="import-an-extended-events-session-template"></a><span data-ttu-id="7f4ed-134">Importieren einer Sitzungsvorlage für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-134">Import an Extended Events Session Template</span></span>  
 <span data-ttu-id="7f4ed-135">Sie können mit dem **Objekt-Explorer**eine Vorlage für eine Sitzung für erweiterte Ereignisse importieren.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-135">Using **Object Explorer**, you can import a template for an Extended Events session.</span></span> <span data-ttu-id="7f4ed-136">Dies ist beispielsweise hilfreich, um eine Sitzung aus einer Vorlage zu erstellen, die aus einer anderen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-136">For example, you may want to do this to create a session from a template that was exported from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7f4ed-137">Zum Importieren einer Sitzung für erweiterte Ereignisse müssen Sie über die erforderlichen `ALTER ANY EVENT SESSION`-Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-137">To import an Extended Events session, you must have the necessary `ALTER ANY EVENT SESSION` permissions.</span></span>  
  
 <span data-ttu-id="7f4ed-138">Bevor Sie eine Vorlagendatei importieren, stellen Sie sicher, dass die Datei aus einer vertrauenswürdigen Quelle stammt.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-138">Before you import a template file, make sure that the file is from a trusted source.</span></span> <span data-ttu-id="7f4ed-139">Die Vorlagendateien sollten an einem Speicherort gespeichert werden, bei dem das NTFS-Dateisystem verwendet und der Zugriff auf Benutzer eingeschränkt wird, die zum Anzeigen der Informationen autorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-139">Template files should be saved to a location that uses the NTFS file system and where access is restricted to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="7f4ed-140">So importieren Sie eine Sitzung für erweiterte Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-140">To import an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="7f4ed-141">Erweitern Sie im **Objekt-Explorer**die Knoten **Verwaltung**und **Erweiterte Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="7f4ed-141">In **Object Explorer**, expand the **Management**, and then **Extended Events** nodes.</span></span>  
  
2.  <span data-ttu-id="7f4ed-142">Klicken Sie mit der rechten Maustaste auf **Sitzungen** , und wählen Sie anschließend **Neue Sitzung**.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-142">Right-click **Sessions** and select **New Session**.</span></span>  
  
3.  <span data-ttu-id="7f4ed-143">Geben Sie einen Namen für die Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-143">Specify a name for the session.</span></span>  
  
4.  <span data-ttu-id="7f4ed-144">Erweitern Sie das Dropdownfeld **Vorlage** .</span><span class="sxs-lookup"><span data-stu-id="7f4ed-144">Expand the **Template** drop down box.</span></span>  
  
5.  <span data-ttu-id="7f4ed-145">Klicken Sie auf **\<File From ...> Öffnen**, und suchen Sie nach der Sitzung (XML-Datei), die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-145">Click **\<File From ...>Open** and browse for the session (XML file) you want to import.</span></span>  
  
 <span data-ttu-id="7f4ed-146">Die Sitzung wird unter dem Knoten **Sitzungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-146">The session appears under the **Sessions** node.</span></span> <span data-ttu-id="7f4ed-147">Standardmäßig die Sitzung nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-147">By default, the session is not started.</span></span>  
  
## <a name="edit-an-extended-events-session"></a><span data-ttu-id="7f4ed-148">Bearbeiten einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-148">Edit an Extended Events Session</span></span>  
 <span data-ttu-id="7f4ed-149">Sie können eine Sitzung für erweiterte Ereignisse in Objekt-Explorer bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-149">You can edit an Extended Events session in Object Explorer.</span></span>  
  
 <span data-ttu-id="7f4ed-150">So bearbeiten Sie eine Sitzung für erweiterte Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-150">To edit an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="7f4ed-151">Erweitern Sie im **Objekt-Explorer**die Knoten **Verwaltung**, **Erweiterte Ereignisse**und **Sitzungen** .</span><span class="sxs-lookup"><span data-stu-id="7f4ed-151">In **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="7f4ed-152">Klicken Sie mit der rechten Maustaste auf eine Sitzung, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-152">Right-click a session and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="7f4ed-153">Wählen Sie im Abschnitt **Seite auswählen** die Seite oder Seiten aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-153">In the **Select a page** section, select the page or pages you want to edit.</span></span>  
  
4.  <span data-ttu-id="7f4ed-154">Klicken Sie nach der Überarbeitung der Ereignissitzung auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-154">After you finish revising the event session, click **OK**.</span></span>  
  
## <a name="script-an-event-session-definition-using-tsql"></a><span data-ttu-id="7f4ed-155">Skript für eine Ereignissitzung als Definition mit [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f4ed-155">Script an Event Session Definition Using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
 <span data-ttu-id="7f4ed-156">Sowohl der Assistent für neue Sitzungen als auch das Dialogfeld "Neue Sitzung" verfügen über eine Skriptoption, die den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code generiert, der die Sitzung für erweiterte Ereignisse definiert.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-156">Both the New Session Wizard and the New Session dialog have a Script option that generates the [!INCLUDE[tsql](../../includes/tsql-md.md)] that defines the Extended Events session.</span></span>  
  
 <span data-ttu-id="7f4ed-157">Sie können auf den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code für eine vorhandene Sitzung für erweiterte Ereignisse zugreifen, indem Sie mit der rechten Maustaste auf den Sitzungsnamen klicken, die Option **Skript für Sitzung als**und dann **Erstellen in**auswählen.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-157">You can access the [!INCLUDE[tsql](../../includes/tsql-md.md)] for an existing Extended Events session by right clicking the session name, selecting **Script Session as**, and then selecting **Create to**.</span></span>  
  
## <a name="delete-an-extended-events-session"></a><span data-ttu-id="7f4ed-158">Löschen einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7f4ed-158">Delete an Extended Events Session</span></span>  
 <span data-ttu-id="7f4ed-159">Sie können eine Sitzung für erweiterte Ereignisse löschen:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-159">You can delete an Extended Events session:</span></span>  
  
-   <span data-ttu-id="7f4ed-160">Im Abfrage-Editor mit `DROP EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-160">In Query Editor using `DROP EVENT SESSION`.</span></span>  
  
-   <span data-ttu-id="7f4ed-161">Im **Objekt-Explorer**</span><span class="sxs-lookup"><span data-stu-id="7f4ed-161">In **Object Explorer**.</span></span>  
  
 <span data-ttu-id="7f4ed-162">Wenn Sie eine Ereignissitzung löschen, werden alle Konfigurationsinformationen entfernt, und die Sitzungsdefinition wird nicht mehr in der „sys.server_event_sessions“-Katalogsicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-162">When you delete an event session, all configuration information is removed and the session definition no longer appears in the sys.server_event_sessions catalog view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f4ed-163">system_health und AlwaysOn_health sind in enthalten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . löschen Sie Sie nicht.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-163">system_health and AlwaysOn_health are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; do not delete them.</span></span> <span data-ttu-id="7f4ed-164">system_health ist standardmäßig aktiviert (weitere Informationen finden Sie unter [Verwenden der system_health-Sitzung](use-the-ssms-xe-profiler.md)).</span><span class="sxs-lookup"><span data-stu-id="7f4ed-164">system_health is enabled by default (for more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md)).</span></span> <span data-ttu-id="7f4ed-165">AlwaysOn_health ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-165">AlwaysOn_health is off by default.</span></span> <span data-ttu-id="7f4ed-166">Diese Sitzungen erfassen Daten, die für das Diagnostizieren von Leistungsproblemen hilfreich sein können.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-166">These sessions collect data that can be useful for diagnosing performance issues.</span></span>  
  
 <span data-ttu-id="7f4ed-167">Zum Löschen einer Sitzung für erweiterte Ereignisse müssen Sie über die ALTER ANY EVENT SESSION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-167">To delete an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="7f4ed-168">So löschen Sie eine Sitzung für erweiterte Ereignisse im **Objekt-Explorer**:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-168">To delete an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="7f4ed-169">Erweitern Sie die Knoten **Verwaltung**, **Erweiterte Ereignisse**und anschließend **Sitzungen** .</span><span class="sxs-lookup"><span data-stu-id="7f4ed-169">Expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="7f4ed-170">Klicken Sie mit der rechten Maustaste auf eine Sitzung, und wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-170">Right-click a session and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="7f4ed-171">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-171">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="7f4ed-172">Klicken Sie nach der Überarbeitung der Ereignissitzung auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f4ed-172">After you finish revising the event session, click **OK**.</span></span>  
  
 <span data-ttu-id="7f4ed-173">Geben Sie die folgenden Anweisungen ein, und ersetzen Sie dabei **Sitzungsname**durch den Namen der Sitzung für erweiterte Ereignisse, die Sie löschen möchten, um eine Sitzung für erweiterte Ereignisse im *Abfrage-Editor* zu löschen:</span><span class="sxs-lookup"><span data-stu-id="7f4ed-173">To delete an Extended Events session in the **Query Editor**, Issue the following statements, replacing *session_name* with the name of the Extended Events session that you want to delete:</span></span>  
  
```  
DROP EVENT SESSION [session_name]  
ON SERVER  
```  
  
  
