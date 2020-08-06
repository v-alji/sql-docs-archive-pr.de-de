---
title: Editor für den Task ' SQL Server Objekte übertragen ' (Seite Objekte) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfersqlserverobjects.objects.f1
helpviewer_keywords:
- Transfer SQL Server Objects Task Editor
ms.assetid: 8cc09118-70ac-4013-8308-d87f8411ca0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7038939b02d17b2449a374be51f7f9fa42eae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718451"
---
# <a name="transfer-sql-server-objects-task-editor-objects-page"></a><span data-ttu-id="d408a-102">Editor für den Task 'SQL Server-Objekte übertragen' (Seite Objekte)</span><span class="sxs-lookup"><span data-stu-id="d408a-102">Transfer SQL Server Objects Task Editor (Objects Page)</span></span>
  <span data-ttu-id="d408a-103">Verwenden Sie die Seite **Objekte** des Dialogfelds **Editor für den Task 'SQL Server-Objekte übertragen'** , um die Eigenschaften für das Kopieren eines oder mehrerer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte von einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in eine andere anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d408a-103">Use the **Objects** page of the **Transfer SQL Server Objects Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="d408a-104">Tabellen, Sichten, gespeicherte Prozeduren und benutzerdefinierte Funktionen sind beispielsweise [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte, die Sie kopieren können.</span><span class="sxs-lookup"><span data-stu-id="d408a-104">Tables, views, stored procedures, and user-defined functions are a few examples of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects that you can copy.</span></span> <span data-ttu-id="d408a-105">Weitere Informationen zu diesem Task finden Sie unter [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span><span class="sxs-lookup"><span data-stu-id="d408a-105">For more information about this task, see [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d408a-106">Der Benutzer, der den Task „ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte übertragen“ erstellt, benötigt die entsprechende Berechtigung, die Quellserverobjekte zum Kopieren auszuwählen, sowie die Berechtigung, auf die Datenbank des Zielservers zuzugreifen, auf den die Objekte übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="d408a-106">The user who creates the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task must have sufficient permissions on the source server objects to select them for copying, and permission to access the destination server database where the objects will be transferred.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="d408a-107">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="d408a-107">Static Options</span></span>  
 <span data-ttu-id="d408a-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="d408a-108">**SourceConnection**</span></span>  
 <span data-ttu-id="d408a-109">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Quellserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d408a-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="d408a-110">**SourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="d408a-110">**SourceDatabase**</span></span>  
 <span data-ttu-id="d408a-111">Wählen Sie eine Datenbank auf dem Quellserver aus, aus der die Objekte kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-111">Select a database on the source server from which objects will be copied.</span></span>  
  
 <span data-ttu-id="d408a-112">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="d408a-112">**DestinationConnection**</span></span>  
 <span data-ttu-id="d408a-113">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Zielserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d408a-113">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="d408a-114">**DestinationDatabase**</span><span class="sxs-lookup"><span data-stu-id="d408a-114">**DestinationDatabase**</span></span>  
 <span data-ttu-id="d408a-115">Wählen Sie eine Datenbank auf dem Zielserver aus, auf den die Objekte kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-115">Select a database on the destination server to which objects will be copied.</span></span>  
  
 <span data-ttu-id="d408a-116">**DropObjectsFirst**</span><span class="sxs-lookup"><span data-stu-id="d408a-116">**DropObjectsFirst**</span></span>  
 <span data-ttu-id="d408a-117">Bestimmen Sie, ob die ausgewählten Objekte vor dem Kopieren zuerst auf dem Zielserver gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-117">Select whether the selected objects will be dropped first on the destination server before copying.</span></span>  
  
 <span data-ttu-id="d408a-118">**IncludeExtendedProperties**</span><span class="sxs-lookup"><span data-stu-id="d408a-118">**IncludeExtendedProperties**</span></span>  
 <span data-ttu-id="d408a-119">Bestimmen Sie, ob erweiterte Eigenschaften beim Kopieren von Objekten vom Quellserver auf den Zielserver beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-119">Select whether extended properties will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="d408a-120">**CopyData**</span><span class="sxs-lookup"><span data-stu-id="d408a-120">**CopyData**</span></span>  
 <span data-ttu-id="d408a-121">Bestimmen Sie, ob beim Kopieren von Objekten vom Quellserver auf den Zielserver Daten beinhaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-121">Select whether data will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="d408a-122">**ExistingData**</span><span class="sxs-lookup"><span data-stu-id="d408a-122">**ExistingData**</span></span>  
 <span data-ttu-id="d408a-123">Bestimmen Sie, wie die Daten auf den Zielserver kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-123">Specify how data will be copied to the destination server.</span></span> <span data-ttu-id="d408a-124">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="d408a-124">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="d408a-125">Wert</span><span class="sxs-lookup"><span data-stu-id="d408a-125">Value</span></span>|<span data-ttu-id="d408a-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d408a-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d408a-127">**Replace**</span><span class="sxs-lookup"><span data-stu-id="d408a-127">**Replace**</span></span>|<span data-ttu-id="d408a-128">Daten auf dem Zielserver werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="d408a-128">Data on the destination server will be overwritten.</span></span>|  
