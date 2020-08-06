---
title: Operator benachrichtigen (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.notifyoperatortask.f1
helpviewer_keywords:
- Notify Operator task
- notifications [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 6c816c68-c6d6-44e4-bb34-c8e060a958a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed5158a4ec5cfe8374fedbb2afbca1294b58f05e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724846"
---
# <a name="notify-operator-task"></a><span data-ttu-id="1dd94-102">Operator benachrichtigen (Task)</span><span class="sxs-lookup"><span data-stu-id="1dd94-102">Notify Operator Task</span></span>
  <span data-ttu-id="1dd94-103">Der Task Operator benachrichtigen sendet Benachrichtigungsmeldungen an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agentoperatoren.</span><span class="sxs-lookup"><span data-stu-id="1dd94-103">The Notify Operator task sends notification messages to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operators.</span></span> <span data-ttu-id="1dd94-104">Bei einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agentoperator handelt es sich um einen Alias für eine Person oder Gruppe, die elektronische Benachrichtigungen empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="1dd94-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator is an alias for a person or group that can receive electronic notifications.</span></span> <span data-ttu-id="1dd94-105">Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Operatoren finden Sie unter [Operatoren](../../ssms/agent//operators.md).</span><span class="sxs-lookup"><span data-stu-id="1dd94-105">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operators, see [Operators](../../ssms/agent//operators.md).</span></span>  
  
 <span data-ttu-id="1dd94-106">Mit dem Task „Operator benachrichtigen“ kann ein Paket mindestens einen Operator per E-Mail, Pager oder **net send**benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="1dd94-106">By using the Notify Operator task, a package can notify one or more operators via e-mail, pager, or **net send**.</span></span> <span data-ttu-id="1dd94-107">Jeder Operator kann mit verschiedenen Methoden benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="1dd94-107">Each operator can be notified by different methods.</span></span> <span data-ttu-id="1dd94-108">Beispielsweise wird OperatorA per E-Mail und Pager benachrichtigt, OperatorB dagegen per Pager und **net send**.</span><span class="sxs-lookup"><span data-stu-id="1dd94-108">For example, OperatorA is notified by e-mail and pager, and OperatorB is notified by pager and **net send**.</span></span> <span data-ttu-id="1dd94-109">Die Operatoren, die Benachrichtigungen vom Task erhalten, müssen Mitglieder der **OperatorNotify** -Auflistung im Task Operator benachrichtigen sein.</span><span class="sxs-lookup"><span data-stu-id="1dd94-109">The operators who receive notifications from the task must be members of the **OperatorNotify** collection on the Notify Operator task.</span></span>  
  
 <span data-ttu-id="1dd94-110">Der Task "Operator benachrichtigen" ist der einzige Datenbankwartungstask, der keine Transact-SQL-Anweisung und keinen DBCC-Befehl kapselt.</span><span class="sxs-lookup"><span data-stu-id="1dd94-110">The Notify Operator task is the only database maintenance task that does not encapsulate a Transact-SQL statement or a DBCC command.</span></span>  
  
## <a name="configuration-of-the-notify-operator-task"></a><span data-ttu-id="1dd94-111">Konfiguration des Tasks "Operator benachrichtigen"</span><span class="sxs-lookup"><span data-stu-id="1dd94-111">Configuration of the Notify Operator Task</span></span>  
 <span data-ttu-id="1dd94-112">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="1dd94-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="1dd94-113">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="1dd94-113">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="1dd94-114">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="1dd94-114">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="1dd94-115">Task „Operator benachrichtigen“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="1dd94-115">Notify Operator Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/notify-operator-task-maintenance-plan.md)  
  
 <span data-ttu-id="1dd94-116">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="1dd94-116">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="1dd94-117">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="1dd94-117">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
