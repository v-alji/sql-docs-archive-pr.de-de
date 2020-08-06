---
title: 'Lektion 1: Erstellen des RDL-Schemas Visual Studio-Projekt | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a8411e3f0458ccda8c291d5c86a4467bb051a263
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694886"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a><span data-ttu-id="5157d-102">Lektion 1: Erstellen des RDL-Schemaprojekts in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5157d-102">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>
  <span data-ttu-id="5157d-103">In diesem Lernprogramm erstellen Sie eine einfache Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="5157d-103">For this tutorial, you will create a simple console application.</span></span> <span data-ttu-id="5157d-104">In diesem Tutorial wird davon ausgegangen, dass Sie in entwickeln [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5157d-104">This tutorial assumes you are developing in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5157d-105">Wenn Sie auf den Berichtsserver-Webdienst zugreifen, der in [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] mit Advanced Services ausgeführt wird, müssen Sie "_SQLExpress" an den "ReportServer"-Pfad anfügen.</span><span class="sxs-lookup"><span data-stu-id="5157d-105">When accessing the Report Server Web service running on [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, you must append "_SQLExpress" to the "ReportServer" path.</span></span> <span data-ttu-id="5157d-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5157d-106">For example:</span></span>  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a><span data-ttu-id="5157d-107">So erstellen Sie den Webdienstproxy</span><span class="sxs-lookup"><span data-stu-id="5157d-107">To create the web service proxy</span></span>  
  
1.  <span data-ttu-id="5157d-108">Wählen Sie im **Startmenü** **Alle Programme**und dann Microsoft Visual Studio aus, und klicken Sie dann auf **Visual Studio-Tools**und dann auf **Visual Studio 2010-Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="5157d-108">From the **Start** menu, select **All Programs**, then Microsoft Visual Studio, then **Visual Studio Tools**, and then **Visual Studio 2010 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="5157d-109">Führen Sie den folgenden Befehl im Eingabeaufforderungsfenster aus, wenn Sie C# verwenden:</span><span class="sxs-lookup"><span data-stu-id="5157d-109">In the command prompt window, run the following command if you are using C#:</span></span>  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="5157d-110">Wenn Sie Visual Basic verwenden, führen Sie dann den folgenden Befehl aus: ///</span><span class="sxs-lookup"><span data-stu-id="5157d-110">If you are using Visual Basic, then run the following command:</span></span>  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="5157d-111">Dieser Befehl generiert eine .cs oder eine .vb-Datei.</span><span class="sxs-lookup"><span data-stu-id="5157d-111">This command generates a .cs or .vb file.</span></span> <span data-ttu-id="5157d-112">Sie fügen diese Datei der Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="5157d-112">You will add this file to your application.</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="5157d-113">So erstellen Sie eine Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5157d-113">To create a console application</span></span>  
  
1.  <span data-ttu-id="5157d-114">Zeigen Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt** , um das Dialogfeld **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5157d-114">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="5157d-115">Klicken Sie im linken Bereich unter **installierte Vorlagen**entweder auf **Visual Basic** oder den **Visual c#** -Knoten, und wählen Sie eine Kategorie von Projekttypen aus der erweiterten Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5157d-115">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="5157d-116">Wählen Sie den Projekttyp **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="5157d-116">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="5157d-117">Geben Sie im Feld **Name** einen Namen für das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="5157d-117">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="5157d-118">Geben Sie den Namen ein `SampleRDLSchema` .</span><span class="sxs-lookup"><span data-stu-id="5157d-118">Type the name `SampleRDLSchema`.</span></span>  
  
5.  <span data-ttu-id="5157d-119">Geben Sie im Feld **Speicherort** den Pfad ein, in dem Sie das Projekt speichern möchten, oder klicken Sie auf **Durchsuchen** , um zum Ordner zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="5157d-119">In the **Location** box, type the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="5157d-120">Eine reduzierte Ansicht des Projekts wird in Projektmappen-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5157d-120">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
7.  <span data-ttu-id="5157d-121">Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5157d-121">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
8.  <span data-ttu-id="5157d-122">Navigieren Sie zum Speicherort der CS-oder VB-Datei, die Sie generiert haben, wählen Sie die Datei aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5157d-122">Navigate to the location for the .cs or .vb file you generated, then select the file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5157d-123">Damit der Webverweis funktionsfähig ist, muss auch dem <xref:System.Web.Services>-Namespace ein Verweis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5157d-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
9. <span data-ttu-id="5157d-124">Klicken Sie im Menü Projekt auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="5157d-124">On the Project menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="5157d-125">Wählen Sie im Dialogfeld **Verweis hinzufügen** auf der Registerkarte **.net** die Option **System. Web. Services**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5157d-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
     <span data-ttu-id="5157d-126">Weitere Informationen zum Herstellen einer Verbindung mit dem Report Server-Webdienst finden Sie unter [Building Applications using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="5157d-126">For more information about how to connect to the Report Server Web service, see [Building Applications Using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
10. <span data-ttu-id="5157d-127">Erweitern Sie den Projektknoten im Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="5157d-127">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="5157d-128">Sie werden feststellen, dass dem Projekt eine Codedatei mit dem Standardnamen Program.cs (bzw. Module1.vb für [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="5157d-128">You will see a code file with the default name of Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
11. <span data-ttu-id="5157d-129">Öffnen Sie die Datei Program.cs (Module1.vb für [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]), und ersetzen Sie den Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5157d-129">Open the Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) file and replace the code with the following:</span></span>  
  
     <span data-ttu-id="5157d-130">Mit dem folgenden Code werden die Methodenstubs bereitgestellt, die zum Implementieren der Funktionalität zum Laden, Aktualisieren und Speichern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5157d-130">The following code provides the method stubs we will use to implement the Load, Update and Save functionality.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="5157d-131">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="5157d-131">Next Lesson</span></span>  
 <span data-ttu-id="5157d-132">In der nächsten Lektion generieren Sie mithilfe des XML-Schemadefinitionstools (Xsd.exe) Klassen aus dem RDL-Schema und fügen diese in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="5157d-132">In the next lesson, you will use the XML Schema Definition Tool (Xsd.exe) to generate classes from the RDL schema and include them in your project.</span></span> <span data-ttu-id="5157d-133">Weitere [Informationen finden Sie unter Lektion 2: Generieren von Klassen aus dem RDL-Schema mithilfe des XSD-Tools](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5157d-133">See [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5157d-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5157d-134">See Also</span></span>  
 <span data-ttu-id="5157d-135">[Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema &#40;SSRS-Tutorial generiert wurden&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="5157d-135">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="5157d-136">Berichtsdefinitionssprache (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5157d-136">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
