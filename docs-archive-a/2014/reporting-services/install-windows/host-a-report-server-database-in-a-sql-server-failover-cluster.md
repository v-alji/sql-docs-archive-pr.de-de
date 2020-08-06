---
title: Hosten einer Berichtsserver-Datenbank in einem SQL Server-Failovercluster | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7bd5f019-2857-452f-a023-cc3b9e93aec4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 921ce03fd08e7820266b828d5848f64db1e257ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700839"
---
# <a name="host-a-report-server-database-in-a-sql-server-failover-cluster"></a><span data-ttu-id="4d82e-102">Hosten einer Berichtsserver-Datenbank in einem SQL Server-Failovercluster</span><span class="sxs-lookup"><span data-stu-id="4d82e-102">Host a Report Server Database in a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4d82e-103">unterstützt Failoverclustering, sodass Sie mehrere Datenträger für eine oder mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4d82e-103">provides failover clustering support so that you can use multiple disks for one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances.</span></span> <span data-ttu-id="4d82e-104">Failovercluster werden nur für die Berichtsserver-Datenbank unterstützt; Sie können den Berichtsserver-Dienst nicht als Teil eines Failoverclusters ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d82e-104">Failover clustering is supported only for the report server database; you cannot run the Report Server service as part of a failover cluster.</span></span>  
  
 <span data-ttu-id="4d82e-105">Damit eine Berichtsserver-Datenbank in einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster gehostet werden kann, muss der Cluster bereits installiert und konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="4d82e-105">To host a report server database on a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the cluster must already be installed and configured.</span></span> <span data-ttu-id="4d82e-106">Daraufhin können Sie den Failovercluster als Servernamen auswählen, wenn Sie die Berichtsserver-Datenbank auf der Seite Setup der Datenbank des [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstools erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d82e-106">You can then select the failover cluster as the server name when you create the report server database in the Database Setup page of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>  
  
 <span data-ttu-id="4d82e-107">Obwohl der Berichtsserver-Dienst nicht Bestandteil eines Failoverclusters sein kann, können Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] auf einem Computer installieren, auf dem ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4d82e-107">Although the Report Server service cannot participate in a failover cluster, you can install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] on a computer that has a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster installed.</span></span> <span data-ttu-id="4d82e-108">Der Berichtsserver wird unabhängig vom Failovercluster ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d82e-108">The report server runs independently of the failover cluster.</span></span> <span data-ttu-id="4d82e-109">Wenn Sie einen Berichtsserver auf einem Computer installieren, der Bestandteil einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failoverinstanz ist, müssen Sie den Failovercluster nicht für die Berichtsserver-Datenbank verwenden. Sie können eine andere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz zum Hosten der Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d82e-109">If you install a report server on a computer that is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover instance, you are not required to use the failover cluster for the report server database; you can use a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d82e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d82e-110">See Also</span></span>  
 <span data-ttu-id="4d82e-111">[Berichtsserver-Datenbank &#40;einheitlicher SSRS-Modus&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="4d82e-111">[Report Server Database &#40;SSRS Native Mode&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="4d82e-112">Erstellen einer Berichtsserver-Datenbank &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="4d82e-112">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
  
  
