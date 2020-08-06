---
title: Erweiterter Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.advancededitor.columnmappings.f1
- sql12.dts.designer.advancededitor.inputcolumns.f1
- sql12.dts.designer.advancededitor.columnproperties.f1
- sql12.dts.designer.advancededitor.componentproperties.f1
- sql12.dts.designer.advancededitor.connections.f1
ms.assetid: 5ad0ac71-fa8b-4c26-bd42-e6ef00c87571
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4897f2589acdeb93efecbdf9aacde07d21ca42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615533"
---
# <a name="advanced-editor"></a><span data-ttu-id="a7921-102">Erweiterter Editor</span><span class="sxs-lookup"><span data-stu-id="a7921-102">Advanced Editor</span></span>
  <span data-ttu-id="a7921-103">Verwenden Sie das Dialogfeld **Erweiterter Editor** , um Eigenschaften für das ausgewählte [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Objekt zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a7921-103">Use the **Advanced Editor** dialog box to configure to configure properties for the selected [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="a7921-104">**Erweiterter Editor** ist für die meisten [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Objekte verfügbar, die konfigurierbare Eigenschaften aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a7921-104">The **Advanced Editor** is available for most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects that have configurable properties.</span></span> <span data-ttu-id="a7921-105">Es ist der einzige verfügbare Editor für jene Objekte, die keine benutzerdefinierte Benutzeroberfläche bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a7921-105">It is the only editor available for those objects that do not expose a custom user interface.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="a7921-106">-Datenflussobjekte haben Eigenschaften, die auf der Komponentenebene, der Eingabe- und Ausgabeebene und der Ebene der Eingabe- und Ausgabespalten festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="a7921-106">data flow objects have properties that can be set at the component level, the input and output level, and the input and output column level.</span></span> <span data-ttu-id="a7921-107">**Erweiterter Editor** zählt alle allgemeinen und benutzerdefinierten Eigenschaften des ausgewählten Objekts auf und zeigt sie auf jeweils bis zu vier von fünf der folgenden Registerkarten an:</span><span class="sxs-lookup"><span data-stu-id="a7921-107">The **Advanced Editor** enumerates all the common and custom properties of the selected object and displays them on up to four of the following five tabs as applicable:</span></span>  
  
-   <span data-ttu-id="a7921-108">**Verbindungs-Manager** – verwenden Sie diese Registerkarte, um Verbindungseigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a7921-108">**Connection Managers** -- use this tab to set connection properties</span></span>  
  
-   <span data-ttu-id="a7921-109">**Komponenteneigenschaften** – verwenden Sie diese Registerkarte, um Eigenschaften auf Komponentenebene festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a7921-109">**Component Properties** -- use this tab to set component-level properties</span></span>  
  
-   <span data-ttu-id="a7921-110">**Spaltenzuordnungen** – verwenden Sie diese Registerkarte, um verfügbare Spalten als Ausgabespalten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7921-110">**Column Mappings** -- use this tab to map available columns as output columns</span></span>  
  
-   <span data-ttu-id="a7921-111">**Eingabespalten** – verwenden Sie diese Registerkarte, um Eingabespalten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a7921-111">**Input Columns** -- use this tab to select input columns</span></span>  
  
-   <span data-ttu-id="a7921-112">**Eingabe- und Ausgabeeigenschaften** – verwenden Sie diese Registerkarte, um Eingabe- und Ausgabeeigenschaften festzulegen. Sie können mithilfe dieser Registerkarte auch Ausgaben hinzufügen und entfernen, Spalten für Ein- und Ausgaben auswählen oder entfernen und Eigenschaften für Ein- und Ausgaben festlegen.</span><span class="sxs-lookup"><span data-stu-id="a7921-112">**Input and Output Properties** -- use this tab to set input and output properties; and to add and remove outputs, select or remove columns for inputs and outputs, and set properties for inputs and outputs</span></span>  
  
 <span data-ttu-id="a7921-113">Die angezeigten Eigenschaften variieren je nach Komponente.</span><span class="sxs-lookup"><span data-stu-id="a7921-113">The properties displayed vary by component.</span></span> <span data-ttu-id="a7921-114">Weitere Informationen zu den Eigenschaften, die in **Erweiterter Editor**angezeigt werden können, finden Sie unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a7921-114">For more information on the properties that may be displayed in the **Advanced Editor**, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a7921-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="a7921-115">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
-   [<span data-ttu-id="a7921-116">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="a7921-116">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
-   [<span data-ttu-id="a7921-117">Pfadeigenschaften</span><span class="sxs-lookup"><span data-stu-id="a7921-117">Path Properties</span></span>](../../2014/integration-services/path-properties.md)  
  
 <span data-ttu-id="a7921-118">Weitere Informationen zu den speziellen Komponenten, die Sie bearbeiten, finden Sie in der Beschreibung der Komponenten im Abschnitt zu den Datenflusselementen in der Objekt- und Konzeptdokumentation von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a7921-118">For more information about the specific component that you are editing, see the description of the component in the Data Flow Elements section of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts documentation:</span></span>  
  
-   [<span data-ttu-id="a7921-119">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="a7921-119">Integration Services Transformations</span></span>](data-flow/transformations/integration-services-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7921-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7921-120">See Also</span></span>  
 [<span data-ttu-id="a7921-121">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="a7921-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
