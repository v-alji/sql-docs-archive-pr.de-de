---
title: Verwenden des URL-Zugriffs in einer Windows-Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8f8b901481b1d6fcc3cdd8626b43cd3a69174c1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719729"
---
# <a name="using-url-access-in-a-windows-application"></a><span data-ttu-id="9f0fb-102">Verwenden des URL-Zugriffs in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="9f0fb-102">Using URL Access in a Windows Application</span></span>
  <span data-ttu-id="9f0fb-103">Obwohl der URL-Zugriff auf einen Berichtsserver für eine Webumgebung optimiert ist, können Sie mit dem URL-Zugriff auch [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Berichte in eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anwendung integrieren.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-103">Although URL access to a report server is optimized for a Web environment, you can also use URL access to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] reports into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="9f0fb-104">Aber der URL-Zugriff, der auch Windows Forms umfasst, erfordert trotzdem die Verwendung der Webbrowsertechnologie.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-104">However, URL access that involves Windows Forms still requires that you use Web browser technology.</span></span> <span data-ttu-id="9f0fb-105">Sie können folgende Integrationsszenarien mit dem URL-Zugriff und Windows Forms verwenden:</span><span class="sxs-lookup"><span data-stu-id="9f0fb-105">You can use the following integration scenarios with URL access and Windows Forms:</span></span>  
  
-   <span data-ttu-id="9f0fb-106">Zeigen Sie einen Bericht in einer Windows Forms-Anwendung an, indem Sie einen Webbrowser programmgesteuert starten.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-106">Display a report from a Windows Form application by starting a Web browser programmatically.</span></span>  
  
-   <span data-ttu-id="9f0fb-107">Verwenden Sie das <xref:System.Windows.Forms.WebBrowser>-Steuerelement auf einer Windows Form, um einen Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-107">Use the <xref:System.Windows.Forms.WebBrowser> control on a Windows Form to display a report.</span></span>  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a><span data-ttu-id="9f0fb-108">Starten von Internet Explorer von einer Windows Form</span><span class="sxs-lookup"><span data-stu-id="9f0fb-108">Starting Internet Explorer from a Windows Form</span></span>  
 <span data-ttu-id="9f0fb-109">Sie können über die <xref:System.Diagnostics.Process>-Klasse auf einen Prozess zugreifen, der auf einem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-109">You can use the <xref:System.Diagnostics.Process> class to access a process that is running on a computer.</span></span> <span data-ttu-id="9f0fb-110">Die- <xref:System.Diagnostics.Process> Klasse ist ein nützliches [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Konstrukt zum Starten, beenden, Steuern und Überwachen von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-110">The <xref:System.Diagnostics.Process> class is a useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construct for starting, stopping, controlling, and monitoring applications.</span></span> <span data-ttu-id="9f0fb-111">Um einen bestimmten Bericht in der Berichtsserver-Datenbank anzuzeigen, können Sie den Prozess **IExplore** starten, indem Sie die URL an den Bericht übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-111">To view a specific report in your report server database, you can start the **IExplore** process, passing in the URL to the report.</span></span> <span data-ttu-id="9f0fb-112">Folgendes Codebeispiel kann verwendet werden, um [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer zu starten und eine spezielle URL zu übergeben, wenn ein Benutzer auf eine Schaltfläche in einer Windows Form klickt.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-112">The following code example can be used to start [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer and pass a specific report URL when the user clicks a button on a Windows Form.</span></span>  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a><span data-ttu-id="9f0fb-113">Integrieren eines Browsersteuerelements auf einer Windows Form</span><span class="sxs-lookup"><span data-stu-id="9f0fb-113">Embedding a Browser Control on a Windows Form</span></span>  
 <span data-ttu-id="9f0fb-114">Wenn Sie den Bericht nicht in einem externen Webbrowser anzeigen möchten, können Sie einen Webbrowser nahtlos als Teil der Windows Form integrieren, indem Sie das <xref:System.Windows.Forms.WebBrowser>-Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-114">If you do not want to view your report in an external Web browser, you can embed a Web browser seamlessly as part of your Windows Form using the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a><span data-ttu-id="9f0fb-115">So fügen Sie der Windows Form das Webbrowser-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="9f0fb-115">To add the WebBrowser control to your Windows Form</span></span>  
  
1.  <span data-ttu-id="9f0fb-116">Erstellen Sie entweder in oder in eine neue Windows-Anwendung [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f0fb-116">Create a new Windows application in either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
2.  <span data-ttu-id="9f0fb-117">Suchen Sie im Dialogfeld **Toolbox** das <xref:System.Windows.Forms.WebBrowser>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-117">Locate the <xref:System.Windows.Forms.WebBrowser> control in the **Toolbox** Dialog Box.</span></span>  
  
     <span data-ttu-id="9f0fb-118">Wenn **Toolbox** nicht sichtbar ist, können Sie darauf zugreifen, indem Sie im Menüelement **Ansicht** auf **Toolbox** klicken.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-118">If the **Toolbox** is not visible you can access it by clicking the **View** menu item and selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="9f0fb-119">Ziehen Sie das <xref:System.Windows.Forms.WebBrowser>-Steuerelement auf die Entwurfsoberfläche des Windows Form.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-119">Drag the <xref:System.Windows.Forms.WebBrowser>control onto the design surface of your Windows Form.</span></span>  
  
     <span data-ttu-id="9f0fb-120">Das als webBrowser1 bezeichnete <xref:System.Windows.Forms.WebBrowser>-Steuerelement wird zum Formular hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-120">The <xref:System.Windows.Forms.WebBrowser>control named webBrowser1 is added to the Form</span></span>  
  
 <span data-ttu-id="9f0fb-121">Sie leiten das <xref:System.Windows.Forms.WebBrowser>-Steuerelement an eine URL weiter, indem Sie seine **Navigate**-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-121">You direct the <xref:System.Windows.Forms.WebBrowser> control to a URL by calling its **Navigate** method.</span></span> <span data-ttu-id="9f0fb-122">Sie können dem <xref:System.Windows.Forms.WebBrowser>-Steuerelement zur Laufzeit eine bestimmte URL-Zugriffszeichenfolge zuordnen, wie in folgendem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f0fb-122">You can assign a specific URL access string to your <xref:System.Windows.Forms.WebBrowser> control at run time as shown in the following example.</span></span>  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f0fb-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f0fb-123">See Also</span></span>  
 <span data-ttu-id="9f0fb-124">[Integrieren von Reporting Services in Anwendungen](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="9f0fb-124">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="9f0fb-125">[Integrieren von Reporting Services mithilfe des URL-Zugriffs](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="9f0fb-125">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="9f0fb-126">[Integrieren von Reporting Services mithilfe von SOAP](integrating-reporting-services-using-soap.md) </span><span class="sxs-lookup"><span data-stu-id="9f0fb-126">[Integrating Reporting Services Using SOAP](integrating-reporting-services-using-soap.md) </span></span>  
 <span data-ttu-id="9f0fb-127">[Integrieren von Reporting Services mithilfe der Report Viewer-Steuerelemente](integrating-reporting-services-using-reportviewer-controls.md) </span><span class="sxs-lookup"><span data-stu-id="9f0fb-127">[Integrating Reporting Services Using the ReportViewer Controls](integrating-reporting-services-using-reportviewer-controls.md) </span></span>  
 [<span data-ttu-id="9f0fb-128">URL-Zugriff &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9f0fb-128">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
