---
title: Warnungs Eigenschaften-neue Warnung (Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.general.f1
ms.assetid: f5c11610-62e3-44df-9800-a5dc35be4a09
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471b0062ecc805e83020495e422f8914baec5f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722229"
---
# <a name="alert-properties-new-alert-general-page"></a><span data-ttu-id="3e924-102">Warnungs Eigenschaften-neue Warnung (Seite "Allgemein")</span><span class="sxs-lookup"><span data-stu-id="3e924-102">Alert Properties-New Alert (General Page)</span></span>
  <span data-ttu-id="3e924-103">Mithilfe dieser Seite können Sie die allgemeinen Eigenschaften von-Agent-Warnungen anzeigen und ändern [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e924-103">Use this page to view and modify the general properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3e924-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3e924-104">Options</span></span>  
 <span data-ttu-id="3e924-105">**Name**</span><span class="sxs-lookup"><span data-stu-id="3e924-105">**Name**</span></span>  
 <span data-ttu-id="3e924-106">Ändern Sie den Namen der Warnung.</span><span class="sxs-lookup"><span data-stu-id="3e924-106">Change the name of the alert.</span></span>  
  
 <span data-ttu-id="3e924-107">**Aktivieren**</span><span class="sxs-lookup"><span data-stu-id="3e924-107">**Enable**</span></span>  
 <span data-ttu-id="3e924-108">Aktivieren Sie die Warnung.</span><span class="sxs-lookup"><span data-stu-id="3e924-108">Enable the alert.</span></span> <span data-ttu-id="3e924-109">Wenn die Warnung nicht aktiviert ist, werden die in der Warnung angegebenen Aktionen nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e924-109">When the alert is not enabled, the actions specified in the alert do not occur.</span></span>  
  
 <span data-ttu-id="3e924-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="3e924-110">**Type**</span></span>  
 <span data-ttu-id="3e924-111">Wählen Sie den Typ der Warnung aus:</span><span class="sxs-lookup"><span data-stu-id="3e924-111">Select the type of alert:</span></span>  
  
-   <span data-ttu-id="3e924-112">**SQL Server-Ereigniswarnung** reagiert auf Meldungen im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="3e924-112">**SQL Server event alert** responds to messages in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
-   <span data-ttu-id="3e924-113">**SQL Server-Leistungsstatuswarnung** reagiert auf eine bestimmte Bedingung in einem Leistungsindikator.</span><span class="sxs-lookup"><span data-stu-id="3e924-113">**SQL Server performance condition alert** responds to a specific condition in a performance counter.</span></span>  
  
-   <span data-ttu-id="3e924-114">**WMI-Ereigniswarnung** reagiert auf ein WMI-Ereignis (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="3e924-114">**WMI event alert** responds to a Windows Management Instrumentation (WMI) event.</span></span>  
  
## <a name="sql-server-event-alert-options"></a><span data-ttu-id="3e924-115">Optionen für die SQL Server-Ereigniswarnung</span><span class="sxs-lookup"><span data-stu-id="3e924-115">SQL Server Event Alert Options</span></span>  
 <span data-ttu-id="3e924-116">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="3e924-116">**Database name**</span></span>  
 <span data-ttu-id="3e924-117">Geben Sie eine Datenbank für das Ereignis an, oder geben Sie **Alle Datenbanken** an, damit auf eine Meldung unabhängig von der Datenbank reagiert wird, in der das Ereignis auftritt.</span><span class="sxs-lookup"><span data-stu-id="3e924-117">Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.</span></span>  
  
 <span data-ttu-id="3e924-118">**Fehlernummer**</span><span class="sxs-lookup"><span data-stu-id="3e924-118">**Error number**</span></span>  
 <span data-ttu-id="3e924-119">Geben Sie an, dass dieses Ereignis auf einen Fehler reagiert, und geben Sie die Fehlernummer an.</span><span class="sxs-lookup"><span data-stu-id="3e924-119">Specify that this event responds to an error, and specify the error number.</span></span>  
  
 <span data-ttu-id="3e924-120">**Severity**</span><span class="sxs-lookup"><span data-stu-id="3e924-120">**Severity**</span></span>  
 <span data-ttu-id="3e924-121">Geben Sie an, dass dieses Ereignis auf alle Meldungen innerhalb eines bestimmten Schweregrads reagiert, und geben Sie den Schweregrad an.</span><span class="sxs-lookup"><span data-stu-id="3e924-121">Specify that this event responds to any message with a specific severity level, and specify the severity level.</span></span>  
  
 <span data-ttu-id="3e924-122">**Warnung auslösen, wenn eine Meldung Folgendes enthält**</span><span class="sxs-lookup"><span data-stu-id="3e924-122">**Raise alert when message contains**</span></span>  
 <span data-ttu-id="3e924-123">Filtert Ereignisse nach einer bestimmten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3e924-123">Filter events by a specific string.</span></span> <span data-ttu-id="3e924-124">Wenn diese Option ausgewählt ist, reagiert die Warnung nur auf Ereignisse, die eine bestimmte Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="3e924-124">When this option is selected, the alert only responds to events that contain a specific string.</span></span>  
  
 <span data-ttu-id="3e924-125">**Meldungs Text**</span><span class="sxs-lookup"><span data-stu-id="3e924-125">**Message text**</span></span>  
 <span data-ttu-id="3e924-126">Geben Sie die Zeichenfolge ein, die zum Filtern von Ereignissen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e924-126">Specify the string to use to filter events.</span></span>  
  
## <a name="sql-server-performance-condition-alerts"></a><span data-ttu-id="3e924-127">SQL Server-Leistungsstatuswarnungen</span><span class="sxs-lookup"><span data-stu-id="3e924-127">SQL Server Performance Condition Alerts</span></span>  
 <span data-ttu-id="3e924-128">**Object**</span><span class="sxs-lookup"><span data-stu-id="3e924-128">**Object**</span></span>  
 <span data-ttu-id="3e924-129">Geben Sie das zu überwachende Leistungsobjekt an.</span><span class="sxs-lookup"><span data-stu-id="3e924-129">Specify the performance object to monitor.</span></span>  
  
 <span data-ttu-id="3e924-130">**Leistungsindikator**</span><span class="sxs-lookup"><span data-stu-id="3e924-130">**Counter**</span></span>  
 <span data-ttu-id="3e924-131">Geben Sie den Leistungsindikator innerhalb des Leistungsobjekts an, der überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e924-131">Specify the counter within the performance object to monitor.</span></span>  
  
 <span data-ttu-id="3e924-132">**Instanz**</span><span class="sxs-lookup"><span data-stu-id="3e924-132">**Instance**</span></span>  
 <span data-ttu-id="3e924-133">Geben Sie die Instanz des Leistungsindikators an, die überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e924-133">Specify the instance of the counter to monitor.</span></span>  
  
 <span data-ttu-id="3e924-134">**Warnung, falls Leistungsindikator**</span><span class="sxs-lookup"><span data-stu-id="3e924-134">**Alert if counter**</span></span>  
 <span data-ttu-id="3e924-135">Geben Sie das Verhalten des Leistungsindikators an, auf das die Warnung reagiert.</span><span class="sxs-lookup"><span data-stu-id="3e924-135">Specify the behavior of the counter that the alert responds to.</span></span> <span data-ttu-id="3e924-136">Die Warnung könnte beispielsweise auf eine Bedingung reagieren, bei der der Wert des Leistungsindikators **Freier Speicherplatz in 'tempdb' (KB)** unter eine bestimmte Grenze fällt, oder auf eine Bedingung, bei der der Wert für **SQL-Kompilierungen/Sekunde** einen bestimmten Wert übersteigt.</span><span class="sxs-lookup"><span data-stu-id="3e924-136">For example, you may want the alert to respond to a condition where the value of the **Free space in tempdb (KB)** counter falls below a certain value, or you may want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.</span></span>  
  
 <span data-ttu-id="3e924-137">**Wert**</span><span class="sxs-lookup"><span data-stu-id="3e924-137">**Value**</span></span>  
 <span data-ttu-id="3e924-138">Geben Sie einen Wert für den Leistungsindikator an.</span><span class="sxs-lookup"><span data-stu-id="3e924-138">Specify a value for the counter.</span></span>  
  
## <a name="wmi-event-alert-options"></a><span data-ttu-id="3e924-139">WMI-Ereigniswarnungsoptionen</span><span class="sxs-lookup"><span data-stu-id="3e924-139">WMI Event Alert Options</span></span>  
 <span data-ttu-id="3e924-140">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="3e924-140">**Namespace**</span></span>  
 <span data-ttu-id="3e924-141">Geben Sie den Namespace an, der für die WQL-Anweisung (WMI Query Language) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e924-141">Specify the namespace to use for the WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="3e924-142">Es werden nur Namespaces auf dem Computer unterstützt, auf dem der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3e924-142">Only namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
 <span data-ttu-id="3e924-143">**Abfrage**</span><span class="sxs-lookup"><span data-stu-id="3e924-143">**Query**</span></span>  
 <span data-ttu-id="3e924-144">Geben Sie die WQL-Anweisung an, die das Ereignis identifiziert, auf das die Warnung reagiert.</span><span class="sxs-lookup"><span data-stu-id="3e924-144">Specify the WQL statement that identifies the event that the alert responds to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e924-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e924-145">See Also</span></span>  
 <span data-ttu-id="3e924-146">[Warnungen](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="3e924-146">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="3e924-147">[Verwenden von WQL mit dem WMI-Anbieter für Server Ereignisse](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span><span class="sxs-lookup"><span data-stu-id="3e924-147">[Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span></span>  
 <span data-ttu-id="3e924-148">[Erstellen einer Warnung mithilfe einer Fehlernummer](create-an-alert-using-an-error-number.md) </span><span class="sxs-lookup"><span data-stu-id="3e924-148">[Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md) </span></span>  
 [<span data-ttu-id="3e924-149">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="3e924-149">Create an Alert Using Severity Level</span></span>](create-an-alert-using-severity-level.md)  
  
  
