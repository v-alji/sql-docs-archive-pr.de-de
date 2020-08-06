---
title: Eigenschaften des SQL Server-Agents (Registerkarte Auftragssystem)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621304"
---
# <a name="sql-server-agent-properties-job-system-page"></a><span data-ttu-id="baaf1-102">Eigenschaften des SQL Server-Agents (Registerkarte Auftragssystem)</span><span class="sxs-lookup"><span data-stu-id="baaf1-102">SQL Server Agent Properties (Job System Page)</span></span>
  <span data-ttu-id="baaf1-103">Mithilfe dieser Seite können Sie anzeigen und ändern, wie Aufträge vom- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="baaf1-103">Use this page to view and modify how the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service manages jobs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="baaf1-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="baaf1-104">Options</span></span>  
 <span data-ttu-id="baaf1-105">**Timeoutintervall beim Herunterfahren (in Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="baaf1-105">**Shutdown time-out interval (in seconds)**</span></span>  
 <span data-ttu-id="baaf1-106">Gibt an, wie viele Sekunden der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent vor dem Herunterfahren auf den Abschluss von Aufträgen abwartet.</span><span class="sxs-lookup"><span data-stu-id="baaf1-106">Specifies the number of seconds that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for jobs to complete before shutting down.</span></span> <span data-ttu-id="baaf1-107">Wenn der Auftrag noch nach dem angegebenen Intervall ausgeführt wird, wird das Beenden des Auftrags vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent erzwungen.</span><span class="sxs-lookup"><span data-stu-id="baaf1-107">If the job is still running after the interval specified, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent forcefully stops the job.</span></span>  
  
 <span data-ttu-id="baaf1-108">**Nichtadministrator-Proxykonto verwenden**</span><span class="sxs-lookup"><span data-stu-id="baaf1-108">**Use a non-administrator proxy account**</span></span>  
 <span data-ttu-id="baaf1-109">Legt ein Nichtadministrator-Proxykonto für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent fest.</span><span class="sxs-lookup"><span data-stu-id="baaf1-109">Sets a non-administrator proxy account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="baaf1-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]und höhere Versionen unterstützen mehrere Proxys. Daher ist diese Option nur bei der Verwaltung [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von verfügbar. Agent-Versionen vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="baaf1-110">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="baaf1-111">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="baaf1-111">**User name**</span></span>  
 <span data-ttu-id="baaf1-112">Geben Sie den Namen des Benutzers für das Nichtadministrator-Proxykonto ein.</span><span class="sxs-lookup"><span data-stu-id="baaf1-112">Type the name of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="baaf1-113">unterstützt mehrere Proxys. Diese Option betrifft daher nur die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Versionen vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baaf1-113">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="baaf1-114">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="baaf1-114">**Password**</span></span>  
 <span data-ttu-id="baaf1-115">Geben Sie das Kennwort des Benutzers für das Nichtadministrator-Proxykonto ein.</span><span class="sxs-lookup"><span data-stu-id="baaf1-115">Type the password of the user for the non-administrator proxy account.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="baaf1-116">und höhere Versionen unterstützen mehrere Proxys. Diese Option betrifft daher nur die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Versionen vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baaf1-116">and later versions support multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="baaf1-117">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="baaf1-117">**Domain**</span></span>  
 <span data-ttu-id="baaf1-118">Geben Sie die Domäne des Benutzers für das Nichtadministrator-Proxykonto ein.</span><span class="sxs-lookup"><span data-stu-id="baaf1-118">Type the domain of the user for the non-administrative proxy account.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="baaf1-119">unterstützt mehrere Proxys. Diese Option betrifft daher nur die Verwaltung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Versionen vor [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baaf1-119">supports multiple proxies, therefore this option is only applicable when managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent versions prior to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baaf1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baaf1-120">See Also</span></span>  
 [<span data-ttu-id="baaf1-121">Implementieren von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="baaf1-121">Implement Jobs</span></span>](implement-jobs.md)  
  
  
