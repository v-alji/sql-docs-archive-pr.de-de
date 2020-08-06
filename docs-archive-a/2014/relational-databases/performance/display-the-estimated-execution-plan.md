---
title: Anzeigen des geschätzten Ausführungsplans | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697988"
---
# <a name="display-the-estimated-execution-plan"></a><span data-ttu-id="23202-102">Anzeigen des geschätzten Ausführungsplans</span><span class="sxs-lookup"><span data-stu-id="23202-102">Display the Estimated Execution Plan</span></span>
  <span data-ttu-id="23202-103">In diesem Thema wird das Generieren grafischer geschätzter Ausführungspläne mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]beschreiben.</span><span class="sxs-lookup"><span data-stu-id="23202-103">This topic describes how to generate graphical estimated execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="23202-104">Beim Generieren von geschätzten Ausführungsplänen werden die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen oder -Batches nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23202-104">When estimated execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches do not execute.</span></span> <span data-ttu-id="23202-105">Stattdessen zeigt der generierte Ausführungsplan den Abfrageausführungsplan an, den [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] bei tatsächlicher Ausführung der Abfragen mit größter Wahrscheinlichkeit verwenden würde.</span><span class="sxs-lookup"><span data-stu-id="23202-105">Instead, the execution plan that is generated displays the query execution plan that [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] would most probably use if the queries were actually executed.</span></span>  
  
 <span data-ttu-id="23202-106">Zum Verwenden dieser Funktion müssen die Benutzer die entsprechenden Berechtigungen haben, um die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage auszuführen, für die ein grafischer Ausführungsplan generiert wird. Den Benutzern muss auch die SHOWPLAN-Berechtigung für alle Datenbanken erteilt werden, auf die die Abfrage verweist.</span><span class="sxs-lookup"><span data-stu-id="23202-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a><span data-ttu-id="23202-107">So zeigen Sie den geschätzten Ausführungsplan für eine Abfrage an</span><span class="sxs-lookup"><span data-stu-id="23202-107">To display the estimated execution plan for a query</span></span>  
  
1.  <span data-ttu-id="23202-108">Klicken Sie auf der Symbolleiste auf **Datenbank-Engine-Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="23202-108">On the toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="23202-109">Sie können auch eine vorhandene Abfrage öffnen und den geschätzten Ausführungsplan anzeigen, indem Sie auf die Symbolleisten-Schaltfläche **Datei öffnen** klicken und die vorhandene Abfrage suchen.</span><span class="sxs-lookup"><span data-stu-id="23202-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="23202-110">Geben Sie die Abfrage, für die Sie den geschätzten Ausführungsplan anzeigen möchten, ein.</span><span class="sxs-lookup"><span data-stu-id="23202-110">Enter the query for which you would like to display the estimated execution plan.</span></span>  
  
3.  <span data-ttu-id="23202-111">Klicken Sie im Menü **Abfrage** auf **Geschätzten Ausführungsplan anzeigen** , oder klicken Sie auf die Symbolleisten-Schaltfläche **Geschätzten Ausführungsplan anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="23202-111">On the **Query** menu, click **Display Estimated Execution Plan** or click the **Display Estimated Execution Plan** toolbar button.</span></span> <span data-ttu-id="23202-112">Der geschätzte Ausführungsplan wird im Ergebnisbereich auf der Registerkarte **Ausführungsplan** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23202-112">The estimated execution plan is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="23202-113">Um weitere Informationen anzuzeigen, lassen Sie den Mauszeiger über den logischen und physischen Operatorsymbolen ruhen. Die Beschreibung und die Eigenschaften des Operators werden nun in der QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23202-113">To view additional information, pause the mouse over the logical and physical operator icons and view the description and properties of the operator in the displayed ToolTip.</span></span> <span data-ttu-id="23202-114">Sie können die Operatoreigenschaften auch im Eigenschaftenfenster anzeigen.</span><span class="sxs-lookup"><span data-stu-id="23202-114">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="23202-115">Klicken Sie mit der rechten Maustaste auf einen Operator, und klicken Sie auf **Eigenschaften**, wenn die Eigenschaften nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="23202-115">If Properties is not visible, right-click an operator and click **Properties**.</span></span> <span data-ttu-id="23202-116">Wählen Sie einen Operator aus, um seine Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23202-116">Select an operator to view its properties.</span></span>  
  
4.  <span data-ttu-id="23202-117">Um die Anzeige des Ausführungsplans zu ändern, klicken Sie mit der rechten Maustaste auf den Ausführungsplan, und wählen Sie **Vergrößern**, **Verkleinern**, **Vergrößern/Verkleinern**oder **Zoom anpassen**aus.</span><span class="sxs-lookup"><span data-stu-id="23202-117">To alter the display of the execution plan, right-click the execution plan and select **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="23202-118">Mit**Vergrößern** und **Verkleinern** können Sie den Ausführungsplan in festgelegten Schritten vergrößern oder verkleinern.</span><span class="sxs-lookup"><span data-stu-id="23202-118">**Zoom In** and **Zoom Out** allow you to magnify or reduce the execution plan by fixed amounts.</span></span> <span data-ttu-id="23202-119">**Vergrößern/Verkleinern** ermöglicht Ihnen, die Anzeigevergrößerung nach Wunsch festzulegen, etwa auf 80 Prozent.</span><span class="sxs-lookup"><span data-stu-id="23202-119">**Custom Zoom** allows you to define your own display magnification, such as zooming at 80 percent.</span></span> <span data-ttu-id="23202-120">Mit**Zoom anpassen** können Sie den Ausführungsplan an die Größe des Ergebnisbereichs anpassen.</span><span class="sxs-lookup"><span data-stu-id="23202-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
