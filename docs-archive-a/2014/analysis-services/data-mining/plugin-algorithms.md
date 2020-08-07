---
title: Plug-in-Algorithmen Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- third-party algorithms [Analysis Services]
- algorithms [data mining], creating
- plugin algorithms [Analysis Services]
ms.assetid: fe364ddc-576e-42fc-9ced-baa399992f92
author: minewiskan
ms.author: owend
ms.openlocfilehash: ebc5e007dcc6de7fb25d59547e21f1e892100570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718973"
---
# <a name="plugin-algorithms"></a><span data-ttu-id="2c918-102">Plug-In-Algorithmen</span><span class="sxs-lookup"><span data-stu-id="2c918-102">Plugin Algorithms</span></span>
  <span data-ttu-id="2c918-103">Zusätzlich zu den [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] von bereitgestellten Algorithmen gibt es viele andere Algorithmen, die Sie für Data Mining verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c918-103">In addition to the algorithms that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, there are many other algorithms that you can use for data mining.</span></span> <span data-ttu-id="2c918-104">Entsprechend stellt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] einen Mechanismus bereit, um von Drittanbietern erstellte Algorithmen als Plug-Ins zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="2c918-104">Accordingly, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides a mechanism for "plugging in" algorithms that are created by third parties.</span></span> <span data-ttu-id="2c918-105">Vorausgesetzt, die Algorithmen erfüllen bestimmte Standards, können Sie diese in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] genauso verwenden, wie die [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="2c918-105">As long as the algorithms follow certain standards, you can use them within [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] just as you use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms.</span></span> <span data-ttu-id="2c918-106">Plug-in-Algorithmen verfügen über alle Funktionen von Algorithmen, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2c918-106">Plugin algorithms have all the capabilities of algorithms that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides.</span></span>  
  
 <span data-ttu-id="2c918-107">Eine vollständige Beschreibung der Schnittstellen, die von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verwendet werden, um mit Plug-In-Algorithmen zu kommunizieren, finden Sie in den Beispielen für die Erstellung eines benutzerdefinierten Algorithmus und für benutzerdefinierte Modell-Viewer auf der [CodePlex-](https://go.microsoft.com/fwlink/?LinkID=87843) Website.</span><span class="sxs-lookup"><span data-stu-id="2c918-107">For a full description of the interfaces that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses to communicate with plugin algorithms, see the samples for creating a custom algorithm and custom model viewer that are published on [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) Web site.</span></span>  
  
## <a name="algorithm-requirements"></a><span data-ttu-id="2c918-108">Anforderungen für Algorithmen</span><span class="sxs-lookup"><span data-stu-id="2c918-108">Algorithm Requirements</span></span>  
 <span data-ttu-id="2c918-109">Damit ein Algorithmus als Plug-In in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]integriert werden kann, müssen Sie die folgenden COM-Schnittstellen implementieren:</span><span class="sxs-lookup"><span data-stu-id="2c918-109">To plug an algorithm into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must implement the following COM interfaces:</span></span>  
  
 `IDMAlgorithm`  
 <span data-ttu-id="2c918-110">Implementiert einen Algorithmus, der Modelle erstellt und implementiert die Vorhersagevorgänge der resultierenden Modelle.</span><span class="sxs-lookup"><span data-stu-id="2c918-110">Implements an algorithm that produces models, and implements the prediction operations of the resulting models.</span></span>  
  
 `IDMAlgorithmNavigation`  
 <span data-ttu-id="2c918-111">Ermöglicht Browsern den Zugriff auf die Inhalte von Modellen.</span><span class="sxs-lookup"><span data-stu-id="2c918-111">Enables browsers to access the content of the models.</span></span>  
  
 `IDMPersist`  
 <span data-ttu-id="2c918-112">Ermöglicht [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]das Laden und Speichern der vom Algorithmus trainierten Modelle.</span><span class="sxs-lookup"><span data-stu-id="2c918-112">Enables the models that the algorithm trains to be saved and loaded by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 `IDMAlgorithmMetadata`  
 <span data-ttu-id="2c918-113">Beschreibt die Funktionen und Eingabeparameter des Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="2c918-113">Describes the capabilities and input parameters of the algorithm.</span></span>  
  
 `IDMAlgorithmFactory`  
 <span data-ttu-id="2c918-114">Erstellt Instanzen der Objekte, die die Algorithmusschnittstelle implementieren und stellt für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] einen Zugriff auf die Schnittstelle der Algorithmusmetadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="2c918-114">Creates instances of the objects that implement the algorithm interface, and provides [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] with access to the algorithm-metadata interface.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="2c918-115">verwendet diese COM-Schnittstellen zum Kommunizieren mit den Plug-In-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="2c918-115">uses these COM interfaces to communicate with plugin algorithms.</span></span> <span data-ttu-id="2c918-116">Obwohl die verwendeten Plug-In-Algorithmen die [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Spezifikation OLE DB für Data Mining unterstützen müssen, müssen Sie nicht alle Data Mining-Optionen in der Spezifikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2c918-116">Although plugin algorithms that you use must support the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB for Data Mining specification, they do not have to support all the data mining options in the specification.</span></span> <span data-ttu-id="2c918-117">Mit dem [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) -Schemarowset können Sie die Funktionen eines Algorithmus ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2c918-117">You can use the [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) schema rowset to determine the capabilities of an algorithm.</span></span> <span data-ttu-id="2c918-118">Dieses Schemarowset führt die unterstützten Data Mining-Optionen für jeden Anbieter von Plug-In-Algorithmen auf.</span><span class="sxs-lookup"><span data-stu-id="2c918-118">This schema rowset lists the data mining support options for each plugin algorithm provider.</span></span>  
  
 <span data-ttu-id="2c918-119">Sie müssen neue Algorithmen registrieren, bevor Sie sie mit [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c918-119">You must register new algorithms before you use them with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="2c918-120">Fügen Sie die folgenden Informationen in die INI-Datei der Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ein, in die die Algorithmen integriert werden sollen, um einen Algorithmus zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="2c918-120">To register an algorithm, include the following information in the .ini file of the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on which you want to include the algorithms:</span></span>  
  
-   <span data-ttu-id="2c918-121">Der Algorithmusname</span><span class="sxs-lookup"><span data-stu-id="2c918-121">The algorithm name</span></span>  
  
-   <span data-ttu-id="2c918-122">ProgID (dies ist optional und wird nur für Plug-In-Algorithmen eingefügt)</span><span class="sxs-lookup"><span data-stu-id="2c918-122">ProgID (this is optional and will only be included for plugin algorithms)</span></span>  
  
-   <span data-ttu-id="2c918-123">Ein Flag, das angibt, ob der Algorithmus aktiviert ist oder nicht</span><span class="sxs-lookup"><span data-stu-id="2c918-123">A flag that indicates whether the algorithm is enabled or not</span></span>  
  
 <span data-ttu-id="2c918-124">Das folgende Codebeispiel illustriert die Registrierung eines neuen Algorithmus:</span><span class="sxs-lookup"><span data-stu-id="2c918-124">The following code sample illustrates how to register a new algorithm:</span></span>  
  
 `<ConfigurationSettings>`  
  
 `...`  
  
 `<DataMining>`  
  
 `...`  
  
 `<Algorithms>`  
  
 `...`  
  
 `<Sample_Plugin_Algorithm>`  
  
 `<Enabled>1</Enabled>`  
  
 `<ProgID>Microsoft.DataMining.SamplePlugInAlgorithm.Factory</ProgID>`  
  
 `</Sample_PlugIn_Algorithm>`  
  
 `...`  
  
 `</Algorithms>`  
  
 `...`  
  
 `</DataMining>`  
  
 `...`  
  
 `</ConfigurationSettings>`  
  
## <a name="see-also"></a><span data-ttu-id="2c918-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c918-125">See Also</span></span>  
 <span data-ttu-id="2c918-126">[Data Mining-Algorithmen &#40;Analysis Services Data Mining-&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="2c918-126">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="2c918-127">DMSCHEMA_MINING_SERVICES-Rowset</span><span class="sxs-lookup"><span data-stu-id="2c918-127">DMSCHEMA_MINING_SERVICES Rowset</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset)  
  
  
