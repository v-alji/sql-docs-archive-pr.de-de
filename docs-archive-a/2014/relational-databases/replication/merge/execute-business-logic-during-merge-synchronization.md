---
title: Ausführen der Geschäftslogik während der Mergesynchronisierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- custom error resolution [SQL Server replication]
- custom change handling [SQL Server replication]
- errors [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
ms.assetid: 9d4da2ef-c17f-4a31-a1f6-5c3b7ca85f71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1e082cbbb46ceae712cd39925c28fe89988a3793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607706"
---
# <a name="execute-business-logic-during-merge-synchronization"></a><span data-ttu-id="9a380-102">Ausführen der Geschäftslogik während der Mergesynchronisierung</span><span class="sxs-lookup"><span data-stu-id="9a380-102">Execute Business Logic During Merge Synchronization</span></span>
  <span data-ttu-id="9a380-103">Im Geschäftslogikhandler können Sie eine Assembly in verwaltetem Code schreiben, die während des Mergesynchronisierungsvorgangs aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9a380-103">The business logic handler framework allows you to write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="9a380-104">Die Assembly enthält Geschäftslogik, die auf viele Bedingungen während der Synchronisierung reagieren kann: Datenänderungen, Konflikte und Fehler.</span><span class="sxs-lookup"><span data-stu-id="9a380-104">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="9a380-105">Das Geschäftslogikhandler-Framework stellt ein einfaches Programmiermodell bereit. Dabei weisen die Daten, die der Mergeprozess an Ihre Assembly übergibt, das Format eines ADO.NET-Datasets auf. Auf diese Weise können Sie auf Ihren Kenntnissen von ADO.NET aufbauen und müssen sich mit keiner neuen proprietären Schnittstelle vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="9a380-105">The business logic handler framework provides a simple programming model, and the data that the merge process provides to your assembly is in the form of an ADO.NET data set, so you can leverage knowledge of ADO.NET rather than learning a proprietary interface.</span></span> <span data-ttu-id="9a380-106">Weitere Informationen zum Programmieren von Geschäftslogikhandlern finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="9a380-106">For more information on programming business logic handlers, see:</span></span>  
  
-   <span data-ttu-id="9a380-107">In der API-Referenz (Application Programming Interface, Schnittstelle für Anwendungsprogrammierung): <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span><span class="sxs-lookup"><span data-stu-id="9a380-107">The application programming interface (API) reference: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span></span>  
  
-   <span data-ttu-id="9a380-108">Anweisungen zum Implementieren eines Geschäftslogikhandlers: [Implementieren eines Geschäftslogikhandlers für einen Mergeartikel](../implement-a-business-logic-handler-for-a-merge-article.md)</span><span class="sxs-lookup"><span data-stu-id="9a380-108">Instructions on how to implement a business logic handler: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md)</span></span>  
  
## <a name="uses-for-business-logic-handlers"></a><span data-ttu-id="9a380-109">Verwendungsmöglichkeiten für Geschäftslogikhandler</span><span class="sxs-lookup"><span data-stu-id="9a380-109">Uses for Business Logic Handlers</span></span>  
 <span data-ttu-id="9a380-110">Bei der Mergesynchronisierung können Geschäftslogikhandler für folgende Zwecke aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="9a380-110">The merge synchronization process can invoke business logic handlers to perform:</span></span>  
  
-   <span data-ttu-id="9a380-111">Verarbeiten von benutzerdefinierten Änderungen</span><span class="sxs-lookup"><span data-stu-id="9a380-111">Custom change handling</span></span>  
  
-   <span data-ttu-id="9a380-112">Benutzerdefinierte Konfliktlösung</span><span class="sxs-lookup"><span data-stu-id="9a380-112">Custom conflict resolution</span></span>  
  
