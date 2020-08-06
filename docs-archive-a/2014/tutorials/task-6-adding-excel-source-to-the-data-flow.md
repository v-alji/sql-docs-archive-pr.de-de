---
title: 'Aufgabe 6: Hinzufügen der Excel-Quelle zum Datenfluss | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0209055e-cb6b-4a07-909e-836596727a2c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ae183dee04619a407655026a49b189f7bb3ac6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620690"
---
# <a name="task-6-adding-excel-source-to-the-data-flow"></a><span data-ttu-id="18d0a-102">Aufgabe 6: Hinzufügen der Excel-Quelle zum Datenfluss</span><span class="sxs-lookup"><span data-stu-id="18d0a-102">Task 6: Adding Excel Source to the Data Flow</span></span>
  <span data-ttu-id="18d0a-103">In dieser Aufgabe fügen Sie dem Datenfluss eine Excel-Quelle hinzu, um Lieferantendaten aus der Excel-Quelldatei zu lesen.</span><span class="sxs-lookup"><span data-stu-id="18d0a-103">In this task, you add an Excel Source to the data flow to read supplier data from the source Excel file.</span></span> <span data-ttu-id="18d0a-104">Die Excel-Quelle extrahiert Daten aus Arbeitsblättern oder Bereichen in Microsoft Excel-Arbeitsmappen.</span><span class="sxs-lookup"><span data-stu-id="18d0a-104">The Excel Source extracts data from worksheets or ranges in Microsoft Excel workbooks.</span></span> <span data-ttu-id="18d0a-105">Weitere Informationen finden Sie im Thema [Excel-Quelle](../integration-services/data-flow/excel-source.md) .</span><span class="sxs-lookup"><span data-stu-id="18d0a-105">See [Excel Source](../integration-services/data-flow/excel-source.md) topic for more details.</span></span>

1.  <span data-ttu-id="18d0a-106">Ziehen Sie **Excel-Quelle** aus **anderen Quellen** in der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="18d0a-106">Drag-drop **Excel Source** from **Other Sources** in **SSIS Toolbox** to the **Data Flow** tab.</span></span>

2.  <span data-ttu-id="18d0a-107">Klicken Sie in der Registerkarte **Datenfluss** mit der rechten Maustaste auf **Excel-Quelle** , und klicken Sie auf **Umbenennen**</span><span class="sxs-lookup"><span data-stu-id="18d0a-107">Right-click on **Excel Source** in the **Data Flow** tab, and click **Rename**.</span></span>

3.  <span data-ttu-id="18d0a-108">Geben **Sie Lieferantendaten aus Excel-Datei lesen** ein, und drücken **Sie Eingabe**.</span><span class="sxs-lookup"><span data-stu-id="18d0a-108">Type **Read Supplier Data from Excel File** and press **ENTER**.</span></span>

4.  <span data-ttu-id="18d0a-109">Doppelklicken Sie auf **Lieferantendaten aus Excel-Datei lesen** , um das Dialogfeld **Quellen-Editor für Excel** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="18d0a-109">Double-click **Read Supplier Data from Excel File** to launch the **Excel Source Editor** dialog box.</span></span>

5.  <span data-ttu-id="18d0a-110">Klicken Sie im Dialogfeld **Quellen-Editor für Excel** auf **neu** , um eine Excel-Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="18d0a-110">In the **Excel Source Editor** dialog box, click **New** to create an Excel connection.</span></span>

6.  <span data-ttu-id="18d0a-111">Klicken Sie im Dialogfeld **Excel-Verbindungs-Manager** auf **Durchsuchen**, und wählen Sie dann im Ordner **EIM Tutorial** die **Suppliers.xls** Datei aus.</span><span class="sxs-lookup"><span data-stu-id="18d0a-111">In the **Excel Connection Manager** dialog box, click **Browse**, and then select the **Suppliers.xls** file in the **EIM Tutorial** folder.</span></span> <span data-ttu-id="18d0a-112">Vergewissern Sie sich, dass im Feld Excel- **Version** **Microsoft Excel 97-2003** ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="18d0a-112">Confirm that **Microsoft Excel 97-2003** is selected in the **Excel Version** box and then click **OK**.</span></span>

     <span data-ttu-id="18d0a-113">![Excel-Verbindungs-Manager (Dialogfeld)](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel-Verbindungs-Manager (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="18d0a-113">![Excel Connection Manager Dialog Box](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel Connection Manager Dialog Box")</span></span>

7.  <span data-ttu-id="18d0a-114">Wählen Sie im Dialogfeld **Quellen-Editor für Excel** im Listenfeld Name der Excel- **Tabelle** den Wert **incomingsuppliers $** aus.</span><span class="sxs-lookup"><span data-stu-id="18d0a-114">In the **Excel Source Editor** dialog box, select **IncomingSuppliers$** in the **Name of the Excel sheet** list box.</span></span>

     <span data-ttu-id="18d0a-115">![Name der Excel-Tabelle – Lieferanten Eingang ($)](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name der Excel-Tabelle – Lieferanten Eingang ($)")</span><span class="sxs-lookup"><span data-stu-id="18d0a-115">![Name of Excel Sheet - Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name of Excel Sheet - Incoming Suppliers$")</span></span>

8.  <span data-ttu-id="18d0a-116">Klicken Sie auf **Vorschau** , um die Daten in der Excel-Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="18d0a-116">Click **Preview** to preview the data in Excel file.</span></span>

9. <span data-ttu-id="18d0a-117">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="18d0a-117">Click **OK** to close the dialog box.</span></span>

10. <span data-ttu-id="18d0a-118">Ziehen Sie die Transformation für die **DQS-Bereinigung** in **andere Transformationen** der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** unter **Lieferantendaten aus Excel-Datei lesen**.</span><span class="sxs-lookup"><span data-stu-id="18d0a-118">Drag-drop **DQS Cleansing** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Read Supplier Data from Excel File**.</span></span> <span data-ttu-id="18d0a-119">Die DQS-Bereinigungstransformation verwendet Data Quality Services (DQS), um die Daten zu korrigieren, indem sie genehmigte Regeln in der Wissensdatenbank anwendet.</span><span class="sxs-lookup"><span data-stu-id="18d0a-119">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data by applying approved rules in the knowledge base.</span></span> <span data-ttu-id="18d0a-120">Diese Transformation erstellt zur Laufzeit ein DQS-Bereinigungsprojekt auf dem DQS-Server.</span><span class="sxs-lookup"><span data-stu-id="18d0a-120">This transform, at runtime, creates a DQS cleansing project on the DQS server.</span></span> <span data-ttu-id="18d0a-121">Weitere Informationen finden Sie im Thema zur [Transformation der DQS-Bereinigung](https://msdn.microsoft.com/library/ee677619.aspx) .</span><span class="sxs-lookup"><span data-stu-id="18d0a-121">See [DQS Cleansing Transformation](https://msdn.microsoft.com/library/ee677619.aspx) topic for more details.</span></span>

## <a name="next-step"></a><span data-ttu-id="18d0a-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="18d0a-122">Next Step</span></span>

[<span data-ttu-id="18d0a-123">Aufgabe 7: Hinzufügen der Transformation für DQS-Bereinigung zum Datenfluss</span><span class="sxs-lookup"><span data-stu-id="18d0a-123">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>](task-7-adding-dqs-cleansing-transform-to-the-data-flow.md)

### <a name="see-also"></a><span data-ttu-id="18d0a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18d0a-124">See Also</span></span>

[<span data-ttu-id="18d0a-125">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="18d0a-125">Data Flow</span></span>](../integration-services/data-flow/data-flow.md)
