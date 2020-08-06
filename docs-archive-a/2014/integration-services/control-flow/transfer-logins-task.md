---
title: Task „Anmeldungen übertragen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.f1
helpviewer_keywords:
- Transfer Logins task [Integration Services]
ms.assetid: 1df60fd6-c019-405d-8155-c330dbac2cc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d42d39b6cc7c2f350e3e3adc774be23934981369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607918"
---
# <a name="transfer-logins-task"></a><span data-ttu-id="e1115-102">Task "Anmeldungen übertragen"</span><span class="sxs-lookup"><span data-stu-id="e1115-102">Transfer Logins Task</span></span>
  <span data-ttu-id="e1115-103">Mit dem Task "Anmeldungen übertragen" wird mindestens eine Anmeldung zwischen den Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]übertragen.</span><span class="sxs-lookup"><span data-stu-id="e1115-103">The Transfer Logins task transfers one or more logins between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="transfer-logins-between-instances-of-sql-server"></a><span data-ttu-id="e1115-104">Übertragen von Anmeldungen zwischen den Instanzen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1115-104">Transfer Logins Between Instances of SQL Server</span></span>  
 <span data-ttu-id="e1115-105">Der Task "Anmeldungen übertragen" unterstützt eine Quelle und ein Ziel in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1115-105">The Transfer Logins task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="e1115-106">Events</span><span class="sxs-lookup"><span data-stu-id="e1115-106">Events</span></span>  
 <span data-ttu-id="e1115-107">Die Task löst ein Informationsereignis aus, das die Anzahl der übertragenen Anmeldungen meldet, sowie ein Warnungsereignis, wenn eine Anmeldung überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e1115-107">The task raises an information event that reports the number of logins transferred and a warning event when a login is overwritten.</span></span>  
  
 <span data-ttu-id="e1115-108">Die Task "Anmeldungen übertragen" meldet keinen schrittweisen Fortschritt der Anmeldeübertragung; sie meldet nur 0 % und 100 % der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="e1115-108">The Transfer Logins task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="e1115-109">Ausführungswert</span><span class="sxs-lookup"><span data-stu-id="e1115-109">Execution Value</span></span>  
 <span data-ttu-id="e1115-110">Der Ausführungswert, definiert in der `ExecutionValue`-Eigenschaft der Task, gibt die Anzahl der übertragenen Anmeldungen zurück.</span><span class="sxs-lookup"><span data-stu-id="e1115-110">The execution value, defined in the `ExecutionValue` property of the task, returns the number of logins transferred.</span></span> <span data-ttu-id="e1115-111">Indem der `ExecValueVariable`-Eigenschaft der Task "Anmeldungen übertragen" eine benutzerdefinierte Variable zugewiesen wird, können Informationen über die Anmeldeübertragung anderen Objekten im Paket zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e1115-111">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Logins task, information about the login transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="e1115-112">Weitere Informationen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) und [Verwenden von Variablen in Paketen](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e1115-112">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="e1115-113">Protokolleinträge</span><span class="sxs-lookup"><span data-stu-id="e1115-113">Log Entries</span></span>  
 <span data-ttu-id="e1115-114">Die Task "Anmeldungen übertragen" enthält die folgenden benutzerdefinierten Protokolleinträge:</span><span class="sxs-lookup"><span data-stu-id="e1115-114">The Transfer Logins task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="e1115-115">TransferLoginsTaskStarTransferringObjects    Dieser Protokolleintrag meldet, dass die Übertragung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="e1115-115">TransferLoginsTaskStarTransferringObjects    This log entry reports the transfer has started.</span></span> <span data-ttu-id="e1115-116">Der Protokolleintrag enthält die Startzeit.</span><span class="sxs-lookup"><span data-stu-id="e1115-116">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="e1115-117">TransferLoginsTaskFinishedTransferringObjects   Dieser Protokolleintrag meldet, dass die Übertragung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e1115-117">TransferLoginsTaskFinishedTransferringObjects   This log entry reports the transfer has completed.</span></span> <span data-ttu-id="e1115-118">Der Protokolleintrag enthält die Beendigungszeit.</span><span class="sxs-lookup"><span data-stu-id="e1115-118">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="e1115-119">Außerdem meldet ein Protokolleintrag für das `OnInformation`-Ereignis die Anzahl der übertragenen Anmeldungen, und für das `OnWarning`-Ereignis wird ein Protokolleintrag für jede Anmeldung im Ziel geschrieben, die überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e1115-119">In addition, a log entry for the `OnInformation` event reports the number of logins that were transferred, and a log entry for the `OnWarning` event is written for each login on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="e1115-120">Sicherheit und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e1115-120">Security and Permissions</span></span>  
 <span data-ttu-id="e1115-121">Um nach Anmeldungen auf dem Quellserver zu suchen und Anmeldungen auf dem Zielserver zu erstellen, muss der Benutzer Mitglied der sysadmin-Serverrolle auf beiden Servern sein.</span><span class="sxs-lookup"><span data-stu-id="e1115-121">To browse logins on the source server and to create logins on the destination server, the user must be a member of the sysadmin server role on both servers.</span></span>  
  
