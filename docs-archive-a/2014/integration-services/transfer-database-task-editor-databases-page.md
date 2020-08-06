---
title: Editor für den Task Datenbanken übertragen (Seite Datenbanken) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.database.f1
helpviewer_keywords:
- Transfer Database Task Editor
ms.assetid: ccdb74d0-4bea-420c-a726-2e0eb8957e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df4452e28a32463a7825e9c64cfd053f98c53ee8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694642"
---
# <a name="transfer-database-task-editor-databases-page"></a><span data-ttu-id="41a49-102">Editor für den Task Datenbanken übertragen (Seite Datenbanken)</span><span class="sxs-lookup"><span data-stu-id="41a49-102">Transfer Database Task Editor (Databases Page)</span></span>
  <span data-ttu-id="41a49-103">Verwenden Sie die Seite **Datenbanken** des Dialogfelds **Editor für den Task Datenbanken übertragen** , um die Eigenschaften für die im Task Datenbanken übertragen verwendeten Quell- und Zieldatenbanken anzugeben.</span><span class="sxs-lookup"><span data-stu-id="41a49-103">Use the **Databases** page of the **Transfer Database Task Editor** dialog box to specify properties for the source and destination databases involved in the Transfer Database task.</span></span> <span data-ttu-id="41a49-104">Der Task Datenbanken übertragen kopiert oder verschiebt eine [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank zwischen zwei Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41a49-104">The Transfer Database task copies or moves a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database between two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="41a49-105">Dieser Task kann auch verwendet werden, um eine Datenbank innerhalb desselben Servers zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="41a49-105">This task can also be used to copy a database within the same server.</span></span> <span data-ttu-id="41a49-106">Weitere Informationen zu diesem Task finden Sie unter [Datenbanken übertragen (Task)](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="41a49-106">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="41a49-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="41a49-107">Options</span></span>  
 <span data-ttu-id="41a49-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="41a49-108">**SourceConnection**</span></span>  
 <span data-ttu-id="41a49-109">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Quellserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="41a49-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="41a49-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="41a49-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="41a49-111">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Zielserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="41a49-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="41a49-112">**DestinationDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="41a49-112">**DestinationDatabaseName**</span></span>  
 <span data-ttu-id="41a49-113">Geben Sie den Namen der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank auf dem Zielserver an.</span><span class="sxs-lookup"><span data-stu-id="41a49-113">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database on the destination server.</span></span>  
  
 <span data-ttu-id="41a49-114">Um dieses Feld automatisch mit dem Namen der Quelldatenbank aufzufüllen, geben Sie zuerst die **SourceConnection** (Quellverbindung) und den **SourceDatabaseName** (Quelldatenbanknamen) an.</span><span class="sxs-lookup"><span data-stu-id="41a49-114">To automatically populate this field with the source database name, specify the **SourceConnection** and **SourceDatabaseName** first.</span></span>  
  
 <span data-ttu-id="41a49-115">Um die Datenbank auf dem Zielserver umzubenennen, geben Sie in diesem Feld den neuen Namen an.</span><span class="sxs-lookup"><span data-stu-id="41a49-115">To rename the database on the destination server, type the new name in this field.</span></span>  
  
 <span data-ttu-id="41a49-116">**DestinationDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="41a49-116">**DestinationDatabaseFiles**</span></span>  
 <span data-ttu-id="41a49-117">Gibt die Namen und Speicherorte der Datenbankdateien auf dem Zielserver an.</span><span class="sxs-lookup"><span data-stu-id="41a49-117">Specifies the names and locations of the database files on the destination server.</span></span>  
  
 <span data-ttu-id="41a49-118">Um dieses Feld automatisch mit den Namen und Speicherorten der Quelldatenbankdateien aufzufüllen, geben Sie zuerst die **SourceConnection**(Quellverbindung), den **SourceDatabaseName**(Quelldatenbanknamen) und die **SourceDatabaseFiles** (Quelldatenbankdateien) an.</span><span class="sxs-lookup"><span data-stu-id="41a49-118">To automatically populate this field with the source database file names and locations, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first.</span></span>  
  
 <span data-ttu-id="41a49-119">Um die Datenbankdateien umzubenennen oder neue Speicherorte auf dem Zielserver anzugeben, tragen Sie in diesem Feld die Quelldatenbankinformationen ein und klicken dann auf die Schaltfläche zum Durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="41a49-119">To rename the database files or to specify the new locations on the destination server, populate this field with the source database information, and then click the browse button.</span></span> <span data-ttu-id="41a49-120">Bearbeiten Sie im Dialogfeld **Zieldatenbankdateien** die Einträge für **Zieldatei**, **Zielordner**oder **Netzwerkdateifreigabe**.</span><span class="sxs-lookup"><span data-stu-id="41a49-120">In the **Destination database files** dialog box, edit the **Destination File**, **Destination Folder**, or **Network File Share**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41a49-121">Wenn Sie die Datenbankdateien über die Schaltfläche zum Durchsuchen auswählen, wird der Dateispeicherort in der Notation des lokalen Laufwerks angegeben, z.B. C:\\.</span><span class="sxs-lookup"><span data-stu-id="41a49-121">If you locate the database files by using the browse button, the file location is entered using the local drive notation: for example, c:\\.</span></span> <span data-ttu-id="41a49-122">Diese müssen Sie durch die Notation der Netzwerkfreigabe ersetzen, einschließlich des Computernamens und des Freigabenamens.</span><span class="sxs-lookup"><span data-stu-id="41a49-122">You must replace this with the network share notation, including the computer name and share name.</span></span> <span data-ttu-id="41a49-123">Wenn die standardmäßige Administrationsfreigabe verwendet wird, müssen Sie die $-Notation verwenden und über Administratorzugriff auf die Freigabe verfügen.</span><span class="sxs-lookup"><span data-stu-id="41a49-123">If the default administrative share is used, you must use the $ notation, and have administrative access to the share.</span></span>  
  
 <span data-ttu-id="41a49-124">**DestinationOverwrite**</span><span class="sxs-lookup"><span data-stu-id="41a49-124">**DestinationOverwrite**</span></span>  
 <span data-ttu-id="41a49-125">Geben Sie an, ob die Datenbank auf dem Zielserver überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="41a49-125">Specify whether the database on the destination server can be overwritten.</span></span>  
  
 <span data-ttu-id="41a49-126">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="41a49-126">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="41a49-127">Wert</span><span class="sxs-lookup"><span data-stu-id="41a49-127">Value</span></span>|<span data-ttu-id="41a49-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41a49-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41a49-129">**True**</span><span class="sxs-lookup"><span data-stu-id="41a49-129">**True**</span></span>|<span data-ttu-id="41a49-130">Zielserverdatenbank überschreiben.</span><span class="sxs-lookup"><span data-stu-id="41a49-130">Overwrite destination server database.</span></span>|  
|<span data-ttu-id="41a49-131">**False**</span><span class="sxs-lookup"><span data-stu-id="41a49-131">**False**</span></span>|<span data-ttu-id="41a49-132">Zielserverdatenbank nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="41a49-132">Do not overwrite destination server database.</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="41a49-133">Die Daten in der Zielserverdatenbank werden überschrieben, wenn Sie für **DestinationOverwrite** **True**angeben. Dies kann zu Datenverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="41a49-133">The data in the destination server database will be overwritten if you specify **True** for **DestinationOverwrite**, which may result in data loss.</span></span> <span data-ttu-id="41a49-134">Um dies zu vermeiden, sollten Sie die Zielserverdatenbank an einem anderen Speicherort sichern, bevor Sie den Task Datenbanken übertragen ausführen.</span><span class="sxs-lookup"><span data-stu-id="41a49-134">To avoid this, back up the destination server database to another location before executing the Transfer Database task.</span></span>  
  
 <span data-ttu-id="41a49-135">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="41a49-135">**Action**</span></span>  
 <span data-ttu-id="41a49-136">Gibt an, ob der Task die Datenbank auf den Zielserver kopiert ( **Kopieren** ) oder verschiebt ( **Verschieben** ).</span><span class="sxs-lookup"><span data-stu-id="41a49-136">Specify whether the task will **Copy** or **Move** the database to the destination server.</span></span>  
  
 <span data-ttu-id="41a49-137">**Methode**</span><span class="sxs-lookup"><span data-stu-id="41a49-137">**Method**</span></span>  
 <span data-ttu-id="41a49-138">Gibt an, ob der Task ausgeführt wird, während sich die Datenbank auf dem Quellserver im Online- oder Offlinemodus befindet.</span><span class="sxs-lookup"><span data-stu-id="41a49-138">Specify whether the task will be executed while the database on the source server is in online or offline mode.</span></span>  
  
 <span data-ttu-id="41a49-139">Um eine Datenbank im Offlinemodus zu übertragen, muss der Benutzer, der das Paket ausführt, ein Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="41a49-139">To transfer a database using offline mode, the user that runs the package must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="41a49-140">Um eine Datenbank im Onlinemodus zu übertragen, muss der Benutzer, der das Paket ausführt, ein Mitglied der festen Serverrolle **sysadmin** oder der Besitzer (**dbo**) der ausgewählten Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="41a49-140">To transfer a database using the online mode, the user that runs the package must be a member of the **sysadmin** fixed server role, or the database owner (**dbo**) of the selected database.</span></span>  
  
 <span data-ttu-id="41a49-141">**SourceDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="41a49-141">**SourceDatabaseName**</span></span>  
 <span data-ttu-id="41a49-142">Wählen Sie den Namen der zu kopierenden oder zu verschiebenden Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="41a49-142">Select the name of the database to be copied or moved.</span></span>  
  
 <span data-ttu-id="41a49-143">**SourceDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="41a49-143">**SourceDatabaseFiles**</span></span>  
 <span data-ttu-id="41a49-144">Klicken Sie auf die Schaltfläche zum Durchsuchen, um die Datenbankdateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="41a49-144">Click the browse button to select the database files.</span></span>  
  
 <span data-ttu-id="41a49-145">**ReattachSourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="41a49-145">**ReattachSourceDatabase**</span></span>  
 <span data-ttu-id="41a49-146">Geben Sie an, ob der Task versuchen soll, die Quelldatenbank wieder anzufügen, falls ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="41a49-146">Specify whether the task will attempt to reattach the source database if a failure occurs.</span></span>  
  
 <span data-ttu-id="41a49-147">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="41a49-147">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="41a49-148">Wert</span><span class="sxs-lookup"><span data-stu-id="41a49-148">Value</span></span>|<span data-ttu-id="41a49-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41a49-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41a49-150">**True**</span><span class="sxs-lookup"><span data-stu-id="41a49-150">**True**</span></span>|<span data-ttu-id="41a49-151">Quelldatenbank wieder anfügen.</span><span class="sxs-lookup"><span data-stu-id="41a49-151">Reattach source database.</span></span>|  
|<span data-ttu-id="41a49-152">**False**</span><span class="sxs-lookup"><span data-stu-id="41a49-152">**False**</span></span>|<span data-ttu-id="41a49-153">Quelldatenbank nicht wieder anfügen.</span><span class="sxs-lookup"><span data-stu-id="41a49-153">Do not reattach source database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41a49-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41a49-154">See Also</span></span>  
 <span data-ttu-id="41a49-155">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="41a49-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="41a49-156">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="41a49-156">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="41a49-157">[Editor für den Task Datenbanken übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="41a49-157">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="41a49-158">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="41a49-158">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="41a49-159">SMO-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="41a49-159">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
