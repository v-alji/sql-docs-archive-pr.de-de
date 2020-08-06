---
title: Task „Fehlermeldungen übertragen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.f1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952acc28a79fef7e7351c97400e05bc7ba5b9243
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607921"
---
# <a name="transfer-error-messages-task"></a><span data-ttu-id="62403-102">Fehlermeldungen übertragen (Task)</span><span class="sxs-lookup"><span data-stu-id="62403-102">Transfer Error Messages Task</span></span>
  <span data-ttu-id="62403-103">Der Task „Fehlermeldungen übertragen“ überträgt eine oder mehrere benutzerdefinierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlermeldungen zwischen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62403-103">The Transfer Error Messages task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined error messages between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62403-104">Benutzerdefinierte Meldungen sind Meldungen mit einem Bezeichner gleich oder größer als 50000.</span><span class="sxs-lookup"><span data-stu-id="62403-104">User-defined messages are messages with an identifier that is equal to or greater than 50000.</span></span> <span data-ttu-id="62403-105">Meldungen mit einem Bezeichner kleiner als 50000 sind Systemfehlermeldungen und können nicht mithilfe des Tasks "Fehlermeldungen übertragen" übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="62403-105">Messages with an identifier less than 50000 are system error messages, and cannot be transferred by using the Transfer Error Messages task.</span></span>  
  
 <span data-ttu-id="62403-106">Der Task Fehlermeldungen übertragen kann so konfiguriert werden, dass alle Fehlermeldungen oder nur die angegebenen Fehlermeldungen übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="62403-106">The Transfer Error Messages task can be configured to transfer all error messages, or only the specified error messages.</span></span> <span data-ttu-id="62403-107">Benutzerdefinierte Fehlermeldungen stehen möglicherweise in einer Vielzahl von verschiedenen Sprachen zur Verfügung, und der Task kann so konfiguriert werden, dass nur Meldungen in ausgewählten Sprachen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="62403-107">User-defined error messages may be available in a number of different languages and the task can be configured to transfer only messages in selected languages.</span></span> <span data-ttu-id="62403-108">Auf dem Zielserver muss eine Version der Meldung in us_english vorhanden sein, die Codepage 1033 verwendet, bevor Sie andere Sprachversionen auf diesen Server übertragen können.</span><span class="sxs-lookup"><span data-stu-id="62403-108">A us_english version of the message that uses code page 1033 must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
 <span data-ttu-id="62403-109">Die sysmessages-Tabelle in der master-Datenbank enthält alle Fehlermeldungen, sowohl Systemfehlermeldungen als auch benutzerdefinierte Fehlermeldungen, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62403-109">The sysmessages table in the master database contains all the error messages-both system and user-defined-that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses.</span></span>  
  
 <span data-ttu-id="62403-110">Die zu übertragenden benutzerdefinierten Meldungen sind auf dem Ziel möglicherweise schon vorhanden.</span><span class="sxs-lookup"><span data-stu-id="62403-110">The user-defined messages to be transferred may already exist on the destination.</span></span> <span data-ttu-id="62403-111">Eine Fehlermeldung wird als doppelte Fehlermeldung definiert, wenn der Bezeichner und die Sprache identisch sind.</span><span class="sxs-lookup"><span data-stu-id="62403-111">An error message is defined as a duplicate error message if the identifier and the language are the same.</span></span> <span data-ttu-id="62403-112">Es gibt folgende Möglichkeiten, um den Task "Fehlermeldungen übertragen" zur Verarbeitung bereits vorhandener Fehlermeldungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="62403-112">The Transfer Error Messages task can be configured to handle existing error messages in the following ways:</span></span>  
  
-   <span data-ttu-id="62403-113">Vorhandene Fehlermeldungen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="62403-113">Overwrite existing error messages.</span></span>  
  
-   <span data-ttu-id="62403-114">Der Task erzeugt einen Fehler, wenn doppelte Meldungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="62403-114">Fail the task when duplicate messages exist.</span></span>  
  
