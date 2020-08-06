---
title: Laden von Daten mithilfe des OLE DB-Ziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- loading data
- OLE DB destination [Integration Services]
- destinations [Integration Services], OLE DB
ms.assetid: 78899498-725e-4300-a7af-f983f4ea384b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e8d1123ae91d9e68c00fbe3e05c490383afe0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700089"
---
# <a name="load-data-by-using-the-ole-db-destination"></a><span data-ttu-id="360e8-102">Laden von Daten mithilfe des OLE DB-Ziels</span><span class="sxs-lookup"><span data-stu-id="360e8-102">Load Data by Using the OLE DB Destination</span></span>
  <span data-ttu-id="360e8-103">Das Paket muss bereits mindestens einen Datenflusstask und eine Quelle enthalten, damit Sie ein OLE DB-Ziel hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="360e8-103">To add and configure an OLE DB destination, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-load-data-using-an-ole-db-destination"></a><span data-ttu-id="360e8-104">So laden Sie Daten mithilfe eines OLE DB-Zieles</span><span class="sxs-lookup"><span data-stu-id="360e8-104">To load data using an OLE DB destination</span></span>  
  
1.  <span data-ttu-id="360e8-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="360e8-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="360e8-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="360e8-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="360e8-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus **Toolbox**das OLE DB-Ziel auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="360e8-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="360e8-108">Verbinden Sie das OLE DB-Ziel mit dem Datenfluss, indem Sie einen Konnektor von einer Datenquelle oder einer vorherigen Transformation auf das Ziel ziehen.</span><span class="sxs-lookup"><span data-stu-id="360e8-108">Connect the OLE DB destination to the data flow by dragging a connector from a data source or a previous transformation to the destination.</span></span>  
  
5.  <span data-ttu-id="360e8-109">Doppelklicken Sie auf das OLE DB-Ziel.</span><span class="sxs-lookup"><span data-stu-id="360e8-109">Double-click the OLE DB destination.</span></span>  
  
6.  <span data-ttu-id="360e8-110">Wählen Sie im Dialogfeld **Ziel-Editor für OLE DB** auf der Seite **Verbindungs-Manager** einen vorhandenen OLE DB-Verbindungs-Manager aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="360e8-110">In the **OLE DB Destination Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="360e8-111">Weitere Informationen finden Sie unter [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="360e8-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="360e8-112">Wählen Sie die Datenzugriffsmethode aus:</span><span class="sxs-lookup"><span data-stu-id="360e8-112">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="360e8-113">**Tabelle oder Sicht** Wählen Sie eine Tabelle oder Sicht in der Datenbank aus, die die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="360e8-113">**Table or view** Select a table or view in the database that contains the data.</span></span>  
  
    -   <span data-ttu-id="360e8-114">**Tabelle oder Sicht – schnelles Laden** Wählen Sie eine Tabelle oder Sicht in der Datenbank aus, die die Daten enthält, und legen Sie dann die Optionen für schnelles Laden fest: **Identität beibehalten**, **NULL-Werte beibehalten**, **Tabellensperre**, **Einschränkungen überprüfen**, **Zeilen pro Batch**oder **Maximale Einfügungscommitgröße**.</span><span class="sxs-lookup"><span data-stu-id="360e8-114">**Table or view - fast load** Select a table or view in the database that contains the data, and then set the fast-load options: **Keep identity**, **Keep null**, **Table lock**, **Check constraint**, **Rows per batch**, or **Maximum insert commit size**.</span></span>  
  
    -   <span data-ttu-id="360e8-115">**Variable für Tabellenname oder Sichtname** Wählen Sie die benutzerdefinierte Variable aus, die den Namen einer Tabelle oder Sicht in der Datenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="360e8-115">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database.</span></span>  
  
    -   <span data-ttu-id="360e8-116">**Variable für Tabellenname oder Sichtname – schnelles Laden** Wählen Sie die benutzerdefinierte Variable aus, die den Namen einer Tabelle oder Sicht in der Datenbank enthält, in der die Daten gespeichert sind, und legen Sie dann die Optionen für schnelles Laden fest.</span><span class="sxs-lookup"><span data-stu-id="360e8-116">**Table name or view name variable fast load** Select the user-defined variable that contains the name of a table or view in the database that contains the data, and then set the fast-load options.</span></span>  
  
    -   <span data-ttu-id="360e8-117">**SQL-Befehl** Geben Sie einen SQL-Befehl ein, oder klicken Sie auf **Abfrage erstellen** , um mit **Abfrage-Generator**einen SQL-Befehl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="360e8-117">**SQL command** Type an SQL command or click **Build Query** to write an SQL command by using the **Query Builder**.</span></span>  
  
8.  <span data-ttu-id="360e8-118">Klicken Sie auf **Zuordnungen** , und ordnen Sie Spalten aus der Liste **Verfügbare Eingabespalten** Spalten in der Liste **Verfügbare Zielspalten** zu, indem Sie Spalten von einer Liste in eine andere Liste ziehen.</span><span class="sxs-lookup"><span data-stu-id="360e8-118">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="360e8-119">Vom OLE DB-Ziel werden automatisch gleichnamige Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="360e8-119">The OLE DB destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="360e8-120">Klicken Sie auf **Fehlerausgabe**, um die Fehlerausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="360e8-120">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="360e8-121">Weitere Informationen finden Sie unter [Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="360e8-121">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="360e8-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="360e8-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="360e8-123">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="360e8-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="360e8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="360e8-124">See Also</span></span>  
 <span data-ttu-id="360e8-125">[OLE DB-Ziel](ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="360e8-125">[OLE DB Destination](ole-db-destination.md) </span></span>  
 <span data-ttu-id="360e8-126">[SQL Server Integration Services-Transformationen](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="360e8-126">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="360e8-127">[SQL Server Integration Services-Pfade](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="360e8-127">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="360e8-128">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="360e8-128">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
