---
title: 'Aufgabe 13: Hinzufügen OLE DB Ziels zum Schreiben von Daten in die MDS-Stagingtabelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e6c67fa9-bb52-44a9-82f6-d86551cf12b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77799782518a3be2441b4c461467e3132781298d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698973"
---
# <a name="task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table"></a><span data-ttu-id="fecb0-102">Aufgabe 13: Hinzufügen von OLE DB-Zielen zum Schreiben von Daten in die MDS-Stagingtabelle</span><span class="sxs-lookup"><span data-stu-id="fecb0-102">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>
  <span data-ttu-id="fecb0-103">Nachdem Sie die Werte für " **importtype** " und " **batchtag** " allen Datensätzen hinzugefügt haben, können Sie Sie für das Staging an MDS senden.</span><span class="sxs-lookup"><span data-stu-id="fecb0-103">Now that you have added **ImportType** and **BatchTag** values to all records, you are ready to send them over to MDS for staging.</span></span> <span data-ttu-id="fecb0-104">In dieser Aufgabe verwenden Sie das OLE DB Ziel, um die Daten in die **Stagingtabelle "STG. supplier_Leaf** " zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="fecb0-104">In this task, you use the OLE DB Destination to write the data into **stg.supplier_Leaf** staging table.</span></span>  
  
1.  <span data-ttu-id="fecb0-105">Ziehen Sie **OLE DB Ziel** aus dem Abschnitt **andere Ziele** in der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** , und legen Sie Sie unter für **MDS erforderliche Spalten hinzufügen**fest.</span><span class="sxs-lookup"><span data-stu-id="fecb0-105">Drag **OLE DB Destination** from **Other Destinations** section in the **SSIS Toolbox** to the **Data Flow** tab and drop it under **Add Columns Required by MDS**.</span></span>  
  
2.  <span data-ttu-id="fecb0-106">Klicken Sie mit der rechten Maustaste auf **OLE DB Ziel** auf der Registerkarte **Datenfluss** , und klicken Sie auf **Umbenennen**</span><span class="sxs-lookup"><span data-stu-id="fecb0-106">Right-click **OLE DB Destination** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="fecb0-107">Geben Sie **Daten in MDS-Stagingtabelle schreiben ein,** und drücken **Sie die Eingabe**Taste</span><span class="sxs-lookup"><span data-stu-id="fecb0-107">Type **Write Supplier Data to MDS Staging Table** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="fecb0-108">Verbinden Sie die **von MDS benötigten Add-Spalten** , um Lieferantendaten mit dem blauen Connector **in die MDS-Stagingtabelle zu schreiben** .</span><span class="sxs-lookup"><span data-stu-id="fecb0-108">Connect the **Add Columns Required by MDS** to **Write Supplier Data to MDS Staging Table** using the blue connector.</span></span>  
  
4.  <span data-ttu-id="fecb0-109">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf **Lieferantendaten in MDS-Stagingtabelle schreiben** .</span><span class="sxs-lookup"><span data-stu-id="fecb0-109">Double-click **Write Supplier Data to MDS Staging Table** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="fecb0-110">Stellen Sie im Dialog Feld **Ziel-Editor für OLE DB** sicher, dass **(local). MDS** (oder **localhost. MDS**) für das Feld **OLE DB Verbindungs-Manager** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="fecb0-110">In the **OLE DB Destination Editor** Dialog box, make sure that **(local).MDS** (or **localhost.MDS**) is selected for the **OLE DB Connection Manager** field.</span></span>  
  
6.  <span data-ttu-id="fecb0-111">Wählen Sie **STG aus. Supplier_Leaf** Tabelle aus der Liste der **Namen der Tabelle oder Sicht**.</span><span class="sxs-lookup"><span data-stu-id="fecb0-111">Select **stg.Supplier_Leaf** table from the list of **Name of the table or the view**.</span></span>  
  
     <span data-ttu-id="fecb0-112">![Ziel-Editor für OLE DB](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "Ziel-Editor für OLE DB")</span><span class="sxs-lookup"><span data-stu-id="fecb0-112">![OLEDB Destination Editor](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "OLEDB Destination Editor")</span></span>  
  
7.  <span data-ttu-id="fecb0-113">Wechseln Sie zur Seite Zuordnungen, indem Sie im Menü **auf der linken** Seite auf **Zuordnung** klicken.</span><span class="sxs-lookup"><span data-stu-id="fecb0-113">Switch to the **Mappings** page by clicking **Mapping** on the menu on left.</span></span>  
  
8.  <span data-ttu-id="fecb0-114">Ordnen Sie die **Eingabe** -und **Ziel** Spalten zu, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fecb0-114">Map **input** and **destination** columns as shown in the following table.</span></span>  
  
     <span data-ttu-id="fecb0-115">![Ziel-Editor für OLE DB – Zuordnungen](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "Ziel-Editor für OLE DB – Zuordnungen")</span><span class="sxs-lookup"><span data-stu-id="fecb0-115">![OLEDB Destination Editor - Mappings](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "OLEDB Destination Editor - Mappings")</span></span>  
  
9. <span data-ttu-id="fecb0-116">Vergewissern Sie sich, dass Sie **_Output** Spalten für Eingabe Spalten verwenden, nicht die **_Status** -oder **_Source** Spalten.</span><span class="sxs-lookup"><span data-stu-id="fecb0-116">Confirm that you are using **_Output** columns for Input Columns, not the **_Status** or **_Source** columns.</span></span> <span data-ttu-id="fecb0-117">**_Output** Spalten enthalten die Ausgabewerte der DQS-Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="fecb0-117">**_Output** columns contain the output values from DQS Cleansing.</span></span>  
  
10. <span data-ttu-id="fecb0-118">Klicken Sie auf **OK** , um das Dialogfeld **Ziel-Editor OLE DB** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="fecb0-118">Click **OK** to close the **OLE DB Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="fecb0-119">Der Datenfluss sollte wie in folgendem Bild aussehen.</span><span class="sxs-lookup"><span data-stu-id="fecb0-119">The data flow should like the following image.</span></span>  
  
     <span data-ttu-id="fecb0-120">![Abgeschlossener Datenfluss](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Abgeschlossener Datenfluss")</span><span class="sxs-lookup"><span data-stu-id="fecb0-120">![Completed Data Flow](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Completed Data Flow")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="fecb0-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fecb0-121">Next Step</span></span>  
 [<span data-ttu-id="fecb0-122">Aufgabe 14: Hinzufügen des Tasks „SQL ausführen“ zur Ablaufsteuerung, um die gespeicherte Prozedur für MDS auszuführen</span><span class="sxs-lookup"><span data-stu-id="fecb0-122">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>](../../2014/tutorials/task-14-add-execute-to-control-flow-run-mds-stored-procedure.md)  
  
  
