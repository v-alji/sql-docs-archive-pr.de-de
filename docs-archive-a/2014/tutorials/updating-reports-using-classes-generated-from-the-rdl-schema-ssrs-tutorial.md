---
title: Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema generiert wurden (SSRS-Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609565"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a><span data-ttu-id="bf00a-102">Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema generiert wurden (SSRS-Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="bf00a-102">Updating Reports Using Classes Generated from the RDL Schema (SSRS Tutorial)</span></span>
  <span data-ttu-id="bf00a-103">In diesem Tutorial wird veranschaulicht, wie Sie mit dem XML Schema Definition-Tool (Xsd.exe) Klassen generieren, mit denen Sie Berichts Definitions Dateien (RDL-und RDLC-Dateien) mit der-Klasse serialisieren und deserialisieren können [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="bf00a-103">This tutorial illustrates how to use the XML Schema Definition Tool (Xsd.exe) to generate classes that allow you to serialize and deserialize report definition files (.rdl and .rdlc) with the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="bf00a-104">Lernziele</span><span class="sxs-lookup"><span data-stu-id="bf00a-104">What You Will Learn</span></span>  
 <span data-ttu-id="bf00a-105">Im Rahmen dieses Lernprogramms führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="bf00a-105">During the course of this tutorial, you will complete the following activities:</span></span>  
  
-   <span data-ttu-id="bf00a-106">Erstellen Sie eine Anwendung mithilfe der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Projektvorlage Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="bf00a-106">Create an application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="bf00a-107">Generieren von Klassen aus dem RDL-Schema (Report Definition Language) mit dem **XSD** -Tool.</span><span class="sxs-lookup"><span data-stu-id="bf00a-107">Generate classes from the Report Definition Language (RDL) schema using the **xsd** tool.</span></span>  
  
-   <span data-ttu-id="bf00a-108">Sie stellen eine Verbindung mit einem Berichtsserver her und rufen eine Berichtsdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="bf00a-108">Connect to a report server and retrieve a report definition.</span></span>  
  
-   <span data-ttu-id="bf00a-109">Sie schreiben Code zum Aktualisieren der Berichtsdefinitionsdatei.</span><span class="sxs-lookup"><span data-stu-id="bf00a-109">Write code to update the report definition file.</span></span>  
  
-   <span data-ttu-id="bf00a-110">Sie speichern die aktualisierte Berichtsdefinition wieder auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="bf00a-110">Save the updated report definition back to the report server.</span></span>  
  
-   <span data-ttu-id="bf00a-111">Sie führen die RDL-Schema-Anwendung (VB/C#) aus.</span><span class="sxs-lookup"><span data-stu-id="bf00a-111">Run the RDL Schema Application (VB/C#).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf00a-112">Bei Berichten ohne Beschreibung verursachen die in diesem Lernprogramm bereitgestellten Codebeispiele u. U. einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="bf00a-112">The code samples provided in this tutorial might fail for reports having no description.</span></span> <span data-ttu-id="bf00a-113">Dies liegt daran, dass für Berichte, für die keine Beschreibung angegeben wurde, keine Beschreibungseigenschaft vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bf00a-113">The failure is because the description property does not exist for the reports with description not specified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf00a-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bf00a-114">Requirements</span></span>  
 <span data-ttu-id="bf00a-115">Für die vollständige Bearbeitung des Lernprogramms benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bf00a-115">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="bf00a-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf00a-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="bf00a-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf00a-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="bf00a-118">Ausreichende Berechtigungen für den Zugriff auf Berichte sowie zum Veröffentlichen von Berichten für den Berichtsserver-Webdienst auf dem Computer, auf dem sich der Berichtsserver befindet.</span><span class="sxs-lookup"><span data-stu-id="bf00a-118">Sufficient permissions to be able to access and publish reports to the Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="bf00a-119">Eine Installation der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]-Beispieldatenbank auf einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz.</span><span class="sxs-lookup"><span data-stu-id="bf00a-119">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database installed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="bf00a-120">Einen auf Ihrem Berichtsserver installierten Bericht.</span><span class="sxs-lookup"><span data-stu-id="bf00a-120">A report installed on your report server.</span></span> <span data-ttu-id="bf00a-121">Für dieses Lernprogramm wird der Beispielbericht Company Sales 2012 verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf00a-121">This tutorial uses the sample report, Company Sales 2012.</span></span> <span data-ttu-id="bf00a-122">Weitere Informationen zu Beispiel Berichten finden Sie unter [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="bf00a-122">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf00a-123">Die Beispiele werden nicht automatisch beim Setup installiert. Sie können sie jedoch jederzeit installieren.</span><span class="sxs-lookup"><span data-stu-id="bf00a-123">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="bf00a-124">Weitere Informationen zu Beispielen finden Sie unter [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="bf00a-124">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="bf00a-125">**Geschätzte Zeit bis zum Abschluss des Tutorials:** 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="bf00a-125">**Estimated time to complete the tutorial:** 30 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="bf00a-126">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="bf00a-126">Tasks</span></span>  
 [<span data-ttu-id="bf00a-127">Lektion 1: Erstellen des RDL-Schemaprojekts in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf00a-127">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [<span data-ttu-id="bf00a-128">Lektion 2: Generieren von Klassen aus dem RDL-Schema mithilfe des XSD-Tools</span><span class="sxs-lookup"><span data-stu-id="bf00a-128">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [<span data-ttu-id="bf00a-129">Lektion 3: Laden einer Berichtsdefinition vom Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="bf00a-129">Lesson 3: Load a Report Definition from the Report Server</span></span>](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [<span data-ttu-id="bf00a-130">Lektion 4: Programmgesteuertes Update der Berichtsdefinition</span><span class="sxs-lookup"><span data-stu-id="bf00a-130">Lesson 4: Update the Report Definition Programmatically</span></span>](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [<span data-ttu-id="bf00a-131">Lektion 5: Veröffentlichen der Berichtsdefinition auf dem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="bf00a-131">Lesson 5: Publish the Report Definition to the Report Server</span></span>](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [<span data-ttu-id="bf00a-132">Lektion 6: Ausführen der RDL-Schema Anwendung &#40;VB-C&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="bf00a-132">Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;</span></span>](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf00a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf00a-133">See Also</span></span>  
 [<span data-ttu-id="bf00a-134">Berichtsdefinitionssprache (SSRS)</span><span class="sxs-lookup"><span data-stu-id="bf00a-134">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
