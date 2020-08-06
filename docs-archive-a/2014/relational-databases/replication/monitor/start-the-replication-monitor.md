---
title: Starten des Replikationsmonitors | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cff23206923825d0e86e47ad6921c19f45e68b35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725506"
---
# <a name="start-the-replication-monitor"></a><span data-ttu-id="9a5e0-102">Starten des Replikationsmonitors</span><span class="sxs-lookup"><span data-stu-id="9a5e0-102">Start the Replication Monitor</span></span>
  <span data-ttu-id="9a5e0-103">Der Replikationsmonitor kann von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] auf jeder Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]oder von der Eingabeaufforderung aus gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-103">Replication Monitor can be started from [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on any instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], or from the command prompt.</span></span> <span data-ttu-id="9a5e0-104">Nach dem Starten des Replikationsmonitors können Sie einen oder mehrere Verleger für die Überwachung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-104">After starting Replication Monitor, add one or more Publishers to monitor.</span></span> <span data-ttu-id="9a5e0-105">Weitere Informationen finden Sie unter [Hinzufügen und Entfernen von Verlegern vom Replikationsmonitor aus](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9a5e0-105">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a><span data-ttu-id="9a5e0-106">So starten Sie den Replikationsmonitor von SQL Server Management Studio aus</span><span class="sxs-lookup"><span data-stu-id="9a5e0-106">To start Replication Monitor from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9a5e0-107">Stellen Sie eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-107">Connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9a5e0-108">Klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** oder auf einen der Unterordner dieses Ordners, und klicken Sie dann auf **Replikationsmonitor starten**.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-108">Right-click the **Replication** folder or any of its subfolders, and then click **Launch Replication Monitor**.</span></span>  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a><span data-ttu-id="9a5e0-109">So starten Sie den Replikationsmonitor von der Eingabeaufforderung aus</span><span class="sxs-lookup"><span data-stu-id="9a5e0-109">To start Replication Monitor from the command prompt</span></span>  
  
1.  <span data-ttu-id="9a5e0-110">Navigieren Sie von der Eingabeaufforderung zum Installationsverzeichnis für Tools.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-110">From the command prompt, navigate to the tools installation directory.</span></span> <span data-ttu-id="9a5e0-111">Der Standardpfad ist [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-111">The default path is [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span></span>  
  
2.  <span data-ttu-id="9a5e0-112">Führen Sie sqlmonitor.exe aus.</span><span class="sxs-lookup"><span data-stu-id="9a5e0-112">Run sqlmonitor.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5e0-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a5e0-113">See Also</span></span>  
 [<span data-ttu-id="9a5e0-114">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="9a5e0-114">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
