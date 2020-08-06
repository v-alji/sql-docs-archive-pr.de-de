---
title: Massenladen von Daten mithilfe des SQL Server-Ziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: 8f982f85-a82e-4e2d-9cd8-cd2f85402d8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92ed530ae849f7a4ce123cded421ac0cd0c411ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617217"
---
# <a name="bulk-load-data-by-using-the-sql-server-destination"></a><span data-ttu-id="7afc9-102">Massenladen von Daten mithilfe des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="7afc9-102">Bulk Load Data by Using the SQL Server Destination</span></span>
  <span data-ttu-id="7afc9-103">Das Paket muss bereits mindestens einen Datenflusstask und eine Datenquelle enthalten, damit Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="7afc9-103">To add and configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, the package must already include at least one Data Flow task and a data source.</span></span>  
  
### <a name="to-load-data-using-a-sql-server-destination"></a><span data-ttu-id="7afc9-104">So laden Sie Daten mithilfe eines SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="7afc9-104">To load data using a SQL Server destination</span></span>  
  
1.  <span data-ttu-id="7afc9-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="7afc9-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="7afc9-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7afc9-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="7afc9-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ziel auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="7afc9-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="7afc9-108">Verbinden Sie das Ziel mit einer Quelle oder einer vorherigen Transformation im Datenfluss, indem Sie einen Konnektor auf das Ziel ziehen.</span><span class="sxs-lookup"><span data-stu-id="7afc9-108">Connect the destination to a source or a previous transformation in the data flow by dragging a connector to the destination.</span></span>  
  
5.  <span data-ttu-id="7afc9-109">Doppelklicken Sie auf das Ziel.</span><span class="sxs-lookup"><span data-stu-id="7afc9-109">Double-click the destination.</span></span>  
  
6.  <span data-ttu-id="7afc9-110">Wählen Sie im Dialogfeld **Ziel-Editor für SQL**auf der Seite **Verbindungs-Manager** einen vorhandenen OLE SQL-Verbindungs-Manager aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7afc9-110">In the **SQL Server Destination Editor**, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="7afc9-111">Weitere Informationen finden Sie unter [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7afc9-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="7afc9-112">Führen Sie eine der folgenden Aktionen aus, um die Tabelle oder die Sicht anzugeben, in die die Daten geladen werden sollen:</span><span class="sxs-lookup"><span data-stu-id="7afc9-112">To specify the table or view into which to load the data, do one of the following:</span></span>  
  
    -   <span data-ttu-id="7afc9-113">Wählen Sie eine vorhandene Tabelle oder Sicht aus.</span><span class="sxs-lookup"><span data-stu-id="7afc9-113">Select an existing table or view.</span></span>  
  
    -   <span data-ttu-id="7afc9-114">Klicken Sie auf **Neu**, und schreiben Sie im Dialogfeld **Tabelle erstellen** eine SQL-Anweisung, mit der eine Tabelle oder Sicht erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7afc9-114">Click **New**, and in the **Create Table** dialog boxwrite an SQL statement that creates a table or view.</span></span>  
  
        > [!NOTE]  
        >  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="7afc9-115">generiert eine Standard-CREATE TABLE-Anweisung auf Grundlage der verbundenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7afc9-115">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="7afc9-116">Diese Standard-CREATE TABLE-Anweisung enthält nicht das FILESTREAM-Attribut, selbst wenn die Quelltabelle eine Spalte mit der Erklärung des FILESTREAM-Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="7afc9-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="7afc9-117">Um eine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Komponente mit dem FILESTREAM-Attribut auszuführen, implementieren Sie zunächst die FILESTREAM-Speicherung in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="7afc9-117">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="7afc9-118">Fügen Sie dann das FILESTREAM-Attribut der CREATE TABLE-Anweisung im Dialogfeld **Tabelle erstellen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="7afc9-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="7afc9-119">Weitere Informationen finden Sie unter [Blob-Daten &#40;Binary Large Object, SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7afc9-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="7afc9-120">Klicken Sie auf **Zuordnungen** , und ordnen Sie Spalten aus der Liste **Verfügbare Eingabespalten** Spalten in der Liste **Verfügbare Zielspalten** zu, indem Sie Spalten von einer Liste in eine andere Liste ziehen.</span><span class="sxs-lookup"><span data-stu-id="7afc9-120">Click **Mappings** and map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7afc9-121">Vom Ziel werden automatisch gleichnamige Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7afc9-121">The destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="7afc9-122">Klicken Sie auf **Erweitert** , und legen Sie die Optionen für das Massenladen fest: **Identität beibehalten**, **NULL-Werte beibehalten**, **Tabellensperre**, **Einschränkungen überprüfen**und **Trigger auslösen**.</span><span class="sxs-lookup"><span data-stu-id="7afc9-122">Click **Advanced** and set the bulk load options: **Keep identity**, **Keep nulls**, **Table lock**, **Check constraints**, and **Fire triggers**.</span></span>  
  
     <span data-ttu-id="7afc9-123">Optional können Sie die erste und letzte einzufügende Eingabezeile, die maximal zulässige Anzahl von Fehlern, nach der der Einfügevorgang beendet wird, sowie die Spalten, nach der der Einfügevorgang sortiert wird, angeben.</span><span class="sxs-lookup"><span data-stu-id="7afc9-123">Optionally, specify the first and last input rows to insert, the maximum number of errors that can occur before the insert operation stops, and the columns on which the insert is sorted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7afc9-124">Die Sortierreihenfolge wird durch die Reihenfolge bestimmt, in der die Spalten aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="7afc9-124">The sort order is determined by the order in which the columns are listed.</span></span>  
  
10. <span data-ttu-id="7afc9-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7afc9-125">Click **OK**.</span></span>  
  
11. <span data-ttu-id="7afc9-126">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7afc9-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7afc9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7afc9-127">See Also</span></span>  
 <span data-ttu-id="7afc9-128">[SQL Server Destination](sql-server-destination.md) </span><span class="sxs-lookup"><span data-stu-id="7afc9-128">[SQL Server Destination](sql-server-destination.md) </span></span>  
 <span data-ttu-id="7afc9-129">[SQL Server Integration Services-Transformationen](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="7afc9-129">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="7afc9-130">[SQL Server Integration Services-Pfade](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="7afc9-130">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="7afc9-131">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="7afc9-131">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
