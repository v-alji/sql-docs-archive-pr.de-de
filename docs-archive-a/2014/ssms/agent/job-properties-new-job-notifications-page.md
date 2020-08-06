---
title: 'Auftrags Eigenschaften: neuer Auftrag (Seite "Benachrichtigungen") | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609002"
---
# <a name="job-properties-new-job-notifications-page"></a><span data-ttu-id="b45ab-102">Auftragseigenschaften: Neuer Auftrag (Seite „Benachrichtigungen“)</span><span class="sxs-lookup"><span data-stu-id="b45ab-102">Job Properties: New Job (Notifications Page)</span></span>
  <span data-ttu-id="b45ab-103">Verwenden Sie diese Seite, um Aktionen festzulegen, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die der-Agent ausführt, wenn der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b45ab-103">Use this page to set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b45ab-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b45ab-104">Options</span></span>  
 <span data-ttu-id="b45ab-105">**E**</span><span class="sxs-lookup"><span data-stu-id="b45ab-105">**E-mail**</span></span>  
 <span data-ttu-id="b45ab-106">Diese Option wird ausgewählt, um bei Abschluss des Auftrags eine E-Mail zu senden.</span><span class="sxs-lookup"><span data-stu-id="b45ab-106">Select this option to send e-mail when the job completes.</span></span> <span data-ttu-id="b45ab-107">Nachdem Sie die Option ausgewählt haben, müssen Sie den zu benachrichtigenden Operator und die Bedingung auswählen, durch die die Benachrichtigung ausgelöst wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**oder **Beim Abschluss des Auftrags**.</span><span class="sxs-lookup"><span data-stu-id="b45ab-107">After selecting this option, choose the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="b45ab-108">**Seite**</span><span class="sxs-lookup"><span data-stu-id="b45ab-108">**Page**</span></span>  
 <span data-ttu-id="b45ab-109">Diese Option wird ausgewählt, um eine E-Mail an den Pager des Operators zu senden, wenn der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b45ab-109">Select this option to send e-mail to an operator's pager when the job completes.</span></span> <span data-ttu-id="b45ab-110">Nachdem Sie die Option ausgewählt haben, müssen Sie den zu benachrichtigenden Operator und die Bedingung auswählen, durch die die Benachrichtigung ausgelöst wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**oder **Beim Abschluss des Auftrags**.</span><span class="sxs-lookup"><span data-stu-id="b45ab-110">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="b45ab-111">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="b45ab-111">**Net send**</span></span>  
 <span data-ttu-id="b45ab-112">Diese Option wird ausgewählt, um einen Operator bei Abschluss des Auftrags über net send zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="b45ab-112">Select this option to use net send to notify an operator when the job completes.</span></span> <span data-ttu-id="b45ab-113">Nachdem Sie die Option ausgewählt haben, müssen Sie den zu benachrichtigenden Operator und die Bedingung auswählen, durch die die Benachrichtigung ausgelöst wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**oder **Beim Abschluss des Auftrags**.</span><span class="sxs-lookup"><span data-stu-id="b45ab-113">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="b45ab-114">**In das Windows-Anwendungsereignisprotokoll schreiben**</span><span class="sxs-lookup"><span data-stu-id="b45ab-114">**Write to the Windows Application event log**</span></span>  
 <span data-ttu-id="b45ab-115">Diese Option wird ausgewählt, um bei Abschluss des Auftrags einen Eintrag in das Anwendungsereignisprotokoll zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b45ab-115">Select this option to write an entry in the application event log when the job completes.</span></span> <span data-ttu-id="b45ab-116">Nachdem Sie die Option ausgewählt haben, müssen Sie die Bedingung angeben, durch die veranlasst wird, dass der Eintrag geschrieben wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**und **Beim Abschluss des Auftrags**.</span><span class="sxs-lookup"><span data-stu-id="b45ab-116">After selecting this option, specify the condition that will cause the entry to be written: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="b45ab-117">**Auftrag automatisch löschen**</span><span class="sxs-lookup"><span data-stu-id="b45ab-117">**Automatically delete job**</span></span>  
 <span data-ttu-id="b45ab-118">Diese Option wird ausgewählt, um den Auftrag bei Abschluss zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b45ab-118">Select this option to delete the job when the job completes.</span></span> <span data-ttu-id="b45ab-119">Nachdem Sie die Option ausgewählt haben, müssen Sie die Bedingung angeben, durch die veranlasst wird, dass der Auftrag gelöscht wird. Die Bedingungen sind **Bei erfolgreicher Auftragsausführung**, **Bei Auftragsfehler**und **Beim Abschluss des Auftrags**.</span><span class="sxs-lookup"><span data-stu-id="b45ab-119">After selecting this option, specify the condition that will trigger deletion of the job: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45ab-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b45ab-120">See Also</span></span>  
 <span data-ttu-id="b45ab-121">[Implementieren von Aufträgen](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="b45ab-121">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="b45ab-122">Konfigurieren von SQL Server-Agent-Mail zum Verwenden von Datenbank-E-Mails</span><span class="sxs-lookup"><span data-stu-id="b45ab-122">Configure SQL Server Agent Mail to Use Database Mail</span></span>](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
