---
title: Vollziehen des Austritts mehrerer Zielserver aus einem Masterserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
ms.openlocfilehash: b31a8bc38968733de0a23f67a71772721c8baedd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699224"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="24406-102">Defect Multiple Target Servers from a Master Server</span><span class="sxs-lookup"><span data-stu-id="24406-102">Defect Multiple Target Servers from a Master Server</span></span>
  <span data-ttu-id="24406-103">In diesem Thema wird beschrieben, wie Sie den Austritt mehrerer Zielserver aus einer Multiserver-Verwaltungskonfiguration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]vollziehen.</span><span class="sxs-lookup"><span data-stu-id="24406-103">This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="24406-104">Führen Sie die folgenden Schritte auf dem Masterserver aus.</span><span class="sxs-lookup"><span data-stu-id="24406-104">Run this procedure from the master server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="24406-105">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="24406-105">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="24406-106">So tragen Sie bei einem Masterserver mehrere Zielserver aus</span><span class="sxs-lookup"><span data-stu-id="24406-106">To defect multiple target servers from a master server</span></span>  
  
1.  <span data-ttu-id="24406-107">Erweitern Sie im **Objekt-Explorer**einen Server, der als Masterserver konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="24406-107">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="24406-108">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserververwaltung**, und klicken Sie dann auf **Zielserver verwalten**.</span><span class="sxs-lookup"><span data-stu-id="24406-108">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="24406-109">Klicken Sie auf **Anweisungen bereitstellen**, und klicken Sie in der Liste **Anweisungstyp** auf **Austragen**.</span><span class="sxs-lookup"><span data-stu-id="24406-109">Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.</span></span>  
  
4.  <span data-ttu-id="24406-110">Führen Sie unter **Empfänger**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="24406-110">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="24406-111">Klicken Sie auf **Alle Zielserver** , um alle Zielserver dieses Masterservers auszutragen.</span><span class="sxs-lookup"><span data-stu-id="24406-111">Click **All target servers** to defect all target servers of this master server.</span></span> <span data-ttu-id="24406-112">Verwenden Sie diese Option, wenn die aktuelle Multiserververwaltungskonfiguration vollständig deinstalliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="24406-112">Use this option if you want to completely uninstall the current multiserver administration configuration.</span></span>  
  
    -   <span data-ttu-id="24406-113">Klicken Sie auf **Diese Zielserver**, und klicken Sie dann auf das entsprechende Feld **Auswählen** , um einige, aber nicht alle Zielserver dieses Masterservers auszutragen.</span><span class="sxs-lookup"><span data-stu-id="24406-113">Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24406-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24406-114">See Also</span></span>  
 <span data-ttu-id="24406-115">[Erstellen einer Multiserverumgebung](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="24406-115">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="24406-116">[Automatisierte Verwaltung in einem Unternehmen](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="24406-116">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="24406-117">Vollziehen des Austritts eines Zielservers aus einem Masterserver</span><span class="sxs-lookup"><span data-stu-id="24406-117">Defect a Target Server from a Master Server</span></span>](defect-a-target-server-from-a-master-server.md)  
  
  