|<span data-ttu-id="d408a-129">**Append**</span><span class="sxs-lookup"><span data-stu-id="d408a-129">**Append**</span></span>|<span data-ttu-id="d408a-130">Die vom Quellserver kopierten Daten werden an die vorhandenen Daten auf dem Zielserver angehängt.</span><span class="sxs-lookup"><span data-stu-id="d408a-130">Data copied from the source server will be appended to existing data on the destination server.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="d408a-131">Die Option **ExistingData** ist nur verfügbar, wenn **CopyData** auf **True**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d408a-131">The **ExistingData** option is only available when **CopyData** is set to **True**.</span></span>  
  
 <span data-ttu-id="d408a-132">**CopySchema**</span><span class="sxs-lookup"><span data-stu-id="d408a-132">**CopySchema**</span></span>  
 <span data-ttu-id="d408a-133">Bestimmen Sie, ob mit dem Task „ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte übertragen“ auch das Schema kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-133">Select whether the schema is copied during the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d408a-134">**CopySchema** ist nur für [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d408a-134">**CopySchema** is only available for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-135">**UseCollation**</span><span class="sxs-lookup"><span data-stu-id="d408a-135">**UseCollation**</span></span>  
 <span data-ttu-id="d408a-136">Bestimmen Sie, ob die Übertragung von Objekten die auf dem Quellserver angegebene Sortierung beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-136">Select whether the transfer of objects should include the collation specified on the source server.</span></span>  
  
 <span data-ttu-id="d408a-137">**IncludeDependentObjects**</span><span class="sxs-lookup"><span data-stu-id="d408a-137">**IncludeDependentObjects**</span></span>  
 <span data-ttu-id="d408a-138">Bestimmen Sie, ob beim Kopieren auch die kaskadierenden Objekte, die von den für das Kopieren ausgewählten Objekten abhängig sind, kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-138">Select whether copying the selected objects will cascade to include other objects that depend on the objects selected for copying.</span></span>  
  
 <span data-ttu-id="d408a-139">**CopyAllObjects**</span><span class="sxs-lookup"><span data-stu-id="d408a-139">**CopyAllObjects**</span></span>  
 <span data-ttu-id="d408a-140">Bestimmen Sie, ob der Task alle Objekte der angegebenen Quelldatenbank oder nur die ausgewählten Objekte kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-140">Select whether the task will copy all objects in the specified source database or only selected objects.</span></span>  <span data-ttu-id="d408a-141">Wenn Sie diese Option auf False festlegen, haben Sie die Möglichkeit, die zu übertragenden Objekte auszuwählen. Dazu werden dann die dynamischen Optionen des Bereichs **CopyAllObjects**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d408a-141">Setting this option to False gives you the option to select the objects to transfer, and displays the dynamic options in the section, **CopyAllObjects**.</span></span>  
  
 <span data-ttu-id="d408a-142">**ObjectsToCopy**</span><span class="sxs-lookup"><span data-stu-id="d408a-142">**ObjectsToCopy**</span></span>  
 <span data-ttu-id="d408a-143">Erweitern Sie **ObjectsToCopy** , um anzugeben, welche Objekte von der Quelldatenbank in die Zieldatenbank kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-143">Expand **ObjectsToCopy** to specify which objects should be copied from the source database to the destination database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d408a-144">**ObjectsToCopy** ist nur verfügbar, wenn **CopyAllObjects** auf **False**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d408a-144">**ObjectsToCopy** is only available when **CopyAllObjects** is set to **False**.</span></span>  
  
 <span data-ttu-id="d408a-145">Die Optionen zum Kopieren der folgenden Objekttypen werden nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d408a-145">The options to copy the following types of objects are supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="d408a-146">Assemblys</span><span class="sxs-lookup"><span data-stu-id="d408a-146">Assemblies</span></span>  
  
 <span data-ttu-id="d408a-147">Partitionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d408a-147">Partition functions</span></span>  
  
 <span data-ttu-id="d408a-148">Partitionsschemas</span><span class="sxs-lookup"><span data-stu-id="d408a-148">Partition schemes</span></span>  
  
 <span data-ttu-id="d408a-149">Schemas</span><span class="sxs-lookup"><span data-stu-id="d408a-149">Schemas</span></span>  
  
 <span data-ttu-id="d408a-150">Benutzerdefinierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="d408a-150">User-defined aggregates</span></span>  
  
 <span data-ttu-id="d408a-151">Benutzerdefinierte Typen</span><span class="sxs-lookup"><span data-stu-id="d408a-151">User-defined types</span></span>  
  
 <span data-ttu-id="d408a-152">XML-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="d408a-152">XML schema collections</span></span>  
  
 <span data-ttu-id="d408a-153">**CopyDatabaseUsers**</span><span class="sxs-lookup"><span data-stu-id="d408a-153">**CopyDatabaseUsers**</span></span>  
 <span data-ttu-id="d408a-154">Geben Sie an, ob die Übertragung Datenbankbenutzer beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-154">Specify whether database users should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-155">**CopyDatabaseRoles**</span><span class="sxs-lookup"><span data-stu-id="d408a-155">**CopyDatabaseRoles**</span></span>  
 <span data-ttu-id="d408a-156">Geben Sie an, ob die Übertragung Datenbankrollen beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-156">Specify whether database roles should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-157">**CopySqlServerLogins**</span><span class="sxs-lookup"><span data-stu-id="d408a-157">**CopySqlServerLogins**</span></span>  
 <span data-ttu-id="d408a-158">Geben Sie an, ob die Übertragung [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldungen beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-158">Specify whether [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-159">**CopyObjectLevelPermissions**</span><span class="sxs-lookup"><span data-stu-id="d408a-159">**CopyObjectLevelPermissions**</span></span>  
 <span data-ttu-id="d408a-160">Geben Sie an, ob die Übertragung Berechtigungen auf Objektebene beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-160">Specify whether object-level permissions should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-161">**CopyIndexes**</span><span class="sxs-lookup"><span data-stu-id="d408a-161">**CopyIndexes**</span></span>  
 <span data-ttu-id="d408a-162">Geben Sie an, ob die Übertragung Indizes beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-162">Specify whether indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-163">**CopyTriggers**</span><span class="sxs-lookup"><span data-stu-id="d408a-163">**CopyTriggers**</span></span>  
 <span data-ttu-id="d408a-164">Geben Sie an, ob die Übertragung Trigger beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-164">Specify whether triggers should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-165">**CopyFullTextIndexes**</span><span class="sxs-lookup"><span data-stu-id="d408a-165">**CopyFullTextIndexes**</span></span>  
 <span data-ttu-id="d408a-166">Geben Sie an, ob die Übertragung Volltextindizes beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-166">Specify whether full-text indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-167">**CopyPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="d408a-167">**CopyPrimaryKeys**</span></span>  
 <span data-ttu-id="d408a-168">Geben Sie an, ob die Übertragung Primärschlüssel beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-168">Specify whether primary keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-169">**CopyForeignKeys**</span><span class="sxs-lookup"><span data-stu-id="d408a-169">**CopyForeignKeys**</span></span>  
 <span data-ttu-id="d408a-170">Geben Sie an, ob die Übertragung Fremdschlüssel beinhalten soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-170">Specify whether foreign keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="d408a-171">**GenerateScriptsInUnicode**</span><span class="sxs-lookup"><span data-stu-id="d408a-171">**GenerateScriptsInUnicode**</span></span>  
 <span data-ttu-id="d408a-172">Geben Sie an, ob die generierten Übertragungsskripts das Unicode-Format aufweisen sollen.</span><span class="sxs-lookup"><span data-stu-id="d408a-172">Specify whether the generated transfer scripts are in Unicode format.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="d408a-173">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="d408a-173">Dynamic Options</span></span>  
  
### <a name="copyallobjects--false"></a><span data-ttu-id="d408a-174">CopyAllObjects = False</span><span class="sxs-lookup"><span data-stu-id="d408a-174">CopyAllObjects = False</span></span>  
 <span data-ttu-id="d408a-175">**CopyAllTables**</span><span class="sxs-lookup"><span data-stu-id="d408a-175">**CopyAllTables**</span></span>  
 <span data-ttu-id="d408a-176">Bestimmen Sie, ob der Task alle Tabellen der angegebenen Quelldatenbank oder nur die ausgewählten Tabellen kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-176">Select whether the task will copy all tables in the specified source database or only the selected tables.</span></span>  
  
 <span data-ttu-id="d408a-177">**TablesList**</span><span class="sxs-lookup"><span data-stu-id="d408a-177">**TablesList**</span></span>  
 <span data-ttu-id="d408a-178">Klicken Sie auf diese Option, um das Dialogfeld **Tabellen auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-178">Click to open the **Select Tables** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-179">**CopyAllViews**</span><span class="sxs-lookup"><span data-stu-id="d408a-179">**CopyAllViews**</span></span>  
 <span data-ttu-id="d408a-180">Bestimmen Sie, ob der Task alle Sichten der angegebenen Quelldatenbank oder nur die ausgewählten Sichten kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-180">Select whether the task will copy all views in the specified source database or only the selected views.</span></span>  
  
 <span data-ttu-id="d408a-181">**ViewsList**</span><span class="sxs-lookup"><span data-stu-id="d408a-181">**ViewsList**</span></span>  
 <span data-ttu-id="d408a-182">Klicken Sie auf diese Option, um das Dialogfeld **Sichten auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-182">Click to open the **Select Views** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-183">**CopyAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="d408a-183">**CopyAllStoredProcedures**</span></span>  
 <span data-ttu-id="d408a-184">Bestimmen Sie, ob der Task alle benutzerdefinierten gespeicherten Prozeduren der angegebenen Quelldatenbank oder nur die ausgewählten Prozeduren kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-184">Select whether the task will copy all user-defined stored procedures in the specified source database or only the selected procedures.</span></span>  
  
 <span data-ttu-id="d408a-185">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="d408a-185">**StoredProceduresList**</span></span>  
 <span data-ttu-id="d408a-186">Klicken Sie auf diese Option, um das Dialogfeld **Gespeicherte Prozeduren auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-186">Click to open the **Select Stored Procedures** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-187">**CopyAllUserDefinedFunctions**</span><span class="sxs-lookup"><span data-stu-id="d408a-187">**CopyAllUserDefinedFunctions**</span></span>  
 <span data-ttu-id="d408a-188">Bestimmen Sie, ob der Task alle benutzerdefinierten Funktionen der angegebenen Quelldatenbank oder nur die ausgewählten benutzerdefinierten Prozeduren kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-188">Select whether the task will copy all user-defined functions in the specified source database or only the selected UDFs.</span></span>  
  
 <span data-ttu-id="d408a-189">**UserDefinedFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="d408a-189">**UserDefinedFunctionsList**</span></span>  
 <span data-ttu-id="d408a-190">Klicken Sie auf diese Option, um das Dialogfeld **Benutzerdefinierte Funktionen auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-190">Click to open the **Select User Defined Functions** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-191">**CopyAllDefaults**</span><span class="sxs-lookup"><span data-stu-id="d408a-191">**CopyAllDefaults**</span></span>  
 <span data-ttu-id="d408a-192">Bestimmen Sie, ob der Task alle Standardwerte der angegebenen Quelldatenbank oder nur die ausgewählten Standardwerte kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-192">Select whether the task will copy all defaults in the specified source database or only the selected defaults.</span></span>  
  
 <span data-ttu-id="d408a-193">**DefaultsList**</span><span class="sxs-lookup"><span data-stu-id="d408a-193">**DefaultsList**</span></span>  
 <span data-ttu-id="d408a-194">Klicken Sie auf diese Option, um das Dialogfeld **Standardwerte auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-194">Click to open the **Select Defaults** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-195">**CopyAllUserDefinedDataTypes**</span><span class="sxs-lookup"><span data-stu-id="d408a-195">**CopyAllUserDefinedDataTypes**</span></span>  
 <span data-ttu-id="d408a-196">Bestimmen Sie, ob der Task alle benutzerdefinierten Datentypen der angegebenen Quelldatenbank oder nur die ausgewählten benutzerdefinierten Datentypen kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-196">Select whether the task will copy all user-defined data types in the specified source database or only the selected user-defined data types.</span></span>  
  
 <span data-ttu-id="d408a-197">**UserDefinedDataTypesList**</span><span class="sxs-lookup"><span data-stu-id="d408a-197">**UserDefinedDataTypesList**</span></span>  
 <span data-ttu-id="d408a-198">Klicken Sie auf diese Option, um das Dialogfeld **Benutzerdefinierte Datentypen auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-198">Click to open the **Select User-Defined Data Types** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-199">**CopyAllPartitionFunctions**</span><span class="sxs-lookup"><span data-stu-id="d408a-199">**CopyAllPartitionFunctions**</span></span>  
 <span data-ttu-id="d408a-200">Bestimmen Sie, ob der Task alle benutzerdefinierten Partitionsfunktionen der angegebenen Quelldatenbank oder nur die ausgewählten Partitionsfunktionen kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-200">Select whether the task will copy all user-defined partition functions in the specified source database or only the selected partition functions.</span></span> <span data-ttu-id="d408a-201">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-201">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-202">**PartitionFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="d408a-202">**PartitionFunctionsList**</span></span>  
 <span data-ttu-id="d408a-203">Klicken Sie auf diese Option, um das Dialogfeld **Partitionsfunktionen auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-203">Click to open the **Select Partition Functions** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-204">**CopyAllPartitionSchemes**</span><span class="sxs-lookup"><span data-stu-id="d408a-204">**CopyAllPartitionSchemes**</span></span>  
 <span data-ttu-id="d408a-205">Bestimmen Sie, ob der Task alle Partitionsschemas der angegebenen Quelldatenbank oder nur die ausgewählten Partitionsschemas kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-205">Select whether the task will copy all partition schemes in the specified source database or only the selected partition schemes.</span></span> <span data-ttu-id="d408a-206">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-206">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-207">**PartitionSchemesList**</span><span class="sxs-lookup"><span data-stu-id="d408a-207">**PartitionSchemesList**</span></span>  
 <span data-ttu-id="d408a-208">Klicken Sie auf diese Option, um das Dialogfeld **Partitionsschemas auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-208">Click to open the **Select Partition Schemes** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-209">**CopyAllSchemas**</span><span class="sxs-lookup"><span data-stu-id="d408a-209">**CopyAllSchemas**</span></span>  
 <span data-ttu-id="d408a-210">Bestimmen Sie, ob der Task alle Schemas der angegebenen Quelldatenbank oder nur die ausgewählten Schemas kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-210">Select whether the task will copy all schemas in the specified source database or only the selected schemas.</span></span> <span data-ttu-id="d408a-211">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-211">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-212">**SchemasList**</span><span class="sxs-lookup"><span data-stu-id="d408a-212">**SchemasList**</span></span>  
 <span data-ttu-id="d408a-213">Klicken Sie auf diese Option, um das Dialogfeld **Schemas auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-213">Click to open the **Select Schemas** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-214">**CopyAllSqlAssemblies**</span><span class="sxs-lookup"><span data-stu-id="d408a-214">**CopyAllSqlAssemblies**</span></span>  
 <span data-ttu-id="d408a-215">Bestimmen Sie, ob der Task alle SQL-Assemblys der angegebenen Quelldatenbank oder nur die ausgewählten SQL-Assemblys kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-215">Select whether the task will copy all SQL assemblies in the specified source database or only the selected SQL assemblies.</span></span> <span data-ttu-id="d408a-216">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-216">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-217">**SqlAssembliesList**</span><span class="sxs-lookup"><span data-stu-id="d408a-217">**SqlAssembliesList**</span></span>  
 <span data-ttu-id="d408a-218">Klicken Sie auf diese Option, um das Dialogfeld **Assemblys auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-218">Click to open the **Select SQL Assemblies** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-219">**CopyAllUserDefinedAggregates**</span><span class="sxs-lookup"><span data-stu-id="d408a-219">**CopyAllUserDefinedAggregates**</span></span>  
 <span data-ttu-id="d408a-220">Bestimmen Sie, ob der Task alle benutzerdefinierten Aggregate der angegebenen Quelldatenbank oder nur die ausgewählten benutzerdefinierten Aggregate kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-220">Select whether the task will copy all user-defined aggregates in the specified source database or only the selected user-defined aggregates.</span></span> <span data-ttu-id="d408a-221">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-221">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-222">**UserDefinedAggregatesList**</span><span class="sxs-lookup"><span data-stu-id="d408a-222">**UserDefinedAggregatesList**</span></span>  
 <span data-ttu-id="d408a-223">Klicken Sie auf diese Option, um das Dialogfeld **Benutzerdefinierte Aggregate** auswählen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-223">Click to open the **Select User-Defined Aggregates** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-224">**CopyAllUserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="d408a-224">**CopyAllUserDefinedTypes**</span></span>  
 <span data-ttu-id="d408a-225">Bestimmen Sie, ob der Task alle benutzerdefinierten Typen der angegebenen Quelldatenbank oder nur die ausgewählten benutzerdefinierten Datentypen kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-225">Select whether the task will copy all user-defined types in the specified source database or only the selected UDTs.</span></span> <span data-ttu-id="d408a-226">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-226">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-227">**UserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="d408a-227">**UserDefinedTypes**</span></span>  
 <span data-ttu-id="d408a-228">Klicken Sie auf diese Option, um das Dialogfeld **Benutzerdefinierte Typen** auswählen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-228">Click to open the **Select User-Defined Types** dialog box.</span></span>  
  
 <span data-ttu-id="d408a-229">**CopyAllXmlSchemaCollections**</span><span class="sxs-lookup"><span data-stu-id="d408a-229">**CopyAllXmlSchemaCollections**</span></span>  
 <span data-ttu-id="d408a-230">Bestimmen Sie, ob der Task alle XML-Schemaauflistungen der angegebenen Quelldatenbank oder nur die ausgewählten XML-Schemaauflistungen kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d408a-230">Select whether the task will copy all XML Schema collections in the specified source database or only the selected XML schema collections.</span></span> <span data-ttu-id="d408a-231">Dies wird nur in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d408a-231">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d408a-232">**XmlSchemaCollectionsList**</span><span class="sxs-lookup"><span data-stu-id="d408a-232">**XmlSchemaCollectionsList**</span></span>  
 <span data-ttu-id="d408a-233">Klicken Sie auf diese Option, um das Dialogfeld **XML-Schemaauflistungen** auswählen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d408a-233">Click to open the **Select XML Schema Collections** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d408a-234">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d408a-234">See Also</span></span>  
 <span data-ttu-id="d408a-235">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d408a-235">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d408a-236">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d408a-236">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="d408a-237">[Editor für den Task „SQL Server-Objekte übertragen“ &#40;Seite „Allgemein“&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d408a-237">[Transfer SQL Server Objects Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d408a-238">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="d408a-238">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="d408a-239">[Datenformate für Massenimport oder Massenexport &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d408a-239">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 [<span data-ttu-id="d408a-240">Überlegungen zur Sicherheit bei SQL Server-Installationen</span><span class="sxs-lookup"><span data-stu-id="d408a-240">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
