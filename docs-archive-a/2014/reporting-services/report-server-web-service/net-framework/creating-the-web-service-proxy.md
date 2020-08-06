---
title: Erstellen des Webdienstproxys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: b1217843-8d3d-49f3-a0d2-d35b0db5b2df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d080b96fa29e906c044561a684d58275af9f61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697498"
---
# <a name="creating-the-web-service-proxy"></a><span data-ttu-id="5b858-102">Erstellen des Webdienstproxys</span><span class="sxs-lookup"><span data-stu-id="5b858-102">Creating the Web Service Proxy</span></span>
  <span data-ttu-id="5b858-103">Ein Client und ein Webdienst können über SOAP-Nachrichten kommunizieren, die die Eingabe- und Ausgabeparameter als XML-Datei einkapseln.</span><span class="sxs-lookup"><span data-stu-id="5b858-103">A client and a Web service can communicate using SOAP messages, which encapsulate the input and output parameters as XML.</span></span> <span data-ttu-id="5b858-104">Eine Proxyklasse ordnet XML-Elementen Parameter zu und sendet dann die SOAP-Nachrichten über ein Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="5b858-104">A proxy class maps parameters to XML elements and then sends the SOAP messages over a network.</span></span> <span data-ttu-id="5b858-105">So sorgt die Proxyklasse dafür, dass Sie nicht auf der SOAP-Ebene mit dem Webdienst kommunizieren müssen. Außerdem können Sie die Webdienstmethoden in jeder Entwicklungsumgebung aufrufen, die SOAP- und Webdienstproxys unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b858-105">In this way, the proxy class frees you from having to communicate with the Web service at the SOAP level and allows you to invoke Web service methods in any development environment that supports SOAP and Web service proxies.</span></span>  
  
 <span data-ttu-id="5b858-106">Es gibt zwei Möglichkeiten, dem Entwicklungsprojekt mithilfe von eine Proxy Klasse hinzuzufügen [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] : mit dem WSDL-Tool in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] und durch Hinzufügen eines Webverweises in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b858-106">There are two ways to add a proxy class to your development project using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: with the WSDL tool in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], and by adding a Web reference in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="5b858-107">In den folgenden Abschnitten wird dieser Betreff detaillierter erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b858-107">The following sections discuss this subject in further detail.</span></span>  
  
