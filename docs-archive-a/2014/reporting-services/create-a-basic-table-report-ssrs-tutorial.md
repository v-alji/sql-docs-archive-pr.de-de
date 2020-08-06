---
title: Erstellen eines einfachen Tabellenberichts (SSRS-Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [Reporting Services]
- tutorials [Reporting Services]
- reports [Reporting Services], creating
ms.assetid: 3b539b4b-26f2-4c0b-b506-80f175679a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e0f42869a3bfa88e0c6646fd447968c8ba3a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607547"
---
# <a name="create-a-basic-table-report-ssrs-tutorial"></a><span data-ttu-id="7106d-102">Erstellen eines einfachen Tabellenberichts (SSRS-Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="7106d-102">Create a Basic Table Report (SSRS Tutorial)</span></span>
  <span data-ttu-id="7106d-103">Dieses Tutorial hilft Ihnen, mit dem Berichts-Designer einen einfachen Tabellenbericht zu erstellen, der auf der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank basiert.</span><span class="sxs-lookup"><span data-stu-id="7106d-103">This tutorial is designed to help you create a basic table report based on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database using Report Designer.</span></span> <span data-ttu-id="7106d-104">Sie können die Berichte auch mithilfe des Berichts-Generators oder des Berichts-Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="7106d-104">You can also use Report Builder or the Report Wizard to create reports.</span></span> <span data-ttu-id="7106d-105">In diesem Lernprogramm erstellen Sie ein Berichtsprojekt, richten Verbindungsinformationen ein, definieren eine Abfrage, fügen einen Tabellendatenbereich hinzu und zeigen den Bericht in der Vorschau an.</span><span class="sxs-lookup"><span data-stu-id="7106d-105">In this tutorial, you will create a report project, set up connection information, define a query, add a Table data region, group and total some fields, and preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7106d-106">Zum Durcharbeiten dieses Lernprogramms müssen Sie [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] im einheitlichen Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="7106d-106">To complete this tutorial, you must be running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode.</span></span> <span data-ttu-id="7106d-107">Wenn Sie [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] im integrierten SharePoint-Modus verwenden, können die Schritte nicht ausgeführt werden, in denen Berichtsserver-URLs enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7106d-107">If you are running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint integrated mode, the steps that use report server URLs do not work.</span></span> <span data-ttu-id="7106d-108">Weitere Informationen zu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Modi finden Sie unter [Reporting Services-Berichts Server](reporting-services-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="7106d-108">For more information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, see [Reporting Services Report Server](reporting-services-report-server.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7106d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7106d-109">Requirements</span></span>  
 <span data-ttu-id="7106d-110">Auf Ihrem System müssen zum Verwenden dieses Lernprogramms folgende Anwendungen installiert sein:</span><span class="sxs-lookup"><span data-stu-id="7106d-110">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="7106d-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]Datenbank-Engine.</span><span class="sxs-lookup"><span data-stu-id="7106d-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database engine.</span></span>  
  
-   <span data-ttu-id="7106d-112">Die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7106d-112">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  <span data-ttu-id="7106d-113">Weitere Informationen finden Sie unter [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) ( https://go.microsoft.com/fwlink/?LinkId=245471). .</span><span class="sxs-lookup"><span data-stu-id="7106d-113">For more information, see [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) (https://go.microsoft.com/fwlink/?LinkId=245471)..</span></span> <span data-ttu-id="7106d-114">Weitere Informationen zur Unterstützung von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Beispiel Datenbanken und Beispielcode für [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] finden Sie unter [Übersicht über Datenbanken und Beispiele](https://go.microsoft.com/fwlink/?LinkId=110391) auf der CodePlex-Website.</span><span class="sxs-lookup"><span data-stu-id="7106d-114">For more information about support for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sample databases and sample code for [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], see [Databases and Samples Overview](https://go.microsoft.com/fwlink/?LinkId=110391) on the CodePlex Web site.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="7106d-115">.</span><span class="sxs-lookup"><span data-stu-id="7106d-115">.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="7106d-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7106d-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNote64Samp](../includes/ssnote64samp-md.md)]  
  
 <span data-ttu-id="7106d-117">Sie müssen auch über Leseberechtigung verfügen, um Daten aus der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="7106d-117">You must also have read-only permissions to retrieve data from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="7106d-118">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="7106d-118">Tasks</span></span>  
 [<span data-ttu-id="7106d-119">Lektion 1: Erstellen eines Berichtsserverprojekts &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7106d-119">Lesson 1: Creating a Report Server Project &#40;Reporting Services&#41;</span></span>](lesson-1-creating-a-report-server-project-reporting-services.md)  
  
 [<span data-ttu-id="7106d-120">Lektion 2: Angeben von Verbindungsinformationen &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7106d-120">Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;</span></span>](lesson-2-specifying-connection-information-reporting-services.md)  
  
 [<span data-ttu-id="7106d-121">Lektion 3: Definieren eines Datasets für den Tabellenbericht &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7106d-121">Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;</span></span>](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)  
  
 [<span data-ttu-id="7106d-122">Lektion 4: Hinzufügen einer Tabelle zum Bericht &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7106d-122">Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;</span></span>](lesson-4-adding-a-table-to-the-report-reporting-services.md)  
  
 [<span data-ttu-id="7106d-123">Lektion 5: Formatieren eines Berichts &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7106d-123">Lesson 5: Formatting a Report &#40;Reporting Services&#41;</span></span>](lesson-5-formatting-a-report-reporting-services.md)  
  
 [<span data-ttu-id="7106d-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7106d-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span></span>](lesson-6-adding-grouping-and-totals-reporting-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="7106d-125">Wenn Sie Tutorials überprüfen, empfiehlt es sich, der Symbolleiste in der Dokument Anzeige **die Schaltflächen** **weiter** und zurück hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7106d-125">When reviewing tutorials, we recommend that you add **Next** and **Previous** buttons to the document viewer toolbar.</span></span> <span data-ttu-id="7106d-126">Weitere Informationen finden Sie weiter oben unter</span><span class="sxs-lookup"><span data-stu-id="7106d-126">For more information, see.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7106d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7106d-127">See Also</span></span>  
 [<span data-ttu-id="7106d-128">Reporting Services-Tutorials (SSRS)</span><span class="sxs-lookup"><span data-stu-id="7106d-128">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](reporting-services-tutorials-ssrs.md)  
  
  
