---
title: Konfigurieren von Warnungen zur Benachrichtigung von Richtlinienadministratoren bei Richtlinienfehlern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9eb84ced3bb6313dd5920deaf479925556f08fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695577"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a><span data-ttu-id="3a5ca-102">Konfigurieren von Warnungen zur Benachrichtigung von Richtlinienadministratoren bei Richtlinienfehlern</span><span class="sxs-lookup"><span data-stu-id="3a5ca-102">Configure Alerts to Notify Policy Administrators of Policy Failures</span></span>
  <span data-ttu-id="3a5ca-103">Wenn Richtlinien der richtlinienbasierten Verwaltung in einem der drei automatisierten Auswertungsmodi ausgeführt werden, wird bei einem Richtlinienverstoß eine Meldung im Ereignisprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-103">When Policy-Based Management policies are executed in one of the three automated evaluation modes, if a policy violation occurs, a message is written to the event log.</span></span> <span data-ttu-id="3a5ca-104">Wenn Sie bei Aufzeichnung einer solchen Meldung im Ereignisprotokoll benachrichtigt werden möchten, können Sie eine Warnung erstellen, die die Meldung erkennt und eine Aktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-104">To be notified when this message is written to the event log, you can create an alert to detect the message and perform an action.</span></span> <span data-ttu-id="3a5ca-105">Die Warnung sollte die Meldungen wie in der folgenden Tabelle gezeigt erkennen.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-105">The alert should detect the messages as shown in the following table.</span></span>  
  
|<span data-ttu-id="3a5ca-106">Ausführungsmodus</span><span class="sxs-lookup"><span data-stu-id="3a5ca-106">Execution mode</span></span>|<span data-ttu-id="3a5ca-107">Meldungsnummer</span><span class="sxs-lookup"><span data-stu-id="3a5ca-107">Message number</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="3a5ca-108">Bei Änderung - Verhindern</span><span class="sxs-lookup"><span data-stu-id="3a5ca-108">On change: prevent</span></span><br /><br /> <span data-ttu-id="3a5ca-109">(wenn automatisch)</span><span class="sxs-lookup"><span data-stu-id="3a5ca-109">(if automatic)</span></span>|<span data-ttu-id="3a5ca-110">34050</span><span class="sxs-lookup"><span data-stu-id="3a5ca-110">34050</span></span>|  
|<span data-ttu-id="3a5ca-111">Bei Änderung - Verhindern</span><span class="sxs-lookup"><span data-stu-id="3a5ca-111">On change: prevent</span></span><br /><br /> <span data-ttu-id="3a5ca-112">(wenn bedarfsgesteuert)</span><span class="sxs-lookup"><span data-stu-id="3a5ca-112">(if On demand)</span></span>|<span data-ttu-id="3a5ca-113">34051</span><span class="sxs-lookup"><span data-stu-id="3a5ca-113">34051</span></span>|  
|<span data-ttu-id="3a5ca-114">Nach Zeitplan</span><span class="sxs-lookup"><span data-stu-id="3a5ca-114">On schedule</span></span>|<span data-ttu-id="3a5ca-115">34052</span><span class="sxs-lookup"><span data-stu-id="3a5ca-115">34052</span></span>|  
|<span data-ttu-id="3a5ca-116">Bei Änderung</span><span class="sxs-lookup"><span data-stu-id="3a5ca-116">On change</span></span>|<span data-ttu-id="3a5ca-117">34053</span><span class="sxs-lookup"><span data-stu-id="3a5ca-117">34053</span></span>|  
  
 <span data-ttu-id="3a5ca-118">Wie Sie eine Warnung einrichten können, um auf Fehlermeldungen der richtlinienbasierten Verwaltung zu reagieren, wird in den folgenden Themen erläutert:</span><span class="sxs-lookup"><span data-stu-id="3a5ca-118">To set up an alert to respond to the Policy-Based Management error messages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="3a5ca-119">Erstellen eines Operators</span><span class="sxs-lookup"><span data-stu-id="3a5ca-119">Create an Operator</span></span>](../../ssms/agent/create-an-operator.md)  
  
