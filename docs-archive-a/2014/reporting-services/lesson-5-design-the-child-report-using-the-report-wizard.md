---
title: 'Lektion 5: Entwerfen des untergeordneten Berichts mithilfe des Berichts-Assistenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19a3f927-ea97-4f40-a5f8-cd5f2598e4da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f188a914fc2a2bb8370843191a31474a54c02aa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609715"
---
# <a name="lesson-5-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="f056e-102">Lektion 5: Entwerfen des untergeordneten Berichts mithilfe des Berichts-Assistenten</span><span class="sxs-lookup"><span data-stu-id="f056e-102">Lesson 5: Design the Child Report using the Report Wizard</span></span>
  <span data-ttu-id="f056e-103">Nachdem Sie eine Datenverbindung und eine Datentabelle für den untergeordneten Bericht erstellt haben, entwerfen Sie im nächsten Schritt den untergeordneten Bericht mithilfe des Berichts-Assistenten im Berichts-Designer.</span><span class="sxs-lookup"><span data-stu-id="f056e-103">After you create a data connection and data table for the child report, your next step is to design the child report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="f056e-104">Weitere Informationen zum Berichts-Designer finden Sie unter [Entwerfen von Berichten mithilfe des Berichts-Designers (SSRS)](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f056e-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="f056e-105">So entwerfen Sie den untergeordneten Bericht mithilfe des Berichts-Assistenten</span><span class="sxs-lookup"><span data-stu-id="f056e-105">To design the child report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="f056e-106">Stellen Sie sicher, dass die Website der obersten Ebene im **Projektmappen-Explorer**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f056e-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="f056e-107">Klicken Sie mit der rechten Maustaste auf die Website, und wählen Sie **Neues Element hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="f056e-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="f056e-108">Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Berichts-Assistent**, geben Sie einen Namen für die Berichtsdatei ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f056e-108">In the **Add New Item** dialog box, click **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="f056e-109">Daraufhin wird der Berichts-Assistent gestartet.</span><span class="sxs-lookup"><span data-stu-id="f056e-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="f056e-110">Klicken Sie auf der Seite **Dataseteigenschaften** im Feld **Datenquelle** auf **DataSet2**.</span><span class="sxs-lookup"><span data-stu-id="f056e-110">In the **Dataset Properties** page, in the **Data source** box, click **DataSet2**.</span></span>  
  
     <span data-ttu-id="f056e-111">Das Feld **Verfügbare Datasets** wird automatisch anhand der erstellen DataTable aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f056e-111">The **Available datasets** box is automatically updated with the DataTable you created.</span></span>  
  
5.  <span data-ttu-id="f056e-112">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f056e-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f056e-113">Gehen Sie auf der Seite **Felder anordnen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="f056e-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="f056e-114">Ziehen Sie **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**und **StockedQty** aus **Verfügbare Felder** in das Feld **Werte** .</span><span class="sxs-lookup"><span data-stu-id="f056e-114">Drag **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**, and **StockedQty** from **Available Fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="f056e-115">Klicken Sie auf den Pfeil neben **Sum (ProductID)**, **Sum (PurchaseOrderID)**, **Sum (purchaseorderdetailid)**, **Sum (OrderQty)**, **Sum (receivedqty)**, **Sum (RejectedQty)** und **Sum (stockedqty)** , und löschen Sie die **Sum** -Auswahl.</span><span class="sxs-lookup"><span data-stu-id="f056e-115">Click the arrow next to **Sum(ProductID)**, **Sum(PurchaseOrderID)**, **Sum(PurchaseOrderDetailID)**, **Sum(OrderQty)**, **Sum(ReceivedQty)**, **Sum(RejectedQty)**, and **Sum(StockedQty)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="f056e-116">Klicken Sie zweimal auf **Weiter** , und klicken Sie auf **Fertig stellen** , um den **Berichts-Assistenten**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f056e-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="f056e-117">Die RDLC-Datei ist jetzt erstellt.</span><span class="sxs-lookup"><span data-stu-id="f056e-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="f056e-118">Die Datei wird im Berichts-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f056e-118">The file opens in Report Designer.</span></span> <span data-ttu-id="f056e-119">Die entworfene Tablix wird jetzt auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f056e-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="f056e-120">Fügen Sie bei geöffneter RDLC-Datei auf folgende Weise einen Parameter hinzu:</span><span class="sxs-lookup"><span data-stu-id="f056e-120">With the .rdlc file open, add a parameter by doing the following:</span></span>  
  
    1.  <span data-ttu-id="f056e-121">Klicken Sie im \*\*\*\* Berichtsdatenbereich auf **Parameter** , und klicken Sie dann auf **Parameter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f056e-121">Click **Parameters** in the **Report Data** pane, and then click **Add Parameters**.</span></span>  
  
    2.  <span data-ttu-id="f056e-122">Geben Sie im Feld **Name** die Zeichenfolge **productid** ein.</span><span class="sxs-lookup"><span data-stu-id="f056e-122">Enter **productid** in the **Name** box.</span></span>  
  
    3.  <span data-ttu-id="f056e-123">Vergewissern Sie sich, dass im Listenfeld **Datentyp** der Eintrag **Integer** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f056e-123">Confirm that **Integer** is selected in the **Data Type** list box.</span></span>  
  
    4.  <span data-ttu-id="f056e-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f056e-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="f056e-125">Speichern Sie die RDLC-Datei.</span><span class="sxs-lookup"><span data-stu-id="f056e-125">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="f056e-126">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="f056e-126">Next Task</span></span>  
 <span data-ttu-id="f056e-127">Sie haben erfolgreich den untergeordneten Bericht mit dem Berichts-Assistenten entworfen.</span><span class="sxs-lookup"><span data-stu-id="f056e-127">You have successfully designed the child report by using the Report Wizard.</span></span> <span data-ttu-id="f056e-128">Als Nächstes fügen Sie der Websiteanwendung ein ReportViewer-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="f056e-128">Next, you will add a ReportViewer control to the website application.</span></span>  
  
  
