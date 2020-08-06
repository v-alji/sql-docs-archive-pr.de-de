---
title: Zugreifen auf den Report Server-Webdienst mithilfe von Visual Basic oder Visual c# (SSRS-Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- walkthroughs [Reporting Services]
- Reporting Services, Web service
- Web service [Reporting Services], tutorials
ms.assetid: cf688163-4ac0-475b-b6dd-6f2f05b553c6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3dc2599b4fafe682d74089d637918e04db9ed219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720563"
---
# <a name="accessing-the-report-server-web-service-using-visual-basic-or-visual-c-ssrs-tutorial"></a><span data-ttu-id="8809e-102">Zugreifen auf den Berichtsserver-Webdienst mithilfe von Visual Basic oder Visual C# (SSRS-Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="8809e-102">Accessing the Report Server Web Service Using Visual Basic or Visual C# (SSRS Tutorial)</span></span>
  <span data-ttu-id="8809e-103">Im folgenden Tutorial wird veranschaulicht, wie Sie über eine mit oder erstellte Anwendung auf den Report Server-Webdienst zugreifen [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8809e-103">The following tutorial shows you how to access the Report Server Web service from an application created with [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] or [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="8809e-104">Lernziele</span><span class="sxs-lookup"><span data-stu-id="8809e-104">What You Will Learn</span></span>  
 <span data-ttu-id="8809e-105">Im Rahmen dieses Lernprogramms führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="8809e-105">During the course of this tutorial, you will complete the following:</span></span>  
  
-   <span data-ttu-id="8809e-106">Erstellen Sie eine Client Anwendung mithilfe der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Projektvorlage für Konsolen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="8809e-106">Create a client application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="8809e-107">Hinzufügen eines Webverweises für den Berichtsserver-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="8809e-107">Add a Web reference for the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="8809e-108">Schreiben von Code für den Zugriff auf den Webdienst.</span><span class="sxs-lookup"><span data-stu-id="8809e-108">Write code to access the Web service.</span></span>  
  
-   <span data-ttu-id="8809e-109">Ausführen der Konsolenanwendung im Debugmodus.</span><span class="sxs-lookup"><span data-stu-id="8809e-109">Run the console application in debug mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8809e-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8809e-110">Requirements</span></span>  
 <span data-ttu-id="8809e-111">Für die vollständige Bearbeitung des Lernprogramms benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8809e-111">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="8809e-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8809e-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="8809e-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]oder ähnlich [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] -kompatibles Entwicklungs Tool.</span><span class="sxs-lookup"><span data-stu-id="8809e-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] or a similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-compatible development tool.</span></span>  
  
-   <span data-ttu-id="8809e-114">Ausreichende Berechtigungen für den Zugriff auf den Berichtsserver-Webdienst von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf dem Computer, auf dem sich der Berichtsserver befindet.</span><span class="sxs-lookup"><span data-stu-id="8809e-114">Sufficient permissions to be able to access the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="8809e-115">Einen auf Ihrem Berichtsserver installierten Bericht.</span><span class="sxs-lookup"><span data-stu-id="8809e-115">A report installed on your report server.</span></span> <span data-ttu-id="8809e-116">Für dieses Lernprogramm wird der Beispielbericht Company Sales verwendet.</span><span class="sxs-lookup"><span data-stu-id="8809e-116">This tutorial uses the sample report, Company Sales.</span></span> <span data-ttu-id="8809e-117">Weitere Informationen zu Beispiel Berichten finden Sie unter [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="8809e-117">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8809e-118">Die Beispiele werden nicht automatisch beim Setup installiert. Sie können sie jedoch jederzeit installieren.</span><span class="sxs-lookup"><span data-stu-id="8809e-118">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="8809e-119">Weitere Informationen zu Beispielen finden Sie unter [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="8809e-119">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="8809e-120">**Geschätzte Zeit bis zum Abschluss des Tutorials:** 60 Minuten</span><span class="sxs-lookup"><span data-stu-id="8809e-120">**Estimated time to complete the tutorial:** 60 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="8809e-121">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="8809e-121">Tasks</span></span>  
 [<span data-ttu-id="8809e-122">Lektion 1: Erstellen des Webdienst-Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="8809e-122">Lesson 1: Creating the Web Service Client Project</span></span>](../../2014/tutorials/lesson-1-creating-the-web-service-client-project.md)  
  
 [<span data-ttu-id="8809e-123">Lektion 2: Hinzufügen eines Webverweises</span><span class="sxs-lookup"><span data-stu-id="8809e-123">Lesson 2: Adding a Web Reference</span></span>](../../2014/tutorials/lesson-2-adding-a-web-reference.md)  
  
 [<span data-ttu-id="8809e-124">Lektion 3: Zugriff auf den Webdienst</span><span class="sxs-lookup"><span data-stu-id="8809e-124">Lesson 3: Accessing the Web Service</span></span>](../../2014/tutorials/lesson-3-accessing-the-web-service.md)  
  
 [<span data-ttu-id="8809e-125">Lektion 4: Ausführen der Anwendung &#40;VB-VC&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="8809e-125">Lesson 4: Running the Application &#40;VB-VC&#35;&#41;</span></span>](../../2014/tutorials/lesson-4-running-the-application-vb-vcsharp.md)  
  
  