-   <span data-ttu-id="9a380-113">Benutzerdefinierte Fehlerbehebung</span><span class="sxs-lookup"><span data-stu-id="9a380-113">Custom error resolution</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a380-114">Der von Ihnen angegebene Geschäftslogikhandler wird für jede Zeile ausgeführt, die synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9a380-114">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="9a380-115">Eine komplexe Logik und Aufrufe anderer Anwendungen oder Netzwerkdienste können sich auf die Leistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="9a380-115">Complex logic and calls to other applications or network services can impact performance.</span></span>  
  
### <a name="custom-change-handling"></a><span data-ttu-id="9a380-116">Verarbeiten von benutzerdefinierten Änderungen</span><span class="sxs-lookup"><span data-stu-id="9a380-116">Custom Change Handling</span></span>  
 <span data-ttu-id="9a380-117">Der Geschäftslogikhandler kann bei der Verarbeitung von Datenänderungen aufgerufen werden, die keine Konflikte verursachen, und eine von drei Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="9a380-117">The business logic handler can be invoked during the processing of non-conflicting data changes and can perform one of three actions:</span></span>  
  
-   <span data-ttu-id="9a380-118">Daten ablehnen</span><span class="sxs-lookup"><span data-stu-id="9a380-118">Reject the data</span></span>  
  
     <span data-ttu-id="9a380-119">Das ist bei Anwendungen nützlich, bei denen keine Änderungen von einem oder an einen bestimmten Abonnenten weitergegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a380-119">This is useful for applications that do not want changes propagated to or from a given Subscriber.</span></span> <span data-ttu-id="9a380-120">Ein Administrator kann z.B. Einfügungen herausfiltern, die nicht in die Partition des Abonnenten gehören, oder Löschungen ablehnen, die auf einem Abonnenten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a380-120">For example, an administrator could filter out inserts that do not belong in the Subscriber's partition, or possibly reject deletes performed at a Subscriber.</span></span> <span data-ttu-id="9a380-121">Ein weiteres Beispiel ist eine Anwendung, die eine Bestellung ablehnt, die auf einem Abonnenten eingegeben wird, weil der Bestand nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9a380-121">As another example, an application could reject an order entered at a Subscriber because the inventory is no longer available.</span></span>  
  
-   <span data-ttu-id="9a380-122">Daten annehmen</span><span class="sxs-lookup"><span data-stu-id="9a380-122">Accept the data</span></span>  
  
     <span data-ttu-id="9a380-123">Das ist bei Anwendungen nützlich, bei denen Datenänderungen überprüft werden müssen, die auf dem Verleger oder dem Abonnenten vorgenommen wurden, bevor sie weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9a380-123">This is useful for applications in which it is necessary to review data changes made at either the Publisher or Subscriber before allowing them to be propagated.</span></span> <span data-ttu-id="9a380-124">Beispielsweise kann eine Anwendung der mittleren Ebene neue Bestellungen überprüfen, die über den Außendienst eingehen, und in einen Beschaffungsworkflowprozess der mittleren Ebene integrieren.</span><span class="sxs-lookup"><span data-stu-id="9a380-124">For example, a mid-tier application could examine new orders coming in from the field and integrate with a procurement workflow process in the mid-tier.</span></span>  
  
-   <span data-ttu-id="9a380-125">Benutzerdefinierte Daten anwenden</span><span class="sxs-lookup"><span data-stu-id="9a380-125">Apply custom data</span></span>  
  
     <span data-ttu-id="9a380-126">Das ist bei Anwendungen nützlich, die bestimmte Datenwerte oder Vorgänge überschreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="9a380-126">This is useful for applications that need to override specific data values or operations.</span></span> <span data-ttu-id="9a380-127">Eine Anwendung kann z. B. eine Zeilenlöschung in ein spezielles Update transformieren, das eine **status** -Spalte in der Zeile auf einen Wert "gelöscht" festlegt und dann die Identität des Clients ermittelt, der das Löschen ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="9a380-127">For example, an application could transform a row delete into a special update that sets a **status** column in the row to a value of "deleted" and then tracks the identity of the client performing the delete.</span></span> <span data-ttu-id="9a380-128">Das kann zum Überwachen und für Workflowzwecke nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="9a380-128">This might be useful for auditing or workflow purposes.</span></span>  
  
