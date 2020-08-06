---
title: 'Lektion 2: Angeben von Verbindungsinformationen (Reporting Services) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c187f0abdc4b277a5f1428407b5c42ca4fd6fee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699327"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a><span data-ttu-id="9f9e7-102">Lektion 2: Angeben von Verbindungsinformationen (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="9f9e7-102">Lesson 2: Specifying Connection Information (Reporting Services)</span></span>
  <span data-ttu-id="9f9e7-103">Nachdem Sie dem Tutorial-Projekt einen Bericht hinzugefügt haben, müssen Sie eine *Datenquelle*erstellen. Bei dieser handelt es sich um Verbindungsinformationen, mit denen der Bericht auf Daten aus einer relationalen Datenbank, einer mehrdimensionalen Datenbank oder einer sonstigen Ressource zugreift.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-103">After you add a report to the Tutorial project, you need to define a *data source*, which is connection information the report uses to access data from either a relational database, multidimensional database, or other resource.</span></span>  
  
 <span data-ttu-id="9f9e7-104">In dieser Lektion verwenden Sie die Beispieldatenbank [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] als Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-104">In this lesson, you will use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database as your data source.</span></span> <span data-ttu-id="9f9e7-105">In diesem Tutorial wird davon ausgegangen, dass sich diese Datenbank in einer Standard Instanz von befindet [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] , die auf dem lokalen Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-105">This tutorial assumes that this database is located in a default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed on your local computer.</span></span>  
  
### <a name="to-set-up-a-connection"></a><span data-ttu-id="9f9e7-106">So richten Sie eine Verbindung ein</span><span class="sxs-lookup"><span data-stu-id="9f9e7-106">To set up a connection</span></span>  
  
1.  <span data-ttu-id="9f9e7-107">Klicken Sie im **Berichtsdaten** Bereich auf **neu** , und klicken Sie dann auf **Datenquelle...**.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-107">In the **Report Data** pane, click **New** and then click **Data Source...**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9f9e7-108">Zum Anzeigen des **Berichtsdatenbereichs** klicken Sie im Menü **Ansicht** auf **Berichtsdaten**.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-108">If the **Report Data** pane is not visible, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="9f9e7-109">Geben Sie in **Name**den Namen [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)]ein.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-109">In **Name**, type [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span></span>  
  
3.  <span data-ttu-id="9f9e7-110">Stellen Sie sicher, dass **Eingebettete Verbindung** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-110">Make sure **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="9f9e7-111">Wählen Sie unter **Typ**die Option **Microsoft SQL Server**aus.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-111">In **Type**, select **Microsoft SQL Server**.</span></span>  
  
5.  <span data-ttu-id="9f9e7-112">Geben Sie für **Verbindungszeichenfolge**Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9f9e7-112">In **Connection string**, type the following:</span></span>  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     <span data-ttu-id="9f9e7-113">Bei dieser Verbindungszeichenfolge wird davon ausgegangen, dass [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], der Berichtsserver und die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank zusammen auf dem lokalen Computer installiert sind und Sie über die Berechtigung verfügen, sich bei der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank anzumelden.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-113">This connection string assumes that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the report server, and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database are all installed on the local computer and that you have permission to log on to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9f9e7-114">Wenn Sie [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services oder eine benannte Instanz verwenden, muss die Verbindungszeichenfolge Instanzinformationen einschließen:</span><span class="sxs-lookup"><span data-stu-id="9f9e7-114">If you are using [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services or a named instance, the connection string must include instance information:</span></span>  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  <span data-ttu-id="9f9e7-115">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Datenverbindungen, Datenquellen und Verbindungs](data-connections-data-sources-and-connection-strings-in-reporting-services.md) Zeichenfolgen in Reporting Services und [Dialog Feld "Datenquellen Eigenschaften", "Allgemein](data-source-properties-dialog-box-general.md)".</span><span class="sxs-lookup"><span data-stu-id="9f9e7-115">For more information about connection strings, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) and [Data Source Properties Dialog Box, General](data-source-properties-dialog-box-general.md).</span></span>  
  
6.  <span data-ttu-id="9f9e7-116">Klicken Sie im linken Bereich auf **Anmeldeinformationen** , und klicken Sie auf **Windows-Authentifizierung verwenden (integrierte Sicherheit)**.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-116">Click **Credentials** in the left pane and click **Use Windows Authentication (integrated security)**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="9f9e7-117">die Datenquelle [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] wird dem **Berichtsdaten** Bereich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-117">data source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] is added to the **Report Data** pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="9f9e7-118">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="9f9e7-118">Next Task</span></span>  
 <span data-ttu-id="9f9e7-119">Sie haben erfolgreich eine Verbindung mit der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Beispieldatenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-119">You have successfully defined a connection to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="9f9e7-120">Als Nächstes erstellen Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="9f9e7-120">Next, you will create the report.</span></span> <span data-ttu-id="9f9e7-121">Weitere Informationen finden Sie unter [Lektion 3: Definieren eines Datasets für den Tabellenbericht (Reporting Services)](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f9e7-121">See [Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9e7-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f9e7-122">See Also</span></span>  
 [<span data-ttu-id="9f9e7-123">Datenverbindungen, Datenquellen und Verbindungszeichenfolgen in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f9e7-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
