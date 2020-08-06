---
title: Definieren einer Datenquelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5a3e83c9-8788-431e-85b0-a68c79377ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdf00b47360341e2b9a99654482d65be83b86503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608058"
---
# <a name="defining-a-data-source"></a><span data-ttu-id="61d4e-102">Definieren einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="61d4e-102">Defining a Data Source</span></span>
  <span data-ttu-id="61d4e-103">Nach dem Erstellen eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekts beginnen Sie im Allgemeinen die Arbeit an dem Projekt, indem Sie mindestens eine Datenquelle definieren, die vom Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="61d4e-103">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you generally start working with the project by defining one or more data sources that the project will use.</span></span> <span data-ttu-id="61d4e-104">Wenn Sie eine Datenquelle definieren, definieren Sie die Verbindungszeichenfolgeinformationen, die zum Verbinden der Datenquelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61d4e-104">When you define a data source, you are defining the connection string information that will be used to connect to the data source.</span></span> <span data-ttu-id="61d4e-105">Weitere Informationen finden Sie unter [Erstellen einer Datenquelle &#40;SSAS – mehrdimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="61d4e-105">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="61d4e-106">In der folgenden Aufgabe definieren Sie die AdventureWorksDWSQLServer2012-Beispieldatenbank als Datenquelle für das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Projekt.</span><span class="sxs-lookup"><span data-stu-id="61d4e-106">In the following task, you define the AdventureWorksDWSQLServer2012 sample database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="61d4e-107">Während sich diese Datenbank für die Zwecke dieses Lernprogramms auf Ihrem lokalen Computer befindet, werden Quelldatenbanken häufig auf mindestens einem Remotecomputer gehostet.</span><span class="sxs-lookup"><span data-stu-id="61d4e-107">While this database is located on your local computer for the purposes of this tutorial, source databases are frequently hosted on one or more remote computers.</span></span>  
  
### <a name="to-define-a-new-data-source"></a><span data-ttu-id="61d4e-108">So definieren Sie eine neue Datenquelle</span><span class="sxs-lookup"><span data-stu-id="61d4e-108">To define a new data source</span></span>  
  
1.  <span data-ttu-id="61d4e-109">Klicken Sie im Projektmappen-Explorer (auf der rechten Seite des Microsoft Visual Studio-Fensters) mit der rechten Maustaste auf **Datenquellen**und anschließend auf **Neue Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="61d4e-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Sources**, and then click **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="61d4e-110">Klicken Sie auf der Seite **Willkommen beim Datenquellen-Assistenten** des **Datenquellen-Assistenten**auf **Weiter** , um die Seite **Wählen Sie aus, wie die Verbindung definiert werden soll** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="61d4e-110">On the **Welcome to the Data Source Wizard** page of the **Data Source Wizard**, click **Next** to open the **Select how to define the connection** page.</span></span>  
  
3.  <span data-ttu-id="61d4e-111">Auf der Seite **Wählen Sie aus, wie die Verbindung definiert werden soll** können Sie eine Datenquelle basierend auf einer neuen Verbindung, basierend auf einer vorhandenen Verbindung oder basierend auf einem vorher definierten Datenquellenobjekt definieren.</span><span class="sxs-lookup"><span data-stu-id="61d4e-111">On the **Select how to define the connection** page, you can define a data source based on a new connection, based on an existing connection, or based on a previously defined data source object.</span></span> <span data-ttu-id="61d4e-112">Im Rahmen dieses Lernprogramms definieren Sie eine Datenquelle auf der Basis einer neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="61d4e-112">In this tutorial, you define a data source based on a new connection.</span></span> <span data-ttu-id="61d4e-113">Überprüfen Sie, ob die Option **Eine neue Datenquelle basierend auf einer vorhandenen oder neuen Verbindung erstellen** ausgewählt ist, und klicken Sie anschließend auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="61d4e-113">Verify that **Create a data source based on an existing or new connection** is selected, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="61d4e-114">Im Dialogfeld **Verbindungs-Manager** definieren Sie Verbindungseigenschaften für die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="61d4e-114">In the **Connection Manager** dialog box, you define connection properties for the data source.</span></span> <span data-ttu-id="61d4e-115">Überprüfen Sie im Listenfeld **Anbieter** , ob **Native OLE DB\SQL Server Native Client 11.0** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="61d4e-115">In the **Provider** list box, verify that **Native OLE DB\SQL Server Native Client 11.0** is selected.</span></span>  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="61d4e-116">unterstützt auch andere Anbieter, die in der **Anbieter** -Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="61d4e-116">also supports other providers, which are displayed in the **Provider** list.</span></span>  
  
