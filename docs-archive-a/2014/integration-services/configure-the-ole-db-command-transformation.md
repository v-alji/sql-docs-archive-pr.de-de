---
title: Konfigurieren der Transformation für OLE DB Befehl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [Integration Services]
- OLE DB Command transformation
ms.assetid: c800f167-3d2e-4c10-8ba3-a02f1872ccea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1714a6b798c6d8256052fd3c16bd86182480bcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722985"
---
# <a name="configure-the-ole-db-command-transformation"></a><span data-ttu-id="d2be4-102">Konfigurieren der Transformation für OLE DB-Befehl</span><span class="sxs-lookup"><span data-stu-id="d2be4-102">Configure the OLE DB Command Transformation</span></span>
  <span data-ttu-id="d2be4-103">Das Paket muss bereits mindestens einen Datenflusstask und eine Quelle, wie z. B. eine Flatfilequelle oder eine OLE DB-Quelle, einschließen, damit Sie eine Transformation für OLE DB-Befehl hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="d2be4-103">To add and configure an OLE DB Command transformation, the package must already include at least one Data Flow task and a source such as a Flat File source or an OLE DB source.</span></span> <span data-ttu-id="d2be4-104">Diese Transformation wird normalerweise zum Ausführen parametrisierter Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2be4-104">This transformation is typically used for running parameterized queries.</span></span>  
  
### <a name="to-configure-the-ole-db-command-transformation"></a><span data-ttu-id="d2be4-105">So konfigurieren Sie die Transformation für OLE DB-Befehl</span><span class="sxs-lookup"><span data-stu-id="d2be4-105">To configure the OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="d2be4-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="d2be4-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d2be4-107">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d2be4-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d2be4-108">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Fenster **Toolbox**die Transformation für OLE DB-Befehl auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="d2be4-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB Command transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="d2be4-109">Verbinden Sie die Transformation für den OLE DB-Befehl mit dem Datenfluss, indem Sie einen Connector (der grüne oder rote Pfeil) von einer Datenquelle oder einer vorherigen Transformation mit der Maus auf die Transformation für den OLE DB-Befehl ziehen.</span><span class="sxs-lookup"><span data-stu-id="d2be4-109">Connect the OLE DB Command transformation to the data flow by dragging a connector-the green or red arrow-from a data source or a previous transformation to the OLE DB Command transformation.</span></span>  
  
5.  <span data-ttu-id="d2be4-110">Klicken Sie mit der rechten Maustaste auf die Komponente, und wählen Sie „Bearbeiten“ oder **Erweiterten Editor anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="d2be4-110">Right-click the component and select Edit or Show **Advanced Editor**.</span></span>  
  
