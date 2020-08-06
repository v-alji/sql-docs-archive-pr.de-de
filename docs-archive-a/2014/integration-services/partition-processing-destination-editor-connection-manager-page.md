---
title: Ziel-Editor für Partitions Verarbeitung (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a0f79dfcc9c0d98d871a49618f4dabfb8a3bbac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617161"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="80438-102">Ziel-Editor für Partitionsverarbeitung (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="80438-102">Partition Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="80438-103">Geben Sie auf der Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für Partitionsverarbeitung** eine Verbindung mit einem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt oder einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="80438-103">Use the **Connection Manager** page of the **Partition Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="80438-104">Weitere Informationen zum Ziel für Partitionsverarbeitung finden Sie unter [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="80438-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80438-105">Hier beschriebene Tasks gelten nicht für tabellarische Analysis Services-Modelle.</span><span class="sxs-lookup"><span data-stu-id="80438-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="80438-106">Sie können Partitionsspalten für tabellarische Modelle keine Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="80438-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="80438-107">Sie können stattdessen den Analysis Services-Task "DDL ausführen" [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) verwenden, um die Partition zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="80438-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="80438-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="80438-108">Options</span></span>  
 <span data-ttu-id="80438-109">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="80438-109">**Connection manager**</span></span>  
 <span data-ttu-id="80438-110">Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="80438-110">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="80438-111">**Neu**</span><span class="sxs-lookup"><span data-stu-id="80438-111">**New**</span></span>  
 <span data-ttu-id="80438-112">Erstellen Sie mithilfe des Dialogfelds **Analysis Services-Verbindungs-Manager hinzufügen** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="80438-112">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="80438-113">**Liste der verfügbaren Partitionen**</span><span class="sxs-lookup"><span data-stu-id="80438-113">**List of available partitions**</span></span>  
 <span data-ttu-id="80438-114">Wählen Sie die zu verarbeitende Partition aus.</span><span class="sxs-lookup"><span data-stu-id="80438-114">Select the partition to process.</span></span>  
  
 <span data-ttu-id="80438-115">**Verarbeitungsmethode**</span><span class="sxs-lookup"><span data-stu-id="80438-115">**Processing method**</span></span>  
 <span data-ttu-id="80438-116">Wählen Sie die Verarbeitungsmethode aus.</span><span class="sxs-lookup"><span data-stu-id="80438-116">Select the processing method.</span></span> <span data-ttu-id="80438-117">Der Standardwert für diese Option ist **Vollständig**.</span><span class="sxs-lookup"><span data-stu-id="80438-117">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="80438-118">Wert</span><span class="sxs-lookup"><span data-stu-id="80438-118">Value</span></span>|<span data-ttu-id="80438-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="80438-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80438-120">Hinzufügen (inkrementell)</span><span class="sxs-lookup"><span data-stu-id="80438-120">Add (incremental)</span></span>|<span data-ttu-id="80438-121">Führt eine inkrementelle Verarbeitung der Partition aus.</span><span class="sxs-lookup"><span data-stu-id="80438-121">Perform an incremental processing of the partition.</span></span>|  
|<span data-ttu-id="80438-122">Vollständig</span><span class="sxs-lookup"><span data-stu-id="80438-122">Full</span></span>|<span data-ttu-id="80438-123">Führt eine vollständige Verarbeitung der Partition aus.</span><span class="sxs-lookup"><span data-stu-id="80438-123">Perform full processing of the partition.</span></span>|  
|<span data-ttu-id="80438-124">Nur Daten</span><span class="sxs-lookup"><span data-stu-id="80438-124">Data only</span></span>|<span data-ttu-id="80438-125">Führt eine Verarbeitung der Updates für die Partition aus.</span><span class="sxs-lookup"><span data-stu-id="80438-125">Perform an update processing of the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80438-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80438-126">See Also</span></span>  
 <span data-ttu-id="80438-127">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="80438-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="80438-128">[Ziel-Editor für Partitions Verarbeitung &#40;Seite Zuordnungen&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="80438-128">[Partition Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="80438-129">Ziel-Editor für Partitionsverarbeitung &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="80438-129">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
