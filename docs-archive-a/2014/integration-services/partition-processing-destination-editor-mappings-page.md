---
title: Ziel-Editor für Partitions Verarbeitung (Seite Zuordnungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.mapping.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: e75b766c-85ba-453e-9576-4a1a34f91ecc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3855b15c7ebf1f6fa95c941931869064d552680e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621575"
---
# <a name="partition-processing-destination-editor-mappings-page"></a><span data-ttu-id="37ba2-102">Ziel-Editor für Partitionsverarbeitung (Seite Zuordnungen)</span><span class="sxs-lookup"><span data-stu-id="37ba2-102">Partition Processing Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="37ba2-103">Auf der Seite **Zuordnungen** des Dialogfelds **Ziel-Editor für Partitionsverarbeitung** können Sie Eingabespalten Partitionsspalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="37ba2-103">Use the **Mappings** page of the **Partition Processing Destination Editor** dialog box to map input columns to partition columns.</span></span>  
  
 <span data-ttu-id="37ba2-104">Weitere Informationen zum Ziel für Partitionsverarbeitung finden Sie unter [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="37ba2-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37ba2-105">Hier beschriebene Tasks gelten nicht für tabellarische Analysis Services-Modelle.</span><span class="sxs-lookup"><span data-stu-id="37ba2-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="37ba2-106">Sie können Partitionsspalten für tabellarische Modelle keine Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="37ba2-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="37ba2-107">Sie können stattdessen den Analysis Services-Task "DDL ausführen" [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) verwenden, um die Partition zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="37ba2-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="37ba2-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="37ba2-108">Options</span></span>  
 <span data-ttu-id="37ba2-109">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="37ba2-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="37ba2-110">Zeigt die Liste der verfügbaren Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="37ba2-110">View the list of available input columns.</span></span> <span data-ttu-id="37ba2-111">Mithilfe eines Drag-und-Drop-Vorgangs können Sie verfügbare Eingabespalten in der Tabelle Zielspalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="37ba2-111">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="37ba2-112">**Verfügbare Zielspalten**</span><span class="sxs-lookup"><span data-stu-id="37ba2-112">**Available Destination Columns**</span></span>  
 <span data-ttu-id="37ba2-113">Zeigt die Liste der verfügbaren Zielspalten an.</span><span class="sxs-lookup"><span data-stu-id="37ba2-113">View the list of available destination columns.</span></span> <span data-ttu-id="37ba2-114">Mithilfe eines Drag-und-Drop-Vorgangs können Sie verfügbare Zielspalten in der Tabelle Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="37ba2-114">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="37ba2-115">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="37ba2-115">**Input Column**</span></span>  
 <span data-ttu-id="37ba2-116">Zeigen Sie die in obiger Tabelle ausgewählten Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="37ba2-116">View input columns selected from the table above.</span></span> <span data-ttu-id="37ba2-117">Die Zuordnungen können Sie mithilfe der Liste **Verfügbare Eingabespalten**ändern.</span><span class="sxs-lookup"><span data-stu-id="37ba2-117">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="37ba2-118">**Zielspalte**</span><span class="sxs-lookup"><span data-stu-id="37ba2-118">**Destination Column**</span></span>  
 <span data-ttu-id="37ba2-119">Zeigt alle verfügbaren Zielspalten an, und ob sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="37ba2-119">View each available destination column, whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ba2-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37ba2-120">See Also</span></span>  
 <span data-ttu-id="37ba2-121">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="37ba2-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="37ba2-122">[Ziel-Editor für Partitions Verarbeitung &#40;Seite Verbindungs-Manager&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="37ba2-122">[Partition Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="37ba2-123">Ziel-Editor für Partitionsverarbeitung &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="37ba2-123">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
