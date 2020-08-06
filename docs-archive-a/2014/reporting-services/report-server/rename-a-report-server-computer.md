---
title: Umbenennen eines Berichtsservercomputers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- renaming report servers
ms.assetid: 82fc4ba2-291a-4939-a025-271b8d687c54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe8f699c17f9e5f1e11406ac6e5c161488767ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622432"
---
# <a name="rename-a-report-server-computer"></a><span data-ttu-id="e57fd-102">Umbenennen eines Berichtsservercomputers</span><span class="sxs-lookup"><span data-stu-id="e57fd-102">Rename a Report Server Computer</span></span>
  <span data-ttu-id="e57fd-103">Durch das Umbenennen eines Computers wird eine entsprechende Namensänderung für den Webserver und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz verursacht (falls sie auf demselben Computer installiert ist).</span><span class="sxs-lookup"><span data-stu-id="e57fd-103">Renaming a computer causes a corresponding name change for the Web server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (if it is on the same computer).</span></span> <span data-ttu-id="e57fd-104">In einigen Fällen kann nach einer Computernamensänderung möglicherweise nicht mehr auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e57fd-104">In some cases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] may not be accessible after a computer name change.</span></span> <span data-ttu-id="e57fd-105">Führen Sie die Schritte in diesem Thema aus, um einen Berichtsserver nach einer Änderung des Computernamens neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e57fd-105">Use the steps provided in this topic to reconfigure a report server after a computer name change.</span></span>  
  
## <a name="renaming-a-sql-server-database-engine"></a><span data-ttu-id="e57fd-106">Umbenennen einer SQL Server-Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="e57fd-106">Renaming a SQL Server Database Engine</span></span>  
 <span data-ttu-id="e57fd-107">Führen Sie die folgenden Aktionen aus, wenn Sie die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz umbenannt haben, in der die Berichtsserver-Datenbank ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="e57fd-107">If you rename the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance that runs the report server database, do the following:</span></span>  
  
1.  <span data-ttu-id="e57fd-108">Starten Sie das Reporting Services-Konfigurationstool, und stellen Sie eine Verbindung mit dem Berichtsserver her, der die Berichtsserver-Datenbank auf dem umbenannten Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="e57fd-108">Start the Reporting Services Configuration tool and connect to the report server that uses the report server database on the renamed server.</span></span>  
  
2.  <span data-ttu-id="e57fd-109">Öffnen Sie die Seite Setup der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e57fd-109">Open the Database Setup page.</span></span>  
  
