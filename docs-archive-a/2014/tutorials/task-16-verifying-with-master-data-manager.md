---
title: 'Aufgabe 16: Überprüfen mit Master Data Manager | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 57ad9d3e-8f95-4df6-af01-c291ccf49164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d1649582f97e9e08691726745e4ba14b2f8226bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700509"
---
# <a name="task-16-verifying-with-master-data-manager"></a><span data-ttu-id="c7579-102">Aufgabe 16: Überprüfung mit dem Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="c7579-102">Task 16: Verifying with Master Data Manager</span></span>
  <span data-ttu-id="c7579-103">In dieser Aufgabe prüfen Sie den Status des vom SSIS-Paket gesendeten Batchauftrags und verifizieren, ob die Daten mit Master Data Manager auf den MDS-Server hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="c7579-103">In this task, you check the status of the batch job submitted by the SSIS package and verify that the data was uploaded to MDS server by using Master Data Manager.</span></span>  
  
1.  <span data-ttu-id="c7579-104">Starten Sie **Master Data Manager** ( `http://localhost/MDS` ).</span><span class="sxs-lookup"><span data-stu-id="c7579-104">Launch **Master Data Manager** (`http://localhost/MDS`).</span></span> <span data-ttu-id="c7579-105">Wenn Sie bereits geöffnet ist, klicken Sie oben auf **Microsoft SQL Server Master Data Services** , um zur **Startseite**zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="c7579-105">If it is already open, click **Microsoft SQL Server Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="c7579-106">Klicken Sie auf **Integrations Management**.</span><span class="sxs-lookup"><span data-stu-id="c7579-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="c7579-107">Beachten Sie, dass es einen Batch mit dem Namen **eimbatch** gibt, den Sie in der Liste übermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="c7579-107">Notice that there is a batch with named **EIMBatch** that you submitted in the list.</span></span> <span data-ttu-id="c7579-108">Klicken Sie in der Menüleiste auf **Daten importieren** , wenn der folgende Bildschirm nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7579-108">Click **Import Data** on the menu bar if you do not see the following screen.</span></span>  
  
     <span data-ttu-id="c7579-109">![EIM-Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM-Batch")</span><span class="sxs-lookup"><span data-stu-id="c7579-109">![EIM Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM Batch")</span></span>  
  
4.  <span data-ttu-id="c7579-110">Wechseln Sie zurück zur Startseite, indem Sie oben auf **SQL Server 2012 Master Data Services** klicken.</span><span class="sxs-lookup"><span data-stu-id="c7579-110">Switch back to the home page by click **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
5.  <span data-ttu-id="c7579-111">Stellen Sie sicher, dass das Modell **Suppliers** als **Modell** ausgewählt ist und **VERSION_1** für die **Version**ausgewählt ist, und klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c7579-111">Make sure that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**, and click **Explorer**.</span></span>  
  
6.  <span data-ttu-id="c7579-112">Sie können das in MDS importierte Daten-SSIS-Paket anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7579-112">You can see the data SSIS package imported into MDS.</span></span> <span data-ttu-id="c7579-113">Die Daten sollten bereinigt werden und keine doppelten **Code** Werte aufweisen (Hinweis: die **SupplierID-** Spalte in Excel entspricht dem **Code** -Attribut der Lieferanten Entität in MDS).</span><span class="sxs-lookup"><span data-stu-id="c7579-113">The data should be cleansed and have no duplicates **Code** values (Note: **SupplierID** column in Excel corresponds to **Code** attribute of Supplier entity in MDS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c7579-114">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c7579-114">Next Step</span></span>  
 [<span data-ttu-id="c7579-115">Aufgabe 17: Überprüfung des vom SSIS-Paket erstellten DQS-Bereinigungsprojekts</span><span class="sxs-lookup"><span data-stu-id="c7579-115">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>](../../2014/tutorials/task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package.md)  
  
  
