---
title: Datenfluss Pfad-Editor (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.general.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: 72a9ff1d-3748-41d1-a9b2-63f4a77bba24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71eca61b1454e2e8cb811bbe450f584191ae77b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697066"
---
# <a name="data-flow-path-editor-general-page"></a><span data-ttu-id="0f01c-102">Datenflusspfad-Editor (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="0f01c-102">Data Flow Path Editor (General Page)</span></span>
  <span data-ttu-id="0f01c-103">Mithilfe des Dialogfelds **Datenflusspfad-Editor** legen Sie Pfadeigenschaften fest, zeigen Metadaten an und verwalten die mit dem Pfad verknüpften Daten-Viewer.</span><span class="sxs-lookup"><span data-stu-id="0f01c-103">Use the **Data Flow Path Editor** dialog box to set path properties, view column metadata, and manage the data viewers attached to the path.</span></span>  
  
 <span data-ttu-id="0f01c-104">Mit dem Knoten **Allgemein** des Dialogfelds **Datenflusspfad-Editor** werden der Pfad benannt und beschrieben und die Optionen für die Pfadanmerkungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="0f01c-104">Use the **General** node of the **Data Flow Path Editor** dialog box to name and describe the path, and to specify the options for path annotation.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0f01c-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0f01c-105">Options</span></span>  
 <span data-ttu-id="0f01c-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="0f01c-106">**Name**</span></span>  
 <span data-ttu-id="0f01c-107">Geben Sie einen eindeutigen Namen für den Pfad an.</span><span class="sxs-lookup"><span data-stu-id="0f01c-107">Provide a unique name for the path.</span></span>  
  
 <span data-ttu-id="0f01c-108">**ID**</span><span class="sxs-lookup"><span data-stu-id="0f01c-108">**ID**</span></span>  
 <span data-ttu-id="0f01c-109">Der Herkunftsbezeichner des Pfads.</span><span class="sxs-lookup"><span data-stu-id="0f01c-109">The lineage identifier of the path.</span></span> <span data-ttu-id="0f01c-110">Diese Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="0f01c-110">This property is read-only.</span></span>  
  
 <span data-ttu-id="0f01c-111">**IdentificationString**</span><span class="sxs-lookup"><span data-stu-id="0f01c-111">**IdentificationString**</span></span>  
 <span data-ttu-id="0f01c-112">Die Zeichenfolge, die den Pfad identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0f01c-112">The string that identifies the path.</span></span> <span data-ttu-id="0f01c-113">Wird automatisch aus dem oben eingegebenen Namen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="0f01c-113">Automatically generated from the name entered above.</span></span>  
  
 <span data-ttu-id="0f01c-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0f01c-114">**Description**</span></span>  
 <span data-ttu-id="0f01c-115">Beschreiben Sie den Pfad.</span><span class="sxs-lookup"><span data-stu-id="0f01c-115">Describe the path.</span></span>  
  
 <span data-ttu-id="0f01c-116">**PathAnnotation**</span><span class="sxs-lookup"><span data-stu-id="0f01c-116">**PathAnnotation**</span></span>  
 <span data-ttu-id="0f01c-117">Geben Sie den Typ der zu verwendenden Anmerkung ein.</span><span class="sxs-lookup"><span data-stu-id="0f01c-117">Specify the type of annotation to use.</span></span> <span data-ttu-id="0f01c-118">Wählen Sie **Never** , um Anmerkungen zu deaktivieren, **AsNeeded** , um Anmerkungen bei Bedarf zu aktivieren, **SourceName** , um eine Anmerkung automatisch anhand des Werts der Option **SourceName** zu erzeugen, oder **PathName** , um eine Anmerkung automatisch aus dem Wert der **Name** -Eigenschaft zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0f01c-118">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **SourceName** to automatically annotate using the value of the **SourceName** option, and **PathName** to automatically annotate using the value of the **Name** property.</span></span>  
  
 <span data-ttu-id="0f01c-119">**DestinationName**</span><span class="sxs-lookup"><span data-stu-id="0f01c-119">**DestinationName**</span></span>  
 <span data-ttu-id="0f01c-120">Zeigt die Eingabe an, die das Ende des Pfads angibt.</span><span class="sxs-lookup"><span data-stu-id="0f01c-120">Displays the input that is the end of the path.</span></span>  
  
 <span data-ttu-id="0f01c-121">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="0f01c-121">**SourceName**</span></span>  
 <span data-ttu-id="0f01c-122">Zeigt die Ausgabe an, die den Beginn des Pfads angibt.</span><span class="sxs-lookup"><span data-stu-id="0f01c-122">Displays the output that is the start of the path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f01c-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f01c-123">See Also</span></span>  
 <span data-ttu-id="0f01c-124">[Datenfluss Pfad-Editor &#40;Seite "Metadaten"&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span><span class="sxs-lookup"><span data-stu-id="0f01c-124">[Data Flow Path Editor &#40;Metadata Page&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span></span>  
 <span data-ttu-id="0f01c-125">[Datenfluss Pfad-Editor &#40;Seite "Daten-Viewer"&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="0f01c-125">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="0f01c-126">[Datenfluss](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="0f01c-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="0f01c-127">Verwenden von Anmerkungen in Paketen</span><span class="sxs-lookup"><span data-stu-id="0f01c-127">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