3.  <span data-ttu-id="e57fd-110">Geben Sie unter **Servername**den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Namen ein, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="e57fd-110">In **Server Name**, type or select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="e57fd-111">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="e57fd-111">Click **Apply**.</span></span>  
  
 <span data-ttu-id="e57fd-112">Falls der Berichtsserver eine lokale [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz verwendet, können Sie den Server mit *(local)* oder *(local)\instancename* angeben.</span><span class="sxs-lookup"><span data-stu-id="e57fd-112">If the report server is using a local [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, you can use *(local)* or *(local)\instancename* to specify the server.</span></span> <span data-ttu-id="e57fd-113">Wenn Sie mit *(local)* auf den Server verweisen, sind die Verbindungen mit dem Server auch nach einer Umbenennung des Servers weiterhin funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="e57fd-113">If you use *(local)* to refer to the server, you can rename the server and the connections will continue to work.</span></span> <span data-ttu-id="e57fd-114">Wenn Sie einen Remoteserver verwenden oder wenn [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] mithilfe des Servernamens konfiguriert ist, müssen Sie die Datenbank-Verbindungsinformationen bei jeder Änderung des Servernamens aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e57fd-114">If you are using a remote server, or if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is configured using the server name, you must update the database connection information whenever the server name is changed.</span></span>  
  
## <a name="renaming-a-report-server-computer"></a><span data-ttu-id="e57fd-115">Umbenennen eines Berichtsservercomputers</span><span class="sxs-lookup"><span data-stu-id="e57fd-115">Renaming a Report Server Computer</span></span>  
 <span data-ttu-id="e57fd-116">Führen Sie die folgenden Aktionen aus, wenn Sie einen Computer umbenannt haben, auf dem ein Berichtsserver ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="e57fd-116">If you rename a computer that runs a report server, do the following:</span></span>  
  
1.  <span data-ttu-id="e57fd-117">Öffnen Sie **RSReportServer.config** in einem Text-Editor, und ändern `UrlRoot` Sie die Einstellung, um den neuen Servernamen widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="e57fd-117">Open **RSReportServer.config** in a text editor and modify the `UrlRoot` setting to reflect the new server name.</span></span> <span data-ttu-id="e57fd-118">Die `UrlRoot`-Einstellung wird von Übermittlungserweiterungen zum Angeben der URL für den Zugriff auf Elemente verwendet, die auf dem Berichtsserver gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e57fd-118">The `UrlRoot` setting is used by delivery extensions to compose the URL used to access items stored on the report server.</span></span> <span data-ttu-id="e57fd-119">Wenn Sie die URL-Adresse des Berichtsservers ändern, müssen Sie die `UrlRoot`-Einstellung aktualisieren, damit Berichte weiterhin erwartungsgemäß von Abonnements übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="e57fd-119">Changing the report server URL address requires that you update the `UrlRoot` setting so that subscriptions continue to deliver reports as expected.</span></span>  
  
2.  <span data-ttu-id="e57fd-120">Ändern Sie in der gleichen Datei ggf. die `ReportServerUrl`-Einstellung so, dass sie den neuen Servernamen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="e57fd-120">In the same file, if it is set, modify the `ReportServerUrl` setting to reflect the new server name.</span></span> <span data-ttu-id="e57fd-121">Beachten Sie, dass diese Einstellung nicht in jeder Installation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e57fd-121">Note that this setting is not used in every installation.</span></span> <span data-ttu-id="e57fd-122">Falls die Einstellung leer ist, brauchen Sie nichts zu tun.</span><span class="sxs-lookup"><span data-stu-id="e57fd-122">If it is empty, do nothing.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e57fd-123">Falls Sie WINS (Windows Internet Naming Service) im Unternehmensnetzwerk verwenden, sind der Berichtsserver und der Berichts-Manager möglicherweise noch eine Zeit lang unter dem vorherigen Namen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e57fd-123">If you are using Windows Internet Naming Service (WINS) on your corporate network, the report server and Report Manager may continue to be available under the previous name for a period of time.</span></span> <span data-ttu-id="e57fd-124">WINS ordnet jedem Computer, für den es einen Dienst bereitstellt, eine IP-Adresse zu.</span><span class="sxs-lookup"><span data-stu-id="e57fd-124">WINS maps an IP address to each computer it services.</span></span> <span data-ttu-id="e57fd-125">Nachdem die IP-Adresse für den umbenannten Computer von WINS aktualisiert wurde, kann über den alten Computernamen nicht mehr auf einen Berichtsserver oder auf den Berichts-Manager zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e57fd-125">After WINS refreshes the IP address for the renamed computer, the old computer name can no longer be used to access a report server or Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57fd-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e57fd-126">See Also</span></span>  
 <span data-ttu-id="e57fd-127">[RSReportServer-Konfigurationsdatei](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="e57fd-127">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="e57fd-128">[Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="e57fd-128">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="e57fd-129">[Reporting Services-Berichtsserver &#40;einheitlicher Modus&#41;](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="e57fd-129">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="e57fd-130">[Starten und Beenden des Berichtsserverdiensts](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="e57fd-130">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 [<span data-ttu-id="e57fd-131">rsconfig-Hilfsprogramm (SSRS)</span><span class="sxs-lookup"><span data-stu-id="e57fd-131">rsconfig Utility &#40;SSRS&#41;</span></span>](../tools/rsconfig-utility-ssrs.md)  
  
  