## <a name="adding-the-proxy-using-the-wsdl-tool"></a><span data-ttu-id="5b858-108">Hinzufügen des Proxys über das WSDL-Tool</span><span class="sxs-lookup"><span data-stu-id="5b858-108">Adding the Proxy Using the WSDL Tool</span></span>  
 <span data-ttu-id="5b858-109">Das [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-SDK enthält das WSDL-Tool (Web Services Description Language, Wsdl.exe), mit dem Sie einen Webdienstproxy für die Verwendung in der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Entwicklungsumgebung generieren können.</span><span class="sxs-lookup"><span data-stu-id="5b858-109">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK includes the Web Services Description Language tool (Wsdl.exe), which enables you to generate a Web service proxy for use in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] development environment.</span></span> <span data-ttu-id="5b858-110">Die gängigste Art, einen Client Proxy in Sprachen zu erstellen, die Webdienste unterstützen (derzeit c# und [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ), ist die Verwendung des WSDL-Tools.</span><span class="sxs-lookup"><span data-stu-id="5b858-110">The most common way to create a client proxy in languages that support Web services (currently C# and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) is to use the WSDL tool.</span></span>  
  
 <span data-ttu-id="5b858-111">**Hinzufügen einer Proxyklasse zu Ihrem Projekt mithilfe von „Wsdl.exe“**</span><span class="sxs-lookup"><span data-stu-id="5b858-111">**To add a proxy class to your project using Wsdl.exe**</span></span>  
  
1.  <span data-ttu-id="5b858-112">Verwenden Sie Wsdl.exe über eine Eingabeaufforderung, um eine Proxyklasse zu erstellen, und geben Sie (mindestens) die URL zum Berichtsserver-Webdienst an</span><span class="sxs-lookup"><span data-stu-id="5b858-112">From a command prompt, use Wsdl.exe to create a proxy class, specifying (at a minimum) the URL to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="5b858-113">Beispielsweise gibt die folgende Anweisung der Eingabeaufforderung eine URL für den Verwaltungsendpunkt des Berichtsserver-Webdiensts an.</span><span class="sxs-lookup"><span data-stu-id="5b858-113">For example, the following command prompt statement specifies a URL for the management endpoint of the Report Server Web service:</span></span>  
  
    ```  
    wsdl /language:CS /n:"Microsoft.SqlServer.ReportingServices2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="5b858-114">Das WSDL-Tool akzeptiert zum Generieren eines Proxys mehrere Eingabeaufforderungsargumente.</span><span class="sxs-lookup"><span data-stu-id="5b858-114">The WSDL tool accepts a number of command-prompt arguments for generating a proxy.</span></span> <span data-ttu-id="5b858-115">Das vorhergehende Beispiel gibt die Sprache C# an, außerdem einen vorgeschlagenen Namespace für die Verwendung im Proxy (um Namenskonflikte zu verhindern, wenn Sie mehr als einen Webdienst-Endpunkt verwenden), und generiert eine C#-Datei mit dem Namen ReportingService2010.cs.</span><span class="sxs-lookup"><span data-stu-id="5b858-115">The preceding example specifies the language C#, a suggested namespace to use in the proxy (to prevent name collision if using more than one Web service endpoint), and generates a C# file called ReportingService2010.cs.</span></span> <span data-ttu-id="5b858-116">Wenn im Beispiel [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] angegeben worden wäre, wäre eine Proxydatei mit dem Namen ReportingService2010.vb generiert worden.</span><span class="sxs-lookup"><span data-stu-id="5b858-116">If the example had specified [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], the example would have generated a proxy file with the name ReportingService2010.vb.</span></span> <span data-ttu-id="5b858-117">Diese Datei wird in dem Verzeichnis erstellt, von dem Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="5b858-117">This file is created in the directory from which you run the command.</span></span>  
  
2.  <span data-ttu-id="5b858-118">Kompilieren Sie die Proxyklasse in eine Assemblydatei (mit der Erweiterung .dll), und verweisen Sie im Projekt darauf, oder fügen Sie die Klasse als Projektelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b858-118">Compile the proxy class into an assembly file (with the extension .dll) and reference it in your project, or add the class as a project item.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b858-119">Wenn Sie eine Proxyklasse manuell zum Projekt hinzufügen, müssen Sie einen Verweis zu System.Web.Services.dll hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5b858-119">When you add a proxy class to your project manually, you need to add a reference to System.Web.Services.dll.</span></span> <span data-ttu-id="5b858-120">Wenn Sie den Proxy mithilfe eines Webverweises in Visual Studio .NET hinzufügen, wird der Verweis automatisch für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="5b858-120">If you add the proxy using a Web reference in Visual Studio .NET, the reference is automatically created for you.</span></span> <span data-ttu-id="5b858-121">Weitere Informationen finden Sie später in diesem Kapitel unter "Hinzufügen eines Proxys mit einem Webverweis in Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="5b858-121">For more information, see "Adding the Proxy Using a Web Reference in Visual Studio" later in this topic.</span></span>  
  
     <span data-ttu-id="5b858-122">Nachdem Sie die Proxyklasse als Element zu Ihrem Projekt hinzugefügt haben, wird die zugehörige Datei im Projektmappen-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b858-122">After you add the proxy class as an item to your project, the associated file appears in Solution Explorer.</span></span>  
  
3.  <span data-ttu-id="5b858-123">Um den Dienst programmgesteuert aufzurufen, erstellen Sie eine Instanz der Proxyklasse.</span><span class="sxs-lookup"><span data-stu-id="5b858-123">To call the service programmatically, create an instance of the proxy class.</span></span>  
  
     <span data-ttu-id="5b858-124">Im folgenden Codebeispiel wird die Syntax zum Erstellen einer Instanz der <xref:ReportService2010.ReportingService2010>-Proxyklasse in einem Projekt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5b858-124">The following code example shows the syntax for creating an instance of the <xref:ReportService2010.ReportingService2010> proxy class in a project:</span></span>  
  
```vb  
Dim service As New ReportingService2010()  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
  
```  
  
 <span data-ttu-id="5b858-125">Weitere Informationen zum Tool Wsdl.exe, einschließlich der kompletten Syntax, finden Sie unter "Web Services Description Language Tool" in der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5b858-125">For more information about the Wsdl.exe tool, including its full syntax, see "Web Services Description Language Tool" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span> <span data-ttu-id="5b858-126">Eine vollständige Erläuterung zu Webdienstproxys finden Sie unter "Erstellen eines XML-Webdienstproxys" in der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5b858-126">For a full explanation of Web service proxies, see "Creating an XML Web Service Proxy" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="adding-the-proxy-using-a-web-reference-in-visual-studio"></a><span data-ttu-id="5b858-127">Hinzufügen eines Proxys mit einem Webverweis in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b858-127">Adding the Proxy Using a Web Reference in Visual Studio</span></span>  
 <span data-ttu-id="5b858-128">Über einen Webverweis kann ein Projekt einen oder mehrere Webdienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b858-128">A Web reference enables a project to consume one or more Web services.</span></span> [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] <span data-ttu-id="5b858-129">bietet Benutzern die Möglichkeit, Webdienstverweise mit einigen einfachen Schritten zu Projekten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5b858-129">enables users to add Web service references to projects by following a few simple steps.</span></span>  
  
 <span data-ttu-id="5b858-130">**Hinzufügen eines Webverweises zu einem Projekt**</span><span class="sxs-lookup"><span data-stu-id="5b858-130">**To add a Web reference to a project**</span></span>  
  
1.  <span data-ttu-id="5b858-131">Wählen Sie im **Projektmappen-Explorer** das Projekt aus, das den Webdienst beansprucht.</span><span class="sxs-lookup"><span data-stu-id="5b858-131">In **Solution Explorer**, select the project that will consume the Web service.</span></span>  
  
2.  <span data-ttu-id="5b858-132">Klicken Sie im Menü **Projekt** auf **Webverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5b858-132">On the **Project** menu, click **Add Web Reference**.</span></span>  
  
     <span data-ttu-id="5b858-133">Das Dialogfeld **Webverweis hinzufügen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5b858-133">The **Add Web Reference** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="5b858-134">Geben Sie im Feld **URL** den vollständigen Pfad zum Berichtsserver-Webdienst ein.</span><span class="sxs-lookup"><span data-stu-id="5b858-134">In the **URL** field, enter the complete path to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="5b858-135">Eine vereinfachte URL für den Berichtsausführungsendpunkt des Berichtsserver-Webdiensts kann folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="5b858-135">A simplified URL for the report execution endpoint of the Report Server Web service might look like this:</span></span>  
  
    ```  
    http://<Server Name>/reportserver/reportexecution2005.asmx  
    ```  
  
     <span data-ttu-id="5b858-136">Die URL enthält die Domäne, in der der Berichtsserver-Webdienst bereitgestellt wird, den Namen des Ordners, der den Dienst enthält, und den Namen der Ermittlungsdatei für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="5b858-136">The URL contains the domain in which the Report Server Web service is deployed, the name of the folder containing the service, and the name of the discovery file for the service.</span></span> <span data-ttu-id="5b858-137">Eine vollständige Beschreibung der verschiedenen URL-Elemente finden Sie unter [Accessing the SOAP API (Zugriff auf die SOAP-API)](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="5b858-137">For a complete description of the different URL elements, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
     <span data-ttu-id="5b858-138">Eine Beschreibung der vom Webdienst zur Verfügung gestellten Methoden und Eigenschaften befindet sich im Browserbereich auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="5b858-138">A description of the methods and properties provided by the Web service appears in the Browser pane on the left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b858-139">Weitere Informationen zu den zum Berichtsserver-Webdienst gehörigen Elementen finden Sie unter [Report Server Web Service Methods (Webdienstmethoden für Berichtsserver)](../methods/report-server-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5b858-139">For more information about the items associated with the Report Server Web service, see [Report Server Web Service Methods](../methods/report-server-web-service-methods.md).</span></span>  
  
4.  <span data-ttu-id="5b858-140">Überprüfen Sie, dass das Projekt den Berichtsserver-Webdienst verwenden kann und dass Sie über die entsprechende Zugriffsberechtigung für den Berichtsserver verfügen.</span><span class="sxs-lookup"><span data-stu-id="5b858-140">Verify that your project can use the Report Server Web service, and that you have appropriate permission to access the report server.</span></span>  
  
5.  <span data-ttu-id="5b858-141">Geben Sie im Feld **Webverweisname** einen Namen ein, der im Code für den programmgesteuerten Zugriff auf den Berichtsserver-Webdienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b858-141">In the **Web reference name** field, enter a name that you will use in your code to access the Report Server Web service programmatically.</span></span>  
  
6.  <span data-ttu-id="5b858-142">Klicken Sie auf die Schaltfläche **Verweis hinzufügen**, um in der Anwendung einen Verweis zum Webdienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b858-142">Select the **Add Reference** button to create a reference in your application to the Web service.</span></span>  
  
     <span data-ttu-id="5b858-143">Der neue Verweis wird im **Projektmappen-Explorer** unter dem Knoten für Webverweise für das aktive Projekt mit dem im Feld **Webverweisname** angegebenen Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b858-143">The new reference appears in **Solution Explorer** under the Web References node for the active project, named as specified in the **Web reference name** field.</span></span>  
  
7.  <span data-ttu-id="5b858-144">Im **Projektmappen-Explorer** öffnen Sie den Webverweisordner, damit Sie den Namespace für die Webverweisklassen angeben können, die für die Elemente im Projekt zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="5b858-144">In **Solution Explorer**, expand the Web References folder to note the namespace for the Web reference classes that are available to the items in your project.</span></span>  
  
     <span data-ttu-id="5b858-145">Nachdem Sie einen Webverweis zum Projekt hinzugefügt haben, werden die zugehörigen Dateien in einem Ordner im Webverweisordner des **Projektmappen-Explorers** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b858-145">After adding a Web reference to your project, the associated files are displayed in a folder within the Web References folder of **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="5b858-146">Nachdem Sie den Webverweis hinzugefügt haben, erstellen Sie mit folgender Syntax eine Instanz der Proxyklasse:</span><span class="sxs-lookup"><span data-stu-id="5b858-146">After you add the Web reference, use the following syntax to create an instance of the proxy class:</span></span>  
  
```vb  
Dim rs As New myNamespace.myReferenceName.ReportExecutionService()  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
myNamespace.myReferenceName.ReportExecutionService rs = new myNamespace.myReferenceName.ReportExecutionService();  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
```  
  
 <span data-ttu-id="5b858-147">Sie können dem Berichtsserver-Webdienstverweis auch eine **using**-Anweisung (in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] eine **Import**-Anweisung) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5b858-147">You can also add a **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) directive to the Report Server Web service reference.</span></span> <span data-ttu-id="5b858-148">Wenn Sie diese Direktive verwenden, müssen die Typen im Namespace nicht vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="5b858-148">If you use this directive, you do not need to fully qualify the types in the namespace.</span></span> <span data-ttu-id="5b858-149">Hierfür fügen Sie dieser Datei den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="5b858-149">To do this, add the following code to your file:</span></span>  
  
```vb  
Import myNamespace.myReferenceName  
```  
  
```csharp  
using myNamespace.myReferenceName;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b858-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b858-150">See Also</span></span>  
 <span data-ttu-id="5b858-151">[Berichtsserver-Webdienst](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="5b858-151">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="5b858-152">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="5b858-152">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="5b858-153">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5b858-153">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
