---
title: Skripterstellung mit dem Hilfsprogramm „rs.exe“ und dem Webdienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Web service [Reporting Services], scripts
- rs utility
- XML Web service [Reporting Services], scripts
- Report Server Web service, scripts
- scripts [Reporting Services], Web service
ms.assetid: 0ec5ac6e-b3cf-49cd-96f6-6b4b7dc29982
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d84bb8722fd31a08ff7788ad31c601b377c23d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619017"
---
# <a name="script-with-the-rsexe-utility-and-the-web-service"></a><span data-ttu-id="dfeb7-102">Skripterstellung mit dem Hilfsprogramm rs.exe und dem Webdienst</span><span class="sxs-lookup"><span data-stu-id="dfeb7-102">Script with the rs.exe Utility and the Web Service</span></span>
  <span data-ttu-id="dfeb7-103">Entwickler und Berichtsserveradministratoren können auf einem Berichtsserver mithilfe des Hilfsprogramms **rs** (RS.exe) Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="dfeb7-103">Developers and report server administrators can perform operations on a report server through the use of the **rs** utility (RS.exe).</span></span> <span data-ttu-id="dfeb7-104">In diesem Hilfsprogramm können Sie mithilfe von mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] geschriebenen Skripts Berichtsserver programmgesteuert verwalten.</span><span class="sxs-lookup"><span data-stu-id="dfeb7-104">Using this utility, you can programmatically administer a report server using scripts written with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="dfeb7-105">-Skripts können alle Report Server-Webdienstvorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="dfeb7-105">scripts can be used to run any of the Report Server Web service operations.</span></span> <span data-ttu-id="dfeb7-106">Mithilfe von Skripts kann für mehrere Berichte auf einem Server die Sicherheit kopiert werden, zudem können Elemente hinzugefügt und gelöscht, Berichtsserverelemente von einem Server auf einen anderen kopiert werden usw.</span><span class="sxs-lookup"><span data-stu-id="dfeb7-106">Scripting can be used to copy security to multiple reports on a server, to add and delete items, to copy report server items from one server to another and more.</span></span> <span data-ttu-id="dfeb7-107">Weitere Informationen zur Skriptumgebung finden Sie unter [Ausführen einer Reporting Services-Skriptdatei](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="dfeb7-107">For more information about the scripting environment, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md).</span></span> <span data-ttu-id="dfeb7-108">Skriptdateien haben ein bestimmtes Format und werden in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dfeb7-108">Script files take a certain format and are written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span></span> <span data-ttu-id="dfeb7-109">Weitere Informationen finden Sie unter [Formatieren einer Reporting Services-Skriptdatei](format-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="dfeb7-109">For more information, see [Format a Reporting Services Script File](format-a-reporting-services-script-file.md).</span></span>  
  
 <span data-ttu-id="dfeb7-110">Skriptbeispiele finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="dfeb7-110">For script samples, see the following:</span></span>  
  
 <span data-ttu-id="dfeb7-111">[Beispiel Reporting Services rs.exe Skript zum Migrieren von Inhalten Zwischenberichts Servern](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="dfeb7-111">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="dfeb7-112">[SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="dfeb7-112">[SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfeb7-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfeb7-113">See Also</span></span>  
 <span data-ttu-id="dfeb7-114">[Skripts für Bereitstellungs- und Verwaltungsaufgaben](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="dfeb7-114">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="dfeb7-115">[Berichtsserver-Webdienst](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="dfeb7-115">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="dfeb7-116">[Technische Referenz (SSRS)](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dfeb7-116">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="dfeb7-117">Hilfsprogramm RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="dfeb7-117">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
