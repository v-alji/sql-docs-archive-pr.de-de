---
title: Cacheverbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cacheconnection.f1
ms.assetid: 0d8f9324-0c35-4eea-b06d-da3cc2426d2c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 38a858217925496d8dd937d684368bdb2e061b14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621632"
---
# <a name="cache-connection-manager-editor"></a><span data-ttu-id="38343-102">Editor für den Cacheverbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="38343-102">Cache Connection Manager Editor</span></span>
  <span data-ttu-id="38343-103">Der Cacheverbindungs-Manager liest ein Verweisdataset aus der Cachetransformation oder einer Cachedatei (.caw) und kann die Daten in einer Cachedatei speichern.</span><span class="sxs-lookup"><span data-stu-id="38343-103">The Cache connection manager reads a reference dataset from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="38343-104">Die Daten werden immer im Arbeitsspeicher abgelegt.</span><span class="sxs-lookup"><span data-stu-id="38343-104">The data is always stored in memory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38343-105">Der Cacheverbindungs-Manager unterstützt die BLOB-Datentypen (Binary Large Object) DT_TEXT, DT_NTEXT und DT_IMAGE nicht.</span><span class="sxs-lookup"><span data-stu-id="38343-105">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="38343-106">Wenn das Verweisdataset einen BLOB-Datentyp enthält, schlägt die Komponente fehl, wenn Sie das Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="38343-106">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="38343-107">Sie können den **Cacheverbindungs-Manager-Editor** verwenden, um Spaltendatentypen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="38343-107">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span>  
  
 <span data-ttu-id="38343-108">Die Transformation für Suche führt Suchvorgänge im Verweisdataset aus.</span><span class="sxs-lookup"><span data-stu-id="38343-108">The Lookup transformation performs lookups on the reference dataset.</span></span>  
  
 <span data-ttu-id="38343-109">Das Dialogfeld **Editor für den Cacheverbindungs-Manager** schließt die folgenden Registerkarten ein:</span><span class="sxs-lookup"><span data-stu-id="38343-109">The **Cache Connection ManagerEditor** dialog box includes the following tabs:</span></span>  
  
