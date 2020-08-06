---
title: Editor für den Task ' Master ' gespeicherte Prozeduren übertragen ' Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.storedprocedures.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f9fad408b54d4ef27d4c5d06b0d352f366ad9c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718457"
---
# <a name="transfer-master-stored-procedures-task-editor-stored-procedures-page"></a><span data-ttu-id="0a705-102">Editor für den Task 'In 'master' gespeicherte Prozeduren übertragen' (Seite Gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="0a705-102">Transfer Master Stored Procedures Task Editor (Stored Procedures Page)</span></span>
  <span data-ttu-id="0a705-103">Verwenden Sie die Seite **Gespeicherte Prozeduren** im Dialogfeld **Editor für den Task „In 'master' gespeicherte Prozeduren übertragen“** , um die Eigenschaften für das Kopieren einer oder mehrerer benutzerdefinierter gespeicherter Prozeduren aus der **master** -Datenbank einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in die **master** -Datenbank einer anderen Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="0a705-103">Use the **Stored Procedures** page of the **Transfer Master Stored Procedures Task Editor** dialog box to specify properties for copying one or more user-defined stored procedures from the **master** database in one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to a **master** database in another instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0a705-104">Weitere Informationen zu diesem Task finden Sie unter [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="0a705-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a705-105">Dieser Task überträgt lediglich die benutzerdefinierten gespeicherten Prozeduren des **dbo** -Besitzers aus einer **master** -Datenbank auf dem Quellserver in eine **master** -Datenbank auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="0a705-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="0a705-106">Benutzer müssen die CREATE PROCEDURE-Berechtigung für die **master** -Datenbank des Zielservers besitzen oder Mitglieder der festen Serverrolle **sysadmin** auf dem Zielserver sein, um dort gespeicherte Prozeduren erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="0a705-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a705-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0a705-107">Options</span></span>  
 <span data-ttu-id="0a705-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="0a705-108">**SourceConnection**</span></span>  
 <span data-ttu-id="0a705-109">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Quellserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a705-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="0a705-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="0a705-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="0a705-111">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Zielserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a705-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="0a705-112">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="0a705-112">**IfObjectExists**</span></span>  
 <span data-ttu-id="0a705-113">Wählen Sie aus, wie der Task benutzerdefinierte gespeicherte Prozeduren behandeln soll, die in der **master** -Datenbank auf dem Zielserver bereits mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0a705-113">Select how the task should handle user-defined stored procedures of the same name that already exist in the **master** database on the destination server.</span></span>  
  
 <span data-ttu-id="0a705-114">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0a705-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="0a705-115">Wert</span><span class="sxs-lookup"><span data-stu-id="0a705-115">Value</span></span>|<span data-ttu-id="0a705-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a705-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0a705-117">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="0a705-117">**FailTask**</span></span>|<span data-ttu-id="0a705-118">Der Task schlägt fehl, wenn in der **master** -Datenbank auf dem Zielserver bereits gespeicherte Prozeduren mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0a705-118">Task fails if stored procedures of the same name already exist in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="0a705-119">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="0a705-119">**Overwrite**</span></span>|<span data-ttu-id="0a705-120">Der Task überschreibt bereits vorhandene gespeicherte Prozeduren mit demselben Namen in der **master** -Datenbank auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="0a705-120">Task overwrites stored procedures of the same name in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="0a705-121">**Skip**</span><span class="sxs-lookup"><span data-stu-id="0a705-121">**Skip**</span></span>|<span data-ttu-id="0a705-122">Der Task lässt bereits vorhandene gespeicherte Prozeduren mit demselben Namen in der **master** -Datenbank auf dem Zielserver aus.</span><span class="sxs-lookup"><span data-stu-id="0a705-122">Task skips stored procedures of the same name that exist in the **master** database on the destination server.</span></span>|  
  
 <span data-ttu-id="0a705-123">**TransferAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="0a705-123">**TransferAllStoredProcedures**</span></span>  
 <span data-ttu-id="0a705-124">Wählen Sie aus, ob alle benutzerdefinierten gespeicherten Prozeduren in der **master** -Datenbank auf dem Quellserver auf den Zielserver kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a705-124">Select whether all user-defined stored procedures in the **master** database on the source server should be copied to the destination server.</span></span>  
  
|<span data-ttu-id="0a705-125">value</span><span class="sxs-lookup"><span data-stu-id="0a705-125">Value</span></span>|<span data-ttu-id="0a705-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a705-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0a705-127">**True**</span><span class="sxs-lookup"><span data-stu-id="0a705-127">**True**</span></span>|<span data-ttu-id="0a705-128">Kopiert alle benutzerdefinierten gespeicherten Prozeduren in der **master** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0a705-128">Copy all user-defined stored procedures in the **master** database.</span></span>|  
|<span data-ttu-id="0a705-129">**False**</span><span class="sxs-lookup"><span data-stu-id="0a705-129">**False**</span></span>|<span data-ttu-id="0a705-130">Kopiert nur die angegebenen gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="0a705-130">Copy only the specified stored procedures.</span></span>|  
  
 <span data-ttu-id="0a705-131">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="0a705-131">**StoredProceduresList**</span></span>  
 <span data-ttu-id="0a705-132">Wählen Sie aus, welche benutzerdefinierten gespeicherten Prozeduren in der **master** -Datenbank auf dem Quellserver in die **master** -Datenbank auf dem Zielserver kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a705-132">Select which user-defined stored procedures in the **master** database on the source server should be copied to the destination **master** database.</span></span> <span data-ttu-id="0a705-133">Diese Option ist nur verfügbar, wenn **TransferAllStoredProcedures** auf **FALSE**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0a705-133">This option is only available when **TransferAllStoredProcedures** is set to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a705-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a705-134">See Also</span></span>  
 <span data-ttu-id="0a705-135">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0a705-135">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0a705-136">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="0a705-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="0a705-137">[Editor für den Task "Master gespeicherte Prozeduren übertragen" &#40;&#41;Seite](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0a705-137">[Transfer Master Stored Procedures Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="0a705-138">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="0a705-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="0a705-139">SMO-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="0a705-139">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
