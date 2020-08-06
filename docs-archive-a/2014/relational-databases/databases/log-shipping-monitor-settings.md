---
title: Protokollversand-Überwachungseinstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.settings.monitor.f1
ms.assetid: 45e2ba7d-b3aa-4643-9451-bcb991572314
author: stevestein
ms.author: sstein
ms.openlocfilehash: 162fdc1b8b0ef850a7e58d1380c533426e16539c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725865"
---
# <a name="log-shipping-monitor-settings"></a><span data-ttu-id="d9cf8-102">Protokollversand-Überwachungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="d9cf8-102">Log Shipping Monitor Settings</span></span>
  <span data-ttu-id="d9cf8-103">Mithilfe dieser Seite können Sie die Eigenschaften des Protokollversand-Überwachungsservers konfigurieren und ändern.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-103">Use this page to configure and to modify the properties of the log shipping monitor server.</span></span>  
  
 <span data-ttu-id="d9cf8-104">Eine Erläuterung zu den Konzepten des Protokollversands finden Sie unter [Informationen zum Protokollversand &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d9cf8-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d9cf8-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d9cf8-105">Options</span></span>  
 <span data-ttu-id="d9cf8-106">**Überwachungsserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-106">**Monitor server instance**</span></span>  
 <span data-ttu-id="d9cf8-107">Zeigt den Namen der Serverinstanz an, die zurzeit als Überwachungsserver für die Protokollversandkonfiguration konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-107">Displays the name of the server instance that is currently configured as the monitor server for the log shipping configuration.</span></span>  
  
 <span data-ttu-id="d9cf8-108">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-108">**Connect**</span></span>  
 <span data-ttu-id="d9cf8-109">Wählen Sie eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus, die als Überwachungsserver verwendet werden soll, und stellen Sie die entsprechende Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-109">Choose and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be used as the monitor server.</span></span> <span data-ttu-id="d9cf8-110">Das zum Verbinden verwendete Konto muss Mitglied der festen Serverrolle sysadmin auf der sekundären Serverinstanz sein.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-110">The account used to connect must be a member of the sysadmin fixed server role on the secondary server instance.</span></span>  
  
 <span data-ttu-id="d9cf8-111">**Identität des Auftragsproxykontos annehmen (normalerweise ist dies das Dienstkonto des SQL Server-Agents der Serverinstanz, in der der Auftrag ausgeführt wird)**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-111">**By impersonating the proxy account of the job**</span></span>  
 <span data-ttu-id="d9cf8-112">Legt fest, dass der Protokollversand beim Verbinden mit der Überwachungsserverinstanz die Identität des vom SQL Server-Agent verwendeten Proxykontos annimmt.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-112">Have log shipping impersonate the SQL Server Agent proxy account when connecting to the monitor server instance.</span></span> <span data-ttu-id="d9cf8-113">Stellen Sie sicher, dass Sicherungs-, Kopier- und Wiederherstellungsprozesse eine Verbindung mit dem Überwachungsserver herstellen können, damit der Status der Protokollversandvorgänge aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-113">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span>  
  
 <span data-ttu-id="d9cf8-114">**Folgende SQL Server-Anmeldung verwenden**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-114">**Using the following SQL Server login**</span></span>  
 <span data-ttu-id="d9cf8-115">Ermöglichen Sie dem Protokollversand beim Herstellen der Verbindung mit der Überwachungsserverinstanz die Verwendung einer bestimmten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-115">Allow log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login when connecting to the monitor server instance.</span></span> <span data-ttu-id="d9cf8-116">Stellen Sie sicher, dass Sicherungs-, Kopier- und Wiederherstellungsprozesse eine Verbindung mit dem Überwachungsserver herstellen können, damit der Status der Protokollversandvorgänge aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-116">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span> <span data-ttu-id="d9cf8-117">Wählen Sie diese Option aus, wenn der Protokollversand eine bestimmte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung verwenden soll, und geben Sie dann den Anmeldenamen und das Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-117">Choose this option if you want log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and then specify the login and password.</span></span>  
  
 <span data-ttu-id="d9cf8-118">**Verlauf löschen nach**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-118">**Delete history after**</span></span>  
 <span data-ttu-id="d9cf8-119">Geben Sie an, für welchen Zeitraum die Verlaufsinformationen des Protokollversands auf dem Überwachungsserver aufbewahrt werden, bevor sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-119">Specify the amount of time to retain log shipping history information on the monitor server before it is deleted.</span></span>  
  
 <span data-ttu-id="d9cf8-120">**Auftragsname**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-120">**Job name**</span></span>  
 <span data-ttu-id="d9cf8-121">Gibt den Namen des vom SQL Server-Agent bereitgestellten Warnungsauftrags an, mit dem der Protokollversand Warnungen auslöst, wenn beim Sichern oder Wiederherstellen Schwellenwerte überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-121">Indicates the name of the SQL Server Agent alert job used by log shipping to raise alerts when backup or restore thresholds have been exceeded.</span></span> <span data-ttu-id="d9cf8-122">Wenn Sie den Auftrag erstmalig erstellen, können Sie den Namen durch Eingabe in das entsprechende Feld ändern.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-122">When first creating this job, you can change the name by typing in the box.</span></span>  
  
 <span data-ttu-id="d9cf8-123">**Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-123">**Schedule**</span></span>  
 <span data-ttu-id="d9cf8-124">Gibt den aktuellen Zeitplan des vom SQL Server-Agent bereitgestellten Warnungsauftrags an.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-124">Indicates the current schedule of the SQL Server Agent alert job.</span></span>  
  
 <span data-ttu-id="d9cf8-125">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-125">**Edit**</span></span>  
 <span data-ttu-id="d9cf8-126">Ändert die Parameter des vom SQL Server-Agent bereitgestellten Warnungsauftrags.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-126">Modify the SQL Server Agent alert job parameters.</span></span>  
  
 <span data-ttu-id="d9cf8-127">**Diesen Auftrag deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="d9cf8-127">**Disable this job**</span></span>  
 <span data-ttu-id="d9cf8-128">Hält den vom SQL Server-Agent bereitgestellten Warnungsauftrag an.</span><span class="sxs-lookup"><span data-stu-id="d9cf8-128">Suspend the SQL Server Agent alert job.</span></span>  
  
  
