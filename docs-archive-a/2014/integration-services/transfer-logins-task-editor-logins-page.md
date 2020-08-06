---
title: Editor für den Task Anmeldungen übertragen (Seite Anmeldungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.logins.f1
helpviewer_keywords:
- Transfer Logins Task Editor
ms.assetid: bf244c24-bd45-4ece-b66b-78b488f35c5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33fea6c78df75b7eebe8987f952dce33bdc4407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630704"
---
# <a name="transfer-logins-task-editor-logins-page"></a><span data-ttu-id="af7f9-102">Editor für den Task Anmeldungen übertragen (Seite Anmeldungen)</span><span class="sxs-lookup"><span data-stu-id="af7f9-102">Transfer Logins Task Editor (Logins Page)</span></span>
  <span data-ttu-id="af7f9-103">Verwenden Sie die Seite **Anmeldungen** des Dialogfelds **Editor für den Task 'Anmeldungen übertragen'** , um die Eigenschaften für das Kopieren von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldungen von einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in eine andere anzugeben.</span><span class="sxs-lookup"><span data-stu-id="af7f9-103">Use the **Logins** page of the **Transfer Logins Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="af7f9-104">Weitere Informationen zu diesem Task finden Sie unter [Transfer Logins Task](control-flow/transfer-logins-task.md).</span><span class="sxs-lookup"><span data-stu-id="af7f9-104">For more information about this task, see [Transfer Logins Task](control-flow/transfer-logins-task.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af7f9-105">Wenn der Task Anmeldungen übertragen ausgeführt wird, werden auf dem Zielserver Anmeldungen mit zufällig erzeugten Kennwörtern erstellt, und die Kennwörter werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="af7f9-105">When the Transfer Logins task is executed, logins are created on the destination server with random passwords and the passwords are disabled.</span></span> <span data-ttu-id="af7f9-106">Um diese Anmeldungen zu verwenden, muss ein Mitglied der festen Serverrolle **sysadmin** die Kennwörter ändern und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="af7f9-106">To use these logins, a member of the **sysadmin** fixed server role must change the passwords and then enable them.</span></span> <span data-ttu-id="af7f9-107">Die Anmeldung **sa** kann nicht übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="af7f9-107">The **sa** login cannot be transferred.</span></span>  
  
## <a name="options"></a><span data-ttu-id="af7f9-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="af7f9-108">Options</span></span>  
 <span data-ttu-id="af7f9-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="af7f9-109">**SourceConnection**</span></span>  
 <span data-ttu-id="af7f9-110">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Quellserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af7f9-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="af7f9-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="af7f9-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="af7f9-112">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Zielserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af7f9-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="af7f9-113">**LoginsToTransfer**</span><span class="sxs-lookup"><span data-stu-id="af7f9-113">**LoginsToTransfer**</span></span>  
 <span data-ttu-id="af7f9-114">Wählen Sie die vom Quell- auf den Zielserver zu kopierenden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldungen aus.</span><span class="sxs-lookup"><span data-stu-id="af7f9-114">Select the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins to copy from the source to the destination server.</span></span> <span data-ttu-id="af7f9-115">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="af7f9-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="af7f9-116">Wert</span><span class="sxs-lookup"><span data-stu-id="af7f9-116">Value</span></span>|<span data-ttu-id="af7f9-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af7f9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af7f9-118">**AllLogins**</span><span class="sxs-lookup"><span data-stu-id="af7f9-118">**AllLogins**</span></span>|<span data-ttu-id="af7f9-119">Alle auf dem Quellserver vorhandenen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldungen werden auf den Zielserver kopiert.</span><span class="sxs-lookup"><span data-stu-id="af7f9-119">All [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins on the source server will be copied to the destination server.</span></span>|  
|<span data-ttu-id="af7f9-120">**SelectedLogins**</span><span class="sxs-lookup"><span data-stu-id="af7f9-120">**SelectedLogins**</span></span>|<span data-ttu-id="af7f9-121">Nur die mit **LoginsList** angegebenen Anmeldungen werden auf den Zielserver kopiert.</span><span class="sxs-lookup"><span data-stu-id="af7f9-121">Only logins specified with **LoginsList** will be copied to the destination server.</span></span>|  
|<span data-ttu-id="af7f9-122">**AllLoginsFromSelectedDatabases**</span><span class="sxs-lookup"><span data-stu-id="af7f9-122">**AllLoginsFromSelectedDatabases**</span></span>|<span data-ttu-id="af7f9-123">Alle Anmeldungen aus den mit **DatabasesList** angegebenen Datenbanken werden auf den Zielserver kopiert.</span><span class="sxs-lookup"><span data-stu-id="af7f9-123">All logins from the databases specified with **DatabasesList** will be copied to the destination server.</span></span>|  
  
 <span data-ttu-id="af7f9-124">**LoginsList**</span><span class="sxs-lookup"><span data-stu-id="af7f9-124">**LoginsList**</span></span>  
 <span data-ttu-id="af7f9-125">Wählen Sie die auf dem Quellserver vorhandenen Anmeldungen aus, die auf den Zielserver kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="af7f9-125">Select the logins on the source server to be copied to the destination server.</span></span> <span data-ttu-id="af7f9-126">Diese Option ist nur verfügbar, wenn für **LoginsToTransfer** **SelectedLogins**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="af7f9-126">This option is only available when **SelectedLogins** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="af7f9-127">**DatabasesList**</span><span class="sxs-lookup"><span data-stu-id="af7f9-127">**DatabasesList**</span></span>  
 <span data-ttu-id="af7f9-128">Wählen Sie die auf dem Quellserver vorhandenen Datenbanken aus, die Anmeldungen enthalten, die auf den Zielserver kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="af7f9-128">Select the databases on the source server that contain logins to be copied to the destination server.</span></span> <span data-ttu-id="af7f9-129">Diese Option ist nur verfügbar, wenn für **LoginsToTransfer** **AllLoginsFromSelectedDatabases**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="af7f9-129">This option is only available when **AllLoginsFromSelectedDatabases** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="af7f9-130">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="af7f9-130">**IfObjectExists**</span></span>  
 <span data-ttu-id="af7f9-131">Wählen Sie aus, wie der Task Anmeldungen behandeln soll, die auf dem Zielserver bereits mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="af7f9-131">Select how the task should handle logins of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="af7f9-132">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="af7f9-132">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="af7f9-133">Wert</span><span class="sxs-lookup"><span data-stu-id="af7f9-133">Value</span></span>|<span data-ttu-id="af7f9-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af7f9-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af7f9-135">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="af7f9-135">**FailTask**</span></span>|<span data-ttu-id="af7f9-136">Der Task schlägt fehl, wenn auf dem Zielserver bereits Anmeldungen mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="af7f9-136">Task fails if logins of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="af7f9-137">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="af7f9-137">**Overwrite**</span></span>|<span data-ttu-id="af7f9-138">Der Task überschreibt auf dem Zielserver Anmeldungen mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="af7f9-138">Task overwrites logins of the same name on the destination server.</span></span>|  
|<span data-ttu-id="af7f9-139">**Skip**</span><span class="sxs-lookup"><span data-stu-id="af7f9-139">**Skip**</span></span>|<span data-ttu-id="af7f9-140">Der Task lässt Anmeldungen aus, die auf dem Zielserver mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="af7f9-140">Task skips logins of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="af7f9-141">**CopySids**</span><span class="sxs-lookup"><span data-stu-id="af7f9-141">**CopySids**</span></span>  
 <span data-ttu-id="af7f9-142">Wählen Sie aus, ob die den Anmeldungen zugeordneten Sicherheits-IDs auf den Zielserver kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="af7f9-142">Select whether the security identifiers associated with the logins should be copied to the destination server.</span></span> <span data-ttu-id="af7f9-143">**CopySids** muss auf **True** festgelegt sein, wenn der Task Anmeldungen übertragen zusammen mit dem Task Datenbanken übertragen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="af7f9-143">**CopySids** must be set to **True** if the Transfer Logins task is used along with the Transfer Database task.</span></span> <span data-ttu-id="af7f9-144">Anderenfalls werden die kopierten Anmeldungen von der übertragenen Datenbank nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="af7f9-144">Otherwise, the copied logins will not be recognized by the transferred database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7f9-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af7f9-145">See Also</span></span>  
 <span data-ttu-id="af7f9-146">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-146">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="af7f9-147">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-147">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="af7f9-148">[Editor für den Task Anmeldungen übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-148">[Transfer Logins Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="af7f9-149">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-149">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="af7f9-150">[SMO-Verbindungs-Manager](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-150">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="af7f9-151">[Sichere Kennwörter](../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="af7f9-151">[Strong Passwords](../relational-databases/security/strong-passwords.md) </span></span>  
 [<span data-ttu-id="af7f9-152">Überlegungen zur Sicherheit bei SQL Server-Installationen</span><span class="sxs-lookup"><span data-stu-id="af7f9-152">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
