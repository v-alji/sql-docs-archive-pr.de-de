---
title: Sequenzcontainer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sequencecontainer.f1
helpviewer_keywords:
- Sequence container
- grouping control flows
- containers [Integration Services], Sequence
- subset control flow [Integration Services]
ms.assetid: 7731f91e-b8b3-4d96-a0d9-73f568547cb3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b972f923e2134363ba1b378beebebbeb1e5d6bb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619251"
---
# <a name="sequence-container"></a><span data-ttu-id="7cf1a-102">Sequenzcontainer</span><span class="sxs-lookup"><span data-stu-id="7cf1a-102">Sequence Container</span></span>
  <span data-ttu-id="7cf1a-103">Der Sequenzcontainer definiert eine Ablaufsteuerung, die eine Teilmenge der Paketablaufsteuerung ist.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-103">The Sequence container defines a control flow that is a subset of the package control flow.</span></span> <span data-ttu-id="7cf1a-104">Sequenzcontainer gruppieren das Paket zu mehreren separaten Ablaufsteuerungen, die jeweils Tasks und Container enthalten, die innerhalb der allgemeinen Paketablaufsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-104">Sequence containers group the package into multiple separate control flows, each containing one or more tasks and containers that run within the overall package control flow.</span></span>  
  
 <span data-ttu-id="7cf1a-105">Der Sequenzcontainer kann neben anderen Containern Tasks einschließen.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-105">The Sequence container can include multiple tasks in addition to other containers.</span></span> <span data-ttu-id="7cf1a-106">Das Hinzufügen von Tasks und Containern zu einem Sequenzcontainer ist mit dem Hinzufügen von Tasks und Containern zu einem Paket vergleichbar, außer dass Sie die Tasks und Container nicht in den Paketcontainer, sondern in den Sequenzcontainer ziehen.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-106">Adding tasks and containers to a Sequence container is similar to adding them to a package, except you drag the tasks and containers to the Sequence container instead of to the package container.</span></span> <span data-ttu-id="7cf1a-107">Falls der Sequenzcontainer mehrere Tasks oder Container einschließt, können Sie diese wie bei einem Paket mithilfe von Rangfolgeneinschränkungen verbinden.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-107">If the Sequence container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="7cf1a-108">Weitere Informationen finden Sie unter [Rangfolgeneinschränkungen](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1a-108">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="7cf1a-109">Die Verwendung eines Sequenzcontainers bietet viele Vorteile:</span><span class="sxs-lookup"><span data-stu-id="7cf1a-109">There are many benefits of using a Sequence container:</span></span>  
  
-   <span data-ttu-id="7cf1a-110">Deaktivieren von Taskgruppen, um das Debuggen des Pakets auf eine Teilmenge der Paketablaufsteuerung zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-110">Disabling groups of tasks to focus package debugging on one subset of the package control flow.</span></span>  
  
-   <span data-ttu-id="7cf1a-111">Zentrales Verwalten von Eigenschaften in mehreren Tasks, indem Eigenschaften für einen Sequenzcontainer und nicht für die einzelnen Tasks festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-111">Managing properties on multiple tasks in one location by setting properties on a Sequence container instead of on the individual tasks.</span></span>  
  
     <span data-ttu-id="7cf1a-112">Beispielsweise können Sie die `Disable`-Eigenschaft des Sequenzcontainers auf `True` festlegen, um alle Tasks und Container im Sequenzcontainer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-112">For example, you can set the `Disable` property of the Sequence container to `True` to disable all the tasks and containers in the Sequence container.</span></span>  
  
-   <span data-ttu-id="7cf1a-113">Bereitstellen des Bereichs für Variablen, die eine Gruppe verwandter Tasks und Container verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-113">Providing scope for variables that a group of related tasks and containers use.</span></span>  
  
