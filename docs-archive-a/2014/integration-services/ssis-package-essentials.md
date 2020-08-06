---
title: Grundlagen zu SSIS-Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c58ddc13b5c149b84fa550f312782b02786d062
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718511"
---
# <a name="ssis-package-essentials"></a><span data-ttu-id="21b88-102">SSIS-Paketgrundlagen</span><span class="sxs-lookup"><span data-stu-id="21b88-102">SSIS Package Essentials</span></span>
  <span data-ttu-id="21b88-103">Ein Paket ist das Objekt, das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Funktionalität zum Extrahieren, Transformieren und Laden von Daten implementiert.</span><span class="sxs-lookup"><span data-stu-id="21b88-103">A package is the object that implements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] functionality to extract, transform, and load data.</span></span> <span data-ttu-id="21b88-104">Ein Paket lässt sich mit dem [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="21b88-104">You create a package by using the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="21b88-105">Sie können ein Paket aber auch mit dem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Import/Export-Assistenten oder dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Verbindungsprojekt-Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="21b88-105">You can also create a package by running the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard or the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Connections Project Wizard.</span></span> <span data-ttu-id="21b88-106">Weitere Informationen finden Sie unter [SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS-Designer und [Assistent zum Importieren von Projekten](../../2014/integration-services/import-project-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="21b88-106">For more information, [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS Designer and [Import Project Wizard](../../2014/integration-services/import-project-wizard.md).</span></span>  
  
 <span data-ttu-id="21b88-107">Ein Basispaket enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="21b88-107">A basic package includes the following elements:</span></span>  
  
 <span data-ttu-id="21b88-108">**Ablaufsteuerungselemente**</span><span class="sxs-lookup"><span data-stu-id="21b88-108">**Control flow elements**</span></span>  
 <span data-ttu-id="21b88-109">Diese erforderlichen Elemente führen verschiedene Funktionen aus, stellen Struktur bereit, und kontrollieren die Reihenfolge, in der Elemente ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="21b88-109">These required elements perform various functions, provide structure, and control the order in which elements run.</span></span> <span data-ttu-id="21b88-110">Die Hauptablaufsteuerungselemente sind Tasks, Container und Rangfolgeneinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="21b88-110">The main control flow elements are tasks, containers, and precedence constraints.</span></span> <span data-ttu-id="21b88-111">Es muss wenigstens ein Ablaufsteuerungselement in einem Paket geben.</span><span class="sxs-lookup"><span data-stu-id="21b88-111">There must be at least one control flow element in a package.</span></span>  
  
 <span data-ttu-id="21b88-112">Weitere Informationen finden Sie unter [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="21b88-112">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="21b88-113">**Datenflusselemente**</span><span class="sxs-lookup"><span data-stu-id="21b88-113">**Data flow elements**</span></span>  
 <span data-ttu-id="21b88-114">Diese optionalen Elemente extrahieren Daten, ändern Daten und laden Daten in Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="21b88-114">These optional elements extract data, modify data, and load data into data sources.</span></span> <span data-ttu-id="21b88-115">Die Hauptdatenflusselemente sind Quellen, Transformationen und Ziele.</span><span class="sxs-lookup"><span data-stu-id="21b88-115">The main data flow elements are sources, transformations, and destinations.</span></span> <span data-ttu-id="21b88-116">In einem Paket müssen keine Datenflusselemente enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="21b88-116">There does not have to be any data flow elements in package.</span></span>  
  
 <span data-ttu-id="21b88-117">Weitere Informationen finden Sie unter [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="21b88-117">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="21b88-118">Ein Beispiel für das Erstellen eines einfachen Pakets finden Sie unter [Lektion 1: Erstellen des Projekts und Basispakets](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="21b88-118">For an example of how to create a basic package, see [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="21b88-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="21b88-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="21b88-120">Erstellen von Paketen in SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="21b88-120">Create Packages in SQL Server Data Tools</span></span>](create-packages-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="21b88-121">Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="21b88-121">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [<span data-ttu-id="21b88-122">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="21b88-122">Set the Properties of a Task or Container</span></span>](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [<span data-ttu-id="21b88-123">Hinzufügen oder Löschen einer Komponente im Datenfluss</span><span class="sxs-lookup"><span data-stu-id="21b88-123">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a><span data-ttu-id="21b88-124">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="21b88-124">Related Content</span></span>  
  
1.  <span data-ttu-id="21b88-125">Video [Erstellen eines Basispakets (SQL Server-Video)](https://go.microsoft.com/fwlink/?LinkId=131023)auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="21b88-125">Video, [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023), on MSDN.Microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b88-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21b88-126">See Also</span></span>  
 <span data-ttu-id="21b88-127">[Integration Services &#40;SSIS-&#41; Paketen](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="21b88-127">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="21b88-128">Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="21b88-128">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  