6.  <span data-ttu-id="d2be4-111">Wählen Sie auf der Registerkarte **Verbindungs-Manager** in der Liste **Verbindungs-Manager** einen OLE DB-Verbindungs-Manager aus.</span><span class="sxs-lookup"><span data-stu-id="d2be4-111">On the **Connection Managers** tab, select an OLE DB connection manager in the **Connection Manager** list.</span></span> <span data-ttu-id="d2be4-112">Weitere Informationen finden Sie unter [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d2be4-112">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="d2be4-113">Klicken Sie auf die Registerkarte **Komponenteneigenschaften**, und klicken Sie im Feld **SqlCommand** auf die Schaltfläche mit den Auslassungspunkten (**...**).</span><span class="sxs-lookup"><span data-stu-id="d2be4-113">Click the **Component Properties** tab and click the ellipsis button **(...)** in the **SqlCommand** box.</span></span>  
  
8.  <span data-ttu-id="d2be4-114">Geben Sie in **Zeichenfolgenwert-Editor**die parametrisierte SQL-Anweisung mithilfe eines Fragezeichens (?) als Parametermarkierung für jeden Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="d2be4-114">In the **String Value Editor**, type the parameterized SQL statement using a question mark (?) as the parameter marker for each parameter.</span></span>  
  
9. <span data-ttu-id="d2be4-115">Klicken Sie auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="d2be4-115">Click **Refresh**.</span></span> <span data-ttu-id="d2be4-116">Wenn Sie auf **Aktualisieren**klicken, erstellt die Transformation eine Spalte für jeden Parameter in der Sammlung externer Spalten und legt die DBParamInfoFlags-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="d2be4-116">When you click **Refresh**, the transformation creates a column for each parameter in the External Columns collection and sets the DBParamInfoFlags property.</span></span>  
  
10. <span data-ttu-id="d2be4-117">Klicken Sie auf die Registerkarte **Eingabe- und Ausgabeeigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="d2be4-117">Click the **Input and Output Properties** tab.</span></span>  
  
11. <span data-ttu-id="d2be4-118">Erweitern Sie **Eingabe des OLE DB-Befehls**und anschließend **Externe Spalten**.</span><span class="sxs-lookup"><span data-stu-id="d2be4-118">Expand **OLE DB Command Input**, and then expand **External Columns**.</span></span>  
  
12. <span data-ttu-id="d2be4-119">Überprüfen Sie, ob **Externe Spalten** eine Spalte für jeden Parameter in der SQL-Anweisung auflistet.</span><span class="sxs-lookup"><span data-stu-id="d2be4-119">Verify that **External Columns** lists a column for each parameter in the SQL statement.</span></span> <span data-ttu-id="d2be4-120">Die Spaltennamen lauten **Param_0**, **Param_1**usw.</span><span class="sxs-lookup"><span data-stu-id="d2be4-120">The column names are **Param_0**, **Param_1**, and so on.</span></span>  
  
     <span data-ttu-id="d2be4-121">Die Spaltennamen sollten nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d2be4-121">You should not change the column names.</span></span> <span data-ttu-id="d2be4-122">Wenn Sie die Spaltennamen ändern, generiert [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] einen Überprüfungsfehler für die Transformation für den OLE DB-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d2be4-122">If you change the column names, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a validation error for the OLE DB Command transformation.</span></span>  
  
     <span data-ttu-id="d2be4-123">Der Datentyp sollte auch nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d2be4-123">Also, you should not change the data type.</span></span> <span data-ttu-id="d2be4-124">Die DataType-Eigenschaft der einzelnen Spalten wird auf den entsprechenden Datentyp festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2be4-124">The DataType property of each column is set to the correct data type.</span></span>  
  
13. <span data-ttu-id="d2be4-125">Falls **Externe Spalten** keine Spalten auflistet, müssen sie manuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d2be4-125">If **External Columns** lists no columns you must add them manually.</span></span>  
  
    -   <span data-ttu-id="d2be4-126">Klicken Sie für jeden Parameter in der SQL-Anweisung einmal auf **Spalte hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="d2be4-126">Click **Add Column** one time for each parameter in the SQL statement.</span></span>  
  
    -   <span data-ttu-id="d2be4-127">Aktualisieren Sie die Spaltennamen auf **Param_0**, **Param_1**usw.</span><span class="sxs-lookup"><span data-stu-id="d2be4-127">Update the column names to **Param_0**, **Param_1**, and so on.</span></span>  
  
    -   <span data-ttu-id="d2be4-128">Geben Sie einen Wert in der DBParamInfoFlags-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d2be4-128">Specify a value in the DBParamInfoFlags property.</span></span> <span data-ttu-id="d2be4-129">Der Wert muss mit einem Wert in der OLE DB-Enumeration DBPARAMFLAGSENUM übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d2be4-129">The value must match a value in the OLE DB DBPARAMFLAGSENUM enumeration.</span></span> <span data-ttu-id="d2be4-130">Weitere Informationen finden Sie in der OLE DB-Referenzdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d2be4-130">For more information, see the OLE DB reference documentation.</span></span>  
  
    -   <span data-ttu-id="d2be4-131">Geben Sie den Datentyp der Spalte und, in Abhängigkeit vom Datentyp, die Codepage, die Länge, die Genauigkeit und die Dezimalstellen der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="d2be4-131">Specify the data type of the column and, depending on the data type, specify the code page, length, precision, and scale of the column.</span></span>  
  
    -   <span data-ttu-id="d2be4-132">Wenn Sie einen nicht verwendeten Parameter löschen möchten, wählen Sie den Parameter in **Externe Spalten**aus, und klicken Sie auf **Spalte entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d2be4-132">To delete an unused parameter, select the parameter in **External Columns**, and then click **Remove Column**.</span></span>  
  
    -   <span data-ttu-id="d2be4-133">Klicken Sie auf **Spaltenzuordnungen** , und ordnen Sie Spalten in der Liste **Verfügbare Eingabespalten** Parametern in der Liste **Verfügbare Zielspalten** zu.</span><span class="sxs-lookup"><span data-stu-id="d2be4-133">Click **Column Mappings** and map columns in the **Available Input Columns** list to parameters in the **Available Destination Columns** list.</span></span>  
  
14. <span data-ttu-id="d2be4-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2be4-134">Click **OK**.</span></span>  
  
15. <span data-ttu-id="d2be4-135">Klicken Sie im Menü **Datei** auf **Speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d2be4-135">To save the updated package, click **Save** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2be4-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2be4-136">See Also</span></span>  
 <span data-ttu-id="d2be4-137">[Transformation für OLE DB Befehl](data-flow/transformations/ole-db-command-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="d2be4-137">[OLE DB Command Transformation](data-flow/transformations/ole-db-command-transformation.md) </span></span>  
 <span data-ttu-id="d2be4-138">[SQL Server Integration Services-Transformationen](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="d2be4-138">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="d2be4-139">[SQL Server Integration Services-Pfade](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="d2be4-139">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="d2be4-140">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="d2be4-140">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
