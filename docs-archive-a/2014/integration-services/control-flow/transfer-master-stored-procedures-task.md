---
title: In master gespeicherte Prozeduren übertragen (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1915a3129eeb6e14c4315c37f2c6c2bf5b0d5412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724841"
---
# <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="f8a47-102">In master gespeicherte Prozeduren übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="f8a47-102">Transfer Master Stored Procedures Task</span></span>
  <span data-ttu-id="f8a47-103">Der Task „In 'master' gespeicherte Prozeduren übertragen“ überträgt mindestens eine benutzerdefinierte gespeicherte Prozedur zwischen den **master** -Datenbanken der Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a47-103">The Transfer Master Stored Procedures task transfers one or more user-defined stored procedures between **master** databases on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f8a47-104">Um eine gespeicherte Prozedur von der **master** -Datenbank zu übertragen, muss dbo der Besitzer der gespeicherten Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="f8a47-104">To transfer a stored procedure from the **master** database, the owner of the procedure must be dbo.</span></span>  
  
 <span data-ttu-id="f8a47-105">Der Task "In 'master' gespeicherte Prozeduren übertragen" kann zum Übertragen aller gespeicherten Prozeduren oder nur bestimmter gespeicherter Prozeduren konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f8a47-105">The Transfer Master Stored Procedures task can be configured to transfer all stored procedures or only specified stored procedures.</span></span> <span data-ttu-id="f8a47-106">Dieser Task kopiert keine gespeicherten Systemprozeduren.</span><span class="sxs-lookup"><span data-stu-id="f8a47-106">This task does not copy system stored procedures.</span></span>  
  
 <span data-ttu-id="f8a47-107">Die zu übertragenden gespeicherten 'master'-Prozeduren sind eventuell bereits am Ziel vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f8a47-107">The master stored procedures to be transferred may already exist on the destination.</span></span> <span data-ttu-id="f8a47-108">Der Task "In 'master' gespeicherte Prozeduren übertragen" kann zur Verarbeitung bereits vorhandener gespeicherter Prozeduren auf folgende Art und Weise konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="f8a47-108">The Transfer Master Stored Procedures task can be configured to handle existing stored procedures in the following ways:</span></span>  
  
-   <span data-ttu-id="f8a47-109">Überschreiben bereits vorhandener gespeicherter Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="f8a47-109">Overwrite existing stored procedures.</span></span>  
  
-   <span data-ttu-id="f8a47-110">Fehlschlagen des Tasks, wenn doppelte gespeicherte Prozeduren vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f8a47-110">Fail the task when duplicate stored procedures exist.</span></span>  
  
-   <span data-ttu-id="f8a47-111">Überspringen von doppelten gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="f8a47-111">Skip duplicate stored procedures.</span></span>  
  
 <span data-ttu-id="f8a47-112">Zur Laufzeit stellt der Task "In 'master' gespeicherte Prozeduren übertragen" eine Verbindung mit den Quell- und Zielservern her. Dazu werden die SMO-Verbindungs-Manager verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8a47-112">At run time, the Transfer Master Stored Procedures task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="f8a47-113">Die SMO-Verbindungs-Manager werden getrennt vom Task "In 'master' gespeicherte Prozeduren übertragen" konfiguriert. Es wird darauf dann im Task "In 'master' gespeicherte Prozeduren übertragen" verwiesen.</span><span class="sxs-lookup"><span data-stu-id="f8a47-113">The SMO connection managers are configured separately from the Transfer Master Stored Procedures task, and then referenced in the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="f8a47-114">Die SMO-Verbindungs-Manager geben den Server- und Authentifizierungsmodus an, der beim Zugriff auf den Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8a47-114">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="f8a47-115">Weitere Informationen finden Sie unter [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f8a47-115">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a><span data-ttu-id="f8a47-116">Übertragen von gespeicherten Prozeduren zwischen den Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8a47-116">Transferring Stored Procedures Between Instances of SQL Server</span></span>  
 <span data-ttu-id="f8a47-117">Der Task "In 'master' gespeicherte Prozeduren übertragen" unterstützt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Quelle und ein -Ziel.</span><span class="sxs-lookup"><span data-stu-id="f8a47-117">The Transfer Master Stored Procedures task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="f8a47-118">Events</span><span class="sxs-lookup"><span data-stu-id="f8a47-118">Events</span></span>  
 <span data-ttu-id="f8a47-119">Der Task löst ein Informationsereignis aus, das die Anzahl der übertragenen gespeicherten Prozeduren meldet, sowie ein Warnungsereignis, wenn eine gespeicherte Prozedur überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f8a47-119">The task raises an information event that reports the number of stored procedures transferred and a warning event when a stored procedure is overwritten.</span></span>  
  
 <span data-ttu-id="f8a47-120">Der Task "In 'master' gespeicherte Prozeduren übertragen" meldet keinen schrittweisen Fortschritt der Anmeldeübertragung; er meldet nur 0 % und 100 % der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="f8a47-120">The Transfer Master Stored Procedures task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="f8a47-121">Ausführungswert</span><span class="sxs-lookup"><span data-stu-id="f8a47-121">Execution Value</span></span>  
 <span data-ttu-id="f8a47-122">Der Ausführungswert, definiert in der `ExecutionValue`-Eigenschaft des Tasks, gibt die Anzahl der übertragenen gespeicherten Prozeduren zurück.</span><span class="sxs-lookup"><span data-stu-id="f8a47-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of stored procedures transferred.</span></span> <span data-ttu-id="f8a47-123">Indem der `ExecValueVariable`-Eigenschaft des Tasks "In 'master' gespeicherte Prozeduren übertragen" eine benutzerdefinierte Variable zugewiesen wird, können Informationen über die gespeicherten Prozeduren anderen Objekten im Paket zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f8a47-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Master Stored Procedures task, information about the stored procedure transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="f8a47-124">Weitere Informationen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) und [Verwenden von Variablen in Paketen](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f8a47-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="f8a47-125">Protokolleinträge</span><span class="sxs-lookup"><span data-stu-id="f8a47-125">Log Entries</span></span>  
 <span data-ttu-id="f8a47-126">Der Task "In 'master' gespeicherte Prozeduren übertragen" enthält die folgenden benutzerdefinierten Protokolleinträge:</span><span class="sxs-lookup"><span data-stu-id="f8a47-126">The Transfer Master Stored Procedures task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="f8a47-127">TransferStoredProceduresTaskStartTransferringObjects  Dieser Protokolleintrag meldet, dass die Übertragung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="f8a47-127">TransferStoredProceduresTaskStartTransferringObjects  This log entry reports that the transfer has started.</span></span> <span data-ttu-id="f8a47-128">Der Protokolleintrag enthält die Startzeit.</span><span class="sxs-lookup"><span data-stu-id="f8a47-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="f8a47-129">TransferSStoredProceduresTaskFinishedTransferringObjects  Dieser Protokolleintrag meldet, dass die Übertragung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f8a47-129">TransferSStoredProceduresTaskFinishedTransferringObjects  This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="f8a47-130">Der Protokolleintrag enthält die Beendigungszeit.</span><span class="sxs-lookup"><span data-stu-id="f8a47-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="f8a47-131">Außerdem meldet ein Protokolleintrag für das `OnInformation`-Ereignis die Anzahl der übertragenen gespeicherten Prozeduren, und für das `OnWarning`-Ereignis wird ein Protokolleintrag für jede gespeicherte Prozedur am Ziel geschrieben, der überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f8a47-131">In addition, a log entry for the `OnInformation` event reports the number of stored procedures that were transferred, and a log entry for the `OnWarning` event is written for each stored procedure on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="f8a47-132">Sicherheit und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f8a47-132">Security and Permissions</span></span>  
 <span data-ttu-id="f8a47-133">Der Benutzer muss über die Berechtigung zum Anzeigen der Liste mit gespeicherten Prozeduren in der **master** -Datenbank der Quelle verfügen und Mitglied der sysadmin-Serverrolle sein oder über Berechtigungen zum Erstellen von gespeicherten Prozeduren in der **master** -Datenbank auf dem Zielserver verfügen.</span><span class="sxs-lookup"><span data-stu-id="f8a47-133">The user must have permission to view the list of stored procedure in the **master** database on the source, and must be a member of the sysadmin server role or have permission to created stored procedures in the **master** database on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a><span data-ttu-id="f8a47-134">Konfiguration der Tasks "In 'master' gespeicherte Prozeduren übertragen"</span><span class="sxs-lookup"><span data-stu-id="f8a47-134">Configuration of the Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="f8a47-135">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="f8a47-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f8a47-136">Klicken Sie auf eines der folgenden Themen, um Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="f8a47-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f8a47-137">Editor für den Task „In 'master' gespeicherte Prozeduren übertragen“ &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="f8a47-137">Transfer Master Stored Procedures Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="f8a47-138">Editor für den Task „In master gespeicherte Prozeduren übertragen“ &#40;Seite „Gespeicherte Prozeduren“&#41;</span><span class="sxs-lookup"><span data-stu-id="f8a47-138">Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;</span></span>](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [<span data-ttu-id="f8a47-139">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f8a47-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="f8a47-140">Klicken Sie auf das folgende Thema, um Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f8a47-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a><span data-ttu-id="f8a47-141">Programmgesteuertes Konfigurieren des Tasks "In 'master' gespeicherte Prozeduren übertragen"</span><span class="sxs-lookup"><span data-stu-id="f8a47-141">Configuring the Transfer Master Stored Procedures Task Programmatically</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f8a47-142">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f8a47-142">Related Tasks</span></span>  
 <span data-ttu-id="f8a47-143">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="f8a47-143">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f8a47-144">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="f8a47-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8a47-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8a47-145">See Also</span></span>  
 <span data-ttu-id="f8a47-146">[SQL Server-Objekte kopieren (Task)](transfer-sql-server-objects-task.md) </span><span class="sxs-lookup"><span data-stu-id="f8a47-146">[Transfer SQL Server Objects Task](transfer-sql-server-objects-task.md) </span></span>  
 <span data-ttu-id="f8a47-147">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="f8a47-147">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="f8a47-148">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="f8a47-148">Control Flow</span></span>](control-flow.md)  
  
  
