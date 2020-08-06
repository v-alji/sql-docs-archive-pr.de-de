---
title: Ändern des Proxy Kontos für den Hilfsprogramm-Sammlungs Satz auf einer verwaltete Instanz SQL Server (SQL Server-Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ff37ba8b-a08c-4109-b6e2-5748c995a52c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19f60c607ed661ef42c1c1c0e48854cdfd69a912
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609895"
---
# <a name="change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server-sql-server-utility"></a><span data-ttu-id="53303-102">Ändern des Proxykontos für den Hilfsprogramm-Sammlungssatz auf einer verwalteten Instanz von SQL Server (SQL Server-Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="53303-102">Change the Proxy Account for the Utility Collection Set on a Managed Instance of SQL Server (SQL Server Utility)</span></span>
  <span data-ttu-id="53303-103">In diesem Thema wird beschrieben, wie Sie das Proxykonto für den Hilfsprogramm-Sammlungssatz auf einer verwalteten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ändern können.</span><span class="sxs-lookup"><span data-stu-id="53303-103">This topic describes how to change the proxy account for the Utility Collection Set on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="53303-104">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="53303-104">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server"></a><span data-ttu-id="53303-105">So ändern Sie das Proxykonto für den Hilfsprogramm-Sammlungssatz auf einer verwalteten Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="53303-105">To change the proxy account for the utility collection set on a managed instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="53303-106">Entfernen Sie die verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="53303-106">Remove the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
    -   <span data-ttu-id="53303-107">Klicken Sie im **Hilfsprogramm-Explorer** in SSMS auf den Knoten **Verwaltete Instanzen** .</span><span class="sxs-lookup"><span data-stu-id="53303-107">In **Utility Explorer** in SSMS, click on the **Managed Instances** node.</span></span>  
  
    -   <span data-ttu-id="53303-108">Klicken Sie in der Listenansicht **Hilfsprogramm-Explorer** mit der rechten Maustaste auf den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanznamen, und wählen Sie **Verwaltete Instanz entfernen** aus. Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen einer Instanz von SQL Server aus dem SQL Server-Hilfsprogramm](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="53303-108">In the **Utility Explorer** list view, right-click the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name, and select **Remove Managed Instance...**. For more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
2.  <span data-ttu-id="53303-109">Registrieren Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erneut im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="53303-109">Enroll the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility again.</span></span>  
  
    -   <span data-ttu-id="53303-110">Klicken Sie im **Hilfsprogramm-Explorer** in SSMS mit der rechten Maustaste auf den Knoten **Verwaltete Instanzen**, und wählen Sie **Verwaltete Instanz hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="53303-110">In **Utility Explorer** in SSMS, right-click on the **Managed Instances** node, and select **Add Managed Instance...**.</span></span>  
  
    -   <span data-ttu-id="53303-111">Befolgen Sie die Eingabeaufforderungen zum Abschließen des Assistenten, indem Sie das neue Proxykonto angeben.</span><span class="sxs-lookup"><span data-stu-id="53303-111">Follow prompts to complete the wizard, specifying the new proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53303-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53303-112">See Also</span></span>  
 <span data-ttu-id="53303-113">[Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="53303-113">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="53303-114">Problembehandlung beim SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="53303-114">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
