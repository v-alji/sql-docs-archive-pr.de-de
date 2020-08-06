---
title: Extrahieren von Daten mithilfe der OLE DB-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], OLE DB
- OLE DB source [Integration Services]
ms.assetid: 4ca6eeb5-b60e-4b81-86dd-0674be8ae8d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 352d62cc66e3f17fb10839086e7ee9c5307f1a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726110"
---
# <a name="extract-data-by-using-the-ole-db-source"></a><span data-ttu-id="a2c32-102">Extrahieren von Daten mithilfe der OLE DB-Quelle</span><span class="sxs-lookup"><span data-stu-id="a2c32-102">Extract Data by Using the OLE DB Source</span></span>
  <span data-ttu-id="a2c32-103">Um eine OLE DB-Quelle hinzuzufügen und zu konfigurieren, muss das Paket bereits mindestens einen Datenflusstask enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2c32-103">To add and configure an OLE DB source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-ole-db-source"></a><span data-ttu-id="a2c32-104">So extrahieren Sie Daten mithilfe einer OLE DB-Quelle</span><span class="sxs-lookup"><span data-stu-id="a2c32-104">To extract data using an OLE DB Source</span></span>  
  
1.  <span data-ttu-id="a2c32-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="a2c32-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a2c32-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a2c32-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a2c32-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**die OLE DB-Quelle mit der Maus auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="a2c32-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="a2c32-108">Doppelklicken Sie auf die OLE DB-Quelle.</span><span class="sxs-lookup"><span data-stu-id="a2c32-108">Double-click the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="a2c32-109">Wählen Sie im Dialogfeld **Quellen-Editor für OLE DB** auf der Seite **Verbindungs-Manager** einen vorhandenen OLE DB-Verbindungs-Manager aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2c32-109">In the **OLE DB Source Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="a2c32-110">Weitere Informationen finden Sie unter [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a2c32-110">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
6.  <span data-ttu-id="a2c32-111">Wählen Sie die Datenzugriffsmethode aus:</span><span class="sxs-lookup"><span data-stu-id="a2c32-111">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="a2c32-112">**Tabelle oder Sicht** Wählen Sie eine Tabelle oder Sicht in der Datenbank aus, mit der der OLE DB-Verbindungs-Manager eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="a2c32-112">**Table or view** Select a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="a2c32-113">**Variable für Tabellenname oder Sichtname** Wählen Sie die benutzerdefinierte Variable aus, die den Namen einer Tabelle oder Sicht in der Datenbank enthält, mit der der OLE DB-Verbindungs-Manager eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="a2c32-113">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="a2c32-114">**SQL-Befehl** Geben Sie einen SQL-Befehl ein, oder klicken Sie auf **Abfrage erstellen** , um mit dem **Abfrage-Generator**einen SQL-Befehl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2c32-114">**SQL command** Type an SQL command or click **Build Query** to write an SQL command using the **Query Builder**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a2c32-115">Der Befehl kann Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2c32-115">The command can include parameters.</span></span> <span data-ttu-id="a2c32-116">Weitere Informationen finden Sie unter [Zuordnen von Abfrageparametern zu Variablen in einer Datenflusskomponente](map-query-parameters-to-variables-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a2c32-116">For more information, see [Map Query Parameters to Variables in a Data Flow Component](map-query-parameters-to-variables-in-a-data-flow-component.md).</span></span>  
  
    -   <span data-ttu-id="a2c32-117">**SQL-Befehl aus Variable** Wählen Sie die benutzerdefinierte Variable aus, die den SQL-Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="a2c32-117">**SQL command from variable** Select the user-defined variable that contains the SQL command.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a2c32-118">Die Variablen müssen im Bereich desselben Datenflusstasks definiert werden, der die OLE DB-Quelle enthält, oder im Bereich desselben Pakets. Darüber hinaus muss die Variable einen Zeichenfolgen-Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a2c32-118">The variables must be defined in the scope of the same Data Flow task that contains the OLE DB source, or in the scope of the same package; additionally, the variable must have a string data type.</span></span>  
  
7.  <span data-ttu-id="a2c32-119">Um die Zuordnung zwischen externen Spalten und Ausgabespalten zu aktualisieren, klicken Sie auf **Spalten** und wählen in der Liste **Externe Spalte** verschiedene Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="a2c32-119">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="a2c32-120">Aktualisieren Sie optional die Namen von Ausgabespalten, indem Sie Werte in der Liste **Ausgabespalte** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a2c32-120">Optionally, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="a2c32-121">Klicken Sie auf **Fehlerausgabe**, um die Fehlerausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a2c32-121">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="a2c32-122">Weitere Informationen finden Sie unter [Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a2c32-122">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="a2c32-123">Sie können auf **Vorschau** klicken, um bis zu 200 Zeilen der von der OLE DB-Quelle extrahierten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2c32-123">You can click **Preview** to view up to 200 rows of the data extracted by the OLE DB source.</span></span>  
  
11. <span data-ttu-id="a2c32-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2c32-124">Click **OK**.</span></span>  
  
12. <span data-ttu-id="a2c32-125">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a2c32-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c32-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2c32-126">See Also</span></span>  
 <span data-ttu-id="a2c32-127">[OLE DB-Quelle](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="a2c32-127">[OLE DB Source](ole-db-source.md) </span></span>  
 <span data-ttu-id="a2c32-128">[SQL Server Integration Services-Transformationen](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="a2c32-128">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="a2c32-129">[SQL Server Integration Services-Pfade](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="a2c32-129">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="a2c32-130">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="a2c32-130">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
