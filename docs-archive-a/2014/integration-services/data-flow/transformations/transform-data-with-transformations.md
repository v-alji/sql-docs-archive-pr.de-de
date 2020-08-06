---
title: Transformieren von Daten mit Transformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952d8ea4eeea2dd8010a17a2b3deba41447b6231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622231"
---
# <a name="transform-data-with-transformations"></a><span data-ttu-id="2d868-102">Transformieren von Daten mit Transformationen</span><span class="sxs-lookup"><span data-stu-id="2d868-102">Transform Data with Transformations</span></span>
  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2d868-103">schließt drei verschiedene Arten von Datenflusskomponenten ein: Quellen, Transformationen und Ziele.</span><span class="sxs-lookup"><span data-stu-id="2d868-103">includes three types of data flow components: sources, transformations, and destinations.</span></span>  
  
 <span data-ttu-id="2d868-104">Im folgenden Diagramm wird ein einfacher Datenfluss mit einer Quelle, zwei Transformationen und einem Ziel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2d868-104">The following diagram shows a simple data flow that has a source, two transformations, and a destination.</span></span>  
  
 <span data-ttu-id="2d868-105">![Datenfluss](../../media/mw-dts-08.gif "Datenfluss")</span><span class="sxs-lookup"><span data-stu-id="2d868-105">![Data flow](../../media/mw-dts-08.gif "Data flow")</span></span>  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2d868-106">-Transformationen stellen die folgende Funktionalität bereit:</span><span class="sxs-lookup"><span data-stu-id="2d868-106">transformations provide the following functionality:</span></span>  
  
-   <span data-ttu-id="2d868-107">Teilen, Kopieren und Zusammenführen von Rowsets und Ausführen von Suchvorgängen.</span><span class="sxs-lookup"><span data-stu-id="2d868-107">Splitting, copying, and merging rowsets and performing lookup operations.</span></span>  
  
-   <span data-ttu-id="2d868-108">Aktualisieren von Spaltenwerten und Erstellen neuer Spalten durch Anwenden von Transformationen, wie z. B. das Ändern von Großbuchstaben in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="2d868-108">Updating column values and creating new columns by applying transformations such as changing lowercase to uppercase.</span></span>  
  
-   <span data-ttu-id="2d868-109">Ausführen von Business Intelligence-Vorgängen, wie z. B. das Bereinigen von Daten, Text Mining oder das Ausführen von Data Mining-Vorhersageabfragen.</span><span class="sxs-lookup"><span data-stu-id="2d868-109">Performing business intelligence operations such as cleaning data, mining text, or running data mining prediction queries.</span></span>  
  
-   <span data-ttu-id="2d868-110">Erstellen neuer Rowsets, die aus Aggregatwerten oder sortierten Werten, Stichprobendaten oder pivotierten bzw. entpivotierten Daten bestehen.</span><span class="sxs-lookup"><span data-stu-id="2d868-110">Creating new rowsets that consist of aggregate or sorted values, sample data, or pivoted and unpivoted data.</span></span>  
  
-   <span data-ttu-id="2d868-111">Ausführen von Aufgaben, wie z. B. das Exportieren und Importieren von Daten, das Bereitstellen von Überwachungsinformationen sowie das Verwenden von langsam veränderlichen Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="2d868-111">Performing tasks such as exporting and importing data, providing audit information, and working with slowly changing dimensions.</span></span>  
  
 <span data-ttu-id="2d868-112">Weitere Informationen finden Sie unter [Integration Services Transformations](integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="2d868-112">For more information, see [Integration Services Transformations](integration-services-transformations.md).</span></span>  
  
 <span data-ttu-id="2d868-113">Sie können auch benutzerdefinierte Transformationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d868-113">You can also write custom transformations.</span></span> <span data-ttu-id="2d868-114">Weitere Informationen finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) und [Entwickeln bestimmter Arten von Datenflusskomponenten](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span><span class="sxs-lookup"><span data-stu-id="2d868-114">For more information, see [Developing a Custom Data Flow Component](../../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) and [Developing Specific Types of Data Flow Components](../../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md).</span></span>  
  
 <span data-ttu-id="2d868-115">Nachdem Sie dem Datenfluss-Designer die Transformation hinzugefügt haben, jedoch bevor Sie die Transformation konfigurieren, verbinden Sie die Transformation mit dem Datenfluss. Hierzu verbinden Sie die Ausgabe einer anderen Transformation oder Quelle im Datenfluss mit der Eingabe dieser Transformation.</span><span class="sxs-lookup"><span data-stu-id="2d868-115">After you add the transformation to the data flow designer, but before you configure the transformation, you connect the transformation to the data flow by connecting the output of another transformation or source in the data flow to the input of this transformation.</span></span> <span data-ttu-id="2d868-116">Der Konnektor zwischen den beiden Datenflusskomponenten wird als Pfad bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2d868-116">The connector between two data flow components is called a path.</span></span> <span data-ttu-id="2d868-117">Weitere Informationen zum Verbinden von Komponenten und zum Verwenden von Pfaden finden Sie unter [Verbinden von Komponenten mit Pfaden](../../connect-components-with-paths.md).</span><span class="sxs-lookup"><span data-stu-id="2d868-117">For more information about connecting components and working with paths, see [Connect Components with Paths](../../connect-components-with-paths.md).</span></span>  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a><span data-ttu-id="2d868-118">So fügen Sie einem Datenfluss eine Transformation hinzu</span><span class="sxs-lookup"><span data-stu-id="2d868-118">To add a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="2d868-119">Hinzufügen oder Löschen einer Komponente im Datenfluss</span><span class="sxs-lookup"><span data-stu-id="2d868-119">Add or Delete a Component in a Data Flow</span></span>](../add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a><span data-ttu-id="2d868-120">So verbinden Sie eine Transformation mit einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="2d868-120">To connect a transformation to a data flow</span></span>  
  
-   [<span data-ttu-id="2d868-121">Verbinden von Komponenten in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="2d868-121">Connect Components in a Data Flow</span></span>](../connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a><span data-ttu-id="2d868-122">So legen Sie die Eigenschaften einer Transformation fest</span><span class="sxs-lookup"><span data-stu-id="2d868-122">To set the properties of a transformation</span></span>  
  
-   [<span data-ttu-id="2d868-123">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="2d868-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d868-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d868-124">See Also</span></span>  
 <span data-ttu-id="2d868-125">[Datenflusstask](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="2d868-125">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 <span data-ttu-id="2d868-126">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="2d868-126">[Data Flow](../data-flow.md) </span></span>  
 <span data-ttu-id="2d868-127">[Verbinden von Komponenten mit Pfaden](../../connect-components-with-paths.md) </span><span class="sxs-lookup"><span data-stu-id="2d868-127">[Connect Components with Paths](../../connect-components-with-paths.md) </span></span>  
 <span data-ttu-id="2d868-128">[Fehlerbehandlung in Daten](../error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="2d868-128">[Error Handling in Data](../error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="2d868-129">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="2d868-129">Data Flow</span></span>](../data-flow.md)  
  
  
