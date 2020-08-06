---
title: Abrufen und Verstehen der Änderungsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],retrieving data
ms.assetid: af366697-6942-42bb-aea5-18fdef018965
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62f60bf4a79c39b4f0cb7d1ba8fb3f52680a1f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720311"
---
# <a name="retrieve-and-understand-the-change-data"></a><span data-ttu-id="96732-102">Abrufen und Verstehen der Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="96732-102">Retrieve and Understand the Change Data</span></span>
  <span data-ttu-id="96732-103">Im Datenfluss eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, besteht der erste Task darin, die Abfrage auszuführen, bei der die Änderungsdaten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96732-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to run the query that retrieves the change data.</span></span> <span data-ttu-id="96732-104">Sie führen diese Abfrage innerhalb einer Quellkomponente in einem Datenflusstask aus.</span><span class="sxs-lookup"><span data-stu-id="96732-104">You execute this query inside a source component in a Data Flow task.</span></span> <span data-ttu-id="96732-105">Sie können dann Downstream-Transformationen und -Ziele verwenden, um die Änderungsdaten auf Ihr Ziel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="96732-105">You can then use downstream transformations and destinations to apply the change data to your destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96732-106">Das Erstellen einer Abfrage, die eine Tabellenwertfunktion enthält, ist der dritte Schritt beim Erstellen eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt.</span><span class="sxs-lookup"><span data-stu-id="96732-106">The creation of a query that contains a table-valued function is the third step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="96732-107">Weitere Informationen zu dieser Abfrage finden Sie unter [Erstellen der Funktion zum Abrufen der Änderungsdaten](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="96732-107">For more information about this query, see, [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span> <span data-ttu-id="96732-108">Eine Beschreibung des Gesamtprozesses zur Erstellung eines Pakets, das ein inkrementelles Laden von Änderungsdaten ausführt, finden Sie unter [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="96732-108">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="adding-the-data-flow-task"></a><span data-ttu-id="96732-109">Hinzufügen des Datenflusstasks</span><span class="sxs-lookup"><span data-stu-id="96732-109">Adding the Data Flow Task</span></span>  
 <span data-ttu-id="96732-110">Trennen Sie im Datenfluss des Pakets, in dem Sie die Änderungsdaten abrufen, die Zeilen basierend auf dem aufgetretenen Typ der Änderung, und wenden Sie dann die Änderungen auf das Ziel an.</span><span class="sxs-lookup"><span data-stu-id="96732-110">In the data flow of the package, you retrieve the change data, separate the rows based on the type of change that occurred, and then apply the changes to the destination.</span></span>  
  
#### <a name="to-add-a-data-flow-task-to-the-package"></a><span data-ttu-id="96732-111">So fügen Sie dem Paket einen Datenflusstask hinzu</span><span class="sxs-lookup"><span data-stu-id="96732-111">To add a Data Flow task to the package</span></span>  
  
1.  <span data-ttu-id="96732-112">Fügen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf der Registerkarte **Ablaufsteuerung** einen Datenflusstask hinzu.</span><span class="sxs-lookup"><span data-stu-id="96732-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Control Flow** tab, add a Data Flow task.</span></span>  
  
2.  <span data-ttu-id="96732-113">Verbinden Sie den vorhergehenden Task, in dem die Abfragezeichenfolge vorbereitet wurde, mit dem Datenflusstask.</span><span class="sxs-lookup"><span data-stu-id="96732-113">Connect the preceding task that prepared the query string to the Data Flow task.</span></span>  
  
## <a name="configuring-the-source-component-to-query-for-changes"></a><span data-ttu-id="96732-114">Konfigurieren der Quellkomponente zur Abfrage von Änderungen</span><span class="sxs-lookup"><span data-stu-id="96732-114">Configuring the Source Component to Query for Changes</span></span>  
 <span data-ttu-id="96732-115">Die Quellkomponente verwendet die Abfragezeichenfolge, die in einer Variablen vorbereitet und gespeichert wurde, um die Tabellenwertfunktion aufzurufen, mit der die geänderten Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96732-115">The source component uses the query string that was prepared and stored in a variable to calls the table-valued function that retrieves the changed data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96732-116">Weitere Informationen zur Abfragezeichenfolge, die in einer Variablen vorbereitet und gespeichert wurde, finden Sie unter [Vorbereiten zur Abfrage der Änderungsdaten](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="96732-116">For more information about the query string that was prepared and stored in a variable, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span> <span data-ttu-id="96732-117">Weitere Informationen zur Tabellenwertfunktion, mit der die Änderungsdaten abgerufen werden, finden Sie unter [Erstellen der Funktion zum Abrufen der Änderungsdaten](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="96732-117">For more information about the table-valued function that retrieves the change data, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
#### <a name="to-configure-an-ole-db-source-to-retrieve-the-change-data"></a><span data-ttu-id="96732-118">So konfigurieren Sie eine OLE DB-Quelle zum Abrufen der Änderungsdaten</span><span class="sxs-lookup"><span data-stu-id="96732-118">To configure an OLE DB source to retrieve the change data</span></span>  
  
1.  <span data-ttu-id="96732-119">Fügen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf der Registerkarte **Datenfluss** eine OLE DB-Quelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="96732-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Data Flow** tab, add an OLE DB source.</span></span>  
  
2.  <span data-ttu-id="96732-120">Aktivieren Sie im **Quellen-Editor für OLE DB**auf der Seite **Verbindungs-Manager** die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="96732-120">In the **OLE DB Source Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="96732-121">Konfigurieren Sie zur Quelldatenbank eine gültige Verbindung.</span><span class="sxs-lookup"><span data-stu-id="96732-121">Configure a valid connection to the source database.</span></span>  
  
    2.  <span data-ttu-id="96732-122">Wählen Sie für **Datenzugriffsmodus**die Option **SQL-Befehl aus Variable**aus.</span><span class="sxs-lookup"><span data-stu-id="96732-122">For **Data access mode**, select **SQL command from variable**.</span></span>  
  
    3.  <span data-ttu-id="96732-123">Wählen Sie für **Variablenname**die Option **User::SqlDataQuery**aus.</span><span class="sxs-lookup"><span data-stu-id="96732-123">For **Variable name**, select **User::SqlDataQuery**.</span></span>  
  
3.  <span data-ttu-id="96732-124">Vergewissern Sie sich im **Quellen-Editor für OLE DB**auf der Seite **Spalten** , dass alle gewünschten Spalten Ausgabespalten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="96732-124">In the **OLE DB Source Editor**, on the **Columns** page, make sure that all the columns that you want are mapped to output columns.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="96732-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="96732-125">Next Step</span></span>  
 <span data-ttu-id="96732-126">Nachdem Sie eine OLE DB-Quelle konfiguriert haben, um die Änderungsdaten abzurufen, ist der nächste Schritt der Entwurf des Datenflusses im Paket.</span><span class="sxs-lookup"><span data-stu-id="96732-126">After you have configured an OLE DB source to retrieve the change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="96732-127">**Nächstes Thema:** [Verarbeiten von Einfügungen, Updates und Löschungen](process-inserts-updates-and-deletes.md)</span><span class="sxs-lookup"><span data-stu-id="96732-127">**Next topic:** [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md)</span></span>  
  
  
