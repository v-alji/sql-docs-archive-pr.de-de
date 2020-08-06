---
title: Anzeigen eines tatsächlichen Ausführungsplans | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- displaying execution plans
- actual execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
ms.assetid: 9e583a18-5f4a-4054-bfe1-4b2a76630db6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f384e2d2752b7601fbb46b8ee7f7b56a2615651c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698006"
---
# <a name="display-an-actual-execution-plan"></a><span data-ttu-id="67155-102">Anzeigen eines tatsächlichen Ausführungsplans</span><span class="sxs-lookup"><span data-stu-id="67155-102">Display an Actual Execution Plan</span></span>
  <span data-ttu-id="67155-103">In diesem Thema wird das Generieren tatsächlicher grafischer Ausführungspläne mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67155-103">This topic describes how to generate actual graphical execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="67155-104">Beim Generieren tatsächlicher Ausführungspläne werden die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen oder -Batches ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67155-104">When actual execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches execute.</span></span> <span data-ttu-id="67155-105">Der generierte Ausführungsplan zeigt den tatsächlichen Abfrageausführungsplan an, der von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] zur Ausführung der Abfragen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67155-105">The execution plan that is generated displays the actual query execution plan that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses to execute the queries.</span></span>  
  
 <span data-ttu-id="67155-106">Benutzer müssen zum Verwenden dieser Funktion die entsprechenden Berechtigungen zum Ausführen der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen besitzen, für die ein grafischer Ausführungsplan generiert wird. Darüber hinaus muss ihnen die SHOWPLAN-Berechtigung für alle Datenbanken erteilt werden, auf die die Abfrage verweist.</span><span class="sxs-lookup"><span data-stu-id="67155-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-include-an-execution-plan-for-a-query-during-execution"></a><span data-ttu-id="67155-107">So schließen Sie einen Ausführungsplan für eine Abfrage bei der Ausführung ein</span><span class="sxs-lookup"><span data-stu-id="67155-107">To include an execution plan for a query during execution</span></span>  
  
1.  <span data-ttu-id="67155-108">Klicken Sie auf der Symbolleiste von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf **Datenbank-Engine-Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="67155-108">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="67155-109">Sie können auch eine vorhandene Abfrage öffnen und den geschätzten Ausführungsplan anzeigen, indem Sie auf die Symbolleisten-Schaltfläche **Datei öffnen** klicken und die vorhandene Abfrage suchen.</span><span class="sxs-lookup"><span data-stu-id="67155-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="67155-110">Geben Sie die Abfrage ein, für die Sie den tatsächlichen Ausführungsplan anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="67155-110">Enter the query for which you would like to display the actual execution plan.</span></span>  
  
3.  <span data-ttu-id="67155-111">Klicken Sie im Menü **Abfrage** auf **tatsächlichen Ausführungsplan einschließen** , oder klicken Sie auf die Symbolleisten Schaltfläche **tatsächlichen Ausführungsplan einschließen** .</span><span class="sxs-lookup"><span data-stu-id="67155-111">On the **Query** menu, click **Include Actual Execution Plan** or click the **Include Actual Execution Plan** toolbar button</span></span>  
  
4.  <span data-ttu-id="67155-112">Führen Sie die Abfrage aus, indem Sie auf die Symbolleistenschaltfläche **Ausführen** klicken.</span><span class="sxs-lookup"><span data-stu-id="67155-112">Execute the query by clicking the **Execute** toolbar button.</span></span> <span data-ttu-id="67155-113">Der vom Abfrageoptimierer verwendete Plan wird im Ergebnisbereich auf der Registerkarte **Ausführungsplan** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67155-113">The plan used by the query optimizer is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="67155-114">Positionieren Sie die Maus über die logischen und physischen Operatoren, um deren Beschreibung und Eigenschaften in der QuickInfo anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="67155-114">Pause the mouse over the logical and physical operators to view the description and properties of the operators in the displayed ToolTip.</span></span>  
  
     <span data-ttu-id="67155-115">Sie können die Operatoreigenschaften auch im Eigenschaftenfenster anzeigen.</span><span class="sxs-lookup"><span data-stu-id="67155-115">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="67155-116">Falls die Eigenschaften nicht sichtbar sind, klicken Sie mit der rechten Maustaste auf einen Operator, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="67155-116">If Properties is not visible, right-click an operator and select **Properties**.</span></span> <span data-ttu-id="67155-117">Wählen Sie einen Operator aus, um seine Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="67155-117">Select an operator to view its properties.</span></span>  
  
5.  <span data-ttu-id="67155-118">Sie können die Anzeige des Ausführungsplans ändern, indem Sie mit der rechten Maustaste auf den Ausführungsplan klicken und **Vergrößern**, **Verkleinern**, **Vergrößern/Verkleinern**oder **Zoom anpassen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="67155-118">You can alter the display of the execution plan by right-clicking the execution plan and selecting **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="67155-119">Mit**Vergrößern** und **Verkleinern** können Sie den Ausführungsplan vergrößern bzw. verkleinern. Mit **Vergrößern/Verkleinern** können Sie dagegen einen eigenen Zoomfaktor definieren, z. B. 80 Prozent.</span><span class="sxs-lookup"><span data-stu-id="67155-119">**Zoom In** and **Zoom Out** allow you to zoom in or out on the execution plan, while **Custom Zoom** allows you to define your own zoom, such as zooming at 80 percent.</span></span> <span data-ttu-id="67155-120">Mit**Zoom anpassen** können Sie den Ausführungsplan an die Größe des Ergebnisbereichs anpassen.</span><span class="sxs-lookup"><span data-stu-id="67155-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
