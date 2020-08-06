---
title: Wiederverwenden von Paketobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- GUID regenerating [Integration Services]
- reusing packages
- templates [Integration Services]
- copying packages
- regenerating package GUID
ms.assetid: 08f723bf-15b5-44bd-9a46-04e8781bfbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b7612cb2684bb842108068b062e54fbe9dee4327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696946"
---
# <a name="reuse-of-package-objects"></a><span data-ttu-id="5075d-102">Wiederverwenden von Paketobjekten</span><span class="sxs-lookup"><span data-stu-id="5075d-102">Reuse of Package Objects</span></span>
  <span data-ttu-id="5075d-103">Pakete schließen häufig Funktionalität ein, die Sie wiederverwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5075d-103">Frequently packages functionality that you want to reuse.</span></span> <span data-ttu-id="5075d-104">Wenn Sie beispielsweise eine Reihe von Tasks erstellt haben, möchten Sie möglicherweise die Elemente zusammen als eine Gruppe wiederverwenden, oder Sie möchten ein einzelnes Element, z. B. einen Verbindungs-Manager, den Sie in einem anderen [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt erstellt haben, wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="5075d-104">For example, if you created a set of tasks, you might want to reuse the items together as a group, or you might want to reuse a single item such as a connection manager that you created in a different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
## <a name="copy-and-paste"></a><span data-ttu-id="5075d-105">Kopieren und Einfügen</span><span class="sxs-lookup"><span data-stu-id="5075d-105">Copy and Paste</span></span>  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="5075d-106">und der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer unterstützen das Kopieren und Einfügen von Paketobjekten. Hierzu zählen Ablaufsteuerungselemente, Datenflusselemente und Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="5075d-106">and [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer support copying and pasting package objects, which can include control flow items, data flow items, and connection managers.</span></span> <span data-ttu-id="5075d-107">Elemente können aus einem Projekt bzw. aus einem Paket kopiert und in ein anderes Projekt bzw. Paket eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5075d-107">You can copy and paste between projects and between packages.</span></span> <span data-ttu-id="5075d-108">Wenn die Lösung mehrere Projekte enthält, können Sie von einem Projekt in ein anderes kopieren. Dabei können die einzelnen Projekte unterschiedlichen Typs sein.</span><span class="sxs-lookup"><span data-stu-id="5075d-108">If the solution contains multiple projects you can copy between projects, and the projects can be of different types.</span></span>  
  
 <span data-ttu-id="5075d-109">Wenn eine Lösung mehrere Pakete enthält, können Sie diverse Kopier- und Einfügevorgänge zwischen diesen durchführen.</span><span class="sxs-lookup"><span data-stu-id="5075d-109">If a solution contains multiple packages, you can copy and paste between them.</span></span> <span data-ttu-id="5075d-110">Dabei können sich die Pakete im selben oder in einem anderen [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt befinden.</span><span class="sxs-lookup"><span data-stu-id="5075d-110">The packages can be in the same or different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="5075d-111">Paketobjekte können jedoch von anderen Objekten abhängig sein, durch die sie erst gültig sind.</span><span class="sxs-lookup"><span data-stu-id="5075d-111">However, package objects may have dependencies on other objects, without which they are not valid.</span></span> <span data-ttu-id="5075d-112">Beispielsweise verwendet der Task SQL ausführen einen Verbindungs-Manager, den Sie ebenfalls kopieren müssen, um den Task ordnungsgemäß ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="5075d-112">For example, an Execute SQL task uses a connection manager, which you must copy as well to make the task work.</span></span> <span data-ttu-id="5075d-113">Des Weiteren erfordern einige Paketobjekte das Vorhandensein eines bestimmten Objekts im Paket. Ohne dieses Objekt können die kopierten Objekte nicht erfolgreich in das Paket eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5075d-113">Also, some package objects require that the package already contain a certain object, and without this object you cannot successfully paste the copied objects into a package.</span></span> <span data-ttu-id="5075d-114">Sie können beispielsweise einen Datenfluss in ein Paket nur dann einfügen, wenn mindestens ein Datenflusstask im Paket vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5075d-114">For example, you cannot paste a data flow into a package that does not have at least one Data Flow task.</span></span>  
  
 <span data-ttu-id="5075d-115">Möglicherweise müssen Sie ein und dieselben Pakete mehrere Male kopieren.</span><span class="sxs-lookup"><span data-stu-id="5075d-115">You may find that you copy the same packages repeatedly.</span></span> <span data-ttu-id="5075d-116">Sie können diesen Kopiervorgang umgehen, indem Sie diese Pakete als Vorlagen festlegen und beim Erstellen neuer Pakete verwenden.</span><span class="sxs-lookup"><span data-stu-id="5075d-116">To avoid the copy process, you can designate these packages as templates and use them when you create new packages.</span></span>  
  
 <span data-ttu-id="5075d-117">Beim Kopieren eines Paketobjekts weist [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] der `ID`-Eigenschaft des neuen Objekts automatisch einen neuen GUID zu und aktualisiert die `Name`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5075d-117">When you copy a package object, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automatically assigns a new GUID to the `ID` property of the new object and updates the `Name` property.</span></span>  
  
 <span data-ttu-id="5075d-118">Das Kopieren von Variablen ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="5075d-118">You cannot copy variables.</span></span> <span data-ttu-id="5075d-119">Wenn ein Objekt, z. B. ein Task, Variablen verwendet, müssen die Variablen im Zielpaket neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5075d-119">If an object such as a task uses variables, then you must re-create the variables in the destination package.</span></span> <span data-ttu-id="5075d-120">Wenn Sie allerdings das gesamte Paket kopieren, werden die Variablen des Pakets ebenfalls kopiert.</span><span class="sxs-lookup"><span data-stu-id="5075d-120">In contrast, if you copy the entire package, then the variables in the package are also copied.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5075d-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5075d-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5075d-122">Kopieren von Paketobjekten</span><span class="sxs-lookup"><span data-stu-id="5075d-122">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
-   [<span data-ttu-id="5075d-123">Kopieren von Projektelementen</span><span class="sxs-lookup"><span data-stu-id="5075d-123">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
-   [<span data-ttu-id="5075d-124">Speichern eines Pakets als Paketvorlage</span><span class="sxs-lookup"><span data-stu-id="5075d-124">Save a Package as a Package Template</span></span>](../../2014/integration-services/save-a-package-as-a-package-template.md)  
  
  