## <a name="configuration-of-the-transfer-logins-task"></a><span data-ttu-id="e1115-122">Konfiguration des Tasks "Anmeldungen übertragen"</span><span class="sxs-lookup"><span data-stu-id="e1115-122">Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="e1115-123">Die Task "Anmeldungen übertragen" kann so konfiguriert werden, dass alle Anmeldungen, nur die angegebenen Anmeldungen oder alle Anmeldungen, die Zugriff auf bestimmte Datenbanken haben, übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e1115-123">The Transfer Logins task can be configured to transfer all logins, only specified logins, or all logins that have access to specified databases only.</span></span> <span data-ttu-id="e1115-124">Die Anmeldung sa kann nicht übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e1115-124">The sa login cannot be transferred.</span></span> <span data-ttu-id="e1115-125">Die Anmeldung „sa“ kann umbenannt werden. Die umbenannte Anmeldung „sa“ kann jedoch ebenfalls nicht übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="e1115-125">The sa login may be renamed; however, the renamed sa login cannot be transferred either.</span></span>  
  
 <span data-ttu-id="e1115-126">Sie können auch angeben, ob der Task die mit den Anmeldungen verknüpften Sicherheits-IDs (Security Identification Numbers, SIDs) kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="e1115-126">You can also indicate whether the task copies the security identifiers (SIDs) associated with the logins.</span></span> <span data-ttu-id="e1115-127">Wenn die Task "Anmeldungen übertragen" zusammen mit der Task "Datenbanken übertragen" verwendet wird, müssen die SIDs in das Ziel kopiert werden. Anderenfalls werden die übertragenen Anmeldungen nicht von der Zieldatenbank erkannt.</span><span class="sxs-lookup"><span data-stu-id="e1115-127">If the Transfer Logins task is used in conjunction with the Transfer Database task the SIDs must be copied to the destination; otherwise, the transferred logins are not recognized by the destination database.</span></span>  
  
 <span data-ttu-id="e1115-128">Am Ziel werden die übertragenen Anmeldungen deaktiviert, und ihnen werden zufällige Kennwörter zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e1115-128">At the destination, the transferred logins are disabled and assigned random passwords.</span></span> <span data-ttu-id="e1115-129">Ein Mitglied der Rolle sysadmin am Zielserver muss die Kennwörter ändern und die Anmeldungen aktivieren, bevor die Anmeldungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e1115-129">A member of the sysadmin role on the destination server must change the passwords and enable the logins before the logins can be used.</span></span>  
  
 <span data-ttu-id="e1115-130">Die zu übertragenden Anmeldungen sind eventuell bereits am Ziel vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e1115-130">The logins to be transferred may already exist on the destination.</span></span> <span data-ttu-id="e1115-131">Die Task "Anmeldungen übertragen" kann zur Verarbeitung bereits vorhandener Anmeldungen auf folgende Art und Weise konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="e1115-131">The Transfer Logins task can be configured to handle existing logins in the following ways:</span></span>  
  
-   <span data-ttu-id="e1115-132">Bereits vorhandene Anmeldungen werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1115-132">Overwrite existing logins.</span></span>  
  
-   <span data-ttu-id="e1115-133">Task schlägt fehl, wenn doppelte Anmeldungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e1115-133">Fail the task when duplicate logins exist.</span></span>  
  
-   <span data-ttu-id="e1115-134">Doppelte Anmeldungen werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="e1115-134">Skip duplicate logins.</span></span>  
  
 <span data-ttu-id="e1115-135">Zur Laufzeit stellt die Task "Anmeldungen übertragen" eine Verbindung mit den Quell- und Zielservern her. Dazu werden die SMO-Verbindungs-Manager verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1115-135">At run time, the Transfer Logins task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="e1115-136">Die SMO-Verbindungs-Manager werden getrennt von der Task "Anmeldungen übertragen" konfiguriert. Darauf wird dann in der Task "Anmeldungen übertragen" verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e1115-136">The SMO connection managers are configured separately from the Transfer Logins task, and then referenced in the Transfer Logins task.</span></span> <span data-ttu-id="e1115-137">Die SMO-Verbindungs-Manager geben den Server- und Authentifizierungsmodus an, der beim Zugriff auf den Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1115-137">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="e1115-138">Weitere Informationen finden Sie unter [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e1115-138">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e1115-139">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="e1115-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e1115-140">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e1115-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e1115-141">Editor für den Task Anmeldungen übertragen &#40;Seite Allgemein&#41;</span><span class="sxs-lookup"><span data-stu-id="e1115-141">Transfer Logins Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="e1115-142">Editor für den Task „Anmeldungen übertragen“ &#40;Seite „Anmeldungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="e1115-142">Transfer Logins Task Editor &#40;Logins Page&#41;</span></span>](../transfer-logins-task-editor-logins-page.md)  
  
-   [<span data-ttu-id="e1115-143">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e1115-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="e1115-144">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="e1115-144">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e1115-145">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="e1115-145">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-transfer-logins-task"></a><span data-ttu-id="e1115-146">Programmgesteuerte Konfiguration des Tasks "Anmeldungen übertragen"</span><span class="sxs-lookup"><span data-stu-id="e1115-146">Programmatic Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="e1115-147">Klicken Sie auf das folgende Thema, um weitere Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e1115-147">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferLoginsTask.TransferLoginsTask>  
  
  