-   [<span data-ttu-id="38343-110">Registerkarte "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="38343-110">General tab</span></span>](#generaltab)  
  
-   [<span data-ttu-id="38343-111">Registerkarte "Spalten"</span><span class="sxs-lookup"><span data-stu-id="38343-111">Columns tab</span></span>](#columnstab)  
  
 <span data-ttu-id="38343-112">Weitere Informationen zum Cacheverbindungs-Manager finden Sie unter [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="38343-112">To learn more about the Cache Connection Manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
##  <a name="general-tab"></a><a name="generaltab"></a><span data-ttu-id="38343-113">Registerkarte Allgemein</span><span class="sxs-lookup"><span data-stu-id="38343-113">General Tab</span></span>  
 <span data-ttu-id="38343-114">Geben Sie auf der Registerkarte **Allgemein** des Dialogfelds **Editor für den Cacheverbindungs-Manager** an, ob der Cache aus einer Datei gelesen werden soll oder ob der Cache in einer Datei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="38343-114">Use the **General** tab of the **Cache Connection ManagerEditor** dialog box to indicate whether to read the cache from a file or save the cache to a file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="38343-115">Tastatur</span><span class="sxs-lookup"><span data-stu-id="38343-115">Options</span></span>  
 <span data-ttu-id="38343-116">**Name des Verbindungs-Managers**</span><span class="sxs-lookup"><span data-stu-id="38343-116">**Connection manager name**</span></span>  
 <span data-ttu-id="38343-117">Geben Sie einen eindeutigen Namen für die Cacheverbindung im Workflow an.</span><span class="sxs-lookup"><span data-stu-id="38343-117">Provide a unique name for the cache connection in the workflow.</span></span> <span data-ttu-id="38343-118">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38343-118">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="38343-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="38343-119">**Description**</span></span>  
 <span data-ttu-id="38343-120">Beschreiben Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="38343-120">Describe the connection.</span></span> <span data-ttu-id="38343-121">Die bewährte Methode ist hierbei, die Verbindung zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und leichter zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="38343-121">As a best practice, describe the connection according to its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="38343-122">**Dateicache verwenden**</span><span class="sxs-lookup"><span data-stu-id="38343-122">**Use file cache**</span></span>  
 <span data-ttu-id="38343-123">Geben Sie an, ob eine Cachedatei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="38343-123">Indicate whether to use a cache file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38343-124">Die Schutzebene des Pakets gilt nicht für die Cachedatei.</span><span class="sxs-lookup"><span data-stu-id="38343-124">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="38343-125">Wenn die Cachedatei vertrauliche Informationen enthält, schränken Sie den Zugriff auf den Speicherort oder Ordner, in dem Sie die Datei speichern, mithilfe einer Zugriffssteuerungsliste ein.</span><span class="sxs-lookup"><span data-stu-id="38343-125">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="38343-126">Sie sollten nur bestimmten Konten den Zugriff ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="38343-126">You should enable access only to certain accounts.</span></span> <span data-ttu-id="38343-127">Weitere Informationen finden Sie unter [Zugriff auf Dateien, die von Paketen verwendet werden](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="38343-127">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="38343-128">Wenn Sie den Cacheverbindungs-Manager für die Verwendung einer Cachedatei konfigurieren, führt der Verbindungs-Manager eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="38343-128">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
-   <span data-ttu-id="38343-129">Speichern der Daten in einer Datei, wenn eine Cachetransformation so konfiguriert ist, dass Daten aus einer Datenquelle im Datenfluss in den Cacheverbindungs-Manager geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="38343-129">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span> <span data-ttu-id="38343-130">Weitere Informationen finden Sie unter [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="38343-130">For more information, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="38343-131">Lesen von Daten aus der Cachedatei</span><span class="sxs-lookup"><span data-stu-id="38343-131">Read data from the cache file.</span></span>  
  
 <span data-ttu-id="38343-132">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="38343-132">**File name**</span></span>  
 <span data-ttu-id="38343-133">Geben Sie den Pfad und Dateinamen der Cachedatei ein.</span><span class="sxs-lookup"><span data-stu-id="38343-133">Type the path and file name of the cache file.</span></span>  
  
 <span data-ttu-id="38343-134">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="38343-134">**Browse**</span></span>  
 <span data-ttu-id="38343-135">Suchen Sie die Cachedatei.</span><span class="sxs-lookup"><span data-stu-id="38343-135">Locate the cache file.</span></span>  
  
 <span data-ttu-id="38343-136">**Metadaten aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="38343-136">**Refresh Metadata**</span></span>  
 <span data-ttu-id="38343-137">Löschen Sie die Spaltenmetadaten im Cacheverbindungsmanager, und füllen Sie den Cacheverbindungs-Manager erneut mit Spaltenmetadaten aus einer bestimmten Cachedatei auf.</span><span class="sxs-lookup"><span data-stu-id="38343-137">Delete the column metadata in the Cache connection manager and repopulate the Cache connection manager with column metadata from a selected cache file.</span></span>  
  
##  <a name="columns-tab"></a><a name="columnstab"></a><span data-ttu-id="38343-138">Registerkarte Spalten</span><span class="sxs-lookup"><span data-stu-id="38343-138">Columns Tab</span></span>  
 <span data-ttu-id="38343-139">Auf der Registerkarte **Spalten** des Dialogfelds **Editor für den Cacheverbindungs-Manager** können Sie die Eigenschaften jeder Spalte im Cache konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="38343-139">Use the **Columns** tab of the **Cache Connection Manager Editor** dialog box to configure the properties of each column in the cache.</span></span>  
  
### <a name="options"></a><span data-ttu-id="38343-140">Tastatur</span><span class="sxs-lookup"><span data-stu-id="38343-140">Options</span></span>  
 <span data-ttu-id="38343-141">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="38343-141">**Column**</span></span>  
 <span data-ttu-id="38343-142">Geben Sie den Spaltennamen an.</span><span class="sxs-lookup"><span data-stu-id="38343-142">Specify the column name.</span></span>  
  
 <span data-ttu-id="38343-143">**Indexposition**</span><span class="sxs-lookup"><span data-stu-id="38343-143">**Index Position**</span></span>  
 <span data-ttu-id="38343-144">Geben Sie an, welche Spalten Indexspalten sind, indem Sie die Indexposition jeder Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="38343-144">Specify which columns are index columns by specifying the index position of each column.</span></span> <span data-ttu-id="38343-145">Der Index ist eine Auflistung einer oder mehrerer Spalten.</span><span class="sxs-lookup"><span data-stu-id="38343-145">The index is a collection of one or more columns.</span></span>  
  
 <span data-ttu-id="38343-146">Für Nicht-Index-Spalten ist die Indexposition 0.</span><span class="sxs-lookup"><span data-stu-id="38343-146">For non-index columns, the index position is 0.</span></span>  
  
 <span data-ttu-id="38343-147">Für Indexspalten ist die Indexposition eine fortlaufende positive Zahl.</span><span class="sxs-lookup"><span data-stu-id="38343-147">For index columns, the index position is a sequential, positive number.</span></span> <span data-ttu-id="38343-148">Diese Zahl gibt die Reihenfolge an, in der die Suchtransformation Zeilen im Verweisdataset mit Zeilen der Eingabedatenquelle vergleicht.</span><span class="sxs-lookup"><span data-stu-id="38343-148">This number indicates the order in which the Lookup transformation compares rows in the reference dataset to rows in the input data source.</span></span> <span data-ttu-id="38343-149">Die Spalte mit den meisten eindeutigen Werten sollte die niedrigste Indexposition aufweisen.</span><span class="sxs-lookup"><span data-stu-id="38343-149">The column with the most unique values should have the lowest index position.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38343-150">Wenn die Transformation für Suche so konfiguriert ist, dass sie einen Cacheverbindungs-Manager verwendet, können nur Indexspalten im Verweisdataset Eingabespalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="38343-150">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="38343-151">Auch müssen alle Indexspalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="38343-151">Also, all index columns must be mapped.</span></span>  
  
 <span data-ttu-id="38343-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="38343-152">**Type**</span></span>  
 <span data-ttu-id="38343-153">Geben Sie den Datentyp der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="38343-153">Specify the data type of the column.</span></span>  
  
 `Length`  
 <span data-ttu-id="38343-154">Gibt den Datentyp der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="38343-154">Specifies the column data type.</span></span> <span data-ttu-id="38343-155">Wenn für den Datentyp zutreffend, können Sie den Wert von `Length` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="38343-155">If applicable to the data type, you can update `Length`.</span></span>  
  
 `Precision`  
 <span data-ttu-id="38343-156">Gibt die Genauigkeit für bestimmte Spaltendatentypen an.</span><span class="sxs-lookup"><span data-stu-id="38343-156">Specifies the precision for certain column data types.</span></span> <span data-ttu-id="38343-157">Genauigkeit gibt die Anzahl der Ziffern einer Zahl an.</span><span class="sxs-lookup"><span data-stu-id="38343-157">Precision is the number of digits in a number.</span></span> <span data-ttu-id="38343-158">Wenn für den Datentyp zutreffend, können Sie den Wert von `Precision` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="38343-158">If applicable to the data type, you can update `Precision`.</span></span>  
  
 `Scale`  
 <span data-ttu-id="38343-159">Gibt die Dezimalstellen für bestimmte Spaltendatentypen an.</span><span class="sxs-lookup"><span data-stu-id="38343-159">Specifies the scale for certain column data types.</span></span> <span data-ttu-id="38343-160">Dezimalstellen gibt die Anzahl der Nachkommastellen an.</span><span class="sxs-lookup"><span data-stu-id="38343-160">Scale is the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="38343-161">Wenn für den Datentyp zutreffend, können Sie den Wert von `Scale` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="38343-161">If applicable to the data type, you can update `Scale`.</span></span>  
  
 `Code Page`  
 <span data-ttu-id="38343-162">Gibt die Codepage für den Spaltentyp an.</span><span class="sxs-lookup"><span data-stu-id="38343-162">Specifies the code page for the column type.</span></span> <span data-ttu-id="38343-163">Wenn für den Datentyp zutreffend, können Sie den Wert von `Code Page` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="38343-163">If applicable to the data type, you can update `Code Page`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38343-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38343-164">See Also</span></span>  
 [<span data-ttu-id="38343-165">Suchtransformation</span><span class="sxs-lookup"><span data-stu-id="38343-165">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
