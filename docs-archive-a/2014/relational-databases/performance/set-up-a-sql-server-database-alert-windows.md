---
title: Einrichten einer SQL Server-Datenbankwarnung (Windows) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
ms.assetid: 65d2c5c1-921f-4eff-9ef7-149170ab61e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 090eeda2c134857df18d083ce06d460214aa4dfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622604"
---
# <a name="set-up-a-sql-server-database-alert-windows"></a><span data-ttu-id="cdb50-102">Einrichten einer SQL Server-Datenbankwarnung (Windows)</span><span class="sxs-lookup"><span data-stu-id="cdb50-102">Set Up a SQL Server Database Alert (Windows)</span></span>
  <span data-ttu-id="cdb50-103">Sie können mithilfe des Systemmonitors eine Warnung erstellen, die ausgelöst wird, wenn ein Schwellenwert für einen Leistungsindikator des Systemmonitors erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="cdb50-103">Using System Monitor, you can create an alert to be raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="cdb50-104">Als Reaktion auf die Warnung kann der Systemmonitor eine Anwendung starten, wie z. B. eine benutzerdefinierte Anwendung, die für das Verarbeiten der Warnung geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="cdb50-104">In response to the alert, System Monitor can launch an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="cdb50-105">Sie können beispielsweise eine Warnung erstellen, die ausgelöst wird, wenn die Anzahl der Deadlocks einen bestimmten Wert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="cdb50-105">For example, you can create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="cdb50-106">Warnungen können auch mit Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] und dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent definiert werden.</span><span class="sxs-lookup"><span data-stu-id="cdb50-106">Alerts also can be defined using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="cdb50-107">Weitere Informationen finden Sie unter [Warnungen](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="cdb50-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
### <a name="to-set-up-a-sql-server-database-alert"></a><span data-ttu-id="cdb50-108">So richten Sie eine SQL Server-Datenbankwarnung ein</span><span class="sxs-lookup"><span data-stu-id="cdb50-108">To set up a SQL Server database alert</span></span>  
  
1.  <span data-ttu-id="cdb50-109">Erweitern Sie in der Navigationsstruktur des Fensters Leistung die Option **Leistungsprotokolle und Warnungen**.</span><span class="sxs-lookup"><span data-stu-id="cdb50-109">On the navigation tree of the Performance window, expand **Performance Logs and Alerts**.</span></span>  
  
2.  <span data-ttu-id="cdb50-110">Klicken Sie mit der rechten Maustaste auf **Warnungen**, und klicken Sie dann auf **Neue Warnungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="cdb50-110">Right-click **Alerts**, and then click **New Alert Settings**.</span></span>  
  
3.  <span data-ttu-id="cdb50-111">Geben Sie im Dialogfeld **Neue Warnungseinstellungen** einen Namen für die neue Warnung ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb50-111">In the **New Alert Settings** dialog box, type a name for the new alert, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="cdb50-112">Fügen Sie im Dialogfeld für die neue Warnung auf der Registerkarte **Allgemein** einen **Kommentar**hinzu, und klicken Sie auf **Hinzufügen** , um der Warnung einen Leistungsindikator hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cdb50-112">On the **General** tab of the dialog box for the new alert, add a **Comment**, and click **Add** to add a counter to the alert.</span></span>  
  
     <span data-ttu-id="cdb50-113">Jede Warnung muss mindestens einen Leistungsindikator aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cdb50-113">All alerts must have at least one counter.</span></span>  
  
5.  <span data-ttu-id="cdb50-114">Wählen Sie im Dialogfeld Leistungsindikatoren hinzufügen in der Liste **Leistungsobjekt** ein SQL Server-Objekt aus, und wählen Sie dann in der Liste **Leistungsindikatoren wählen**einen Leistungsindikator aus.</span><span class="sxs-lookup"><span data-stu-id="cdb50-114">In the Add Counters dialog box, select a SQL Server object from the **Performance Object** list, and then select a counter from the **Select counters from list**.</span></span>  
  
6.  <span data-ttu-id="cdb50-115">Klicken Sie auf **Hinzufügen**, um der Warnung den Leistungsindikator hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cdb50-115">To add the counter to the alert, click **Add**.</span></span> <span data-ttu-id="cdb50-116">Sie können weitere Leistungsindikatoren hinzufügen, oder klicken Sie auf **Schließen** , um zum Dialogfeld für die neue Warnung zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="cdb50-116">You can continue to add counters, or you can click **Close** to return to the dialog box for the new alert.</span></span>  
  
7.  <span data-ttu-id="cdb50-117">Klicken Sie im Dialogfeld für die neue Warnung in der Liste **Warnung bei Wert** auf **größer als**oder **kleiner als** , und geben Sie dann in das Feld **Limit**einen Schwellenwert ein.</span><span class="sxs-lookup"><span data-stu-id="cdb50-117">In the new alert dialog box, click either **Over** or **Under**in the **Alert when the value is** list, and then enter a threshold value in **Limit**.</span></span>  
  
     <span data-ttu-id="cdb50-118">Die Warnung wird generiert, wenn der Wert für den Leistungsindikator größer oder kleiner als der Schwellwert ist (je nachdem, ob Sie auf **größer als** oder **kleiner als**geklickt haben).</span><span class="sxs-lookup"><span data-stu-id="cdb50-118">The alert is generated when the value for the counter is more than or less than the threshold value (depending on whether you clicked **Over** or **Under**).</span></span>  
  
8.  <span data-ttu-id="cdb50-119">Legen Sie in den Feldern **Daten erfassen alle** die Stichprobenfrequenz fest.</span><span class="sxs-lookup"><span data-stu-id="cdb50-119">In the **Sample data every** boxes, set the sampling frequency.</span></span>  
  
9. <span data-ttu-id="cdb50-120">Legen Sie auf der Registerkarte **Aktion** die Aktionen fest, die jedes Mal ausgeführt werden, wenn die Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="cdb50-120">On the **Action** tab, set actions to occur every time the alert is triggered.</span></span>  
  
10. <span data-ttu-id="cdb50-121">Legen Sie auf der Registerkarte **Zeitplan** den Beginn und das Ende des Zeitplans für die Warnungssuche fest.</span><span class="sxs-lookup"><span data-stu-id="cdb50-121">On the **Schedule** tab, set the start and stop schedule for the alert scan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb50-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cdb50-122">See Also</span></span>  
 [<span data-ttu-id="cdb50-123">Erstellen einer SQL Server-Datenbankwarnung</span><span class="sxs-lookup"><span data-stu-id="cdb50-123">Create a SQL Server Database Alert</span></span>](../performance-monitor/create-a-sql-server-database-alert.md)  
  
  
