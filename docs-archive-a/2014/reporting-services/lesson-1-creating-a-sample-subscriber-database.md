---
title: 'Lektion 1: Erstellen einer Beispiel-Abonnentendatenbank | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6ee49f0858b28c0c4b00fd391b0db7b4d2c54b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726590"
---
# <a name="lesson-1-creating-a-sample-subscriber-database"></a><span data-ttu-id="f35a7-102">Lektion 1: Erstellen einer Beispiel-Abonnentendatenbank</span><span class="sxs-lookup"><span data-stu-id="f35a7-102">Lesson 1: Creating a Sample Subscriber Database</span></span>
  <span data-ttu-id="f35a7-103">Ein datengesteuertes Abonnement können Sie nur dann definieren, wenn Sie über eine Datenquelle verfügen, die Abonnementdaten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f35a7-103">Before you can define a data-driven subscription, you must have a data source that provides subscription data.</span></span> <span data-ttu-id="f35a7-104">In diesem Schritt erstellen Sie eine kleine Datenbank zum Speichern der Abonnementdaten, die in diesem Lernprogramm verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f35a7-104">In this step, you will create a small database to store the subscription data used in this tutorial.</span></span> <span data-ttu-id="f35a7-105">Wenn dann später das Abonnement verarbeitet wird, werden diese Daten vom Berichtsserver abgerufen und verwendet, um die Berichtsausgabe, Übermittlungsoptionen und das Berichtspräsentationsformat benutzerspezifisch anzupassen.</span><span class="sxs-lookup"><span data-stu-id="f35a7-105">Later, when the subscription is processed, the report server retrieves this data and uses it to customize report output, delivery options, and report presentation format.</span></span>  
  
 <span data-ttu-id="f35a7-106">In dieser Lektion wird davon ausgegangen [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , dass Sie zum Erstellen einer [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="f35a7-106">This lesson assumes you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to create a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span>  
  
### <a name="to-create-a-sample-subscriber-database"></a><span data-ttu-id="f35a7-107">So erstellen Sie eine Beispiel-Abonnentendatenbank</span><span class="sxs-lookup"><span data-stu-id="f35a7-107">To create a sample Subscriber database</span></span>  
  
1.  <span data-ttu-id="f35a7-108">Starten Sie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], und stellen Sie eine Verbindung mit einer [!INCLUDE[ssDE](../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="f35a7-108">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and open a connection to a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f35a7-109">Klicken Sie mit der rechten Maustaste auf „Datenbanken“, und wählen Sie **Neue Datenbank...** aus.</span><span class="sxs-lookup"><span data-stu-id="f35a7-109">Right-click on Databases, select **New Database...**.</span></span>  
  
3.  <span data-ttu-id="f35a7-110">Geben Sie im Dialogfeld neue Datenbank unter Datenbankname die Bezeichnung *Abonnenten*ein.</span><span class="sxs-lookup"><span data-stu-id="f35a7-110">In the New Database dialog box, in Database Name, type *Subscribers*.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="f35a7-111">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="f35a7-111">Click the **New Query** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="f35a7-112">Kopieren Sie die folgenden [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen in die leere Abfrage:</span><span class="sxs-lookup"><span data-stu-id="f35a7-112">Copy the following [!INCLUDE[tsql](../includes/tsql-md.md)] statements into the empty query:</span></span>  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
6.  <span data-ttu-id="f35a7-113">Klicken Sie auf **! Ausführen** in der Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="f35a7-113">Click **! Execute** on the toolbar.</span></span>  
  
7.  <span data-ttu-id="f35a7-114">Verwenden Sie eine SELECT-Anweisung, um sicherzustellen, dass drei Datenzeilen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f35a7-114">Use a SELECT statement to verify that you have three rows of data.</span></span> <span data-ttu-id="f35a7-115">Beispiel: `select * from OrderInfo`</span><span class="sxs-lookup"><span data-stu-id="f35a7-115">For example: `select * from OrderInfo`</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f35a7-116">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f35a7-116">Next Steps</span></span>  
 <span data-ttu-id="f35a7-117">Sie haben erfolgreich die Abonnementdaten erstellt, welche die Berichtsverteilung steuern und über die die Berichtsausgabe für jeden Abonnenten angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="f35a7-117">You have successfully created the subscription data that will drive report distribution and vary the report output for each subscriber.</span></span> <span data-ttu-id="f35a7-118">Nun ändern Sie noch die Datenquelleneigenschaften des Berichts, den Sie an die Abonnenten verteilen.</span><span class="sxs-lookup"><span data-stu-id="f35a7-118">Next, you will modify the data source properties of the report you will distribute to subscribers.</span></span> <span data-ttu-id="f35a7-119">Die Datenquelleneigenschaften werden geändert, um den Bericht auf die Übermittlung als datengesteuertes Abonnement vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="f35a7-119">Modifying the data source properties is done to prepare the report for data-driven subscription delivery.</span></span> <span data-ttu-id="f35a7-120">Sie ändern auch den Berichtsentwurf, um einen Parameter einzuschließen, den das Abonnement mit den Abonnentendaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f35a7-120">You will also modify the report design to include a parameter that the subscription will use with the subscriber data.</span></span> <span data-ttu-id="f35a7-121">[Lektion 2: Ändern der Eigenschaften der Berichtsdaten Quelle](lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f35a7-121">[Lesson 2: Modifying the Report Data Source Properties](lesson-2-modifying-the-report-data-source-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f35a7-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f35a7-122">See Also</span></span>  
 <span data-ttu-id="f35a7-123">[Erstellen eines datengesteuerten Abonnements &#40;SSRS-Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f35a7-123">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="f35a7-124">[Erstellen einer Datenbank](../relational-databases/databases/create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="f35a7-124">[Create a Database](../relational-databases/databases/create-a-database.md) </span></span>  
 [<span data-ttu-id="f35a7-125">Erstellen eines einfachen Tabellenberichts &#40;SSRS-Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="f35a7-125">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
