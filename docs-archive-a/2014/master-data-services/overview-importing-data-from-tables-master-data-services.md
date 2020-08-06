---
title: Daten Import (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], about staging process
- importing data [Master Data Services]
- staging process [Master Data Services]
ms.assetid: 181d1e22-379c-45d1-b03c-e1e22ff14164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 403eca212611397fb3ba30f8fe12a2aa8b5e83ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608755"
---
# <a name="data-import-master-data-services"></a><span data-ttu-id="9fc1d-102">Datenimport (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9fc1d-102">Data Import (Master Data Services)</span></span>
  <span data-ttu-id="9fc1d-103">Nach der Erstellung eines Modells für Ihre Daten in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie beginnen, Daten hinzufügen und Änderungen an Daten in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Datenbank vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-103">Once you've created a model for your data in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can start adding data and make changes to data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>   <span data-ttu-id="9fc1d-104">Sie verwenden [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Stagingtabellen, gespeicherte Prozeduren und Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-104">You use [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] staging tables, stored procedures and Master Data Manager .</span></span>

 <span data-ttu-id="9fc1d-105">Sie können auch das verwenden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] , um dem MDS-Repository (-Datenbank) Daten hinzuzufügen [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9fc1d-105">You can also use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)], to add data to the MDS repository ([!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span></span> <span data-ttu-id="9fc1d-106">Weitere Informationen finden Sie unter [Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="9fc1d-106">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>

 <span data-ttu-id="9fc1d-107">Beim Hinzufügen und Aktualisieren von Daten können Sie Folgendes tun.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-107">When you add and update data, you can do the following.</span></span>

-   <span data-ttu-id="9fc1d-108">Laden und Aktualisieren von Elementen und Aktualisieren von Attributwerten</span><span class="sxs-lookup"><span data-stu-id="9fc1d-108">Load and update members, and update attribute values</span></span>

-   <span data-ttu-id="9fc1d-109">Deaktivieren und Löschen von Elementen</span><span class="sxs-lookup"><span data-stu-id="9fc1d-109">Deactivate and delete members</span></span>

-   <span data-ttu-id="9fc1d-110">Verschieben von Elementen der expliziten Hierarchie</span><span class="sxs-lookup"><span data-stu-id="9fc1d-110">Move explicit hierarchy members</span></span>

 <span data-ttu-id="9fc1d-111">Das Hinzufügen und Aktualisieren von Daten besteht hauptsächlich in den folgenden Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-111">Adding and updating data  includes the following main tasks.</span></span>

1.  <span data-ttu-id="9fc1d-112">Laden von Daten in die Stagingtabellen in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-112">Load data into the staging tables in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>

2.  <span data-ttu-id="9fc1d-113">Laden von Daten aus den Stagingtabellen in die entsprechenden [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Tabellen.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-113">Load the data from the staging tables into the appropriate [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] tables.</span></span>

     <span data-ttu-id="9fc1d-114">Zum Laden der Daten verwenden Sie gespeicherte Prozeduren oder [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9fc1d-114">You use staging stored procedures or [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to load the data.</span></span>

> [!NOTE]
>  <span data-ttu-id="9fc1d-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]ist die Unterstützung für die [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] -Stagingprozesse veraltet.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], support for the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging processes is deprecated.</span></span>

## <a name="deactivating-and-deleting-members"></a><span data-ttu-id="9fc1d-116">Deaktivieren und Löschen von Elementen</span><span class="sxs-lookup"><span data-stu-id="9fc1d-116">Deactivating and Deleting Members</span></span>
 <span data-ttu-id="9fc1d-117">Deaktivieren bedeutet, dass das Element erneut aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-117">Deactivating means the member can be reactivated.</span></span> <span data-ttu-id="9fc1d-118">Wenn Sie ein Element erneut aktivieren, werden seine Attribute und Mitgliedschaft in Hierarchien und Auflistungen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-118">If you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span> <span data-ttu-id="9fc1d-119">Alle vorherigen Transaktionen sind intakt.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-119">All previous transactions are intact.</span></span> <span data-ttu-id="9fc1d-120">Deaktivierungstransaktionen werden Administratoren im Funktionsbereich **Versionsverwaltung** von Master Data Manager angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-120">Deactivation transactions are visible to administrators in the **Version Management** functional area of the Master Data Manager.</span></span>

 <span data-ttu-id="9fc1d-121">Löschen bedeutet, das Element dauerhaft vom System zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-121">Deleting means purging the member from the system permanently.</span></span> <span data-ttu-id="9fc1d-122">Alle Transaktionen für das Element, alle Beziehungen und alle Attribute werden dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-122">All transactions for the member, all relationships, and all attributes are permanently deleted.</span></span>

> [!NOTE]
>  <span data-ttu-id="9fc1d-123">Per Staging können Sie keine Elemente erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-123">You cannot use staging to reactivate members.</span></span> <span data-ttu-id="9fc1d-124">Diesen Vorgang müssen Sie manuell in Master Data Manager ausführen.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-124">You must do it manually in the Master Data Manager.</span></span> <span data-ttu-id="9fc1d-125">Weitere Informationen finden Sie unter [Reaktivieren eines Elements oder einer Sammlung &#40;Master Data Services&#41](reactivate-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fc1d-125">For more information, see [Reactivate a Member or Collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span></span>
> 
>  <span data-ttu-id="9fc1d-126">Per Staging können Sie keine Auflistungen löschen oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-126">You cannot use staging to delete or deactivate collections.</span></span> <span data-ttu-id="9fc1d-127">Weitere Informationen zum manuellen Deaktivieren von Sammlungen finden Sie unter [Löschen eines Elements oder einer Sammlung &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fc1d-127">For more information on manually deactivating collections, see [Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span></span>

## <a name="moving-explicit-hierarchy-members"></a><span data-ttu-id="9fc1d-128">Verschieben Elementen der expliziten Hierarchie</span><span class="sxs-lookup"><span data-stu-id="9fc1d-128">Moving explicit hierarchy members</span></span>
 <span data-ttu-id="9fc1d-129">Beim Massenverschieben der Position von Elementen der expliziten Hierarchie können Sie die folgenden Festlegungen treffen.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-129">When you move the location of members in explicit hierarchies in bulk, you can designate the following.</span></span>

-   <span data-ttu-id="9fc1d-130">Ein konsolidiertes Element als übergeordnetes Element eines konsolidierten Elements</span><span class="sxs-lookup"><span data-stu-id="9fc1d-130">A consolidated member as a parent of a consolidated member.</span></span>

-   <span data-ttu-id="9fc1d-131">Ein konsolidiertes Element als übergeordnetes Element eines Blattelements</span><span class="sxs-lookup"><span data-stu-id="9fc1d-131">A consolidated member as a parent of a leaf member.</span></span>

-   <span data-ttu-id="9fc1d-132">Ein Blattelement als ein gleichgeordnetes Element eines Blattelements oder eines konsolidierten Elements</span><span class="sxs-lookup"><span data-stu-id="9fc1d-132">A leaf member as a sibling of a leaf or consolidated member.</span></span>

-   <span data-ttu-id="9fc1d-133">Ein konsolidiertes Element als ein gleichgeordnetes Element eines Blattelements oder eines konsolidierten Elements</span><span class="sxs-lookup"><span data-stu-id="9fc1d-133">A consolidated member as a sibling of a leaf or consolidated member.</span></span>

## <a name="staging-tables-and-stored-procedures"></a><span data-ttu-id="9fc1d-134">Stagingtabellen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9fc1d-134">Staging Tables and Stored Procedures</span></span>
 <span data-ttu-id="9fc1d-135">Die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank enthält die folgenden Typen von Stagingtabellen, die Sie mit Ihren Daten auffüllen können.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-135">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database includes the following types of staging tables that you can populate with your  data.</span></span>

-   [<span data-ttu-id="9fc1d-136">Stagingtabelle für Blattelemente &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc1d-136">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="9fc1d-137">Konsolidierte Elementstagingtabelle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc1d-137">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="9fc1d-138">Stagingtabelle für Beziehungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc1d-138">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)

 <span data-ttu-id="9fc1d-139">Für jede Entität im Modell gibt es eine Stagingtabelle.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-139">For each entity in the model, there is a staging table.</span></span> <span data-ttu-id="9fc1d-140">Der Tabellenname gibt die entsprechende Entität und den Entitätstyp an, wie etwa ein Blattelement.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-140">The table name indicates the corresponding entity, and the entity type such as leaf member.</span></span> <span data-ttu-id="9fc1d-141">In der folgenden Abbildung sind die Stagingtabellen für die Entitäten „Währung“, „Kunde“ und „Produkt“ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-141">The following image shows the staging tables for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="9fc1d-142">![Stagingtabellen in der MDS-Datenbank](../../2014/master-data-services/media/mds-stagingtables.png "Stagingtabellen in der MDS-Datenbank")</span><span class="sxs-lookup"><span data-stu-id="9fc1d-142">![Staging Tables in MDS database](../../2014/master-data-services/media/mds-stagingtables.png "Staging Tables in MDS database")</span></span>

 <span data-ttu-id="9fc1d-143">Der Name der Tabelle wird beim Erstellen einer Entität angegeben und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-143">The name of the  table is specified when an entity is created and cannot be changed.</span></span> <span data-ttu-id="9fc1d-144">Wenn der Stagingtabellenname eine _1 oder eine andere Zahl enthält, war eine andere Tabelle dieses Namens bereits vorhanden, als die Entität erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-144">If the staging table name contains a _1 or other number, another table of that name already existed when the entity was created.</span></span>

 <span data-ttu-id="9fc1d-145">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] beinhaltet die folgenden Typen von gespeicherten Stagingprozeduren.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-145">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] includes the following types of staging stored procedures.</span></span>

-   <span data-ttu-id="9fc1d-146">STG. udp_ \<name> _Leaf</span><span class="sxs-lookup"><span data-stu-id="9fc1d-146">stg.udp_\<name>_Leaf</span></span>

-   <span data-ttu-id="9fc1d-147">STG. udp_ \<name> _Consolidated</span><span class="sxs-lookup"><span data-stu-id="9fc1d-147">stg.udp_\<name>_Consolidated</span></span>

-   <span data-ttu-id="9fc1d-148">STG. udp_ \<name> _Relationship</span><span class="sxs-lookup"><span data-stu-id="9fc1d-148">stg.udp_\<name>_Relationship</span></span>

 <span data-ttu-id="9fc1d-149">Für jede Entität im Modell gibt es drei gespeicherte Prozeduren, die dem Blattelement, dem konsolidierten Element und der Stagingtabelle für Beziehungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-149">For each entity in the model, there are three stored procedures that correspond to the leaf member, consolidated member, and relationship staging tables.</span></span>  <span data-ttu-id="9fc1d-150">In der folgenden Abbildung sind die gespeicherten Stagingprozeduren für die Entitäten „Währung“, „Kunde“ und „Produkt“ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-150">The following image shows the staging stored procedures for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="9fc1d-151">![Gespeicherte Stagingprozeduren in der MDS-Datenbank](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Gespeicherte Stagingprozeduren in der MDS-Datenbank")</span><span class="sxs-lookup"><span data-stu-id="9fc1d-151">![Staging Stored Procedures in MDS database](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Staging Stored Procedures in MDS database")</span></span>

 <span data-ttu-id="9fc1d-152">Weitere Informationen zu den gespeicherten Prozeduren finden Sie unter [Gespeicherte Stagingprozedur &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fc1d-152">For more information on the stored procedures, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>

## <a name="logging-transactions"></a><span data-ttu-id="9fc1d-153">Protokollieren von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="9fc1d-153">Logging Transactions</span></span>
 <span data-ttu-id="9fc1d-154">Alle Transaktionen, die auftreten, wenn Daten oder Beziehungen importiert oder aktualisiert werden, können protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-154">All transactions that occur when data or relationships are imported or updated can be logged.</span></span> <span data-ttu-id="9fc1d-155">Eine Option in der gespeicherten Prozedur ermöglicht diese Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-155">An option in the stored procedure allows this logging.</span></span> <span data-ttu-id="9fc1d-156">Wenn Sie den Stagingprozess mithilfe von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]einleiten, erfolgt keine Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-156">If you initiate the staging process using [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no logging occurs.</span></span>

 <span data-ttu-id="9fc1d-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]wird die Einstellung **Protokollieren aller Stagingtransaktionen** nicht für diese Methode zum Bereitstellen von Daten angewendet.</span><span class="sxs-lookup"><span data-stu-id="9fc1d-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], the **Log staging transactions** setting does not apply to this method of staging data.</span></span>

## <a name="related-content"></a><span data-ttu-id="9fc1d-158">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9fc1d-158">Related Content</span></span>

-   [<span data-ttu-id="9fc1d-159">Überprüfung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc1d-159">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)

-   [<span data-ttu-id="9fc1d-160">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc1d-160">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)


