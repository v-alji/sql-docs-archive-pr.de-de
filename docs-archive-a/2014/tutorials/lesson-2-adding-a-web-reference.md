---
title: 'Lektion 2: Hinzufügen eines Webverweises | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2c2b8b8-6b13-45ca-ab3b-1582447b6807
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 02ca614cb042211ac468246c3003efaa5f2e8fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717113"
---
# <a name="lesson-2-adding-a-web-reference"></a><span data-ttu-id="36dd6-102">Lektion 2: Hinzufügen eines Webverweises</span><span class="sxs-lookup"><span data-stu-id="36dd6-102">Lesson 2: Adding a Web Reference</span></span>
  <span data-ttu-id="36dd6-103">Webdienstermittlung ist der Prozess, durch den ein Client einen Webdienst sucht und seine Dienstbeschreibung erhält.</span><span class="sxs-lookup"><span data-stu-id="36dd6-103">Web service discovery is the process by which a client locates a Web service and obtains its service description.</span></span> <span data-ttu-id="36dd6-104">Der Prozess der Webdienstermittlung in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] beinhaltet das Abfragen einer Website gemäß einem vorher festgelegten Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="36dd6-104">The process of Web service discovery in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] involves interrogating a Web site following a predetermined algorithm.</span></span> <span data-ttu-id="36dd6-105">Ziel des Prozesses ist es, die Dienstbeschreibung zu finden. Diese Beschreibung ist ein XML-Dokument, das WSDL (Web Services Description Language) verwendet.</span><span class="sxs-lookup"><span data-stu-id="36dd6-105">The goal of the process is to locate the service description, which is an XML document that uses the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="36dd6-106">Die Dienstbeschreibung gibt an, welche Dienste verfügbar sind und wie mit diesen Diensten interagiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="36dd6-106">The service description describes what services are available and how to interact with those services.</span></span> <span data-ttu-id="36dd6-107">Ohne eine Dienstbeschreibung ist es nicht möglich, programmgesteuert mit einem Webdienst zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="36dd6-107">Without a service description, it is impossible to programmatically interact with a Web service.</span></span>  
  
 <span data-ttu-id="36dd6-108">Die Anwendung muss ein Kommunizieren mit dem Webdienst sowie eine Suche nach dem Webdienst zur Laufzeit ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="36dd6-108">Your application must have a means to communicate with the Web service and to locate it at run time.</span></span> <span data-ttu-id="36dd6-109">Das Hinzufügen eines Webverweises zum Projekt für den Webdienst generiert zu diesem Zweck eine Proxyklasse, die eine Schnittstelle mit dem Webdienst sowie eine lokale Darstellung des Webdiensts bietet.</span><span class="sxs-lookup"><span data-stu-id="36dd6-109">Adding a Web reference to your project for the Web service does this by generating a proxy class that interfaces with the Web service and provides a local representation of the Web service.</span></span> <span data-ttu-id="36dd6-110">Weitere Informationen finden Sie in der Vorgehensweise zum Generieren eines XML-Webdienstproxys in der Dokumentation zu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36dd6-110">For more information, see "How to: Generate an XML Web Service Proxy" in your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] documentation.</span></span>  
  
### <a name="to-add-a-web-reference"></a><span data-ttu-id="36dd6-111">So fügen Sie einen Webverweis hinzu</span><span class="sxs-lookup"><span data-stu-id="36dd6-111">To add a Web reference</span></span>  
  
1.  <span data-ttu-id="36dd6-112">Klicken Sie im Menü **Projekt** auf **Dienstverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="36dd6-112">On the **Project** menu, click **Add Service Reference**.</span></span>  
  