### <a name="custom-conflict-resolution"></a><span data-ttu-id="9a380-129">Benutzerdefinierte Konfliktlösung</span><span class="sxs-lookup"><span data-stu-id="9a380-129">Custom Conflict Resolution</span></span>  
 <span data-ttu-id="9a380-130">Die Mergereplikation stellt eine Konflikterkennung und -lösung bereit, mit deren Hilfe Sie eine Standardstrategie zur Konfliktlösung übernehmen oder eine benutzerdefinierte Lösung von Konflikten auswählen können.</span><span class="sxs-lookup"><span data-stu-id="9a380-130">Merge replication provides conflict detection and resolution, allowing you to accept a default resolution strategy or choose custom resolution for conflicts.</span></span> <span data-ttu-id="9a380-131">Weitere Informationen finden Sie unter [Erweiterte Konflikterkennung und -lösung bei der Mergereplikation](advanced-merge-replication-conflict-detection-and-resolution.md)angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9a380-131">For more information, see [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span></span> <span data-ttu-id="9a380-132">Der Geschäftslogikhandler kann bei der Verarbeitung von Datenänderungen aufgerufen werden, die Konflikte verursachen, und eine von zwei Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="9a380-132">The business logic handler can be invoked during the processing of conflicting data changes and can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="9a380-133">Standardlösung übernehmen</span><span class="sxs-lookup"><span data-stu-id="9a380-133">Accept default resolution</span></span>  
  
     <span data-ttu-id="9a380-134">Das ist bei Anwendungen nützlich, die einen Konflikt möglicherweise überprüfen, weitere Aktionen ausführen und gegebenenfalls eine benutzerdefinierte Konfliktmeldung protokollieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9a380-134">This is useful for applications that might need to review the conflict, perform additional actions, and possibly log a custom conflict log message.</span></span>  
  
-   <span data-ttu-id="9a380-135">Benutzerdefinierte Lösung ausführen</span><span class="sxs-lookup"><span data-stu-id="9a380-135">Perform custom resolution</span></span>  
  
     <span data-ttu-id="9a380-136">Das ist bei Anwendungen nützlich, die gegebenenfalls ihrer speziellen Geschäftslogik entsprechende Datenwerte auswählen und dieses benutzerdefinierte Dataset für den Synchronisierungsprozess bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="9a380-136">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="9a380-137">Eine Anwendung kann z. B. eine neue Version der gewinnenden Zeile bereitstellen, indem sie Werte aus den Verleger- und Abonnentendatasets kombiniert.</span><span class="sxs-lookup"><span data-stu-id="9a380-137">For example, an application could provide a new version of the winning row by combining values from the Publisher and Subscriber data sets.</span></span>  
  
### <a name="custom-error-resolution"></a><span data-ttu-id="9a380-138">Benutzerdefinierte Fehlerbehebung</span><span class="sxs-lookup"><span data-stu-id="9a380-138">Custom Error Resolution</span></span>  
 <span data-ttu-id="9a380-139">Die benutzerdefinierte Logik kann bei der Weitergabe von Änderungen aufgerufen werden, die zu einem Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="9a380-139">Custom logic can be invoked during the propagation of changes that result in errors.</span></span> <span data-ttu-id="9a380-140">Die Logik kann eine der folgenden beiden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="9a380-140">The logic can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="9a380-141">Standardfehlerbehebung übernehmen</span><span class="sxs-lookup"><span data-stu-id="9a380-141">Accept default error resolution</span></span>  
  
     <span data-ttu-id="9a380-142">Das ist bei Anwendungen nützlich, die einen Fehler möglicherweise überprüfen, weitere Aktionen ausführen und gegebenenfalls eine benutzerdefinierte Fehlermeldung protokollieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9a380-142">This is useful for applications that might need to review the error and perform additional action and possibly log a custom error log message.</span></span>  
  
