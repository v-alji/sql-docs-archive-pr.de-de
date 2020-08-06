---
title: 'Lektion 2: Generieren von Klassen aus dem RDL-Schema mithilfe des XSD-Tools | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a81c87f1-7977-4b30-b6ac-b38b3e2b6398
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2c5db118ad8f94afc72cea44b9a2489f2b4fd7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719090"
---
# <a name="lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool"></a><span data-ttu-id="5b210-102">Lektion 2: Generieren von Klassen aus dem RDL-Schema mithilfe des XSD-Tools</span><span class="sxs-lookup"><span data-stu-id="5b210-102">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>
  <span data-ttu-id="5b210-103">Nachdem Sie das [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]-Projekt erstellt haben, rufen Sie eine lokale Kopie des Berichtsdefinitionsschemas ab, und führen Sie das XML-Schemadefinitionstool (Xsd.exe) aus.</span><span class="sxs-lookup"><span data-stu-id="5b210-103">After you have created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project, the next step is to retrieve a local copy of the report definition schema and run the XML Schema Definition Tool (Xsd.exe).</span></span>  
  
### <a name="to-generate-the-rdl-classes"></a><span data-ttu-id="5b210-104">So generieren Sie RDL-Klassen</span><span class="sxs-lookup"><span data-stu-id="5b210-104">To generate the RDL classes</span></span>  
  
1.  <span data-ttu-id="5b210-105">Öffnen Sie eine Instanz von [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (oder einen entsprechenden Webbrowser), und navigieren Sie zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="5b210-105">Open an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (or equivalent Web browser) and navigate to the following URL:</span></span>  
  
    ```  
    https://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition/ReportDefinition.xsd  
    ```  
  
2.  <span data-ttu-id="5b210-106">Nachdem das RDL-Schema im Browser geöffnet wurde, klicken Sie auf das Menü **Datei** , und wählen Sie **Speichern unter**aus.</span><span class="sxs-lookup"><span data-stu-id="5b210-106">Once the RDL schema has been opened in the browser, browse to the **File** menu, and select **Save As**.</span></span>  
  
3.  <span data-ttu-id="5b210-107">Navigieren Sie zu dem Speicherort, an dem Sie das [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] -Projekt erstellt haben, und speichern Sie das Schema unter dem Dateinamen ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="5b210-107">Browse to the location where you created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project and save the schema with the file name ReportDefinition.xsd.</span></span>  
  
4.  <span data-ttu-id="5b210-108">Nachdem die Datei gespeichert wurde, öffnen Sie eine Instanz der [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] -Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="5b210-108">After the file has been saved, open an instance of the [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] command prompt.</span></span> <span data-ttu-id="5b210-109">Zum Öffnen einer Instanz der Eingabeaufforderung klicken Sie auf das Startmenü, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft Visual Studio 2010**, zeigen Sie auf **Visual Studio-Tools** , und klicken Sie auf **Visual Studio-Eingabeaufforderung (2010)**.</span><span class="sxs-lookup"><span data-stu-id="5b210-109">To open an instance of the command prompt, click the Start menu, point to **All Programs**, point to **Microsoft Visual Studio 2010**, point to **Visual Studio Tools** and click **Visual Studio Command Prompt (2010)**.</span></span>  
  
5.  <span data-ttu-id="5b210-110">Ändern Sie den aktuellen Pfad in den Speicherort, an dem Sie die Datei ReportDefinition.xsd gespeichert haben:</span><span class="sxs-lookup"><span data-stu-id="5b210-110">Change the current path to the location where you saved the ReportDefinition.xsd file:</span></span>  
  
     `CD\<ReportDefinition.xsd Path>`  
  
6.  <span data-ttu-id="5b210-111">Generieren Sie mit dem folgenden Befehl die Datei ReportDefinition.cs, in der die Klassen für das RDL-Schema enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="5b210-111">Generate the ReportDefinition.cs file that contains the classes for the RDL schema with the following command:</span></span>  
  
     `xsd /c /n:SampleRDLSchema ReportDefinition.xsd`  
  
     <span data-ttu-id="5b210-112">Verwenden Sie zum Generieren der Datei ReportDefinition.vb folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="5b210-112">To generate a ReportDefinition.vb file use this command:</span></span>  
  
     `xsd /c /l:VB /n:SampleRDLSchema ReportDefinition.xsd`  
  
7.  <span data-ttu-id="5b210-113">Fügen Sie dem Projekt ReportDefinition.xsd hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b210-113">Add ReportDefinition.xsd your project.</span></span> <span data-ttu-id="5b210-114">Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5b210-114">From the **Project** menu, click **Add Existing Item**.</span></span> <span data-ttu-id="5b210-115">Navigieren Sie zum Speicherort der Datei ReportDefinition.xsd, wählen Sie ReportDefinition.xsd aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5b210-115">Browse to the location of the ReportDefinition.xsd file, select ReportDefinition.xsd, and click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b210-116">Nachdem Sie dem Projekt die Datei ReportDefinition. xsd hinzugefügt haben, werden Sie in **Projektmappen-Explorer** bemerken, dass die ReportDefinition.cs-Datei (. vb) nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5b210-116">After you have added the ReportDefinition.xsd file to the project you will notice in **Solution Explorer** that the ReportDefinition.cs (.vb) file is not there.</span></span> <span data-ttu-id="5b210-117">Um die Datei anzuzeigen, klicken Sie neben der Datei ReportDefinition.xsd auf die Schaltfläche zum Erweitern/Reduzieren.</span><span class="sxs-lookup"><span data-stu-id="5b210-117">To display the file, click the expand/collapse button next to the ReportDefinition.xsd file.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="5b210-118">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="5b210-118">Next Lesson</span></span>  
 <span data-ttu-id="5b210-119">In der nächsten Lektion schreiben Sie Code, um eine Berichtsdefinition mithilfe der aus dem RDL-Schema generierten Klassen von einem Berichtsserver zu laden.</span><span class="sxs-lookup"><span data-stu-id="5b210-119">In the next lesson, you will write code to load a report definition from a report server using the classes you generated from the RDL schema.</span></span> <span data-ttu-id="5b210-120">Siehe [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b210-120">See [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b210-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b210-121">See Also</span></span>  
 <span data-ttu-id="5b210-122">[Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema &#40;SSRS-Tutorial generiert wurden&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="5b210-122">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="5b210-123">Berichtsdefinitionssprache (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5b210-123">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
