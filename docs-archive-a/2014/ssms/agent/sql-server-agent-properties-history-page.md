---
title: SQL Server-Agent-Eigenschaften (Seite Verlauf)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621306"
---
# <a name="sql-server-agent-properties-history-page"></a><span data-ttu-id="cf6bd-102">SQL Server-Agent-Eigenschaften (Seite Verlauf)</span><span class="sxs-lookup"><span data-stu-id="cf6bd-102">SQL Server Agent Properties (History Page)</span></span>
  <span data-ttu-id="cf6bd-103">Mithilfe dieser Seite können Sie Einstellungen für die Verwaltung des Verlaufs Protokolls für den-Agent-Dienst anzeigen und ändern [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf6bd-103">Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service history log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cf6bd-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="cf6bd-104">Options</span></span>  
 <span data-ttu-id="cf6bd-105">**Größe des Auftragsverlaufsprotokolls beschränken**</span><span class="sxs-lookup"><span data-stu-id="cf6bd-105">**Limit size of job history log**</span></span>  
 <span data-ttu-id="cf6bd-106">Legt die Grenzen für die Menge der Auftragsverlaufsinformationen fest, die im Protokoll des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents verbleiben.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-106">Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains in the log.</span></span>  
  
 <span data-ttu-id="cf6bd-107">**Maximale Länge des Auftragsverlaufsprotokolls (in Zeilen)**</span><span class="sxs-lookup"><span data-stu-id="cf6bd-107">**Maximum job history log size (in rows)**</span></span>  
 <span data-ttu-id="cf6bd-108">Legt die maximale Anzahl der Zeilen fest, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent beibehält.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-108">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains.</span></span> <span data-ttu-id="cf6bd-109">Wenn das Protokoll diese Anzahl von Zeilen überschreitet, werden die ältesten Zeilen vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent entfernt, sobald neue Zeilen eingetragen werden.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-109">When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="cf6bd-110">**Maximale Zeilenanzahl pro Auftrag in Auftragsverlauf**</span><span class="sxs-lookup"><span data-stu-id="cf6bd-110">**Maximum job history rows per job**</span></span>  
 <span data-ttu-id="cf6bd-111">Legt die maximale Anzahl von Zeilen fest, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent pro Auftrag beibehält.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-111">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains per job.</span></span> <span data-ttu-id="cf6bd-112">Wenn der Verlauf eines bestimmten Auftrags diese Anzahl von Zeilen überschreitet, werden die ältesten Zeilen vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent entfernt, sobald neue Zeilen eingetragen werden.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-112">When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="cf6bd-113">**Agentverlauf entfernen**</span><span class="sxs-lookup"><span data-stu-id="cf6bd-113">**Remove agent history**</span></span>  
 <span data-ttu-id="cf6bd-114">Gibt an, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent Einträge entfernt, die länger als eine bestimmte Zeitspanne im Protokoll vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-114">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time.</span></span> <span data-ttu-id="cf6bd-115">Dies ist eine einmalige Ausführung zum Löschen des Verlaufs.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-115">This is a one-time execution to remove the history.</span></span> <span data-ttu-id="cf6bd-116">Wenn ein erneut auftretender Auftrag benötigt wird, erstellen und planen Sie einen Wartungsplan mit einem Cleanupauftrag.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-116">If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.</span></span>  
  
 <span data-ttu-id="cf6bd-117">**Älter als**</span><span class="sxs-lookup"><span data-stu-id="cf6bd-117">**Older than**</span></span>  
 <span data-ttu-id="cf6bd-118">Legt die Zeitspanne fest, für die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent die Einträge beibehält.</span><span class="sxs-lookup"><span data-stu-id="cf6bd-118">Sets the amount of time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will retain entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6bd-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf6bd-119">See Also</span></span>  
 [<span data-ttu-id="cf6bd-120">SQL Server-Agent-Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="cf6bd-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