-   <span data-ttu-id="9a380-143">Standardfehlerbehebung übernehmen</span><span class="sxs-lookup"><span data-stu-id="9a380-143">Accept custom error resolution</span></span>  
  
     <span data-ttu-id="9a380-144">Das ist bei Anwendungen nützlich, die gegebenenfalls ihrer speziellen Geschäftslogik entsprechende Datenwerte auswählen und dieses benutzerdefinierte Dataset für den Synchronisierungsprozess bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="9a380-144">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="9a380-145">Werden z. B. Verletzungen doppelter Schlüssel beim Replikationsprozess gefunden, kann der Geschäftslogikhandler eine neue Version der Datenänderung bereitstellen, bei der der Schlüssel keinen Konflikt mehr verursacht.</span><span class="sxs-lookup"><span data-stu-id="9a380-145">For example, if the replication process encounters a duplicate key violation, the business logic handler could provide a new version of the data change in which the key will no longer conflict.</span></span> <span data-ttu-id="9a380-146">Auf dem Verleger oder Abonnenten vorgenommene Änderungen können dann in der Datenbank persistent gespeichert werden, und der Replikationsprozess muss die fehlerhafte Einfügung nicht mehr durch eine Löschung ausgleichen.</span><span class="sxs-lookup"><span data-stu-id="9a380-146">Changes made at the Publisher and Subscriber can then persist in the database, and the replication process doesn't have to compensate for the failed insert with a delete.</span></span>  
  
## <a name="deployment-scenarios-for-business-logic-handlers"></a><span data-ttu-id="9a380-147">Bereitstellungsszenarien für Geschäftslogikhandler</span><span class="sxs-lookup"><span data-stu-id="9a380-147">Deployment Scenarios for Business Logic Handlers</span></span>  
 <span data-ttu-id="9a380-148">Folgende Stellen können Geschäftslogikhandler bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="9a380-148">Business logic handlers can be deployed at:</span></span>  
  
-   <span data-ttu-id="9a380-149">Verteiler</span><span class="sxs-lookup"><span data-stu-id="9a380-149">The Distributor.</span></span> <span data-ttu-id="9a380-150">Verwenden Sie ein Pushabonnement, damit die Geschäftslogik auf dem Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a380-150">Use a push subscription so that business logic is executed at the Distributor.</span></span>  
  
-   <span data-ttu-id="9a380-151">Der Abonnent.</span><span class="sxs-lookup"><span data-stu-id="9a380-151">The Subscriber.</span></span> <span data-ttu-id="9a380-152">Verwenden Sie ein Pullabonnement, damit die Geschäftslogik auf dem Abonnenten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a380-152">Use a pull subscription so that business logic is executed at the Subscriber.</span></span>  
  
-   <span data-ttu-id="9a380-153">Ein IIS-Server (Internetinformationsdienste), wenn die Websynchronisierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a380-153">An Internet Information Services (IIS) server if Web synchronization is used.</span></span> <span data-ttu-id="9a380-154">Verwenden Sie ein mit der Websynchronisierung synchronisiertes Pullabonnement. Der Geschäftslogikhandler wird dann auf dem IIS-Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9a380-154">Use a pull subscription synchronized with Web synchronization, and the business logic handler will execute at the IIS Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a380-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a380-155">See Also</span></span>  
 <span data-ttu-id="9a380-156">[Mergereplikation](merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9a380-156">[Merge Replication](merge-replication.md) </span></span>  
 <span data-ttu-id="9a380-157">[Abonnieren von Veröffentlichungen](../subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="9a380-157">[Subscribe to Publications](../subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="9a380-158">[Synchronisieren von Daten](../synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="9a380-158">[Synchronize Data](../synchronize-data.md) </span></span>  
 [<span data-ttu-id="9a380-159">Websynchronisierung für die Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="9a380-159">Web Synchronization for Merge Replication</span></span>](../web-synchronization-for-merge-replication.md)  
  
  