-   <span data-ttu-id="62403-115">Doppelte Fehlermeldungen auslassen.</span><span class="sxs-lookup"><span data-stu-id="62403-115">Skip duplicate error messages.</span></span>  
  
 <span data-ttu-id="62403-116">Zur Laufzeit stellt der Task "Fehlermeldungen übertragen" mithilfe eines oder zweier SMO-Verbindungs-Manager eine Verbindung mit dem Quell- und Zielserver her.</span><span class="sxs-lookup"><span data-stu-id="62403-116">At run time, the Transfer Error Messages task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="62403-117">Der SMO-Verbindungs-Manager wird unabhängig vom Task "Fehlermeldungen übertragen" konfiguriert, und im Task "Fehlermeldungen übertragen" wird dann darauf verwiesen.</span><span class="sxs-lookup"><span data-stu-id="62403-117">The SMO connection manager is configured separately from the Transfer Error Messages task, and then is referenced in the Transfer Error Messages task.</span></span> <span data-ttu-id="62403-118">Im SMO-Verbindungs-Manager wird der Server sowie der für den Zugriff auf den Server zu verwendende Authentifizierungsmodus angegeben.</span><span class="sxs-lookup"><span data-stu-id="62403-118">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="62403-119">Weitere Informationen finden Sie unter [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="62403-119">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="62403-120">Der Task "Fehlermeldungen übertragen" unterstützt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Quelle und ein Ziel.</span><span class="sxs-lookup"><span data-stu-id="62403-120">The Transfer Error Messages task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="62403-121">Es gibt keinerlei Beschränkungen, welche Version Sie als Quelle oder Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="62403-121">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="62403-122">Events</span><span class="sxs-lookup"><span data-stu-id="62403-122">Events</span></span>  
 <span data-ttu-id="62403-123">Der Task löst ein Informationsereignis aus, das die Anzahl der übertragenen Fehlermeldungen meldet.</span><span class="sxs-lookup"><span data-stu-id="62403-123">The task raises an information event that reports the number of error messages that have been transferred.</span></span>  
  
 <span data-ttu-id="62403-124">Der Task "Fehlermeldungen übertragen" meldet keinen schrittweisen Fortschritt der Fehlermeldungsübertragung; er meldet nur 0 % und 100 % der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="62403-124">The Transfer Error Messages task does not report incremental progress of the error message transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="62403-125">Ausführungswert</span><span class="sxs-lookup"><span data-stu-id="62403-125">Execution Value</span></span>  
 <span data-ttu-id="62403-126">Der in der `ExecutionValue`-Eigenschaft des Tasks definierte Ausführungswert gibt die Anzahl der zu übertragenden Fehlermeldungen zurück.</span><span class="sxs-lookup"><span data-stu-id="62403-126">The execution value, defined in the `ExecutionValue` property of the task, returns the number of error messages that have been transferred.</span></span> <span data-ttu-id="62403-127">Indem der `ExecValueVariable`-Eigenschaft des Tasks "Fehlermeldungen übertragen" eine benutzerdefinierte Variable zugewiesen wird, können Informationen über die Fehlermeldungsübertragung anderen Objekten im Paket zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="62403-127">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Error Message task, information about the error message transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="62403-128">Weitere Informationen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) und [Verwenden von Variablen in Paketen](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="62403-128">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="62403-129">Protokolleinträge</span><span class="sxs-lookup"><span data-stu-id="62403-129">Log Entries</span></span>  
 <span data-ttu-id="62403-130">Der Task "Fehlermeldungen übertragen" enthält die folgenden benutzerdefinierten Protokolleinträge:</span><span class="sxs-lookup"><span data-stu-id="62403-130">The Transfer Error Messages task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="62403-131">TransferErrorMessagesTaskStartTransferringObjects   Dieser Protokolleintrag meldet, dass die Übertragung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="62403-131">TransferErrorMessagesTaskStartTransferringObjects    This log entry reports that the transfer has started.</span></span> <span data-ttu-id="62403-132">Der Protokolleintrag enthält die Startzeit.</span><span class="sxs-lookup"><span data-stu-id="62403-132">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="62403-133">TransferErrorMessagesTaskFinishedTransferringObjects   Dieser Protokolleintrag meldet das Beenden der Übertragung.</span><span class="sxs-lookup"><span data-stu-id="62403-133">TransferErrorMessagesTaskFinishedTransferringObjects   This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="62403-134">Der Protokolleintrag enthält die Beendigungszeit.</span><span class="sxs-lookup"><span data-stu-id="62403-134">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="62403-135">Zusätzlich meldet ein Protokolleintrag für das `OnInformation`-Ereignis die Anzahl der übertragenen Fehlermeldungen. Für jede Fehlermeldung auf dem Ziel, die überschrieben wird, wird außerdem ein Protokolleintrag für das `OnWarning event` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="62403-135">In addition, a log entry for the `OnInformation` event reports the number of error messages that were transferred, and a log entry for the `OnWarning event` is written for each error message on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="62403-136">Sicherheit und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="62403-136">Security and Permissions</span></span>  
 <span data-ttu-id="62403-137">Um neue Fehlermeldungen zu erstellen, muss der Benutzer, von dem das Paket ausgeführt wird, auf dem Zielserver Mitglied der sysadmin- oder serveradmin-Serverrolle sein.</span><span class="sxs-lookup"><span data-stu-id="62403-137">To create new error messages, the user that runs the package must be a member of the sysadmin or serveradmin server role on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a><span data-ttu-id="62403-138">Konfiguration des Tasks "Fehlermeldungen übertragen"</span><span class="sxs-lookup"><span data-stu-id="62403-138">Configuration of the Transfer Error Messages Task</span></span>  
 <span data-ttu-id="62403-139">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="62403-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="62403-140">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="62403-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="62403-141">Editor für den Task „Fehlermeldungen übertragen“ &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="62403-141">Transfer Error Messages Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="62403-142">Editor für den Task „Fehlermeldungen übertragen“ &#40;Seite „Nachrichten“&#41;</span><span class="sxs-lookup"><span data-stu-id="62403-142">Transfer Error Messages Task Editor &#40;Messages Page&#41;</span></span>](../transfer-error-messages-task-editor-messages-page.md)  
  
-   [<span data-ttu-id="62403-143">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="62403-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="62403-144">Klicken Sie auf das folgende Thema, um Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="62403-144">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="62403-145">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="62403-145">Related Tasks</span></span>  
 <span data-ttu-id="62403-146">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="62403-146">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="62403-147">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="62403-147">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="62403-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62403-148">See Also</span></span>  
 <span data-ttu-id="62403-149">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="62403-149">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="62403-150">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="62403-150">Control Flow</span></span>](control-flow.md)  
  
  
