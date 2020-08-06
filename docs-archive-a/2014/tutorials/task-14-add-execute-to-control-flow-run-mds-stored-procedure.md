---
title: 'Aufgabe 14: Hinzufügen von Execute SQL Task zur Ablauf Steuerung, um die gespeicherte Prozedur für MDS auszuführen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9a5d1b52-d505-4e6f-8a89-569329c094e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da8e80b25706c40e749fc364baeb578681e76b42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698930"
---
# <a name="task-14-adding-execute-sql-task-to-control-flow-to-run-the-stored-procedure-for-mds"></a><span data-ttu-id="668dd-102">Aufgabe 14: Hinzufügen des Tasks „SQL ausführen“ zur Ablaufsteuerung, um die gespeicherte Prozedur für MDS auszuführen</span><span class="sxs-lookup"><span data-stu-id="668dd-102">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>
  <span data-ttu-id="668dd-103">Nachdem Sie Daten in die Stagingtabellen von MDS geladen haben, müssen Sie eine gespeicherte Prozedur ausführen, die der Tabelle zugeordnet ist, um die Daten aus dem Staging in die entsprechenden Tabellen in der MDS-Datenbank zu laden.</span><span class="sxs-lookup"><span data-stu-id="668dd-103">After loading data into the staging tables of MDS, you run a stored procedure associated with that table to load the data from staging into the appropriate tables in the MDS database.</span></span> <span data-ttu-id="668dd-104">Diese gespeicherte Prozedur hat zwei erforderliche Parameter, die Sie übergeben müssen: LogFlag und VersionName.</span><span class="sxs-lookup"><span data-stu-id="668dd-104">This stored procedure has two required parameters that you need to pass: LogFlag and VersionName.</span></span> <span data-ttu-id="668dd-105">LogFlag gibt an, ob Transaktionen während des Stagingprozesses protokolliert werden, und VersionName gibt die Version des Modells an.</span><span class="sxs-lookup"><span data-stu-id="668dd-105">LogFlag specifies whether transactions are logged during the staging process and VersionName represents the version of the model.</span></span> <span data-ttu-id="668dd-106">Weitere Informationen finden Sie im Thema [gestaffelte gespeicherte Prozeduren](https://msdn.microsoft.com/library/hh231028.aspx) .</span><span class="sxs-lookup"><span data-stu-id="668dd-106">See [Staged Stored Procedure](https://msdn.microsoft.com/library/hh231028.aspx) topic for more details.</span></span>

 <span data-ttu-id="668dd-107">In dieser Aufgabe fügen Sie der Ablaufsteuerung den Task "SQL ausführen" hinzu, um die gespeicherte Prozedur aufzurufen und die bereitgestellten Daten in die entsprechenden MDS-Tabellen zu laden.</span><span class="sxs-lookup"><span data-stu-id="668dd-107">In this task, you add the Execute SQL Task to the control flow to invoke the stored procedure to load the staged data into appropriate MDS tables.</span></span>

1.  <span data-ttu-id="668dd-108">Wechseln Sie nun zur Registerkarte **Ablauf Steuerung** .</span><span class="sxs-lookup"><span data-stu-id="668dd-108">Now, switch to the **Control Flow** tab.</span></span>

2.  <span data-ttu-id="668dd-109">Ziehen Sie den **Task SQL ausführen** aus der **SSIS-Toolbox** auf die Registerkarte **Ablauf Steuerung** .</span><span class="sxs-lookup"><span data-stu-id="668dd-109">Drag-drop **Execute SQL Task** from the **SSIS Toolbox** to the **Control Flow** tab.</span></span>

3.  <span data-ttu-id="668dd-110">Klicken Sie in der Registerkarte **Ablauf Steuerung** mit der rechten Maustaste auf **SQL ausführen** , und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="668dd-110">Right-click **Execute SQL Task** in the **Control Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="668dd-111">Geben Sie **die gespeicherte Prozedur zum Laden von Daten in MDS ein,** und drücken **Sie Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="668dd-111">Type **Trigger Stored Procedure to Load Data into MDS** and press **ENTER**.</span></span>

4.  <span data-ttu-id="668dd-112">Verbinden von **Empfangs-, Bereinigung-, überein** stimmenden und angleichen Lieferantendaten, um die **gespeicherte Prozedur zum Laden von Daten** mithilfe des grünen Connectors zu veranlassen.</span><span class="sxs-lookup"><span data-stu-id="668dd-112">Connect **Receive, Cleanse, Match, and Curate Supplier Data** to **Trigger Stored Procedure to Load Data** using the green connector.</span></span>

     <span data-ttu-id="668dd-113">![Verbinden mit dem Task "SQL ausführen"](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Verbinden mit dem Task "SQL ausführen"")</span><span class="sxs-lookup"><span data-stu-id="668dd-113">![Connect to Execute SQL Task](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connect to Execute SQL Task")</span></span>

5.  <span data-ttu-id="668dd-114">Fügen Sie mithilfe des Fensters **Variablen** zwei neue Variablen mit den folgenden Einstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="668dd-114">Using the **Variables** window, add two new variables with the following settings.</span></span> <span data-ttu-id="668dd-115">Wenn das Fenster **Variablen** nicht angezeigt wird, klicken Sie in der Menüleiste auf **SSIS** , und klicken Sie dann auf **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="668dd-115">If you do not see the **Variables** window, click **SSIS** on the menu bar and click **Variables**.</span></span>

    |<span data-ttu-id="668dd-116">Name</span><span class="sxs-lookup"><span data-stu-id="668dd-116">Name</span></span>|<span data-ttu-id="668dd-117">Datentyp</span><span class="sxs-lookup"><span data-stu-id="668dd-117">Data Type</span></span>|<span data-ttu-id="668dd-118">Wert</span><span class="sxs-lookup"><span data-stu-id="668dd-118">Value</span></span>|
    |----------|---------------|-----------|
    |<span data-ttu-id="668dd-119">LogFlag</span><span class="sxs-lookup"><span data-stu-id="668dd-119">LogFlag</span></span>|<span data-ttu-id="668dd-120">Int32</span><span class="sxs-lookup"><span data-stu-id="668dd-120">Int32</span></span>|<span data-ttu-id="668dd-121">1</span><span class="sxs-lookup"><span data-stu-id="668dd-121">1</span></span>|
    |<span data-ttu-id="668dd-122">VersionName</span><span class="sxs-lookup"><span data-stu-id="668dd-122">VersionName</span></span>|<span data-ttu-id="668dd-123">String</span><span class="sxs-lookup"><span data-stu-id="668dd-123">String</span></span>|<span data-ttu-id="668dd-124">VERSION_1</span><span class="sxs-lookup"><span data-stu-id="668dd-124">VERSION_1</span></span>|

     <span data-ttu-id="668dd-125">![SSIS-Variablen (Fenster)](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS-Variablen (Fenster)")</span><span class="sxs-lookup"><span data-stu-id="668dd-125">![SSIS Variables Window](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS Variables Window")</span></span>

6.  <span data-ttu-id="668dd-126">Doppelklicken Sie **auf gespeicherte Prozedur ausführen, um Daten in MDS zu laden**.</span><span class="sxs-lookup"><span data-stu-id="668dd-126">Double-click **Trigger Stored Procedure to Load Data into MDS**.</span></span>

7.  <span data-ttu-id="668dd-127">Wählen Sie im Dialogfeld Editor für den **Task ' SQL ausführen** ' **(lokal) aus. MDS** (oder **localhost. MDS**) für die **Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="668dd-127">In the **Execute SQL Task Editor** dialog box, select **(local).MDS** (or **localhost.MDS**) for **Connection**.</span></span>

8.  <span data-ttu-id="668dd-128">Geben Sie **EXEC [STG]. [ein. udp_Supplier_Leaf]?,?,?**</span><span class="sxs-lookup"><span data-stu-id="668dd-128">Type **EXEC [stg].[udp_Supplier_Leaf] ?, ?, ?**</span></span> <span data-ttu-id="668dd-129">für die **SQL-Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="668dd-129">for **SQL Statement**.</span></span> <span data-ttu-id="668dd-130">Sie können den Namen mit SQL Server Management Studio überprüfen.</span><span class="sxs-lookup"><span data-stu-id="668dd-130">You can verify the name by using SQL Server Management Studio.</span></span>

     <span data-ttu-id="668dd-131">![Editor für den Task "SQL ausführen" (Dialogfeld) – Allgemeine Einstellungen](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Editor für den Task "SQL ausführen" (Dialogfeld) – Allgemeine Einstellungen")</span><span class="sxs-lookup"><span data-stu-id="668dd-131">![Execute SQL Editor Dialog Box - General Settings](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Execute SQL Editor Dialog Box - General Settings")</span></span>

9. <span data-ttu-id="668dd-132">Klicken Sie im Menü auf der linken Seite auf **Parameter Zuordnung** .</span><span class="sxs-lookup"><span data-stu-id="668dd-132">Click **Parameter Mapping** from the menu on left.</span></span>

10. <span data-ttu-id="668dd-133">Klicken Sie auf der Seite **Parameter Zuordnung** auf **Hinzufügen** , um eine Zuordnung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="668dd-133">In the **Parameter Mapping** page, click **Add** to add a mapping.</span></span> <span data-ttu-id="668dd-134">Maximieren Sie das Fenster, und passen Sie die Breite der Spalten so an, dass die Werte in den Dropdownlisten vollständig angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="668dd-134">Maximize the window and resize columns so that you can see values in drop-down lists properly.</span></span>

11. <span data-ttu-id="668dd-135">Wählen Sie **User:: VersionName** aus der Dropdown Liste für den **Variablennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="668dd-135">Select **User::VersionName** from the drop-down list for the **Variable Name**.</span></span>

12. <span data-ttu-id="668dd-136">Wählen Sie **nvarchar** als **Datentyp**aus.</span><span class="sxs-lookup"><span data-stu-id="668dd-136">Select **NVARCHAR** for **Data Type**.</span></span>

13. <span data-ttu-id="668dd-137">Geben Sie **0** (null) für den **Parameter Namen**ein.</span><span class="sxs-lookup"><span data-stu-id="668dd-137">Type **0** (zero) for **Parameter Name**.</span></span>

14. <span data-ttu-id="668dd-138">Wiederholen Sie die vorhergehenden vier Schritte, um zwei weitere Variablen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="668dd-138">Repeat the previous four steps to add two more variables.</span></span>

    |<span data-ttu-id="668dd-139">Variablenname</span><span class="sxs-lookup"><span data-stu-id="668dd-139">Variable Name</span></span>|<span data-ttu-id="668dd-140">Datentyp (wichtig)</span><span class="sxs-lookup"><span data-stu-id="668dd-140">Data Type (important)</span></span>|<span data-ttu-id="668dd-141">Parametername</span><span class="sxs-lookup"><span data-stu-id="668dd-141">Parameter Name</span></span>|
    |-------------------|-----------------------------|--------------------|
    |<span data-ttu-id="668dd-142">User::LogFlag</span><span class="sxs-lookup"><span data-stu-id="668dd-142">User::LogFlag</span></span>|<span data-ttu-id="668dd-143">LONG</span><span class="sxs-lookup"><span data-stu-id="668dd-143">LONG</span></span>|<span data-ttu-id="668dd-144">1</span><span class="sxs-lookup"><span data-stu-id="668dd-144">1</span></span>|
    |<span data-ttu-id="668dd-145">User::BatchTag</span><span class="sxs-lookup"><span data-stu-id="668dd-145">User::BatchTag</span></span>|<span data-ttu-id="668dd-146">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="668dd-146">NVARCHAR</span></span>|<span data-ttu-id="668dd-147">2</span><span class="sxs-lookup"><span data-stu-id="668dd-147">2</span></span>|

     <span data-ttu-id="668dd-148">![Editor für den Task "SQL ausführen" – Parameterzuordnung](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Editor für den Task "SQL ausführen" – Parameterzuordnung")</span><span class="sxs-lookup"><span data-stu-id="668dd-148">![Execute SQL Task Editor - Parameter Mapping](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Execute SQL Task Editor - Parameter Mapping")</span></span>

15. <span data-ttu-id="668dd-149">Klicken Sie auf **OK** , um das Dialogfeld **SQL-Editor ausführen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="668dd-149">Click **OK** to close the **Execute SQL Editor** dialog box.</span></span>

## <a name="next-step"></a><span data-ttu-id="668dd-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="668dd-150">Next Step</span></span>
 [<span data-ttu-id="668dd-151">Aufgabe 15: Erstellen und Ausführen des SSIS-Projekts</span><span class="sxs-lookup"><span data-stu-id="668dd-151">Task 15: Building and Running the SSIS Project</span></span>](../../2014/tutorials/task-15-building-and-running-the-ssis-project.md)


