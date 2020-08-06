---
title: Verwenden des Eigenschaftenfensters in Management Studio
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- Properties window [SQL Server Management Studio]
- complex properties [SQL Server Management Studio]
ms.assetid: 903d4aca-f57c-43d9-a893-702eceaa7004
author: rothja
ms.author: jroth
ms.openlocfilehash: 5030bf85fc87482b11e91967ff8fb1baf77a213e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621998"
---
# <a name="use-the-properties-window-in-management-studio"></a><span data-ttu-id="fc751-102">Verwenden des Eigenschaftenfensters in Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc751-102">Use the Properties Window in Management Studio</span></span>
  <span data-ttu-id="fc751-103">Das Eigenschaftenfenster enthält eine Beschreibung des Zustands eines Elements in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], z. B. Verbindungen oder Showplanoperatoren, sowie Informationen zu Datenbankobjekten wie Tabellen, Sichten und Designer.</span><span class="sxs-lookup"><span data-stu-id="fc751-103">The Properties window describes the state of an item in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator, and information about database objects such as tables, views, and designers.</span></span>  
  
 <span data-ttu-id="fc751-104">Im Eigenschaftenfenster können Sie die Eigenschaften der aktuellen Verbindung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fc751-104">You can use the Properties window to view the properties of the current connection.</span></span> <span data-ttu-id="fc751-105">Viele Eigenschaften im Eigenschaftenfenster sind schreibgeschützt, können aber an anderer Stelle in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fc751-105">Many properties are read-only in the Properties window but can be changed elsewhere in the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="fc751-106">So ist beispielsweise die Database-Eigenschaft einer Abfrage im Eigenschaftenfenster schreibgeschützt, kann aber auf der Symbolleiste geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fc751-106">For example, the Database property of a query is read-only in the Properties window, but can be changed on the tool bar.</span></span>  
  
### <a name="to-view-properties-using-the-properties-window"></a><span data-ttu-id="fc751-107">So zeigen Sie Eigenschaften mithilfe des Eigenschaftenfensters an</span><span class="sxs-lookup"><span data-stu-id="fc751-107">To view properties using the Properties window</span></span>  
  
1.  <span data-ttu-id="fc751-108">Wird das Eigenschaftenfenster nicht angezeigt, klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster** , oder drücken Sie F4.</span><span class="sxs-lookup"><span data-stu-id="fc751-108">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="fc751-109">Legen Sie den Fokus auf das anzuzeigende Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="fc751-109">Set the focus on the object that you want to view.</span></span>  
  
3.  <span data-ttu-id="fc751-110">Suchen Sie im Eigenschaftenfenster nach einer bestimmten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fc751-110">Look for a specific property in the Properties window.</span></span>  
  
### <a name="to-view-connection-properties-of-a-query-window"></a><span data-ttu-id="fc751-111">So zeigen Sie Verbindungseigenschaften eines Abfragefensters an</span><span class="sxs-lookup"><span data-stu-id="fc751-111">To view connection properties of a query window</span></span>  
  
1.  <span data-ttu-id="fc751-112">Wird das Eigenschaftenfenster nicht angezeigt, klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster** , oder drücken Sie F4.</span><span class="sxs-lookup"><span data-stu-id="fc751-112">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="fc751-113">Alle Eigenschaften der Verbindung werden im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc751-113">In the Properties window, you can see all the connection properties.</span></span>  
  
### <a name="to-view-the-properties-of-a-showplan-operator"></a><span data-ttu-id="fc751-114">So zeigen Sie die Eigenschaften eines Showplanoperators an</span><span class="sxs-lookup"><span data-stu-id="fc751-114">To view the properties of a Showplan operator</span></span>  
  
1.  <span data-ttu-id="fc751-115">Klicken Sie im Menü **Abfrage** auf **Tatsächlichen Ausführungsplan einschließen**.</span><span class="sxs-lookup"><span data-stu-id="fc751-115">On the **Query** menu, click **Include Actual Execution Plan**.</span></span>  
  
2.  <span data-ttu-id="fc751-116">Geben Sie im SQL-Abfrage-Editor eine Abfrage ein, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="fc751-116">In the SQL Query Editor, type and execute a query.</span></span>  
  
3.  <span data-ttu-id="fc751-117">Wird das Eigenschaftenfenster nicht angezeigt, klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster** , oder drücken Sie F4.</span><span class="sxs-lookup"><span data-stu-id="fc751-117">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
4.  <span data-ttu-id="fc751-118">Klicken Sie im SQL-Abfrage-Editor auf der Registerkarte **Ausführungsplan** auf die Symbole des Operators, um Informationen zu den Operatoren im Eigenschaftenfenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fc751-118">On the **Execution plan** tab of the SQL Query Editor click the icons of the operators to view information about the operators in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc751-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc751-119">See Also</span></span>  
 [<span data-ttu-id="fc751-120">Eigenschaftenfenster &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fc751-120">Properties Window &#40;Management Studio&#41;</span></span>](../../ssms/properties-window-management-studio.md)  
  
  
