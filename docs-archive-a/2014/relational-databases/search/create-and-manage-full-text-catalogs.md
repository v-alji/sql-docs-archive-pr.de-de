---
title: Erstellen und Verwalten von Volltextkatalogen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs [SQL Server], creating
- full-text search [SQL Server], using SQL Server Management Studio
ms.assetid: 824b7131-44a6-4815-89e6-62b7bab060e3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18efd79bc34beee94d4edc61e9165a986edba90b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622516"
---
# <a name="create-and-manage-full-text-catalogs"></a><span data-ttu-id="e2cc2-102">Erstellen und Verwalten von Volltextkatalogen</span><span class="sxs-lookup"><span data-stu-id="e2cc2-102">Create and Manage Full-Text Catalogs</span></span>
  <span data-ttu-id="e2cc2-103">Ein Volltextkatalog ist ein virtuelles Objekt, das keiner Dateigruppe angehört. Es ist ein logisches Konzept, das für eine Gruppe von Volltextindizes steht.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-103">A full-text catalog is a virtual object that does not belong to any filegroup; it is a logical concept that refers to a group of full-text indexes.</span></span>  
  
##  <a name="creating-a-full-text-catalog"></a><a name="creating"></a><span data-ttu-id="e2cc2-104">Erstellen eines voll Text Katalogs</span><span class="sxs-lookup"><span data-stu-id="e2cc2-104">Creating a Full-Text Catalog</span></span>  
  
#### <a name="to-create-a-full-text-catalog"></a><span data-ttu-id="e2cc2-105">So erstellen Sie einen Volltextkatalog</span><span class="sxs-lookup"><span data-stu-id="e2cc2-105">To create a full-text catalog</span></span>  
  
1.  <span data-ttu-id="e2cc2-106">Erweitern Sie im Objekt-Explorer den Server, erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, in der der Volltextkatalog erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-106">In Object Explorer, expand the server, expand **Databases**, and expand the database in which you want to create the full-text catalog.</span></span>  
  
2.  <span data-ttu-id="e2cc2-107">Erweitern Sie **Speicher**, und klicken Sie dann mit der rechten Maustaste auf **Volltextkataloge**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-107">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="e2cc2-108">Wählen Sie **Neuer Volltextkatalog**aus.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-108">Select **New Full-Text Catalog**.</span></span>  
  
4.  <span data-ttu-id="e2cc2-109">Geben Sie im Dialogfeld **Neuer Volltextkatalog** die Informationen für den erneut zu erstellenden Volltextkatalog an.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-109">In the **New Full-Text Catalog** dialog box, specify the information for the catalog that you are re-creating.</span></span> <span data-ttu-id="e2cc2-110">Weitere Informationen finden Sie unter [Neuer Volltextkatalog &#40;Seite „Allgemein“&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="e2cc2-110">For more information, see [New Full-Text Catalog &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2cc2-111">Volltextkatalog-IDs beginnen bei 00005 und werden mit jedem neu erstellten Katalog um eins erhöht.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-111">Full-text catalog IDs begin at 00005 and are incremented by one for each new catalog created.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
  
##  <a name="viewing-the-properties-of-a-full-text-catalog"></a><a name="props"></a><span data-ttu-id="e2cc2-112">Anzeigen der Eigenschaften eines voll Text Katalogs</span><span class="sxs-lookup"><span data-stu-id="e2cc2-112">Viewing the Properties of a Full-Text Catalog</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="e2cc2-113">-Funktionen, z. B. FULLTEXTCATALOGPROPERTY, können verwendet werden, um den Wert verschiedener Eigenschaften der Volltextindizierung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-113">functions such as FULLTEXTCATALOGPROPERTY can be used to obtain the value of various properties related to full-text indexing.</span></span> <span data-ttu-id="e2cc2-114">Diese Informationen sind für die Verwaltung und Problembehandlung der Volltextsuche hilfreich.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-114">This information is useful for administering and troubleshooting full-text search.</span></span>  
  
 <span data-ttu-id="e2cc2-115">In der folgenden Tabelle sind die Eigenschaften aufgeführt, die sich auf Volltextkataloge beziehen.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-115">The following table lists the properties that are related to full-text catalogs.</span></span>  
  
