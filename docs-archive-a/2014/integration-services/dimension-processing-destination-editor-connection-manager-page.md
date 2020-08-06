---
title: Ziel-Editor für Dimensions Verarbeitung (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622230"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="211f0-102">Ziel-Editor für Dimensionsverarbeitung (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="211f0-102">Dimension Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="211f0-103">Verwenden Sie die Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für Dimensionsverarbeitung**, um eine Verbindung mit einem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Projekt oder einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Instanz anzugeben.</span><span class="sxs-lookup"><span data-stu-id="211f0-103">Use the **Connection Manager** page of the **Dimension Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="211f0-104">Weitere Informationen zum Ziel für Dimensionsverarbeitung finden Sie unter [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="211f0-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="211f0-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="211f0-105">Options</span></span>  
 <span data-ttu-id="211f0-106">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="211f0-106">**Connection manager**</span></span>  
 <span data-ttu-id="211f0-107">Wählen Sie einen vorhandenen Verbindungs-Manager aus der Liste aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="211f0-107">Select an existing connection manager from the list, or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="211f0-108">**Neu**</span><span class="sxs-lookup"><span data-stu-id="211f0-108">**New**</span></span>  
 <span data-ttu-id="211f0-109">Erstellen Sie mithilfe des Dialogfelds **Analysis Services-Verbindungs-Manager hinzufügen** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="211f0-109">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="211f0-110">**Liste der verfügbaren Dimensionen**</span><span class="sxs-lookup"><span data-stu-id="211f0-110">**List of available dimensions**</span></span>  
 <span data-ttu-id="211f0-111">Wählen Sie die zu verarbeitende Dimension aus.</span><span class="sxs-lookup"><span data-stu-id="211f0-111">Select the dimension to process.</span></span>  
  
 <span data-ttu-id="211f0-112">**Verarbeitungsmethode**</span><span class="sxs-lookup"><span data-stu-id="211f0-112">**Processing method**</span></span>  
 <span data-ttu-id="211f0-113">Wählen Sie die Verarbeitungsmethode aus, die auf die in der Liste ausgewählte Dimension angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="211f0-113">Select the processing method to apply to the dimension selected in the list.</span></span> <span data-ttu-id="211f0-114">Der Standardwert für diese Option ist **Vollständig**.</span><span class="sxs-lookup"><span data-stu-id="211f0-114">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="211f0-115">Wert</span><span class="sxs-lookup"><span data-stu-id="211f0-115">Value</span></span>|<span data-ttu-id="211f0-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="211f0-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="211f0-117">**Hinzufügen (inkrementell)**</span><span class="sxs-lookup"><span data-stu-id="211f0-117">**Add (incremental)**</span></span>|<span data-ttu-id="211f0-118">Führt eine inkrementelle Verarbeitung der Dimension aus.</span><span class="sxs-lookup"><span data-stu-id="211f0-118">Perform an incremental processing of the dimension.</span></span>|  
|<span data-ttu-id="211f0-119">**Vollständig**</span><span class="sxs-lookup"><span data-stu-id="211f0-119">**Full**</span></span>|<span data-ttu-id="211f0-120">Führt eine vollständige Verarbeitung der Dimension aus.</span><span class="sxs-lookup"><span data-stu-id="211f0-120">Perform full processing of the dimension.</span></span>|  
|<span data-ttu-id="211f0-121">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="211f0-121">**Update**</span></span>|<span data-ttu-id="211f0-122">Führt eine Verarbeitung der Updates für die Dimension aus.</span><span class="sxs-lookup"><span data-stu-id="211f0-122">Perform an update processing of the dimension.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="211f0-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="211f0-123">See Also</span></span>  
 <span data-ttu-id="211f0-124">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="211f0-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="211f0-125">[Ziel-Editor für Dimensions Verarbeitung &#40;Seite Zuordnungen&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="211f0-125">[Dimension Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="211f0-126">Ziel-Editor für Dimensionsverarbeitung &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="211f0-126">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
