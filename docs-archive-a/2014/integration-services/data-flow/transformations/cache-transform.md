---
title: Cachetransformation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetrans.f1
helpviewer_keywords:
- Cache transform
ms.assetid: a5683fc8-9c32-4634-819e-e9815627e4f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34be3252a3caf344c95e13ae45cc485a8c4ffdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619246"
---
# <a name="cache-transform"></a><span data-ttu-id="4ea1b-102">Cachetransformation</span><span class="sxs-lookup"><span data-stu-id="4ea1b-102">Cache Transform</span></span>
  <span data-ttu-id="4ea1b-103">Die Transformation für Cachetransformation generiert ein Verweisdataset für die Transformation für Suche, indem Daten aus einer verbundenen Datenquelle im Datenfluss in einen Cacheverbindungs-Manager geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-103">The Cache Transform transformation generates a reference dataset for the Lookup Transformation by writing data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="4ea1b-104">Die Transformation für Suche führt Suchvorgänge aus, indem Daten in Eingabespalten aus einer verbundenen Datenquelle mit Spalten in der Verweisdatenbank verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-104">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference database.</span></span>  
  
 <span data-ttu-id="4ea1b-105">Sie können den Cacheverbindungs-Manager verwenden, wenn Sie die Transformation für Suche für die Ausführung im Vollcachemodus konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-105">You can use the Cache connection manager when you want to configure the Lookup Transformation to run in the full cache mode.</span></span> <span data-ttu-id="4ea1b-106">In diesem Modus wird das Verweisdataset in den Cache geladen, bevor die Transformation für Suche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-106">In this mode, the reference dataset is loaded into cache before the Lookup Transformation runs.</span></span>  
  
 <span data-ttu-id="4ea1b-107">Anweisungen dazu, wie die Transformation für Suche im Vollcachemodus mit dem Cacheverbindungs-Manager und der Transformation für Cachetransformation konfiguriert wird, finden Sie unter [Implementieren einer Suchtransformation im Vollcachemodus mit dem Cacheverbindungs-Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1b-107">For instructions on how to configure the Lookup transformation in full cache mode with the Cache connection manager and Cache Transform transformation, see [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="4ea1b-108">Weitere Informationen zum Zwischenspeichern des Verweisdatasets finden Sie unter [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1b-108">For more information on caching the reference dataset, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ea1b-109">Die Cachetransformation schreibt nur eindeutige Zeilen in den Cacheverbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-109">The Cache Transform writes only unique rows to the Cache connection manager.</span></span>  
  
 <span data-ttu-id="4ea1b-110">In einem einzelnen Paket kann nur eine Cachetransformation Daten in den gleichen Cacheverbindungs-Manager schreiben.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-110">In a single package, only one Cache Transform can write data to the same Cache connection manager.</span></span> <span data-ttu-id="4ea1b-111">Wenn das Paket mehrere Cachetransformationen enthält, schreibt die erste beim Ausführen des Pakets aufgerufene Cachetransformation die Daten in den Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-111">If the package contains multiple Cache Transforms, the first Cache Transform that is called when the package runs, writes the data to the connection manager.</span></span> <span data-ttu-id="4ea1b-112">Bei den Schreibvorgängen nachfolgender Cachetransformationen treten Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-112">The write operations of subsequent Cache Transforms fail.</span></span>  
  
 <span data-ttu-id="4ea1b-113">Weitere Informationen finden Sie unter [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) und [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1b-113">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
## <a name="configuration-of-the-cache-transform"></a><span data-ttu-id="4ea1b-114">Konfiguration der Cachetransformation</span><span class="sxs-lookup"><span data-stu-id="4ea1b-114">Configuration of the Cache Transform</span></span>  
 <span data-ttu-id="4ea1b-115">Sie können den Cacheverbindungs-Manager so konfigurieren, dass die Daten in einer Cachedatei (.caw) gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-115">You can configure the Cache connection manager to save the data to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="4ea1b-116">Es gibt folgende Möglichkeiten, die Cachetransformation zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4ea1b-116">You can configure the Cache Transform in the following ways:</span></span>  
  
-   <span data-ttu-id="4ea1b-117">Geben Sie den Cacheverbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-117">Specify the Cache connection manager.</span></span>  
  
-   <span data-ttu-id="4ea1b-118">Ordnen Sie die Eingabespalten in der Cachetransformation den Zielspalten im Cacheverbindungs-Manager zu.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-118">Map the input columns in the Cache Transform to destination columns in the Cache connection manager.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ea1b-119">Jede Eingabespalte muss einer Zielspalte zugeordnet werden, und die Spaltendatentypen müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-119">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="4ea1b-120">Andernfalls zeigt der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Designer eine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-120">Otherwise, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
     <span data-ttu-id="4ea1b-121">Sie können den **Cacheverbindungs-Manager-Editor** verwenden, um Spaltendatentypen, Namen und andere Spalteneigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-121">You can use the **Cache Connection Manager Editor** to modify column data types, names, and other column properties.</span></span>  
  
 <span data-ttu-id="4ea1b-122">Eigenschaften können Sie mit dem [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="4ea1b-122">You can set properties through [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span></span> <span data-ttu-id="4ea1b-123">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Erweiterter Editor** festlegen können, finden Sie unter [Transformation Custom Properties](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1b-123">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="4ea1b-124">Weitere Informationen zum Festlegen der Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4ea1b-124">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea1b-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ea1b-125">See Also</span></span>  
 <span data-ttu-id="4ea1b-126">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="4ea1b-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 [<span data-ttu-id="4ea1b-127">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="4ea1b-127">Data Flow</span></span>](../data-flow.md)  
  
  
