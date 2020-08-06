---
title: Cacheverbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b8a7cc8bbe9e93c385fca6257e0be2e79bd3148a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618215"
---
# <a name="cache-connection-manager"></a><span data-ttu-id="4481c-102">Cacheverbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="4481c-102">Cache Connection Manager</span></span>
  <span data-ttu-id="4481c-103">Der Cacheverbindungs-Manager liest Daten aus der Cachetransformation oder einer Cachedatei (.caw) und kann die Daten in einer Cachedatei speichern.</span><span class="sxs-lookup"><span data-stu-id="4481c-103">The Cache connection manager reads data from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="4481c-104">Unabhängig davon, ob der Cacheverbindungs-Manager für die Verwendung einer Cachedatei konfiguriert ist, werden die Daten stets im Arbeitsspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4481c-104">Whether you configure the Cache connection manager to use a cache file, the data is always stored in memory.</span></span>  
  
 <span data-ttu-id="4481c-105">Mit der Transformation für Cachetransformation können Daten aus einer verbundenen Datenquelle im Datenfluss in einen Cacheverbindungs-Manager geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4481c-105">The Cache Transform transformation writes data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="4481c-106">Die Transformation für Suche in einem Paket führt Suchvorgänge in den Daten aus.</span><span class="sxs-lookup"><span data-stu-id="4481c-106">The Lookup transformation in a package performs lookups on the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4481c-107">Der Cacheverbindungs-Manager unterstützt die BLOB-Datentypen (Binary Large Object) DT_TEXT, DT_NTEXT und DT_IMAGE nicht.</span><span class="sxs-lookup"><span data-stu-id="4481c-107">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="4481c-108">Wenn das Verweisdataset einen BLOB-Datentyp enthält, schlägt die Komponente fehl, wenn Sie das Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="4481c-108">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="4481c-109">Sie können den **Cacheverbindungs-Manager-Editor** verwenden, um Spaltendatentypen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4481c-109">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span> <span data-ttu-id="4481c-110">Weitere Informationen finden Sie unter [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-110">For more information, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4481c-111">Die Schutzebene des Pakets gilt nicht für die Cachedatei.</span><span class="sxs-lookup"><span data-stu-id="4481c-111">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="4481c-112">Wenn die Cachedatei vertrauliche Informationen enthält, schränken Sie den Zugriff auf den Speicherort oder Ordner, in dem Sie die Datei speichern, mithilfe einer Zugriffssteuerungsliste ein.</span><span class="sxs-lookup"><span data-stu-id="4481c-112">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="4481c-113">Sie sollten nur bestimmten Konten den Zugriff ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4481c-113">You should enable access only to certain accounts.</span></span> <span data-ttu-id="4481c-114">Weitere Informationen finden Sie unter [Zugriff auf Dateien, die von Paketen verwendet werden](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-114">For more information, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
## <a name="configuration-of-the-cache-connection-manager"></a><span data-ttu-id="4481c-115">Konfiguration des Cacheverbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="4481c-115">Configuration of the Cache Connection Manager</span></span>  
 <span data-ttu-id="4481c-116">Es gibt folgende Möglichkeiten, um den Cacheverbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4481c-116">You can configure the Cache connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="4481c-117">Geben Sie an, ob eine Cachedatei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4481c-117">Indicate whether to use a cache file.</span></span>  
  
     <span data-ttu-id="4481c-118">Wenn Sie den Cacheverbindungs-Manager für die Verwendung einer Cachedatei konfigurieren, führt der Verbindungs-Manager eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4481c-118">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
    -   <span data-ttu-id="4481c-119">Speichern der Daten in einer Datei, wenn eine Cachetransformation so konfiguriert ist, dass Daten aus einer Datenquelle im Datenfluss in den Cacheverbindungs-Manager geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4481c-119">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span>  
  
    -   <span data-ttu-id="4481c-120">Lesen von Daten aus der Cachedatei</span><span class="sxs-lookup"><span data-stu-id="4481c-120">Read data from the cache file.</span></span>  
  
     <span data-ttu-id="4481c-121">Weitere Informationen finden Sie unter [Cache Transform](../data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-121">For more information, see [Cache Transform](../data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="4481c-122">Ändern Sie die Metadaten der im Cache gespeicherten Spalten.</span><span class="sxs-lookup"><span data-stu-id="4481c-122">Change metadata for the columns stored in the cache.</span></span>  
  
-   <span data-ttu-id="4481c-123">Aktualisieren Sie den Cachedateinamen zur Laufzeit mithilfe eines Ausdrucks zum Festlegen der „ConnectionString“-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4481c-123">Update the cache file name at runtime by using an expression to set the ConnectionString property.</span></span> <span data-ttu-id="4481c-124">Weitere Informationen finden Sie unter [Verwenden von Eigenschaftsausdrücken in Paketen](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-124">For more information, see [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>  
  
 <span data-ttu-id="4481c-125">Sie können Eigenschaften mit dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="4481c-125">You can set properties through [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4481c-126">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Designer festlegen können, finden Sie unter [Cacheverbindungs-Manager-Editor](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-126">For more information about the properties that you can set in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="4481c-127">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und unter [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-127">For information about how to configure a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4481c-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4481c-128">Related Tasks</span></span>  
 [<span data-ttu-id="4481c-129">Implementieren einer Suchtransformation im Vollcachemodus mit der Transformation für Cacheverbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="4481c-129">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  