-   <span data-ttu-id="7cf1a-114">Gruppieren vieler Tasks, damit Sie sie durch Erweitern oder Reduzieren des Sequenzcontainers leichter verwalten können.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-114">Grouping many tasks so you can more easily managed them by collapsing and expanding the Sequence container.</span></span>  
  
     <span data-ttu-id="7cf1a-115">Darüber hinaus können Sie Taskgruppen erstellen, die mithilfe des Felds **Gruppe** erweitert und reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-115">You can also create task groups, which expand and collapse using the **Group** box.</span></span> <span data-ttu-id="7cf1a-116">Das Feld **Gruppe** ist jedoch eine Entwurfszeitfunktion ohne Eigenschaften und ohne Laufzeitverhalten.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-116">However, the **Group** box is a design-time feature that has no properties or run-time behavior.</span></span> <span data-ttu-id="7cf1a-117">Weitere Informationen finden Sie unter [Gruppieren von Komponenten oder Aufheben der Gruppierung](../group-or-ungroup-components.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1a-117">For more information, see [Group or Ungroup Components](../group-or-ungroup-components.md)</span></span>  
  
-   <span data-ttu-id="7cf1a-118">Legen Sie ein Transaktionsattribut für den Sequenzcontainer fest, um eine Transaktion für eine Teilmenge der Paketablaufsteuerung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-118">Set a transaction attribute on the Sequence container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="7cf1a-119">Auf diese Weise können Sie Transaktionen mit feinerer Granularität verwalten.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-119">In this way, you can manage transactions at a more granular level.</span></span>  
  
     <span data-ttu-id="7cf1a-120">Wenn z. B. ein Sequenzcontainer zwei verwandte Tasks enthält (einen Task, der Daten in einer Tabelle löscht, und einen anderen Task, der Daten in eine Tabelle einfügt), können Sie eine Transaktion konfigurieren, um sicherzustellen, dass für den Löschvorgang ein Rollback ausgeführt wird, falls beim Einfügen ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-120">For example, if a Sequence container includes two related tasks, one task that deletes data in a table and another task that inserts data into a table, you can configure a transaction to ensure that the delete action is rolled back if the insert action fails.</span></span> <span data-ttu-id="7cf1a-121">Weitere Informationen finden Sie unter [Integration Services-Transaktionen](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1a-121">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-sequence-container"></a><span data-ttu-id="7cf1a-122">Konfiguration des Sequenzcontainers</span><span class="sxs-lookup"><span data-stu-id="7cf1a-122">Configuration of the Sequence Container</span></span>  
 <span data-ttu-id="7cf1a-123">Der Sequenzcontainer weist keine benutzerdefinierte Benutzeroberfläche auf und kann nur im Fenster **Eigenschaften** von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] oder programmgesteuert konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-123">The Sequence container has no custom user interface and you can configure it only in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="7cf1a-124">Informationen zum programmgesteuerten Festlegen dieser Eigenschaften finden Sie in der Dokumentation zur **T:Microsoft.SqlServer.Dts.Runtime.Sequence** -Klasse im Entwicklerhandbuch.</span><span class="sxs-lookup"><span data-stu-id="7cf1a-124">For information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.Sequence** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7cf1a-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7cf1a-125">Related Tasks</span></span>  
 <span data-ttu-id="7cf1a-126">Weitere Informationen zum Festlegen der Eigenschaften der Komponente in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]finden Sie unter [Festlegen der Eigenschaften eines Tasks oder Containers](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="7cf1a-126">For information about how to set properties of the component in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf1a-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cf1a-127">See Also</span></span>  
 <span data-ttu-id="7cf1a-128">[Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="7cf1a-128">[Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="7cf1a-129">[Verbinden von Tasks und Containern mithilfe einer Standardrangfolgen-Einschränkung](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="7cf1a-129">[Connect Tasks and Containers by Using a Default Precedence Constraint](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="7cf1a-130">SQL Server Integration Services-Container</span><span class="sxs-lookup"><span data-stu-id="7cf1a-130">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
