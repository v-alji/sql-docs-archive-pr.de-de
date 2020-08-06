---
title: 'Lektion 3: Entwerfen des übergeordneten Berichts mithilfe des Berichts-Assistenten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3cb6a0972a2bb63e82e80c02b3ce90912ba01c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609721"
---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="83a1a-102">Lektion 3: Entwerfen des übergeordneten Berichts mithilfe des Berichts-Assistenten</span><span class="sxs-lookup"><span data-stu-id="83a1a-102">Lesson 3: Design the Parent Report using the Report Wizard</span></span>
  <span data-ttu-id="83a1a-103">Nachdem Sie eine Datenverbindung und eine Datentabelle für den übergeordneten Bericht erstellt haben, entwerfen Sie im nächsten Schritt den übergeordneten Bericht mithilfe des Berichts-Assistenten im Berichts-Designer.</span><span class="sxs-lookup"><span data-stu-id="83a1a-103">After you create a data connection and a data table for the parent report, your next step is to design the parent report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="83a1a-104">Weitere Informationen zum Berichts-Designer finden Sie unter [Entwerfen von Berichten mithilfe des Berichts-Designers (SSRS)](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="83a1a-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="83a1a-105">So entwerfen Sie den übergeordneten Bericht mithilfe des Berichts-Assistenten</span><span class="sxs-lookup"><span data-stu-id="83a1a-105">To design the parent report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="83a1a-106">Stellen Sie sicher, dass die Website der obersten Ebene im **Projektmappen-Explorer**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="83a1a-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="83a1a-107">Klicken Sie mit der rechten Maustaste auf die Website, und wählen Sie **Neues Element hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="83a1a-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="83a1a-108">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Berichts-Assistent**aus, geben Sie einen Namen für die Berichtsdatei ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="83a1a-108">In the **Add New Item** dialog box, select **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="83a1a-109">Daraufhin wird der Berichts-Assistent gestartet.</span><span class="sxs-lookup"><span data-stu-id="83a1a-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="83a1a-110">Wählen Sie auf der Seite **Dataseteigenschaften** im Feld **Datenquelle** das **DataSet1** aus, das Sie in [Lektion 2: Definieren einer Datenverbindung und einer Datentabelle für den übergeordneten Bericht](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="83a1a-110">On the **Dataset Properties** page, in the **Data source** box, select the **DataSet1** you created in [Lesson 2: Define a Data Connection and Data Table for Parent Report](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span></span>  
    <span data-ttu-id="83a1a-111">Das Feld **Verfügbare Datasets** wird automatisch anhand der oben erstellten **DataTable** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="83a1a-111">The **Available datasets** box is automatically updated with the **DataTable** you created above.</span></span>  
  
5.  <span data-ttu-id="83a1a-112">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="83a1a-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="83a1a-113">Gehen Sie auf der Seite **Felder anordnen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="83a1a-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="83a1a-114">Ziehen Sie **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**und **ReorderLevel** vom Feld **Verfügbare Felder** auf das Feld **Werte** .</span><span class="sxs-lookup"><span data-stu-id="83a1a-114">Drag **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, and **ReorderLevel** from **Available fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="83a1a-115">Klicken Sie auf den Pfeil neben **Sum (ProductID)**, **Sum (SafetyStockLevel)**, **Sum (ReorderLevel)** , und löschen Sie die **Sum** -Auswahl.</span><span class="sxs-lookup"><span data-stu-id="83a1a-115">Click the arrow next to **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="83a1a-116">Klicken Sie zweimal auf **Weiter** , und klicken Sie auf **Fertig stellen** , um den **Berichts-Assistenten**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="83a1a-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="83a1a-117">Die RDLC-Datei ist jetzt erstellt.</span><span class="sxs-lookup"><span data-stu-id="83a1a-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="83a1a-118">Die Datei wird im Berichts-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="83a1a-118">The file opens in Report Designer.</span></span> <span data-ttu-id="83a1a-119">Die entworfene Tablix wird jetzt auf der Entwurfsoberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83a1a-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="83a1a-120">Speichern Sie die RDLC-Datei.</span><span class="sxs-lookup"><span data-stu-id="83a1a-120">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="83a1a-121">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="83a1a-121">Next Task</span></span>  
 <span data-ttu-id="83a1a-122">Sie haben erfolgreich den übergeordneten Bericht mithilfe des Berichts-Assistenten entworfen.</span><span class="sxs-lookup"><span data-stu-id="83a1a-122">You have successfully designed the parent report using the Report Wizard.</span></span> <span data-ttu-id="83a1a-123">Als Nächstes erstellen Sie eine Datenverbindung und eine Datentabelle für den untergeordneten Bericht.</span><span class="sxs-lookup"><span data-stu-id="83a1a-123">Next, you will create a data connection and a data table for the child report.</span></span>  
  
  