2.  <span data-ttu-id="36dd6-113">Klicken Sie im Dialogfeld **Dienstverweis hinzufügen** auf **erweitert**.</span><span class="sxs-lookup"><span data-stu-id="36dd6-113">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3.  <span data-ttu-id="36dd6-114">Klicken Sie im Dialogfeld **Dienst Verweis Einstellungen** auf **Webverweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="36dd6-114">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4.  <span data-ttu-id="36dd6-115">Geben Sie im Dialogfeld **Webverweis hinzufügen** im Feld **URL** die URL ein, um die Dienst Beschreibung des Report Server-Webdiensts zu erhalten, z http://localhost/reportserver/reportservice2010.asmx . b..</span><span class="sxs-lookup"><span data-stu-id="36dd6-115">In the **URL** box of the **Add Web Reference** dialog box, type the URL to obtain the service description of the Report Server Web service, such as http://localhost/reportserver/reportservice2010.asmx.</span></span> <span data-ttu-id="36dd6-116">Klicken Sie dann auf die Schaltfläche " **go** ", um Informationen zum Webdienst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="36dd6-116">Then click the **Go** button to retrieve information about the Web service.</span></span>  
  
     <span data-ttu-id="36dd6-117">\- oder -</span><span class="sxs-lookup"><span data-stu-id="36dd6-117">\- or -</span></span>  
  
     <span data-ttu-id="36dd6-118">Wenn der Report Server-Webdienst auf dem lokalen Computer vorhanden ist, klicken Sie im Browser **Bereich auf den Link Webdienste auf dem lokalen Computer** .</span><span class="sxs-lookup"><span data-stu-id="36dd6-118">If the Report Server Web service exists on the local machine, click the **Web services on the local machine** link in the browser pane.</span></span> <span data-ttu-id="36dd6-119">Klicken Sie dann in der angezeigten Liste auf den Link für den ReportService2010-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="36dd6-119">Then click the link for the ReportService2010 Web service from the list provided.</span></span>  
  
5.  <span data-ttu-id="36dd6-120">Benennen Sie im Feld **Webverweis Name** den Webverweis in ReportService2010 um. Dies ist der Namespace, den Sie für diesen Webverweis verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="36dd6-120">In the **Web reference name** box, rename the Web reference to ReportService2010, which is the namespace you will use for this Web reference.</span></span>  
  
6.  <span data-ttu-id="36dd6-121">Klicken Sie auf **Verweis hinzufügen** , um einen Webverweis für den Zielweb Dienst hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="36dd6-121">Click **Add Reference** to add a Web reference for the target Web service.</span></span>  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] <span data-ttu-id="36dd6-122">lädt die Dienstbeschreibung herunter und generiert eine Proxyklasse als Schnittstelle zwischen der Anwendung und dem Berichtsserver-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="36dd6-122">downloads the service description and generates a proxy class to interface between your application and the Report Server Web service.</span></span> <span data-ttu-id="36dd6-123">Damit der Webverweis funktionsfähig ist, muss auch dem <xref:System.Web.Services>-Namespace ein Verweis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="36dd6-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
7.  <span data-ttu-id="36dd6-124">Klicken Sie im Menü Projekt auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="36dd6-124">On the Project menu, click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="36dd6-125">Wählen Sie im Dialogfeld **Verweis hinzufügen** auf der Registerkarte **.net** die Option **System. Web. Services**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="36dd6-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
 <span data-ttu-id="36dd6-126">Weitere Informationen finden Sie unter [Accessing the SOAP API (Zugriff auf die SOAP-API)](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="36dd6-126">For more information, see [Accessing the SOAP API](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36dd6-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36dd6-127">See Also</span></span>  
 <span data-ttu-id="36dd6-128">[Berichtsserver-Webdienst](../reporting-services/report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="36dd6-128">[Report Server Web Service](../reporting-services/report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="36dd6-129">[Lektion 3: Zugreifen auf den Webdienst](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="36dd6-129">[Lesson 3: Accessing the Web Service](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span></span>  
 [<span data-ttu-id="36dd6-130">Zugreifen auf den Report Server-Webdienst mithilfe von Visual Basic oder Visual C&#35; &#40;SSRS-Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="36dd6-130">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
