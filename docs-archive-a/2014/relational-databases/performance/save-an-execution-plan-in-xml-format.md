---
title: Speichern eines Ausführungsplans im XML-Format | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- XML query plans [SQL Server]
- opening execution plans
- XML Showplans [SQL Server]
- execution plans [SQL Server], saving
- saving execution plans
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 84ed341d186993ed77260e8361156b324c597839
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619777"
---
# <a name="save-an-execution-plan-in-xml-format"></a><span data-ttu-id="68d05-102">Speichern eines Ausführungsplans im XML-Format</span><span class="sxs-lookup"><span data-stu-id="68d05-102">Save an Execution Plan in XML Format</span></span>
  <span data-ttu-id="68d05-103">Verwenden Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , um Ausführungspläne als XML-Datei zu speichern und für die Anzeige zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68d05-103">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.</span></span>  
  
 <span data-ttu-id="68d05-104">Zum Verwenden der Ausführungsplanfunktion in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]oder der XML Showplan-SET-Optionen benötigen Benutzer die entsprechenden Berechtigungen, um die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage auszuführen, für die ein Ausführungsplan generiert wird. Den Benutzern muss auch die SHOWPLAN-Berechtigung für alle Datenbanken erteilt werden, auf die die Abfrage verweist.</span><span class="sxs-lookup"><span data-stu-id="68d05-104">To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-save-a-query-plan-by-using-the-xml-showplan-set-options"></a><span data-ttu-id="68d05-105">So speichern Sie einen Abfrageplan mit den XML Showplan-SET-Optionen</span><span class="sxs-lookup"><span data-stu-id="68d05-105">To save a query plan by using the XML Showplan SET options</span></span>  
  
1.  <span data-ttu-id="68d05-106">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] einen Abfrage-Editor, und stellen Sie eine Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="68d05-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="68d05-107">Aktivieren Sie SHOWPLAN_XML mithilfe der folgenden Anweisung:</span><span class="sxs-lookup"><span data-stu-id="68d05-107">Turn SHOWPLAN_XML on with the following statement:</span></span>  
  
    ```  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="68d05-108">Verwenden Sie die folgende Anweisung, um STATISTICS XML zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="68d05-108">To turn STATISTICS XML on, use the following statement:</span></span>  
  
    ```  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="68d05-109">SHOWPLAN_XML generiert für eine Abfrage zur Kompilierungszeit Informationen zum Abfrageausführungsplan, führt die Abfrage aber nicht aus.</span><span class="sxs-lookup"><span data-stu-id="68d05-109">SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query.</span></span> <span data-ttu-id="68d05-110">STATISTICS XML generiert für eine Abfrage zur Laufzeit Informationen zum Abfrageausführungsplan und führt die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="68d05-110">STATISTICS XML generates run-time query execution plan information for a query, and executes the query.</span></span>  
  
3.  <span data-ttu-id="68d05-111">Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="68d05-111">Execute a query.</span></span> <span data-ttu-id="68d05-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="68d05-112">Example:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  <span data-ttu-id="68d05-113">Klicken Sie im Bereich **Ergebnisse** mit der rechten Maustaste auf den **Microsoft SQL Server XML Showplan** , der den Abfrageplan enthält, und klicken Sie dann auf **Ergebnisse speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="68d05-113">In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.</span></span>  
  
5.  <span data-ttu-id="68d05-114">Klicken Sie im Dialogfeld **Speichern** \<Grid or Text> **Ergebnisse** im Feld **Dateityp** auf **Alle Dateien (\*.\*)** .</span><span class="sxs-lookup"><span data-stu-id="68d05-114">In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.</span></span>  
  
6.  <span data-ttu-id="68d05-115">Geben Sie in das Feld **Dateiname** einen Namen im Format \<name**>.sqlplan\*\* ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="68d05-115">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-save-an-execution-plan-by-using-sql-server-management-studio-options"></a><span data-ttu-id="68d05-116">So speichern Sie einen Ausführungsplan mithilfe der SQL Server Management Studio-Optionen</span><span class="sxs-lookup"><span data-stu-id="68d05-116">To save an execution plan by using SQL Server Management Studio options</span></span>  
  
1.  <span data-ttu-id="68d05-117">Generieren Sie mit [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]entweder einen geschätzten Ausführungsplan oder einen tatsächlichen Ausführungsplan.</span><span class="sxs-lookup"><span data-stu-id="68d05-117">Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="68d05-118">Weitere Informationen finden Sie unter [Anzeigen des geschätzten Ausführungsplans](display-the-estimated-execution-plan.md) oder [Anzeigen eines tatsächlichen Ausführungsplans](display-an-actual-execution-plan.md).</span><span class="sxs-lookup"><span data-stu-id="68d05-118">For more information, see [Display the Estimated Execution Plan](display-the-estimated-execution-plan.md) or [Display an Actual Execution Plan](display-an-actual-execution-plan.md).</span></span>  
  
2.  <span data-ttu-id="68d05-119">Klicken Sie im Ergebnisbereich auf der Registerkarte **Ausführungsplan** auf den grafischen Ausführungsplan und wählen Sie **Ausführungsplan speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="68d05-119">In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.</span></span>  
  
     <span data-ttu-id="68d05-120">Alternativ können Sie **Ausführungsplan speichern unter** auch im Menü **Datei** auswählen.</span><span class="sxs-lookup"><span data-stu-id="68d05-120">As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.</span></span>  
  
3.  <span data-ttu-id="68d05-121">Stellen Sie im Dialogfeld **Speichern unter** sicher, dass der **Dateityp** auf **Ausführungsplandateien (\*.sqlplan)** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="68d05-121">In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.</span></span>  
  
4.  <span data-ttu-id="68d05-122">Geben Sie in das Feld **Dateiname** einen Namen im Format \<name**>.sqlplan\*\* ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="68d05-122">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-open-a-saved-xml-query-plan-in-sql-server-management-studio"></a><span data-ttu-id="68d05-123">So öffnen Sie einen gespeicherten XML-Abfrageplan in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68d05-123">To open a saved XML query plan in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="68d05-124">Wählen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Datei** **Öffnen**, und klicken Sie dann auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="68d05-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="68d05-125">Legen Sie im Dialogfeld **Datei öffnen** den **Dateityp** auf **Ausführungsplandateien (\*.sqlplan)** fest, um eine gefilterte Liste der gespeicherten XML-Abfrageplandateien zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="68d05-125">In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.</span></span>  
  
3.  <span data-ttu-id="68d05-126">Wählen Sie die XML-Abfrageplandatei aus, die Sie anzeigen möchten, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="68d05-126">Select the XML query plan file that you want to view, and click **Open**.</span></span>  
  
     <span data-ttu-id="68d05-127">Alternativ können Sie im Windows-Explorer auf eine Datei mit der Erweiterung **.sqlplan**doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="68d05-127">As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**.</span></span> <span data-ttu-id="68d05-128">Der Plan wird in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]geöffnet.</span><span class="sxs-lookup"><span data-stu-id="68d05-128">The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d05-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68d05-129">See Also</span></span>  
 <span data-ttu-id="68d05-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="68d05-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span></span>  
 [<span data-ttu-id="68d05-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="68d05-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
  
