---
title: Installieren von ADO.NET-Data Services zur Unterstützung von Datenfeed-Exporten von SharePoint-Listen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f32527ae-f623-4e08-adfb-6d3262f5c2ac
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fb47804daee38427f48baefdf3997edda5fb90b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615771"
---
# <a name="install-adonet-data-services-to-support-data-feed-exports-of-sharepoint-lists"></a><span data-ttu-id="50cec-102">Installieren von ADO.NET Data Services, um Datenfeedexporte von SharePoint-Listen zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="50cec-102">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>
  <span data-ttu-id="50cec-103">ADO.NET Data Services sind für einen Datenfeedexport von SharePoint-Listen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="50cec-103">ADO.NET Data Services is required for a data feed export of SharePoint lists.</span></span> <span data-ttu-id="50cec-104">Da diese Komponente nicht im SharePoint-Programm PrerequisiteInstaller von SharePoint 2010 enthalten ist, müssen Sie sie manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="50cec-104">SharePoint 2010 does not include this component in the SharePoint Prerequisite Installer program, so you must install it manually.</span></span>  
  
 <span data-ttu-id="50cec-105">Ohne diese Voraussetzung erhalten Sie den folgenden Fehler, wenn Sie versuchen, eine SharePoint-Liste zu verwenden, die als Datenfeed exportiert wurde: "DTD ist in diesem XML-dokument nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="50cec-105">Without this prerequisite, you will get the following error when you attempt to use a SharePoint list that was exported as a data feed: "For security reasons DTD is prohibited in this XML document.</span></span> <span data-ttu-id="50cec-106">Zum Aktivieren der DTD-Verarbeitung müssen Sie die 'ProhibitDtd'-Eigenschaft für 'XmlReaderSettings' auf 'Parse' festlegen und die Einstellungen an die 'XmlReader.Create'-Methode übergeben."</span><span class="sxs-lookup"><span data-stu-id="50cec-106">To enable DTD processing set the ProhibitDtd property on XmlReaderSettings to false and pass the settings into XmlReader.Create method."</span></span>  
  
 <span data-ttu-id="50cec-107">Verwenden Sie die folgenden Anweisungen, um ADO.NET Data Services auf jedem SharePoint-Server zu installieren, für den der Export von Listen als Datenfeeds zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="50cec-107">Use the following instructions to install ADO.NET Data Services on every SharePoint server for which you want to allow lists to be exported as data feeds.</span></span>  
  
### <a name="download-and-install-adonet-data-services"></a><span data-ttu-id="50cec-108">Herunterladen und Installieren von ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="50cec-108">Download and install ADO.NET Data Services</span></span>  
  
1.  <span data-ttu-id="50cec-109">Wechseln Sie zur Dokumentation zu Hardware-und Softwareanforderungen für SharePoint 2010-, [Hardware-und Softwareanforderungen (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="50cec-109">Go to the hardware and software requirements documentation for SharePoint 2010, [Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span></span>  
  
2.  <span data-ttu-id="50cec-110">Suchen Sie unter **Zugriff auf die entsprechende Software**den Link für ADO.NET Data Services 3,5, der dem verwendeten Betriebssystem entspricht (entweder Windows Server 2008 SP2 oder Windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="50cec-110">In **Access to applicable software**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using (either Windows Server 2008 SP2 or Windows Server 2008 R2).</span></span>  
  
3.  <span data-ttu-id="50cec-111">Klicken Sie auf den Link, und führen Sie das Setupprogramm aus, durch das der Dienst installiert wird.</span><span class="sxs-lookup"><span data-stu-id="50cec-111">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50cec-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50cec-112">See Also</span></span>  
 [<span data-ttu-id="50cec-113">PowerPivot für SharePoint 2010-Installation</span><span class="sxs-lookup"><span data-stu-id="50cec-113">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
