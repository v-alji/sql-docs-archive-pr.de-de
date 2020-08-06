---
title: Formatieren einer Reporting Services-Skriptdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c98a2f6561c3242fec34f7ca11c8304286ccebae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700725"
---
# <a name="format-a-reporting-services-script-file"></a><span data-ttu-id="b26af-102">Formatieren einer Reporting Services-Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="b26af-102">Format a Reporting Services Script File</span></span>
  <span data-ttu-id="b26af-103">Bei einem [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Skript handelt es sich um eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET-Codedatei, die für einen auf WSDL (Web Service Description Language) basierenden Proxy geschrieben wird und die Reporting Services-SOAP-API definiert.</span><span class="sxs-lookup"><span data-stu-id="b26af-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET code file, written against a proxy that is built on Web Service Description Language (WSDL), which defines the Reporting Services SOAP API.</span></span> <span data-ttu-id="b26af-104">Eine Skriptdatei wird als Unicode- oder UTF-8-Textdatei mit der Erweiterung RSS gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b26af-104">A script file is stored as a Unicode or UTF-8 text file with the extension .rss.</span></span>  
  
 <span data-ttu-id="b26af-105">Die Skriptdatei fungiert als [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Modul und kann benutzerdefinierte Prozeduren und Modulebenenvariablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b26af-105">The script file acts as a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] module and can contain user-defined procedures and module-level variables.</span></span> <span data-ttu-id="b26af-106">Damit die Skriptdatei erfolgreich ausgeführt werden kann, muss sie eine Main-Prozedur enthalten.</span><span class="sxs-lookup"><span data-stu-id="b26af-106">For the script file to run successfully, it must contain a Main procedure.</span></span> <span data-ttu-id="b26af-107">Die Main-Prozedur ist die erste Prozedur, auf die bei der Ausführung der Skriptdatei zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b26af-107">The Main procedure is the first procedure that is accessed when your script file runs.</span></span> <span data-ttu-id="b26af-108">In der Main-Prozedur können Sie Webdienstvorgänge hinzufügen und benutzerdefinierte Unterprozeduren ausführen.</span><span class="sxs-lookup"><span data-stu-id="b26af-108">Main is where you can add your Web service operations and run your user defined subprocedures.</span></span> <span data-ttu-id="b26af-109">Im folgenden Code wird eine Main-Prozedur erstellt:</span><span class="sxs-lookup"><span data-stu-id="b26af-109">The following code creates a Main procedure:</span></span>  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 <span data-ttu-id="b26af-110">Von der Skriptumgebung wird automatisch eine Verbindung mit dem Berichtsserver hergestellt, die Webproxyklasse erstellt und eine Verweisvariable (*rs*) für das Webdienstproxyobjekt generiert.</span><span class="sxs-lookup"><span data-stu-id="b26af-110">The script environment automatically connects to the report server, creates the Web proxy class, and generates a reference variable (*rs*) to the Web service proxy object.</span></span> <span data-ttu-id="b26af-111">In den einzelnen von Ihnen erstellten Anweisungen muss nur auf die *rs* -Modulebenenvariable verwiesen werden, um beliebige der in der Webdienstbibliothek verfügbaren Webdienstvorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b26af-111">Individual statements that you create need only refer to the *rs* module-level variable to perform any of the Web service operations that are available in the Web service library.</span></span> <span data-ttu-id="b26af-112">Mit dem folgenden [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Code wird die Webdienstmethode <xref:ReportService2010.ReportingService2010.ListChildren%2A> innerhalb einer Skriptdatei aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="b26af-112">The following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code calls the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method from within a script file:</span></span>  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b26af-113">Benutzeranmeldeinformationen werden von der Skriptumgebung verwaltet und durch Argumente für die Eingabeaufforderung mithilfe von RS.exe übergeben.</span><span class="sxs-lookup"><span data-stu-id="b26af-113">User credentials are managed by the script environment and passed through command prompt arguments through the use of RS.exe.</span></span> <span data-ttu-id="b26af-114">Sie können zwar die *rs* -Variable verwenden, um die Authentifizierung des Webdiensts festzulegen, allerdings wird die Verwendung der Skriptumgebung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b26af-114">Although you can use the *rs* variable to set the authentication of the Web service, it is recommended that you use the script environment.</span></span> <span data-ttu-id="b26af-115">Die Authentifizierung des Webdiensts in der Skriptdatei selbst ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b26af-115">You do not need to authenticate the Web service in the script file itself.</span></span> <span data-ttu-id="b26af-116">Weitere Informationen zum Authentifizieren der Skriptumgebung finden Sie unter [Hilfsprogramm RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b26af-116">For more information about authenticating the script environment, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span>  
  
 <span data-ttu-id="b26af-117">Es werden keine Namespaces innerhalb der Skriptdatei deklariert.</span><span class="sxs-lookup"><span data-stu-id="b26af-117">You do not declare namespaces within the script file.</span></span> <span data-ttu-id="b26af-118">Sie Skriptumgebung stellt Ihnen einige nützliche [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Namespaces zur Verfügung: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml** und **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="b26af-118">The scripting environment makes several useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.</span></span>  
  
 <span data-ttu-id="b26af-119">Skriptbeispiele finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="b26af-119">For script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26af-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b26af-120">See Also</span></span>  
 <span data-ttu-id="b26af-121">[Berichtsserver-Webdienst](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="b26af-121">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="b26af-122">[Technische Referenz (SSRS)](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b26af-122">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="b26af-123">Hilfsprogramm RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="b26af-123">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
