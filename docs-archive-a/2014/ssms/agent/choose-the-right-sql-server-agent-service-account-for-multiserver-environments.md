---
title: Auswählen des richtigen SQL Server-Agent Dienst Kontos für Multiserverumgebungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: stevestein
ms.author: sstein
ms.openlocfilehash: 94ef890f5d2ef2b85d2f4d1023a93747e903a7f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622381"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a><span data-ttu-id="48a49-102">Auswählen des richtigen SQL Server-Agent-Dienstkontos für Multiserverumgebungen</span><span class="sxs-lookup"><span data-stu-id="48a49-102">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>
  <span data-ttu-id="48a49-103">Das Windows-Konto, das Sie für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst auswählen, kann sich wie im Folgenden beschrieben auf das Verhalten einer Multiserverumgebung auswirken:</span><span class="sxs-lookup"><span data-stu-id="48a49-103">The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:</span></span>  
  
-   <span data-ttu-id="48a49-104">Wenn Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst unter einem Konto ausführen, das nicht Mitglied der lokalen Windows-Administratorengruppe ist, treten beim Eintragen von Zielservern bei Masterservern u. U. Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="48a49-104">If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail.</span></span> <span data-ttu-id="48a49-105">In diesem Fall wird die folgende Fehlermeldung zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="48a49-105">If it does, the following error message is returned:</span></span>  
  
     <span data-ttu-id="48a49-106">"Fehler beim Eintragungsvorgang."</span><span class="sxs-lookup"><span data-stu-id="48a49-106">"The enlistment operation failed."</span></span>  
  
     <span data-ttu-id="48a49-107">Starten Sie die Dienste von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent neu, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="48a49-107">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services to resolve this issue.</span></span>  
  
-   <span data-ttu-id="48a49-108">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst unter dem Konto LocalSystem ausgeführt wird, werden Vorgänge zwischen Masterservern und Zielservern nur unterstützt, wenn sich Masterserver und Zielserver auf demselben Computer befinden.</span><span class="sxs-lookup"><span data-stu-id="48a49-108">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer.</span></span> <span data-ttu-id="48a49-109">Wenn Sie diese Konfiguration verwenden, wird beim Eintragen von Zielservern bei einem Masterserver die folgende Meldung zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="48a49-109">If you use this configuration, the following message is returned when you enlist target servers to a master server:</span></span>  
  
     <span data-ttu-id="48a49-110">„Stellen Sie sicher, dass das Agentstartkonto für *<Zielserver-Computername>* Rechte zur Anmeldung als Zielserver besitzt.“</span><span class="sxs-lookup"><span data-stu-id="48a49-110">"Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."</span></span>  
  
     <span data-ttu-id="48a49-111">Sie können diese zu Informationszwecken ausgegebene Meldung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="48a49-111">You can ignore this informational message.</span></span> <span data-ttu-id="48a49-112">Der Eintragungsvorgang wird dennoch erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="48a49-112">The enlistment operation should complete successfully.</span></span>  
  
 <span data-ttu-id="48a49-113">Weitere Informationen zum Auswählen eines Kontos für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst finden Sie unter [Auswählen eines Kontos für den SQL Server-Agent-Dienst](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="48a49-113">For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span>  
  
  
