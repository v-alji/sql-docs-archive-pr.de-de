---
title: Erstellen einer Datenquelle (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616288"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a><span data-ttu-id="9c5f5-102">Erstellen einer Datenquelle (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="9c5f5-102">Creating a Data Source (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="9c5f5-103">A *Datenquelle* ist eine Datenverbindung, die innerhalb Ihres Projekts gespeichert sowie verwaltet und für Ihre [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-103">A *data source* is a data connection that is saved and managed in your project and deployed to your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="9c5f5-104">Die Datenquelle umfasst neben anderen erforderlichen Verbindungseigenschaften den Servernamen und den Namen der Datenbank, auf dem sich Ihre Quelldaten befinden.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-104">The data source contains the names of the server and database where your source data resides, in addition to any other required connection properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c5f5-105">Der Name der Datenbank lautet [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c5f5-105">The name of the database is [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="9c5f5-106">Wenn Sie diese Datenbank nicht bereits installiert haben, finden Sie auf der Seite [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-106">If you have not already installed this database, see the [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) page.</span></span>  
  
### <a name="to-create-a-data-source"></a><span data-ttu-id="9c5f5-107">So erstellen Sie eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="9c5f5-107">To create a data source</span></span>  
  
1.  <span data-ttu-id="9c5f5-108">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Datenquellen** und wählen Sie **Neue Datenquelle**aus.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-108">In **Solution Explorer**, right-click the **Data Sources** folder and select **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="9c5f5-109">Klicken Sie auf der Seite **Willkommen** des Datenquellen-Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-109">On the **Welcome to the Data Source Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="9c5f5-110">Klicken Sie auf der Seite **Wählen Sie aus, wie die Verbindung definiert werden soll** auf **Neu** , um eine Verbindung zur [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] -Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-110">On the **Select how to define the connection** page, click **New** to add a connection to the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="9c5f5-111">Wählen Sie im **Verbindungs-Manager** in der Liste **Anbieter**die Option **Native OLE DB\SQL Server Native Client 11.0**aus.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-111">In the **Provider** list in **Connection Manager**, select **Native OLE DB\SQL Server Native Client 11.0**.</span></span>  
  
5.  <span data-ttu-id="9c5f5-112">Geben Sie im Feld **Servername** den Namen des Servers ein, auf dem [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)]installiert wurde, oder wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-112">In the **Server name** box, type or select the name of the server on which you installed [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span>  
  
     <span data-ttu-id="9c5f5-113">Geben Sie beispielsweise **localhost** ein,  wenn die Datenbank auf dem lokalen Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-113">For example, type **localhost** if the database is hosted on the local server.</span></span>  
  
6.  <span data-ttu-id="9c5f5-114">Wählen Sie in der Gruppe **Am Server anmelden** die Option **Windows-Authentifizierung verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-114">In the **Log onto the server** group, select **Use Windows Authentication**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9c5f5-115">Die Windows-Authentifizierung sollte wenn immer möglich verwendet werden, da hiermit eine größere Sicherheit als bei der SQL Server-Authentifizierung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-115">Whenever possible, implementers should use Windows Authentication, as it provides a more secure authentication method than SQL Server Authentication.</span></span> <span data-ttu-id="9c5f5-116">Die SQL Server-Authentifizierung wird aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-116">However, SQL Server Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="9c5f5-117">Weitere Informationen zu Authentifizierungsmethoden finden Sie unter [Datenbank-Engine Konfiguration-Konto Bereitstellung](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="9c5f5-117">For more information about authentication methods, see [Database Engine Configuration - Account Provisioning](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span></span>  
  
7.  <span data-ttu-id="9c5f5-118">Wählen Sie in der Liste **Datenbanknamen eingeben oder auswählen** den Eintrag [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-118">In the **Select or enter a database name** list, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="9c5f5-119">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-119">Click **Next**.</span></span>  
  
9. <span data-ttu-id="9c5f5-120">Klicken Sie auf der Seite **Identitätswechselinformationen** auf **Dienstkonto verwenden**und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-120">On the **Impersonation Information** page, click **Use the service account**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="9c5f5-121">Hinweis: Auf der Seite **Assistenten abschließen** wird standardmäßig Adventure Works DW 2012 als Name der Datenquelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-121">On the **Completing the Wizard** page, notice that, by default, the data source is named Adventure Works DW 2012.</span></span>  
  
10. <span data-ttu-id="9c5f5-122">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-122">Click **Finish**.</span></span>  
  
     <span data-ttu-id="9c5f5-123">Die neue Datenquelle **Adventure Works DW 2012** wird im Ordner Datenquellen im Projektmappen-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c5f5-123">The new data source, Adventure Works DW 2012, appears in the **Data Sources** folder in Solution Explorer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9c5f5-124">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="9c5f5-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9c5f5-125">Erstellen einer Datenquellen Sicht &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="9c5f5-125">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="9c5f5-126">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="9c5f5-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="9c5f5-127">Erstellen eines Analysis Services Projekts &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="9c5f5-127">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c5f5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c5f5-128">See Also</span></span>  
 <span data-ttu-id="9c5f5-129">[Erstellen einer Datenquelle &#40;mehrdimensionalen SSAS-&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="9c5f5-129">[Create a Data Source &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span></span>  
 <span data-ttu-id="9c5f5-130">[Definieren einer Datenquelle](../analysis-services/lesson-1-2-defining-a-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="9c5f5-130">[Defining a Data Source](../analysis-services/lesson-1-2-defining-a-data-source.md) </span></span>  
 [<span data-ttu-id="9c5f5-131">Festlegen von Identitätswechseloptionen &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="9c5f5-131">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
