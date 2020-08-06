---
title: Erstellen und Bereitstellen eines Caches für die Transformation für Suche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- creating cache files for Lookup transformation
- deploying cache files for Lookup transformation
- Lookup transformation cache files
ms.assetid: cedf5cad-2fac-42d0-ad91-9461e117d330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33b00b84f1f1448c2ee80882aedc3a330ba0a5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607902"
---
# <a name="create-and-deploy-a-cache-for-the-lookup-transformation"></a><span data-ttu-id="a69a2-102">Erstellen und Bereitstellen eines Cache für die Transformation für Suche</span><span class="sxs-lookup"><span data-stu-id="a69a2-102">Create and Deploy a Cache for the Lookup Transformation</span></span>
  <span data-ttu-id="a69a2-103">Sie können eine Cachedatei (.caw) erstellen und für die Transformation zur Suche bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a69a2-103">You can create and deploy a cache file (.caw) for the Lookup transformation.</span></span> <span data-ttu-id="a69a2-104">Das Verweisdataset wird in der Cachedatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a69a2-104">The reference dataset is stored in the cache file.</span></span>  
  
 <span data-ttu-id="a69a2-105">Die Transformation für Suche führt Suchvorgänge aus, indem Daten in Eingabespalten aus einer verbundenen Datenquelle mit Spalten in einem Verweisdataset verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="a69a2-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference dataset.</span></span>  
  
 <span data-ttu-id="a69a2-106">Sie erstellen eine Cachedatei, indem Sie einen Cacheverbindungs-Manager und eine Transformation für Cachetransformation verwenden.</span><span class="sxs-lookup"><span data-stu-id="a69a2-106">You create a cache file by using a Cache connection manager and a Cache Transform transformation.</span></span> <span data-ttu-id="a69a2-107">Weitere Informationen finden Sie unter [Cacheverbindungs-Manager](../../connection-manager/cache-connection-manager.md) und [Cachetransformation](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-107">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
 <span data-ttu-id="a69a2-108">Weitere Informationen zur Transformation für Suche und zu Cachedateien finden Sie unter [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-108">To learn more about the Lookup transformation and cache files, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
### <a name="to-create-a-cache-file"></a><span data-ttu-id="a69a2-109">So erstellen Sie eine Cachedatei</span><span class="sxs-lookup"><span data-stu-id="a69a2-109">To create a cache file</span></span>  
  
1.  <span data-ttu-id="a69a2-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Projekt mit dem gewünschten Paket, und öffnen Sie dann das Paket.</span><span class="sxs-lookup"><span data-stu-id="a69a2-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="a69a2-111">Fügen Sie auf der Registerkarte **Ablaufsteuerung** einen Datenflusstask hinzu.</span><span class="sxs-lookup"><span data-stu-id="a69a2-111">On the **Control Flow** tab, add a Data Flow task.</span></span>  
  
3.  <span data-ttu-id="a69a2-112">Fügen Sie auf der Registerkarte **Datenfluss** dem Datenfluss eine Transformation für Cachetransformation hinzu, und verbinden Sie dann die Transformation mit einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="a69a2-112">On the **Data Flow** tab, add a Cache Transform transformation to the data flow, and then connect the transformation to a data source.</span></span>  
  
     <span data-ttu-id="a69a2-113">Konfigurieren Sie die Datenquelle nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="a69a2-113">Configure the data source as needed.</span></span>  
  
4.  <span data-ttu-id="a69a2-114">Doppelklicken Sie auf die Transformation für Cachetransformation, und klicken Sie dann im **Cachetransformations-Editor**auf der Seite **Verbindungs-Manager** auf **Neu** , um einen neuen Cacheverbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a69a2-114">Double-click the Cache Transform, and then in the **Cache Transformation Editor**, on the **Connection Manager** page, click **New** to create a new Cache connection manager.</span></span>  
  
5.  <span data-ttu-id="a69a2-115">Konfigurieren Sie den Cacheverbindungs-Manager zum Speichern des Cache im **Editor für Cacheverbindungs-Manager**auf der Registerkarte **Allgemein** , indem Sie die folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="a69a2-115">In the **Cache Connection Manager Editor**, on the **General** tab, configure the Cache connection manager to save the cache by selecting the following options:</span></span>  
  
    1.  <span data-ttu-id="a69a2-116">Wählen Sie **Dateicache verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="a69a2-116">Select **Use file cache**.</span></span>  
  
    2.  <span data-ttu-id="a69a2-117">Geben Sie den Dateipfad in das Feld **Dateiname**ein.</span><span class="sxs-lookup"><span data-stu-id="a69a2-117">For **File name**, type the file path.</span></span>  
  
     <span data-ttu-id="a69a2-118">Das System erstellt die Datei, wenn Sie das Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="a69a2-118">The system creates the file when you run the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a69a2-119">Die Schutzebene des Pakets gilt nicht für die Cachedatei.</span><span class="sxs-lookup"><span data-stu-id="a69a2-119">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="a69a2-120">Wenn die Cachedatei vertrauliche Informationen enthält, schränken Sie den Zugriff auf den Speicherort oder Ordner, in dem Sie die Datei speichern, mithilfe einer Zugriffssteuerungsliste ein.</span><span class="sxs-lookup"><span data-stu-id="a69a2-120">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="a69a2-121">Sie sollten nur bestimmten Konten den Zugriff ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a69a2-121">You should enable access only to certain accounts.</span></span> <span data-ttu-id="a69a2-122">Weitere Informationen finden Sie unter [Zugriff auf Dateien, die von Paketen verwendet werden](../../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-122">For more information, see [Access to Files Used by Packages](../../access-to-files-used-by-packages.md).</span></span>  
  
6.  <span data-ttu-id="a69a2-123">Klicken Sie auf die Registerkarte **Spalten** , und geben Sie dann mit der Option **Indexposition** an, welche Spalten die Indexspalten sind.</span><span class="sxs-lookup"><span data-stu-id="a69a2-123">Click the **Columns** tab, and then specify which columns are the index columns by using the **Index Position** option.</span></span>  
  
     <span data-ttu-id="a69a2-124">Für Nicht-Index-Spalten ist die Indexposition 0.</span><span class="sxs-lookup"><span data-stu-id="a69a2-124">For non-index columns, the index position is 0.</span></span> <span data-ttu-id="a69a2-125">Für Indexspalten ist die Indexposition eine fortlaufende positive Zahl.</span><span class="sxs-lookup"><span data-stu-id="a69a2-125">For index columns, the index position is a sequential, positive number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a69a2-126">Wenn die Transformation für Suche so konfiguriert ist, dass sie einen Cacheverbindungs-Manager verwendet, können nur Indexspalten im Verweisdataset Eingabespalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a69a2-126">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="a69a2-127">Auch müssen alle Indexspalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a69a2-127">Also all index columns must be mapped.</span></span>  
  
     <span data-ttu-id="a69a2-128">Weitere Informationen finden Sie unter [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-128">For more information, see [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
7.  <span data-ttu-id="a69a2-129">Konfigurieren Sie die Cacheumwandlung nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="a69a2-129">Configure the Cache Transform as needed.</span></span>  
  
     <span data-ttu-id="a69a2-130">Weitere Informationen finden Sie unter [Cachetransformations-Editor &#40;Seite „Verbindungs-Manager“&#41;](../../cache-transformation-editor-connection-manager-page.md) und [Cachetransformations-Editor &#40;Seite „Zuordnungen“&#41;](../../cache-transformation-editor-mappings-page.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-130">For more information, see [Cache Transformation Editor &#40;Connection Manager Page&#41;](../../cache-transformation-editor-connection-manager-page.md) and [Cache Transformation Editor &#40;Mappings Page&#41;](../../cache-transformation-editor-mappings-page.md).</span></span>  
  
8.  <span data-ttu-id="a69a2-131">Führen Sie das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="a69a2-131">Run the package.</span></span>  
  
### <a name="to-deploy-a-cache-file"></a><span data-ttu-id="a69a2-132">So stellen Sie eine Cachedatei bereit</span><span class="sxs-lookup"><span data-stu-id="a69a2-132">To deploy a cache file</span></span>  
  
1.  <span data-ttu-id="a69a2-133">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Projekt mit dem gewünschten Paket, und öffnen Sie dann das Paket.</span><span class="sxs-lookup"><span data-stu-id="a69a2-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="a69a2-134">Erstellen Sie optional eine Paketkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a69a2-134">Optionally, create a package configuration.</span></span> <span data-ttu-id="a69a2-135">Weitere Informationen finden Sie unter [Erstellen von Paketkonfigurationen](../../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-135">For more information, see [Create Package Configurations](../../create-package-configurations.md).</span></span>  
  
3.  <span data-ttu-id="a69a2-136">Fügen Sie die Cachedatei dem Projekt hinzu, indem Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="a69a2-136">Add the cache file to the project by doing the following:</span></span>  
  
    1.  <span data-ttu-id="a69a2-137">Wählen Sie im Projektmappen-Explorer das Projekt aus, das Sie in Schritt 1 geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="a69a2-137">In Solution Explorer, select the project you opened in step 1.</span></span>  
  
    2.  <span data-ttu-id="a69a2-138">Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a69a2-138">On the **Project** menu, click **AddExisting Item**.</span></span>  
  
    3.  <span data-ttu-id="a69a2-139">Wählen Sie die Cachedatei aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a69a2-139">Select the cache file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="a69a2-140">Die Datei wird im Projektmappen-Explorer im Ordner **Sonstige** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a69a2-140">The file appears in the **Miscellaneous** folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="a69a2-141">Konfigurieren Sie das Projekt, um ein Bereitstellungshilfsprogramm zu erstellen, und erstellen Sie anschließend das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a69a2-141">Configure the project to create a deployment utility, and then build the project.</span></span> <span data-ttu-id="a69a2-142">Weitere Informationen finden Sie unter [Create a Deployment Utility](../../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-142">For more information, see [Create a Deployment Utility](../../create-a-deployment-utility.md).</span></span>  
  
     <span data-ttu-id="a69a2-143">Die Manifestdatei „\<*project name*>SSISDeploymentManifest.xml“ wird erstellt. Diese Datei enthält eine Auflistung der verschiedenen Dateien im Projekt, der Pakete und der Paketkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="a69a2-143">A manifest file, \<*project name*>.SSISDeploymentManifest.xml, is created that lists the miscellaneous files in the project, the packages, and the package configurations.</span></span>  
  
5.  <span data-ttu-id="a69a2-144">Stellen Sie das Paket für das Dateisystem bereit.</span><span class="sxs-lookup"><span data-stu-id="a69a2-144">Deploy the package to the file system.</span></span> <span data-ttu-id="a69a2-145">Weitere Informationen finden Sie unter [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a69a2-145">For more information, see [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69a2-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a69a2-146">See Also</span></span>  
 [<span data-ttu-id="a69a2-147">Erstellen eines Bereitstellungs-Hilfsprogramms</span><span class="sxs-lookup"><span data-stu-id="a69a2-147">Create a Deployment Utility</span></span>](../../create-a-deployment-utility.md)  
  
  
