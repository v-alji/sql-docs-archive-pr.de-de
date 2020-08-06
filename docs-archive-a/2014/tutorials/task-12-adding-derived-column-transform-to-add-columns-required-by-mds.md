---
title: 'Aufgabe 12: Hinzufügen der Transformation für abgeleitete Spalten zum Hinzufügen von für MDS benötigten Spalten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 98ccb271-04da-4126-9729-67e9a479aaef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a4a70dd4d288e425beb2821f6b2aaf440b1d1930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719057"
---
# <a name="task-12-adding-derived-column-transform-to-add-columns-required-by-mds"></a><span data-ttu-id="5bdf2-102">Aufgabe 12: Hinzufügen der Transformation „Abgeleitete Spalten“ zum Hinzufügen der für MDS erforderlichen Spalten</span><span class="sxs-lookup"><span data-stu-id="5bdf2-102">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>
  <span data-ttu-id="5bdf2-103">In dieser Aufgabe fügen Sie die Transformation "Abgeleitete Spalte" zum Datenfluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-103">In this task, you add the Derive Column Transform to the data flow.</span></span> <span data-ttu-id="5bdf2-104">Sie fügen den Datensätzen, die an diese Transformation übermittelt werden, zwei abgeleitete Spalten, **importtype** und **batchtag**, hinzu.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-104">You add two derived columns, **ImportType** and **BatchTag**, to the records passed to this transform.</span></span> <span data-ttu-id="5bdf2-105">Sie sollten diese Spalten hinzufügen, bevor Sie die Daten in Stagingtabellen in MDS hochladen.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-105">You should add these columns before uploading the data to staging tables in MDS.</span></span> <span data-ttu-id="5bdf2-106">Diese beiden Spalten sind für die Stagingtabellen in MDS erforderliche Spalten.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-106">These two are required columns for the staging tables in MDS.</span></span> <span data-ttu-id="5bdf2-107">Weitere Informationen finden Sie unter [Stagingtabellen für Blatt](../master-data-services/leaf-member-staging-table-master-data-services.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-107">See [Leaf Member Staging Tables](../master-data-services/leaf-member-staging-table-master-data-services.md) for more details.</span></span>  
  
1.  <span data-ttu-id="5bdf2-108">Ziehen Sie die **Transformation für abgeleitete Spalten** von **Common** section in der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="5bdf2-108">Drag-drop **Derived Column transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="5bdf2-109">Klicken Sie mit der rechten Maustaste auf die Transformation für **abgeleitete Spalten** auf der Registerkarte **Datenfluss** , und **Klicken Sie**</span><span class="sxs-lookup"><span data-stu-id="5bdf2-109">Right-click **Derived Column** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="5bdf2-110">Geben **Sie Add Columns required by MDS** ein, und drücken **Sie die Eingabe**Taste</span><span class="sxs-lookup"><span data-stu-id="5bdf2-110">Type **Add Columns Required by MDS** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="5bdf2-111">Verbindungs **Filter Duplikate** zum **Hinzufügen von Spalten, die von MDS** mit dem blauen Connector benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-111">Connect **Filter Duplicates** to **Add Columns Required by MDS** using the blue connector.</span></span> <span data-ttu-id="5bdf2-112">Das Dialogfeld **Eingabe Ausgabe Auswahl** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-112">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="5bdf2-113">Wählen Sie im Dialogfeld **Eingabe Ausgabe Auswahl** die Option **eindeutige Datensätze**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-113">In the **Input Output Selection** dialog box, select **Unique Records**, and click **OK**.</span></span>  
  
     <span data-ttu-id="5bdf2-114">![Eingabe-/Ausgabe-Auswahl (Dialogfeld)](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Eingabe-/Ausgabe-Auswahl (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="5bdf2-114">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="5bdf2-115">Klicken Sie in der Menüleiste auf **SSIS** , und klicken Sie auf **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-115">Click **SSIS** on the menu bar and click **Variables**.</span></span>  
  
6.  <span data-ttu-id="5bdf2-116">Klicken Sie im Fenster **Variablen** auf der Symbolleiste auf die Schaltfläche **Variable hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="5bdf2-116">In the **Variables** window, click **Add Variable** button on the toolbar.</span></span>  
  
     <span data-ttu-id="5bdf2-117">![SSIS-Variablen (Fenster)](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS-Variablen (Fenster)")</span><span class="sxs-lookup"><span data-stu-id="5bdf2-117">![SSIS Variables Window](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS Variables Window")</span></span>  
  
7.  <span data-ttu-id="5bdf2-118">Geben Sie **importtype** als **Name** und **2** für den **Wert**ein.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-118">Type **ImportType** for the **Name** and **2** for the **value**.</span></span> <span data-ttu-id="5bdf2-119">Sie geben den Wert 2 an, da Sie einer Entität in MDS neue Elemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-119">You specify the value as 2 because you want to add new members to an entity in MDS.</span></span> <span data-ttu-id="5bdf2-120">Ausführliche Informationen zu diesem Parameter finden Sie unter [Stagingtabelle für Blatt](../master-data-services/leaf-member-staging-table-master-data-services.md)Elemente.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-120">For details about this parameter, see [Leaf Member Staging Table](../master-data-services/leaf-member-staging-table-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="5bdf2-121">Klicken Sie erneut auf die Schaltfläche **Variable hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="5bdf2-121">Click **Add Variable** toolbar button again.</span></span>  
  
9. <span data-ttu-id="5bdf2-122">Geben Sie **batchtag** als **Name**ein, wählen Sie **Zeichenfolge** für den **Datentyp**aus, und geben Sie für den **Wert** **eimbatch** ein.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-122">Type **BatchTag** for the **Name**, select **String** for the **Data type**, and **EIMBatch** for the **Value**.</span></span> <span data-ttu-id="5bdf2-123">**Batchtag** ist nur ein eindeutiger Name für den Batch, den Sie an MDS senden.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-123">**BatchTag** is just a unique name for the batch you will be submitting to MDS.</span></span>  
  
10. <span data-ttu-id="5bdf2-124">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf **Spalten hinzufügen, die von MDS benötigt**werden.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-124">In the **Data Flow** tab, double-click **Add Columns Required by MDS**.</span></span>  
  
11. <span data-ttu-id="5bdf2-125">Geben Sie im Dialogfeld **Transformations-Editor für abgeleitete Spalte** im **Listenfeld im unteren**Bereich **importtype** als Namen der **abgeleiteten Spalte**ein.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-125">In the **Derived Column Transformation Editor** dialog box, in the **list box in the bottom pane**, type **ImportType** for the **Derived Column Name**.</span></span>  
  
12. <span data-ttu-id="5bdf2-126">Erweitern Sie **Variablen und Parameter** im oberen linken Bereich, und ziehen Sie **User:: importtype** in die Spalte **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="5bdf2-126">Expand **Variables and Parameters** in the top-left pane, drag-drop **User::ImportType** to the **Expression** column.</span></span>  
  
     <span data-ttu-id="5bdf2-127">![Transformations-Editor für abgeleitete Spalte](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Transformations-Editor für abgeleitete Spalte")</span><span class="sxs-lookup"><span data-stu-id="5bdf2-127">![Derived Column Transformation Editor](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Derived Column Transformation Editor")</span></span>  
  
13. <span data-ttu-id="5bdf2-128">Geben Sie **batchtag** in der nächsten Zeile für den **Namen der abgeleiteten Spalte**ein.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-128">Type **BatchTag** in the next row for the **Derived Column Name**.</span></span>  
  
14. <span data-ttu-id="5bdf2-129">Ziehen Sie **User:: batchtag** aus **Variablen und Parametern** in die Spalte **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="5bdf2-129">Drag-drop **User::BatchTag** from **Variables and Parameters** to the **Expression** column.</span></span>  
  
15. <span data-ttu-id="5bdf2-130">Klicken Sie auf **OK** , um die **Transformation für abgeleitete Spalten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5bdf2-130">Click **OK** to close the **Derived Column Transformation** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="5bdf2-131">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5bdf2-131">Next Step</span></span>  
 [<span data-ttu-id="5bdf2-132">Aufgabe 13: Hinzufügen von OLE DB-Zielen zum Schreiben von Daten in die MDS-Stagingtabelle</span><span class="sxs-lookup"><span data-stu-id="5bdf2-132">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>](../../2014/tutorials/task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table.md)  
  
  