-   [<span data-ttu-id="3a5ca-120">Create an Alert Using an Error Number</span><span class="sxs-lookup"><span data-stu-id="3a5ca-120">Create an Alert Using an Error Number</span></span>](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="3a5ca-121">Zuweisen von Warnungen zu einem Operator</span><span class="sxs-lookup"><span data-stu-id="3a5ca-121">Assign Alerts to an Operator</span></span>](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a><span data-ttu-id="3a5ca-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3a5ca-122">Permissions</span></span>  
 <span data-ttu-id="3a5ca-123">Bei Bedarf ausgewertete Richtlinien werden im Sicherheitskontext des Benutzers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-123">When policies are evaluated on demand, they execute in the security context of the user.</span></span> <span data-ttu-id="3a5ca-124">Um in das Fehlerprotokoll schreiben zu können, muss der Benutzer über die ALTER TRACE-Berechtigung verfügen oder Mitglied der festen Serverrolle sysadmin sein.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-124">To write to the error log, the user must have ALTER TRACE permissions or be a member of the sysadmin fixed server role.</span></span> <span data-ttu-id="3a5ca-125">Bei Auswertung einer Richtlinie durch einen Benutzer mit niedrigeren Berechtigungen werden eventuell erkannte Fehler nicht in das Ereignisprotokoll geschrieben und lösen keine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-125">Policies that are evaluated by a user that has less privileges will not write to the event log, and will not fire an alert.</span></span>  
  
 <span data-ttu-id="3a5ca-126">Die automatisierten Ausführungsmodi werden als Mitglied der Rolle sysadmin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-126">The automated execution modes execute as a member of the sysadmin role.</span></span> <span data-ttu-id="3a5ca-127">Dies ermöglicht es, dass eventuell erkannte Fehler für die Richtlinie in das Fehlerprotokoll geschrieben werden und eine Warnung auslösen.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-127">This allows the policy to write to the error log and raise an alert.</span></span>  
  
## <a name="additional-considerations-about-alerts"></a><span data-ttu-id="3a5ca-128">Weitere Überlegungen zu Warnungen</span><span class="sxs-lookup"><span data-stu-id="3a5ca-128">Additional Considerations About Alerts</span></span>  
 <span data-ttu-id="3a5ca-129">Beachten Sie die folgenden weiteren Überlegungen zu Warnungen:</span><span class="sxs-lookup"><span data-stu-id="3a5ca-129">Be aware of the following additional considerations about alerts:</span></span>  
  
-   <span data-ttu-id="3a5ca-130">Warnungen werden nur für Richtlinien ausgelöst, die aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-130">Alerts are raised only for policies that are enabled.</span></span> <span data-ttu-id="3a5ca-131">Da **bedarfsgesteuerte** Richtlinien nicht aktiviert werden können, werden Warnungen nicht für Richtlinien ausgelöst, die bedarfsgesteuert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-131">Because **On demand** policies cannot be enabled, alerts are not raised for policies that are executed on demand.</span></span>  
  
-   <span data-ttu-id="3a5ca-132">Wenn die Aktion, die Sie ausführen möchten, das Senden einer E-Mail umfasst, müssen Sie ein E-Mail-Konto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-132">If the action you want to take includes sending an e-mail message, you must configure a mail account.</span></span> <span data-ttu-id="3a5ca-133">Es empfiehlt sich die Verwendung von Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="3a5ca-133">We recommend that you use Database Mail.</span></span> <span data-ttu-id="3a5ca-134">Weitere Informationen zum Einrichten von Datenbank-E-Mail finden Sie unter [Erstellen eines Kontos für Datenbank-E-Mail](../database-mail/create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="3a5ca-134">For more information about how to set up Database Mail, see [Create a Database Mail Account](../database-mail/create-a-database-mail-account.md).</span></span>  
  
  
