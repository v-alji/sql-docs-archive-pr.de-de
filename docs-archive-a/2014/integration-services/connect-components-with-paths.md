---
title: Verbinden von Komponenten mit Pfaden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], connections
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 05633e4c-1370-4b05-802b-f36b07dd71c8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e11955601406406abe48b53197e95c8224762fee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722977"
---
# <a name="connect-components-with-paths"></a><span data-ttu-id="474a6-102">Verbinden von Komponenten mit Pfaden</span><span class="sxs-lookup"><span data-stu-id="474a6-102">Connect Components with Paths</span></span>
  <span data-ttu-id="474a6-103">Den Datenfluss in einem Paket erstellen Sie auf der Entwurfsoberfläche der Registerkarte **Datenfluss** im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer.</span><span class="sxs-lookup"><span data-stu-id="474a6-103">You construct the data flow in a package on the design surface of the **Data Flow** tab in the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="474a6-104">Falls ein Datenfluss zwei Datenflusskomponenten enthält, können Sie diese verbinden, indem Sie die Ausgabe einer Quelle oder Transformation mit der Eingabe einer Transformation oder eines Zieles verbinden.</span><span class="sxs-lookup"><span data-stu-id="474a6-104">If a data flow contains two data flow components, you can connect them by connecting the output of a source or transformation to the input of a transformation or destination.</span></span> <span data-ttu-id="474a6-105">Der Konnektor zwischen den beiden Datenflusskomponenten wird als Pfad bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="474a6-105">The connector between two data flow components is called a path.</span></span>

 <span data-ttu-id="474a6-106">Im folgenden Diagramm wird ein einfacher Datenfluss mit einer Quellkomponente, zwei Transformationen, einer Zielkomponente und den Pfaden, die diese verbinden, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="474a6-106">The following diagram shows a simple data flow with a source component, two transformations, a destination component, and the paths that connect them.</span></span>

 <span data-ttu-id="474a6-107">![Datenfluss](media/mw-dts-08.gif "Datenfluss")</span><span class="sxs-lookup"><span data-stu-id="474a6-107">![Data flow](media/mw-dts-08.gif "Data flow")</span></span>

 <span data-ttu-id="474a6-108">Wenn zwei Komponenten verbunden sind, können Sie die Metadaten der Daten, die über den Pfad verschoben werden, und die Eigenschaften des Pfades in **Datenflusspfad-Editor**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="474a6-108">After two components are connected, you can view the metadata of the data that moves through the path and the properties of the path in **Data Flow Path Editor**.</span></span> <span data-ttu-id="474a6-109">Weitere Informationen finden Sie unter [Integration Services Paths](data-flow/integration-services-paths.md).</span><span class="sxs-lookup"><span data-stu-id="474a6-109">For more information, see [Integration Services Paths](data-flow/integration-services-paths.md).</span></span>

 <span data-ttu-id="474a6-110">Sie können Pfaden auch Daten-Viewer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="474a6-110">You can also add data viewers to paths.</span></span> <span data-ttu-id="474a6-111">Mit einem Daten-Viewer können Sie Daten anzeigen, die zwischen Datenflusskomponenten verschoben werden, wenn das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="474a6-111">A data viewer makes it possible to view data moving between data flow components when the package is run.</span></span>

### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="474a6-112">So verbinden Sie Komponenten in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="474a6-112">To connect components in a data flow</span></span>

-   [<span data-ttu-id="474a6-113">Verbinden von Komponenten in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="474a6-113">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)

### <a name="to-set-path-properties"></a><span data-ttu-id="474a6-114">So legen Sie Pfadeigenschaften fest</span><span class="sxs-lookup"><span data-stu-id="474a6-114">To set path properties</span></span>

-   [<span data-ttu-id="474a6-115">Festlegen der Eigenschaften eines Pfads mithilfe des Datenflusspfad-Editors</span><span class="sxs-lookup"><span data-stu-id="474a6-115">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>](../../2014/integration-services/set-the-properties-of-a-path-by-using-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="474a6-116">So zeigen Sie Pfadmetadaten an</span><span class="sxs-lookup"><span data-stu-id="474a6-116">To view path metadata</span></span>

-   [<span data-ttu-id="474a6-117">Anzeigen von Pfadmetadaten im Datenflusspfad-Editor</span><span class="sxs-lookup"><span data-stu-id="474a6-117">View Path Metadata in the Data Flow Path Editor</span></span>](../../2014/integration-services/view-path-metadata-in-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="474a6-118">So zeigen Sie Pfadmetadaten an</span><span class="sxs-lookup"><span data-stu-id="474a6-118">To view path metadata</span></span>

-   [<span data-ttu-id="474a6-119">Hinzufügen eines Daten-Viewers zu einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="474a6-119">Add a Data Viewer to a Data Flow</span></span>](../../2014/integration-services/add-a-data-viewer-to-a-data-flow.md)

## <a name="see-also"></a><span data-ttu-id="474a6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="474a6-120">See Also</span></span>
 <span data-ttu-id="474a6-121">Datenfluss [Task](control-flow/data-flow-task.md) [-Datenfluss](data-flow/data-flow.md) [Transformieren von Daten mit Transformationen](data-flow/transformations/transform-data-with-transformations.md) [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="474a6-121">[Data Flow Task](control-flow/data-flow-task.md) [Data Flow](data-flow/data-flow.md) [Transform Data with Transformations](data-flow/transformations/transform-data-with-transformations.md) [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>


