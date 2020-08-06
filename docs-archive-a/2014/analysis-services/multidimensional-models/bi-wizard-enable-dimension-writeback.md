---
title: Rück Schreiben von Dimensionen aktivieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
author: minewiskan
ms.author: owend
ms.openlocfilehash: cba4a54e8a51d022c6f84a4c81d32f359a95692a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615659"
---
# <a name="enable-dimension-writeback"></a><span data-ttu-id="85513-102">Rückschreiben von Dimensionen aktivieren</span><span class="sxs-lookup"><span data-stu-id="85513-102">Enable Dimension Writeback</span></span>
  <span data-ttu-id="85513-103">Fügen Sie einem Cube oder einer Dimension die Erweiterung zum Rückschreiben von Dimensionen hinzu, um Benutzern das manuelle Ändern der Dimensionsstruktur und -elemente zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="85513-103">Add the dimension writeback enhancement to a cube or dimension to allow users to manually modify the dimension structure and members.</span></span> <span data-ttu-id="85513-104">Updates für eine Dimension mit aktiviertem Schreibzugriff werden direkt in der Dimensionstabelle aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="85513-104">Updates to a write-enabled dimension are recorded directly in the dimension table.</span></span> <span data-ttu-id="85513-105">Durch diese Erweiterung wird die Einstellung der `WriteEnabled`-Eigenschaft für eine Dimension geändert.</span><span class="sxs-lookup"><span data-stu-id="85513-105">This enhancement changes the `WriteEnabled` property setting for a dimension.</span></span>  
  
 <span data-ttu-id="85513-106">Verwenden Sie den Business Intelligence-Assistenten, um das Rückschreiben von Dimensionen zu aktivieren, und wählen Sie auf der Seite **Erweiterung auswählen** die Option **Rückschreiben von Dimensionen aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="85513-106">To add dimension writeback, you use the Business Intelligence Wizard, and select the **Enable dimension writeback** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="85513-107">Anschließend führt Sie der Assistent durch die Schritte zum Auswählen einer Dimension, für die Sie das Rückschreiben von Dimensionen anwenden möchten, und zum Festlegen dieser Option für die ausgewählte Dimension.</span><span class="sxs-lookup"><span data-stu-id="85513-107">This wizard then guides you through the steps of selecting a dimension to which you want to apply dimension writeback and setting this option for the selected dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85513-108">Das Rückschreiben wird nur für relationale SQL Server-Datenbanken und Data Marts unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85513-108">Writeback is supported for SQL Server relational databases and data marts only.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="85513-109">Auswählen einer Dimension</span><span class="sxs-lookup"><span data-stu-id="85513-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="85513-110">Auf der ersten Seite **Rückschreiben von Dimensionen aktivieren** des Assistenten geben Sie die Dimension an, auf die Sie das Rückschreiben von Dimensionen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="85513-110">On the first **Enable Dimension Writeback** page of the wizard, you specify the dimension to which you want to apply dimension writeback.</span></span> <span data-ttu-id="85513-111">Die Erweiterung zum Rückschreiben von Dimensionen, die dieser ausgewählten Dimension hinzugefügt wurde, führt zu Änderungen an der Dimension.</span><span class="sxs-lookup"><span data-stu-id="85513-111">The dimension writeback enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="85513-112">Diese Änderungen werden an alle Cubes vererbt, die die ausgewählte Dimension enthalten.</span><span class="sxs-lookup"><span data-stu-id="85513-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="setting-dimension-writeback-capability"></a><span data-ttu-id="85513-113">Festlegen des Features zum Rückschreiben von Dimensionen</span><span class="sxs-lookup"><span data-stu-id="85513-113">Setting Dimension Writeback Capability</span></span>  
 <span data-ttu-id="85513-114">Auf der zweiten Seite **Rückschreiben von Dimensionen aktivieren** des Assistenten findet das eigentliche Festlegen der Option **Rückschreiben in der Dimension aktivieren** statt.</span><span class="sxs-lookup"><span data-stu-id="85513-114">On the second **Enable Dimension Writeback** page of the wizard, you actually set the **Enable writeback in the dimension** option.</span></span> <span data-ttu-id="85513-115">Durch Auswählen dieser Option wird die `WriteEnabled`-Eigenschaft der Dimension automatisch auf `True` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85513-115">Selecting this option automatically sets the `WriteEnabled` property of the dimension to `True`.</span></span> <span data-ttu-id="85513-116">Durch Deaktivieren dieser Option wird die Eigenschaft automatisch auf `False` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85513-116">Clearing this option automatically sets the property to `False`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85513-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="85513-117">Remarks</span></span>  
 <span data-ttu-id="85513-118">Beim Erstellen eines neuen Elements müssen Sie jedes Attribut in einer Dimension angeben.</span><span class="sxs-lookup"><span data-stu-id="85513-118">When you create a new member, you must include every attribute in a dimension.</span></span> <span data-ttu-id="85513-119">Sie können kein Element einfügen, ohne dabei einen Wert für das Schlüsselattribut der Dimension anzugeben.</span><span class="sxs-lookup"><span data-stu-id="85513-119">You cannot insert a member without specifying a value for the key attribute of the dimension.</span></span> <span data-ttu-id="85513-120">Deshalb unterliegt das Erstellen von Elementen allen Beschränkungen (z.&#160;B. von NULL verschiedene Schlüsselwerte), die für die Dimensionstabelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="85513-120">Therefore, creating members is subject to any constraints (such as non-null key values) that are defined on the dimension table.</span></span> <span data-ttu-id="85513-121">Sie sollten auch Spalten berücksichtigen, die optional durch Dimensionseigenschaften angegeben werden, z. B. Spalten, die in den Dimensionseigenschaften `CustomRollupColumn`, `CustomRollupPropertiesColumn` oder `UnaryOperatorColumn` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85513-121">You should also consider columns optionally specified by dimension properties, such as columns specified in the `CustomRollupColumn`, `CustomRollupPropertiesColumn` or the `UnaryOperatorColumn` dimension properties.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="85513-122">Wenn Sie SQL Azure als Datenquelle verwenden, um einen Rückschreibevorgang in eine Analysis Services-Datenbank auszuführen, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="85513-122">If you use SQL Azure as a data source to perform writeback into an Analysis Services database, the operation fails.</span></span> <span data-ttu-id="85513-123">Dies ist programmbedingt, da die Anbieteroption, durch die mehrere aktive Resultsets (MARS) aktiviert werden, standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="85513-123">This is by design, because the provider option that enables multiple active result sets (MARS) is not turned on by default.</span></span>  
>   
>  <span data-ttu-id="85513-124">Als Problemumgehung fügen Sie der Verbindungszeichenfolge folgende Einstellung hinzu, damit MARS unterstützt und Rückschreibvorgänge aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="85513-124">The workaround is to add the following setting in the connection string, to support MARS and to enable writeback:</span></span>  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  <span data-ttu-id="85513-125">Weitere Informationen finden [Sie unter Verwenden von mehreren aktiven Resultsets &#40;Mars&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="85513-125">For more information see [Using Multiple Active Result Sets &#40;MARS&#41;](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85513-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85513-126">See Also</span></span>  
 [<span data-ttu-id="85513-127">Dimensionen mit aktiviertem Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="85513-127">Write-Enabled Dimensions</span></span>](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
