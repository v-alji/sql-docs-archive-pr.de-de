---
title: Definieren von Daten Bank Dimensionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], defining
ms.assetid: fe84588b-66a3-4100-a1cf-59b21b7adf01
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad5334e71b0f133f80933a7d1702d8ada7565501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696246"
---
# <a name="define-database-dimensions"></a><span data-ttu-id="9e066-102">Definieren von Datenbankdimensionen</span><span class="sxs-lookup"><span data-stu-id="9e066-102">Define Database Dimensions</span></span>
  <span data-ttu-id="9e066-103">Verwenden Sie den Dimensions-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , um eine vorhandene Daten Bank Dimension in einem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt oder einer Datenbank zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e066-103">Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="9e066-104">Sie können den Dimensions-Designer für die folgenden Aufgaben verwenden:</span><span class="sxs-lookup"><span data-stu-id="9e066-104">You can use Dimension Designer to do the following:</span></span>  
  
-   <span data-ttu-id="9e066-105">Konfigurieren der Eigenschaften der Dimensionsebenen.</span><span class="sxs-lookup"><span data-stu-id="9e066-105">Configure the dimension-level properties.</span></span>  
  
-   <span data-ttu-id="9e066-106">Hinzufügen und Konfigurieren von Dimensionsattributen.</span><span class="sxs-lookup"><span data-stu-id="9e066-106">Add and configure dimension attributes.</span></span>  
  
-   <span data-ttu-id="9e066-107">Definieren und Konfigurieren von benutzerdefinierten Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="9e066-107">Define and configure user-defined hierarchies.</span></span>  
  
-   <span data-ttu-id="9e066-108">Definieren und Konfigurieren von Beziehungen zwischen Attributen.</span><span class="sxs-lookup"><span data-stu-id="9e066-108">Define and configure relationships between attributes.</span></span>  
  
-   <span data-ttu-id="9e066-109">Definieren von Dimensionsübersetzungen.</span><span class="sxs-lookup"><span data-stu-id="9e066-109">Define dimension translations.</span></span>  
  
-   <span data-ttu-id="9e066-110">Bei verarbeiteten Dimensionen können Sie die Dimensionsstruktur durchsuchen und Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9e066-110">For processed dimensions, you can browse the dimension structure and view data.</span></span>  
  
 <span data-ttu-id="9e066-111">Nachdem Sie Dimensionen, Attribute oder Hierarchien geändert haben, müssen Sie sie verarbeiten, damit die Änderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e066-111">After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes.</span></span> <span data-ttu-id="9e066-112">Wenn Sie dabei im Projektmodus arbeiten, müssen Sie die Änderungen vor der Verarbeitung für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9e066-112">When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance before processing.</span></span>  
  
 <span data-ttu-id="9e066-113">Weitere Informationen dazu, wie Sie eine Dimension im Dimensions-Designer öffnen, finden Sie unter [Ändern oder Löschen einer Datenbankdimension im Projektmappen-Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="9e066-113">For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span></span>  
  
 <span data-ttu-id="9e066-114">Der Dimensions-Designer besitzt drei Registerkarten, die in der folgenden Tabelle beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9e066-114">Dimension Designer has three different tabs, which are described in the following table.</span></span>  
  
|<span data-ttu-id="9e066-115">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="9e066-115">Tab</span></span>|<span data-ttu-id="9e066-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9e066-116">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="9e066-117">**Dimensionsstruktur**</span><span class="sxs-lookup"><span data-stu-id="9e066-117">**Dimension Structure**</span></span>|<span data-ttu-id="9e066-118">Verwenden Sie diese Registerkarte, um mit der Struktur einer Dimension zu arbeiten, um das Schema der Datenquellen Sicht für eine Dimension zu überprüfen oder zu erstellen, um Attribute zu verwenden und um Attribute in benutzerdefinierten Hierarchien zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="9e066-118">Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.</span></span>|  
|<span data-ttu-id="9e066-119">**Attributbeziehungen**</span><span class="sxs-lookup"><span data-stu-id="9e066-119">**Attribute Relationships**</span></span>|<span data-ttu-id="9e066-120">Verwenden Sie diese Registerkarte, um die Attributbeziehungen einer Dimension zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9e066-120">Use this tab to create, modify, or delete the attribute relationships of a dimension.</span></span>|  
|<span data-ttu-id="9e066-121">**Translations**</span><span class="sxs-lookup"><span data-stu-id="9e066-121">**Translations**</span></span>|<span data-ttu-id="9e066-122">Auf dieser Registerkarte können Sie Übersetzungen von Dimensionsmetadaten in unterschiedliche Sprachen hinzufügen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9e066-122">Use this tab to add and edit translations of dimension metadata in different languages.</span></span>|  
|<span data-ttu-id="9e066-123">**Browser**</span><span class="sxs-lookup"><span data-stu-id="9e066-123">**Browser**</span></span>|<span data-ttu-id="9e066-124">Auf dieser Registerkarte können Sie die Elemente einer verarbeiteten Dimension sowie die Übersetzungen von Dimensionsmetadaten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9e066-124">Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.</span></span>|  
  
 <span data-ttu-id="9e066-125">In den folgenden Themen werden die Aufgaben beschrieben, die Sie im Dimensions-Designer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="9e066-125">The following topics describe the tasks that you can perform in Dimension Designer.</span></span>  
  
 [<span data-ttu-id="9e066-126">Dimensionsattributeigenschaftenverweis</span><span class="sxs-lookup"><span data-stu-id="9e066-126">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
 <span data-ttu-id="9e066-127">Beschreibt das Definieren und Konfigurieren eines Dimensionsattributs.</span><span class="sxs-lookup"><span data-stu-id="9e066-127">Describes how to define and configure a dimension attribute.</span></span>  
  
 [<span data-ttu-id="9e066-128">Erstellen von benutzerdefinierten Hierarchien</span><span class="sxs-lookup"><span data-stu-id="9e066-128">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
 <span data-ttu-id="9e066-129">Beschreibt das Definieren und Konfigurieren einer benutzerdefinierten Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="9e066-129">Describes how to define and configure a user-defined hierarchy.</span></span>  
  
 [<span data-ttu-id="9e066-130">Definieren von Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="9e066-130">Define Attribute Relationships</span></span>](attribute-relationships-define.md)  
 <span data-ttu-id="9e066-131">Beschreibt das Definieren und Konfigurieren einer Attributbeziehung.</span><span class="sxs-lookup"><span data-stu-id="9e066-131">Describes how to define and configure an attribute relationship.</span></span>  
  
 [<span data-ttu-id="9e066-132">Verwenden des Business Intelligence-Assistenten zum Erweitern von Dimensionen</span><span class="sxs-lookup"><span data-stu-id="9e066-132">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
 <span data-ttu-id="9e066-133">Beschreibt das Verwenden des Business Intelligence-Assistenten zum Optimieren einer Dimension.</span><span class="sxs-lookup"><span data-stu-id="9e066-133">Describes how to use the Business Intelligence Wizard to enhance a dimension.</span></span>  
  
  