|<span data-ttu-id="e2cc2-116">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e2cc2-116">Property</span></span>|<span data-ttu-id="e2cc2-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e2cc2-117">Description</span></span>|<span data-ttu-id="e2cc2-118">Funktion</span><span class="sxs-lookup"><span data-stu-id="e2cc2-118">Function</span></span>|  
|--------------|-----------------|--------------|  
|`AccentSensitivity`|<span data-ttu-id="e2cc2-119">Einstellung für die Unterscheidung nach Akzent.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-119">Accent-sensitivity setting.</span></span>|[<span data-ttu-id="e2cc2-120">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-120">FULLTEXTCATALOGPROPERTY</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)|  
|`ImportStatus`|<span data-ttu-id="e2cc2-121">Gibt an, ob der Volltextkatalog importiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-121">Whether the full-text catalog is being imported.</span></span>|<span data-ttu-id="e2cc2-122">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-122">FULLTEXTCATALOGPROPERTY</span></span>|  
|`IndexSize`|<span data-ttu-id="e2cc2-123">Größe des Volltextkatalogs in Megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="e2cc2-123">Size of the full-text catalog in megabytes (MB).</span></span>|<span data-ttu-id="e2cc2-124">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-124">FULLTEXTCATALOGPROPERTY</span></span>|  
|`ItemCount`|<span data-ttu-id="e2cc2-125">Aktuelle Anzahl der volltextindizierten Objekte im Volltextkatalog.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-125">Number of full-text indexed items currently in the full-text catalog.</span></span>|<span data-ttu-id="e2cc2-126">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-126">FULLTEXTCATALOGPROPERTY</span></span>|  
|`MergeStatus`|<span data-ttu-id="e2cc2-127">Gibt an, ob eine Masterzusammenführung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-127">Whether a master merge is in progress.</span></span>|<span data-ttu-id="e2cc2-128">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-128">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateCompletionAge`|<span data-ttu-id="e2cc2-129">Anzahl von Sekunden, die zwischen dem 01.01.1990, 00:00:00 Uhr, und der Beendigung des letzten Auffüllens des Volltextindex verstrichen sind.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-129">Difference in seconds between the completion of the last full-text index population and 01/01/1990 00:00:00.</span></span>|<span data-ttu-id="e2cc2-130">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-130">FULLTEXTCATALOGPROPERTY</span></span>|  
|`PopulateStatus`|<span data-ttu-id="e2cc2-131">Gibt den Auffüllungsstatus an.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-131">Populate status.</span></span><br /><br /> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]|<span data-ttu-id="e2cc2-132">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-132">FULLTEXTCATALOGPROPERTY</span></span>|  
|`UniqueKeyCount`|<span data-ttu-id="e2cc2-133">Anzahl der eindeutigen Schlüssel im Volltextkatalog.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-133">Number of unique keys in the full-text catalog.</span></span>|<span data-ttu-id="e2cc2-134">FULLTEXTCATALOGPROPERTY</span><span class="sxs-lookup"><span data-stu-id="e2cc2-134">FULLTEXTCATALOGPROPERTY</span></span>|  
  
  
  
##  <a name="rebuilding-a-full-text-catalog"></a><a name="rebuildone"></a><span data-ttu-id="e2cc2-135">Neuerstellen eines voll Text Katalogs</span><span class="sxs-lookup"><span data-stu-id="e2cc2-135">Rebuilding a Full-Text Catalog</span></span>  
  
#### <a name="to-rebuild-a-full-text-catalog"></a><span data-ttu-id="e2cc2-136">So erstellen Sie einen Volltextkatalog erneut</span><span class="sxs-lookup"><span data-stu-id="e2cc2-136">To rebuild a full-text catalog</span></span>  
  
1.  <span data-ttu-id="e2cc2-137">Erweitern Sie im Objekt-Explorer den Server, erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, die den erneut zu erstellenden Volltextkatalog enthält.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-137">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalog that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="e2cc2-138">Erweitern Sie **Speicher**und dann **Volltextkataloge**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-138">Expand **Storage**, and then expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="e2cc2-139">Klicken Sie mit der rechten Maustaste auf den Namen des erneut zu erstellenden Volltextkatalogs, und wählen Sie **Neu erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-139">Right-click the name of the full-text catalog that you want to rebuild, and select **Rebuild**.</span></span>  
  
4.  <span data-ttu-id="e2cc2-140">Klicken Sie auf die Frage **Möchten Sie den Volltextkatalog löschen und neu erstellen?** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-140">To the question **Do you want to delete the full-text catalog and rebuild it?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="e2cc2-141">Klicken Sie im Dialogfeld **Volltextkatalog neu erstellen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-141">In the **Rebuild Full-Text Catalog** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="rebuilding-all-full-text-catalogs-for-a-database"></a><a name="rebuildall"></a><span data-ttu-id="e2cc2-142">Erneutes Erstellen aller voll Text Kataloge für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="e2cc2-142">Rebuilding All Full-Text Catalogs for a Database</span></span>  
  
#### <a name="to-rebuild-the-full-text-catalogs-for-a-database"></a><span data-ttu-id="e2cc2-143">So erstellen Sie die Volltextkataloge für eine Datenbank erneut</span><span class="sxs-lookup"><span data-stu-id="e2cc2-143">To rebuild the full-text catalogs for a database</span></span>  
  
1.  <span data-ttu-id="e2cc2-144">Erweitern Sie im Objekt-Explorer den Server, erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, die die erneut zu erstellenden Volltextkataloge enthält.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-144">In Object Explorer, expand the server, expand **Databases**, and then expand the database that contains the full-text catalogs that you want to rebuild.</span></span>  
  
2.  <span data-ttu-id="e2cc2-145">Erweitern Sie **Speicher**, und klicken Sie dann mit der rechten Maustaste auf **Volltextkataloge**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-145">Expand **Storage**, and then right-click **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="e2cc2-146">Wählen Sie **Alle neu erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-146">Select **Rebuild All**.</span></span>  
  
4.  <span data-ttu-id="e2cc2-147">Klicken Sie bei der Frage **Möchten Sie alle Volltextkataloge löschen und neu erstellen?** auf die Option **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-147">To the question, **Do you want to delete all full-text catalogs and rebuild them?**, click **OK**.</span></span>  
  
5.  <span data-ttu-id="e2cc2-148">Klicken Sie im Dialogfeld **Alle Volltextkataloge neu erstellen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-148">In the **Rebuild All Full-Text Catalogs** dialog box, click **Close**.</span></span>  
  
  
  
##  <a name="removing-a-full-text-catalog-from-a-database"></a><a name="removing"></a><span data-ttu-id="e2cc2-149">Entfernen eines voll Text Katalogs aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="e2cc2-149">Removing a Full-Text Catalog from a Database</span></span>  
  
#### <a name="to-remove-a-full-text-catalog-from-a-database"></a><span data-ttu-id="e2cc2-150">So entfernen Sie einen Volltextkatalog aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="e2cc2-150">To remove a full-text catalog from a database</span></span>  
  
1.  <span data-ttu-id="e2cc2-151">Erweitern Sie im Objekt-Explorer den Server, erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, die den zu entfernenden Volltextkatalog enthält.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-151">In Object Explorer, expand the server, expand **Databases**, and expand the database that contains the full-text catalog you want to remove.</span></span>  
  
2.  <span data-ttu-id="e2cc2-152">Erweitern Sie **Speicher**und dann **Volltextkataloge**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-152">Expand **Storage**, and expand **Full Text Catalogs**.</span></span>  
  
3.  <span data-ttu-id="e2cc2-153">Klicken Sie mit der rechten Maustaste auf den zu entfernenden Katalog, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-153">Right-click the full-text catalog that you want to remove, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="e2cc2-154">Klicken Sie im Dialogfeld **Objekte löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2cc2-154">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="e2cc2-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2cc2-155">See Also</span></span>  
 [<span data-ttu-id="e2cc2-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2cc2-156">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
  
