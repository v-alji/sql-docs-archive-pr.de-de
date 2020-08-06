---
title: Zuordnen von Abfrageparametern zu Variablen in einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 5e26977c-758c-46d6-acf1-4fd9238f0950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b38940313397c7be7a8bcdbd2bf7f5233583096e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724829"
---
# <a name="map-query-parameters-to-variables-in-a-data-flow-component"></a><span data-ttu-id="91f2e-102">Zuordnen von Abfrageparametern zu Variablen in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="91f2e-102">Map Query Parameters to Variables in a Data Flow Component</span></span>
  <span data-ttu-id="91f2e-103">Wenn Sie die OLE DB-Quelle so konfigurieren, dass parametrisierte Abfragen verwendet werden, können Sie die Parameter Variablen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="91f2e-103">When you configure the OLE DB source to use parameterized queries, you can map the parameters to variables.</span></span>  
  
 <span data-ttu-id="91f2e-104">Die OLE DB-Quelle verwendet parametrisierte Abfragen zum Filtern von Daten verwenden, wenn die Quelle eine Verbindung zu einer Datenquelle herstellt.</span><span class="sxs-lookup"><span data-stu-id="91f2e-104">The OLE DB source uses parameterized queries to filter data when the source connects to a data source.</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="91f2e-105">So ordnen Sie einer Variablen einen Abfrageparameter zu</span><span class="sxs-lookup"><span data-stu-id="91f2e-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="91f2e-106">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="91f2e-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="91f2e-107">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="91f2e-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="91f2e-108">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Bereich **Toolbox**die OLE DB-Quelle mit der Maus auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="91f2e-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="91f2e-109">Klicken Sie mit der rechten Maustaste auf die OLE DB-Quelle, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="91f2e-109">Right-click the OLE DB source, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="91f2e-110">Wählen Sie im **Quellen-Editor für OLE DB**einen OLE DB-Verbindungs-Manager zum Herstellen einer Verbindung mit der Datenquelle aus, oder klicken Sie auf **Neu** , um einen neuen OLE DB-Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91f2e-110">In the **OLE DB Source Editor**, select an OLE DB connection manager to use to connect to the data source, or click **New** to create a new OLE DB connection manager.</span></span>  
  
6.  <span data-ttu-id="91f2e-111">Wählen Sie die Option **SQL-Befehl** als Datenzugriffsmodus aus, und geben Sie im Bereich **SQL-Befehlstext** eine parametrisierte Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="91f2e-111">Select the **SQL command** option for data access mode, and then type a parameterized query in the **SQL command text** pane.</span></span>  
  
7.  <span data-ttu-id="91f2e-112">Klicken Sie auf **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="91f2e-112">Click **Parameters**.</span></span>  
  
8.  <span data-ttu-id="91f2e-113">Ordnen Sie im Dialogfeld **Abfrageparameter festlegen** alle Parameter in der Liste **Parameter** einer Variablen in der Liste **Variablen** zu, oder klicken Sie auf **\<New variable>** , um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91f2e-113">In the **Set Query Parameters** dialog box, map each parameter in the **Parameters** list to a variable in the **Variables** list, or create a new variable by clicking **\<New variable>**.</span></span> <span data-ttu-id="91f2e-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="91f2e-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91f2e-115">Nur Systemvariablen und benutzerdefinierte Variablen im Bereich des Pakets, ein übergeordneter Container (z. B. eine Foreach-Schleife) oder der Datenflusstask, in dem die Datenflusskomponente enthalten ist, können zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="91f2e-115">Only system variables and user-defined variables that are in the scope of the package, a parent container such as a Foreach Loop, or the Data Flow task that contains the data flow component are available for mapping.</span></span> <span data-ttu-id="91f2e-116">Die Variable muss einen Datentyp aufweisen, der mit der Spalte in der WHERE-Klausel kompatibel ist, der der Parameter zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="91f2e-116">The variable must have a data type that is compatible with the column in the WHERE clause to which the parameter is assigned.</span></span>  
  
9. <span data-ttu-id="91f2e-117">Sie können auf **Vorschau** klicken, um bis zu 200 Zeilen der von der Abfrage zurückgegebenen Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91f2e-117">You can click **Preview** to view up to 200 rows of the data that the query returns.</span></span>  
  
10. <span data-ttu-id="91f2e-118">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="91f2e-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f2e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91f2e-119">See Also</span></span>  
 <span data-ttu-id="91f2e-120">[OLE DB-Quelle](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="91f2e-120">[OLE DB Source](ole-db-source.md) </span></span>  
 [<span data-ttu-id="91f2e-121">Suchtransformation</span><span class="sxs-lookup"><span data-stu-id="91f2e-121">Lookup Transformation</span></span>](transformations/lookup-transformation.md)  
  
  
