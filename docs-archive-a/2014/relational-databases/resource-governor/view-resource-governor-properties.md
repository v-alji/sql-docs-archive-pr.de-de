---
title: Anzeigen der Eigenschaften der Ressourcenkontrolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties.f1
helpviewer_keywords:
- Resource Governor, properties
ms.assetid: de3510df-f792-4a9d-80fa-f198fd36cdc8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cd7af8f4f8eb3cd0531bc907011846f73f94f6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616468"
---
# <a name="view-resource-governor-properties"></a><span data-ttu-id="2d77f-102">Anzeigen der Eigenschaften der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="2d77f-102">View Resource Governor Properties</span></span>
  <span data-ttu-id="2d77f-103">Auf der Seite Eigenschaften der Ressourcenkontrolle in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]können Sie Ressourcenkontrollentitäten erstellen oder konfigurieren, z. B. Ressourcenpools und Arbeitsauslastungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="2d77f-103">You can create or configure Resource Governor entities, such as resource pools and workload groups, by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="2d77f-104">**Vorbereitungen:**  [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="2d77f-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="2d77f-105">**Eigenschaften der Ressourcenkontrolle anzeigen mit:**  [Seite „Eigenschaften der Ressourcenkontrolle“](#ViewRGProp)</span><span class="sxs-lookup"><span data-stu-id="2d77f-105">**To view Resource Governor properties, using:**  [Resource Governor Properties page](#ViewRGProp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d77f-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2d77f-106">Before You Begin</span></span>  
 <span data-ttu-id="2d77f-107">Neben dem Anzeigen der Eigenschaften von Ressourcenkontrollentitäten können Sie auf der Seite **Eigenschaften der Ressourcenkontrolle** mehrere Konfigurationstasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d77f-107">In addition to viewing the properties of Resource Governor entities, you can perform several configuration tasks using the **Resource Governor Properties** page.</span></span> <span data-ttu-id="2d77f-108">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2d77f-108">For more information, see these topics:</span></span>  
  
-   [<span data-ttu-id="2d77f-109">Aktivieren der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="2d77f-109">Enable Resource Governor</span></span>](enable-resource-governor.md)  
  
-   [<span data-ttu-id="2d77f-110">Deaktivieren der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="2d77f-110">Disable Resource Governor</span></span>](disable-resource-governor.md)  
  
-   [<span data-ttu-id="2d77f-111">Erstellen eines Ressourcenpools</span><span class="sxs-lookup"><span data-stu-id="2d77f-111">Create a Resource Pool</span></span>](create-a-resource-pool.md)  
  
-   [<span data-ttu-id="2d77f-112">Erstellen einer Arbeitsauslastungsgruppe</span><span class="sxs-lookup"><span data-stu-id="2d77f-112">Create a Workload Group</span></span>](create-a-workload-group.md)  
  
-   [<span data-ttu-id="2d77f-113">Ändern der Einstellungen für den Ressourcenpool</span><span class="sxs-lookup"><span data-stu-id="2d77f-113">Change Resource Pool Settings</span></span>](change-resource-pool-settings.md)  
  
-   [<span data-ttu-id="2d77f-114">Ändern der Einstellungen von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="2d77f-114">Change Workload Group Settings</span></span>](change-workload-group-settings.md)  
  
-   [<span data-ttu-id="2d77f-115">Verschieben von Arbeitsauslastungsgruppen</span><span class="sxs-lookup"><span data-stu-id="2d77f-115">Move a Workload Group</span></span>](move-a-workload-group.md)  
  
 <span data-ttu-id="2d77f-116">Nachdem Sie eine Arbeitsauslastungsgruppe oder einen Ressourcenpool hinzugefügt, gelöscht oder verschoben haben, wird die Anweisung ALTER RESOURCE GOVERNOR RECONFIGURE ausgeführt, wenn Sie auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="2d77f-116">When you click **OK** after adding, deleting, or moving a workload group or resource pool, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
 <span data-ttu-id="2d77f-117">Bei einem Fehler beim Erstellungs- oder Neukonfigurierungsvorgang für den Ressourcenpool oder die Arbeitsauslastungsgruppe wird unter dem Titel der Eigenschaftenseite eine zusammenfassende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d77f-117">If the create or reconfigure operation for the resource pool or workload group fails, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="2d77f-118">Klicken Sie auf den Abwärtspfeil an der Fehlermeldung, um eine ausführliche Fehlermeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d77f-118">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
 <span data-ttu-id="2d77f-119">Sie können feststellen, ob eine ausstehende Konfiguration vorliegt, indem Sie die dynamische Verwaltungssicht [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) abfragen, um den aktuellen Status von is_configuration_pending zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d77f-119">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d77f-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2d77f-120">Permissions</span></span>  
 <span data-ttu-id="2d77f-121">Zum Anzeigen der Ressourcenkontrolleigenschaften ist die VIEW SERVER STATER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d77f-121">Viewing resource governor properties requires VIEW SERVER STATER permission.</span></span> <span data-ttu-id="2d77f-122">Für die Konfigurationstasks für die Ressourcenkontrolle ist die CONTROL SERVER-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d77f-122">The resource governor configuration tasks require CONTROL SERVER permission.</span></span>  
  
##  <a name="view-the-resource-governor-properties-page"></a><a name="ViewRGProp"></a><span data-ttu-id="2d77f-123">Anzeigen der Resource Governor Eigenschaften Seite</span><span class="sxs-lookup"><span data-stu-id="2d77f-123">View the Resource Governor Properties Page</span></span>  
 <span data-ttu-id="2d77f-124">**So zeigen Sie Resource Governor-Eigenschaften auf der Seite „Eigenschaften von Resource Governor“ in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2d77f-124">**To view resource governor properties by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="2d77f-125">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]den Objekt-Explorer, und erweitern Sie den Knoten **Verwaltung** rekursiv, bis **Ressourcenkontrolle**angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d77f-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="2d77f-126">Klicken Sie mit der rechten Maustaste auf **Resource Governor** , und klicken Sie dann auf **Eigenschaften**. Damit öffnen Sie die Seite **Eigenschaften des Resource Governors** .</span><span class="sxs-lookup"><span data-stu-id="2d77f-126">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="2d77f-127">Beschreibungen der Felder auf der Seite finden Sie unter [Eigenschaften der Ressourcenkontrolle](#RGProp).</span><span class="sxs-lookup"><span data-stu-id="2d77f-127">For descriptions of the fields in the page, see [Resource Governor Properties](#RGProp).</span></span>  
  
4.  <span data-ttu-id="2d77f-128">Klicken Sie auf **OK**, um Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d77f-128">To save any changes, click **OK**.</span></span>  
  
##  <a name="resource-governor-properties"></a><a name="RGProp"></a><span data-ttu-id="2d77f-129">Eigenschaften von Resource Governor</span><span class="sxs-lookup"><span data-stu-id="2d77f-129">Resource Governor Properties</span></span>  
 <span data-ttu-id="2d77f-130">**Der Name der Klassifizierungsfunktion**</span><span class="sxs-lookup"><span data-stu-id="2d77f-130">**Classifier function name**</span></span>  
 <span data-ttu-id="2d77f-131">Geben Sie die Klassifizierungsfunktion durch Auswahl aus der Liste an.</span><span class="sxs-lookup"><span data-stu-id="2d77f-131">Specify the classifier function by selecting from the list.</span></span>  
  
 <span data-ttu-id="2d77f-132">**Aktivieren der Ressourcenkontrolle**</span><span class="sxs-lookup"><span data-stu-id="2d77f-132">**Enable Resource Governor**</span></span>  
 <span data-ttu-id="2d77f-133">Aktivieren oder deaktivieren Sie die Ressourcenkontrolle, indem Sie das Kontrollkästchen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d77f-133">Enable or disable Resource Governor by selecting or clearing the check box.</span></span>  
  
 <span data-ttu-id="2d77f-134">**Ressourcenpools**</span><span class="sxs-lookup"><span data-stu-id="2d77f-134">**Resource pools**</span></span>  
 <span data-ttu-id="2d77f-135">Erstellen oder ändern Sie die Konfiguration von Ressourcenpools mithilfe des vorhandenen Rasters.</span><span class="sxs-lookup"><span data-stu-id="2d77f-135">Create or change resource pool configuration by using the grid that is provided.</span></span> <span data-ttu-id="2d77f-136">Dieses Raster wird mit Informationen für die vordefinierten internen Pools und Standardpools ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2d77f-136">This grid is populated with information for the predefined internal and default pools.</span></span> <span data-ttu-id="2d77f-137">Wählen Sie einen Pool aus, mit dem Sie arbeiten möchten, indem Sie auf die erste Spalte in der Zeile für den Pool klicken.</span><span class="sxs-lookup"><span data-stu-id="2d77f-137">Select a pool to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="2d77f-138">Klicken Sie zur Erstellung eines neuen Ressourcenpools auf die Zeile, der ein Sternchen ( **&#42;** ) vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="2d77f-138">To create a new resource pool, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="2d77f-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="2d77f-139">**Name**</span></span>  
 <span data-ttu-id="2d77f-140">Geben Sie den Namen des Ressourcenpools an.</span><span class="sxs-lookup"><span data-stu-id="2d77f-140">Specify the name of the resource pool.</span></span>  
  
 <span data-ttu-id="2d77f-141">**Minimaler CPU-Prozentsatz**</span><span class="sxs-lookup"><span data-stu-id="2d77f-141">**Minimum CPU %**</span></span>  
 <span data-ttu-id="2d77f-142">Geben Sie die garantierte durchschnittliche CPU-Bandbreite für alle Anforderungen im Ressourcenpool an, wenn CPU-Konflikte bestehen.</span><span class="sxs-lookup"><span data-stu-id="2d77f-142">Specify the guaranteed average CPU bandwidth for all requests in the resource pool when there is CPU contention.</span></span> <span data-ttu-id="2d77f-143">Der Bereich liegt zwischen 0 und 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-143">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="2d77f-144">**Maximaler CPU-Prozentsatz**</span><span class="sxs-lookup"><span data-stu-id="2d77f-144">**Maximum CPU %**</span></span>  
 <span data-ttu-id="2d77f-145">Geben Sie die maximale durchschnittliche CPU-Bandbreite an, die allen Anforderungen im Ressourcenpool zugewiesen wird, wenn CPU-Konflikte bestehen.</span><span class="sxs-lookup"><span data-stu-id="2d77f-145">Specify the maximum average CPU bandwidth that all requests in this resource pool will receive when there is CPU contention.</span></span> <span data-ttu-id="2d77f-146">Der Bereich liegt zwischen 0 und 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-146">Range is 0 to 100.</span></span> <span data-ttu-id="2d77f-147">Die Standardeinstellung ist 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-147">The default setting is 100.</span></span>  
  
 <span data-ttu-id="2d77f-148">**Minimaler Arbeitsspeicherprozentsatz**</span><span class="sxs-lookup"><span data-stu-id="2d77f-148">**Minimum Memory %**</span></span>  
 <span data-ttu-id="2d77f-149">Geben Sie den Mindestarbeitsspeicher an, der für diesen Ressourcenpool reserviert ist und nicht gemeinsam mit anderen Ressourcenpools verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d77f-149">Specify the minimum amount of memory reserved for this resource pool that can not be shared with other resource pools.</span></span> <span data-ttu-id="2d77f-150">Der Bereich liegt zwischen 0 und 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-150">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="2d77f-151">**Maximaler Arbeitsspeicherprozentsatz**</span><span class="sxs-lookup"><span data-stu-id="2d77f-151">**Maximum Memory %**</span></span>  
 <span data-ttu-id="2d77f-152">Geben Sie den gesamten Serverspeicher an, der für Anforderungen in diesem Ressourcenpool verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d77f-152">Specify the total server memory that can be used by requests in this resource pool.</span></span> <span data-ttu-id="2d77f-153">Der Bereich liegt zwischen 0 und 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-153">Range is 0 to 100.</span></span> <span data-ttu-id="2d77f-154">Die Standardeinstellung ist 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-154">The default setting is 100.</span></span>  
  
 <span data-ttu-id="2d77f-155">Weitere Informationen finden Sie unter [Erstellen eines Ressourcenpools &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d77f-155">For more information, see [CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span></span>  
  
 <span data-ttu-id="2d77f-156">**Arbeitsauslastungsgruppen für Ressourcenpool**</span><span class="sxs-lookup"><span data-stu-id="2d77f-156">**Workload groups for resource pool**</span></span>  
 <span data-ttu-id="2d77f-157">Erstellen oder ändern Sie die Konfiguration von Arbeitsauslastungsgruppen mithilfe des vorhandenen Rasters.</span><span class="sxs-lookup"><span data-stu-id="2d77f-157">Create or change the workload group configuration by using the grid that is provided.</span></span> <span data-ttu-id="2d77f-158">Dieses Raster wird mit Informationen für die vordefinierten internen Gruppen und Standardgruppen ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2d77f-158">This grid is populated with information for the predefined internal and default groups.</span></span> <span data-ttu-id="2d77f-159">Wählen Sie eine Gruppe aus, mit der Sie arbeiten möchten, indem Sie auf die erste Spalte in der Zeile für den Pool klicken.</span><span class="sxs-lookup"><span data-stu-id="2d77f-159">Select a group to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="2d77f-160">Klicken Sie zur Erstellung einer neuen Arbeitsauslastungsgruppe auf die Zeile, der ein Sternchen ( **&#42;** ) vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="2d77f-160">To create a new workload group, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="2d77f-161">**Name**</span><span class="sxs-lookup"><span data-stu-id="2d77f-161">**Name**</span></span>  
 <span data-ttu-id="2d77f-162">Geben Sie den Namen der Arbeitsauslastungsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="2d77f-162">Specify the name of the workload group.</span></span>  
  
 <span data-ttu-id="2d77f-163">**Wichtigkeit**</span><span class="sxs-lookup"><span data-stu-id="2d77f-163">**Importance**</span></span>  
 <span data-ttu-id="2d77f-164">Geben Sie die relative Wichtigkeit einer Anforderung in der Arbeitsauslastungsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="2d77f-164">Specify the relative importance of a request in the workload group.</span></span> <span data-ttu-id="2d77f-165">Die verfügbaren Einstellungen lauten Niedrig, Mittel und Hoch.</span><span class="sxs-lookup"><span data-stu-id="2d77f-165">Available settings are Low, Medium, and High.</span></span>  
  
 <span data-ttu-id="2d77f-166">**Maximale Anforderungen**</span><span class="sxs-lookup"><span data-stu-id="2d77f-166">**Maximum Requests**</span></span>  
 <span data-ttu-id="2d77f-167">Geben Sie die maximale Anzahl gleichzeitiger Anforderungen an, die in der Arbeitsauslastungsgruppe ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2d77f-167">Specify the maximum number of simultaneous requests that are allowed to execute in the workload group.</span></span> <span data-ttu-id="2d77f-168">Dieser Wert muss 0 (null) oder eine positive Ganzzahl sein.</span><span class="sxs-lookup"><span data-stu-id="2d77f-168">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="2d77f-169">**CPU-Zeit (Sek.)**</span><span class="sxs-lookup"><span data-stu-id="2d77f-169">**CPU Time (sec)**</span></span>  
 <span data-ttu-id="2d77f-170">Geben Sie die maximale CPU-Zeit für eine Anforderung an.</span><span class="sxs-lookup"><span data-stu-id="2d77f-170">Specify the maximum amount of CPU time that a request can use.</span></span> <span data-ttu-id="2d77f-171">Dieser Wert muss 0 (null) oder eine positive Ganzzahl sein.</span><span class="sxs-lookup"><span data-stu-id="2d77f-171">Must be 0 or a positive integer.</span></span> <span data-ttu-id="2d77f-172">Bei 0 ist die Zeit unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="2d77f-172">If 0, the time is unlimited.</span></span>  
  
 <span data-ttu-id="2d77f-173">**Arbeitsspeicherzuweisung (%)**</span><span class="sxs-lookup"><span data-stu-id="2d77f-173">**Memory Grant %**</span></span>  
 <span data-ttu-id="2d77f-174">Geben Sie die Höchstmenge an Arbeitsspeicher an, die eine einzelne Anforderung vom Pool in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="2d77f-174">Specify the maximum amount of memory that a single request can take from the pool.</span></span> <span data-ttu-id="2d77f-175">Der Bereich liegt zwischen 0 und 100.</span><span class="sxs-lookup"><span data-stu-id="2d77f-175">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="2d77f-176">**Timeout für Arbeitsspeicherzuweisung (Sek)**</span><span class="sxs-lookup"><span data-stu-id="2d77f-176">**Grant Time-out (sec)**</span></span>  
 <span data-ttu-id="2d77f-177">Geben Sie die maximale Zeit in Sekunden an, die eine Abfrage auf das Freiwerden einer Ressource wartet, bevor die Abfrage fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="2d77f-177">Specify the maximum time that a query can wait for a resource to become available before the query fails.</span></span> <span data-ttu-id="2d77f-178">Dieser Wert muss 0 (null) oder eine positive Ganzzahl sein.</span><span class="sxs-lookup"><span data-stu-id="2d77f-178">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="2d77f-179">**Grad der Parallelität**</span><span class="sxs-lookup"><span data-stu-id="2d77f-179">**Degree of Parallelism**</span></span>  
 <span data-ttu-id="2d77f-180">Geben Sie den maximalen Grad der Parallelität (DOP) für parallele Anforderungen an.</span><span class="sxs-lookup"><span data-stu-id="2d77f-180">Specify the maximum degree of parallelism (DOP) for parallel requests.</span></span> <span data-ttu-id="2d77f-181">Der Bereich liegt zwischen 0 und 64.</span><span class="sxs-lookup"><span data-stu-id="2d77f-181">Range is 0 to 64.</span></span>  
  
 <span data-ttu-id="2d77f-182">Weitere Informationen finden Sie unter [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d77f-182">For more information, see [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span></span>  
  
## <a name="view-resource-governor-properties-by-using-transact-sql"></a><span data-ttu-id="2d77f-183">Anzeigen von Eigenschaften der Ressourcenkontrolle mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d77f-183">View Resource Governor Properties by Using Transact-SQL</span></span>  
 <span data-ttu-id="2d77f-184">**Anzeigen von Eigenschaften der Ressourcenkontrolle mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="2d77f-184">**View resource governor properties by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="2d77f-185">Um die Definitionen von Resource Governor-Entitäten anzuzeigen, verwenden Sie die [Katalogsichten des Resource Governors &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d77f-185">To view the definitions of resource governor entities, use the [Resource Governor Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span></span>  
  
2.  <span data-ttu-id="2d77f-186">Um die aktuelle Konfiguration von Resource Governor-Entitäten anzuzeigen, verwenden Sie die [dynamischen Verwaltungssichten in Verbindung mit dem Resource Governor &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d77f-186">To view the current configuration of resource governor entities, use the [Resource Governor Related Dynamic Management Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d77f-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d77f-187">See Also</span></span>  
 <span data-ttu-id="2d77f-188">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2d77f-188">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="2d77f-189">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2d77f-189">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="2d77f-190">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2d77f-190">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="2d77f-191">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="2d77f-191">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 [<span data-ttu-id="2d77f-192">Klassifizierungsfunktion der Ressourcenkontrolle</span><span class="sxs-lookup"><span data-stu-id="2d77f-192">Resource Governor Classifier Function</span></span>](resource-governor-classifier-function.md)  
  
  