5.  <span data-ttu-id="61d4e-117">Geben Sie im Textfeld **Server Name den Namen** ein `localhost` .</span><span class="sxs-lookup"><span data-stu-id="61d4e-117">In the **Server name** text box, type `localhost`.</span></span>  
  
     <span data-ttu-id="61d4e-118">Um eine Verbindung mit einer benannten Instanz auf Ihrem lokalen Computer herzustellen, geben Sie \*\*localhost \\<Instanzname \> \*\*ein.</span><span class="sxs-lookup"><span data-stu-id="61d4e-118">To connect to a named instance on your local computer, type **localhost\\<instance name\>**.</span></span> <span data-ttu-id="61d4e-119">Geben Sie den Computernamen oder die IP-Adresse ein, um eine Verbindung zu einem spezifischen Computer statt zum lokalen Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="61d4e-119">To connect to the specific computer instead of the local computer, type the computer name or IP address.</span></span>  
  
6.  <span data-ttu-id="61d4e-120">Überprüfen Sie, ob **Windows-Authentifizierung verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="61d4e-120">Verify that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="61d4e-121">Wählen Sie im Listenfeld **Datenbanknamen eingeben oder auswählen** den Eintrag **AdventureWorksDW2012**aus.</span><span class="sxs-lookup"><span data-stu-id="61d4e-121">In the **Select or enter a database name** list, select **AdventureWorksDW2012**.</span></span>  
  
7.  <span data-ttu-id="61d4e-122">Klicken Sie auf **Verbindung testen** , um die Verbindung zur Datenbank zu testen.</span><span class="sxs-lookup"><span data-stu-id="61d4e-122">Click **Test Connection** to test the connection to the database.</span></span>  
  
8.  <span data-ttu-id="61d4e-123">Klicken Sie auf **OK**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="61d4e-123">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="61d4e-124">Auf der Seite **Identitätswechselinformationen** des Assistenten definieren Sie die Sicherheitsinformationen für [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] zur Verbindungsherstellung mit der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="61d4e-124">On the **Impersonation Information** page of the wizard, you define the security credentials for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use to connect to the data source.</span></span> <span data-ttu-id="61d4e-125">Der Identitätswechsel wirkt sich auf das Windows-Konto aus, das zum Herstellen der Verbindung mit der Datenquelle verwendet wird, wenn die Windows-Authentifizierung ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="61d4e-125">Impersonation affects the Windows account used to connect to the data source when Windows Authentication is selected.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="61d4e-126">unterstützt keinen Identitätswechsel für die Verarbeitung von OLAP-Objekten.</span><span class="sxs-lookup"><span data-stu-id="61d4e-126">does not support impersonation for processing OLAP objects.</span></span> <span data-ttu-id="61d4e-127">Wählen Sie **Dienstkonto verwenden**aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="61d4e-127">Select **Use the service account**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="61d4e-128">Bestätigen Sie auf der Seite **Assistenten abschließen** den Standardnamen **Adventure Works DW 2012**, und klicken Sie anschließend auf **Fertig stellen** , um die neue Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61d4e-128">On the **Completing the Wizard** page, accept the default name, **Adventure Works DW 2012**, and then click **Finish** to create the new data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61d4e-129">Wenn Sie die Eigenschaften einer Datenquelle nach dem Erstellen ändern möchten, doppelklicken Sie im Ordner **Datenquellen** auf die Datenquelle, um die Eigenschaften der Datenquelle im **Datenquellen-Designer**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="61d4e-129">To modify the properties of the data source after it has been created, double-click the data source in the **Data Sources** folder to display the data source properties in **Data Source Designer**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="61d4e-130">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="61d4e-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="61d4e-131">Definieren einer Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="61d4e-131">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="61d4e-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61d4e-132">See Also</span></span>  
 [<span data-ttu-id="61d4e-133">Erstellen einer Datenquelle (SSAS: mehrdimensional)</span><span class="sxs-lookup"><span data-stu-id="61d4e-133">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  
  
