---
title: Festlegen der Leerlaufzeit und Leerlaufdauer der CPU (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CPU [SQL Server], idle conditions
- time [SQL Server], CPU idle and duration
- duration of CPU idle [SQL Server]
- SQL Server Agent, CPU idle conditions
- idle time [SQL Server]
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1660f6d70977b8f590a18adf952a6a19f32a26cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726417"
---
# <a name="set-cpu-idle-time-and-duration-sql-server-management-studio"></a><span data-ttu-id="d1da9-102">Festlegen der Leerlaufzeit und Leerlaufdauer der CPU (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d1da9-102">Set CPU Idle Time and Duration (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d1da9-103">In diesem Thema wird erläutert, wie Sie die CPU-Leerlaufbedingung für den Server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]definieren.</span><span class="sxs-lookup"><span data-stu-id="d1da9-103">This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d1da9-104">Die CPU-Leerlauf Definition beeinflusst die Reaktion des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agents auf Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d1da9-104">The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responds to events.</span></span> <span data-ttu-id="d1da9-105">Nehmen wir beispielsweise an, dass Sie die CPU als im Leerlauf befindlich definieren, wenn die durchschnittliche CPU-Auslastung unter 10 Prozent fällt und für 10 Minuten auf dieser Stufe bleibt.</span><span class="sxs-lookup"><span data-stu-id="d1da9-105">For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes.</span></span> <span data-ttu-id="d1da9-106">Wenn Sie Aufträge definiert haben, die immer dann ausgeführt werden sollen, wenn die Server-CPU eine Leerlaufbedingung erfüllt, wird der Auftrag gestartet, wenn die CPU-Auslastung unter 10 Prozent fällt und für 10 Minuten auf dieser Stufe bleibt.</span><span class="sxs-lookup"><span data-stu-id="d1da9-106">Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes.</span></span> <span data-ttu-id="d1da9-107">Wenn es sich dabei um einen Auftrag handelt, der sich spürbar auf die Serverleistung auswirkt, ist die Art wichtig, wie Sie die CPU-Leerlaufbedingung definieren.</span><span class="sxs-lookup"><span data-stu-id="d1da9-107">If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d1da9-108">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1da9-108">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-cpu-idle-time-and-duration"></a><span data-ttu-id="d1da9-109">So legen Sie die Leerlaufzeit und die Leerlaufdauer der CPU fest</span><span class="sxs-lookup"><span data-stu-id="d1da9-109">To set CPU idle time and duration</span></span>  
  
1.  <span data-ttu-id="d1da9-110">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="d1da9-110">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d1da9-111">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, klicken Sie auf **Eigenschaften**, und wählen Sie dann die Seite **Erweitert** aus.</span><span class="sxs-lookup"><span data-stu-id="d1da9-111">Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.</span></span>  
  
3.  <span data-ttu-id="d1da9-112">Führen Sie unter **Bedingung für 'CPU im Leerlauf'** eine der folgenden Aktionen aus :</span><span class="sxs-lookup"><span data-stu-id="d1da9-112">Under **Idle CPU condition**, do the following:</span></span>  
  
    -   <span data-ttu-id="d1da9-113">Aktivieren Sie **Bedingung für 'CPU im Leerlauf' definieren**.</span><span class="sxs-lookup"><span data-stu-id="d1da9-113">Check **Define idle CPU condition.**</span></span>  
  
    -   <span data-ttu-id="d1da9-114">Geben Sie einen Prozentsatz für das Feld **Bei durchschnittlicher CPU-Nutzung unter** (für alle CPUs) an.</span><span class="sxs-lookup"><span data-stu-id="d1da9-114">Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box.</span></span> <span data-ttu-id="d1da9-115">Damit wird die Auslastungsgrenze festgelegt, unterhalb der die CPU als im Leerlauf befindlich angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="d1da9-115">This sets the usage level that the CPU must fall below before it is considered idle.</span></span>  
  
    -   <span data-ttu-id="d1da9-116">Geben Sie einen Wert für Sekunden im Feld **und Verbleiben unterhalb dieser Stufe für** an.</span><span class="sxs-lookup"><span data-stu-id="d1da9-116">Specify a number of seconds for the **And remains below this level for** box.</span></span> <span data-ttu-id="d1da9-117">Damit wird die Dauer der minimalen CPU-Auslastung angegeben, bevor die CPU als im Leerlauf befindlich angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="d1da9-117">This sets the duration that the minimum CPU usage must remain at before it is considered idle.</span></span>  
  
  
