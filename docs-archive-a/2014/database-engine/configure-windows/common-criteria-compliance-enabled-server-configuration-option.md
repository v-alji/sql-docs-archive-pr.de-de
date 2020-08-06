---
title: Common Criteria-Konformität aktiviert (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6722d05351b8b9e80240abb4edef0633a97b6da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608854"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a><span data-ttu-id="e02b0-102">Common Criteria-Kompatibilität aktiviert (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="e02b0-102">common criteria compliance enabled Server Configuration Option</span></span>
  <span data-ttu-id="e02b0-103">Mit der Option Common Criteria-Kompatibilität aktiviert werden die folgenden Elemente aktiviert, die für die Common Criteria erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e02b0-103">The common criteria compliance enabled option enables the following elements that are required for the Common Criteria.</span></span>  
  
|<span data-ttu-id="e02b0-104">Kriterien</span><span class="sxs-lookup"><span data-stu-id="e02b0-104">Criteria</span></span>|<span data-ttu-id="e02b0-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e02b0-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e02b0-106">RIP (Residual Information Protection)</span><span class="sxs-lookup"><span data-stu-id="e02b0-106">Residual Information Protection (RIP)</span></span>|<span data-ttu-id="e02b0-107">Bei RIP muss eine Speicherbelegung mit einem bekannten Muster von Bits überschrieben werden, bevor der Arbeitsspeicher wieder einer neuen Quelle zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e02b0-107">RIP requires a memory allocation to be overwritten with a known pattern of bits before memory is reallocated to a new resource.</span></span> <span data-ttu-id="e02b0-108">Durch Einhalten des RIP-Standards kann die Sicherheit erhöht werden. Beim Überschreiben der Speicherbelegung kann jedoch die Leistung beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="e02b0-108">Meeting the RIP standard can contribute to improved security; however, overwriting the memory allocation can slow performance.</span></span> <span data-ttu-id="e02b0-109">Das Überschreiben wird erst ausgeführt, nachdem die Option Common Criteria-Kompatibilität aktiviert aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="e02b0-109">After the common criteria compliance enabled option is enabled, the overwriting occurs.</span></span>|  
|<span data-ttu-id="e02b0-110">Die Möglichkeit zum Anzeigen von Anmeldestatistiken</span><span class="sxs-lookup"><span data-stu-id="e02b0-110">The ability to view login statistics</span></span>|<span data-ttu-id="e02b0-111">Die Anmeldungsüberwachung wird erst aktiviert, nachdem die Option Common Criteria-Kompatibilität aktiviert aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="e02b0-111">After the common criteria compliance enabled option is enabled, login auditing is enabled.</span></span> <span data-ttu-id="e02b0-112">Immer wenn sich ein Benutzer erfolgreich bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]anmeldet, werden Informationen zum Zeitpunkt der letzten erfolgreichen Anmeldung, zum Zeitpunkt der letzten erfolglosen Anmeldung sowie zur Anzahl der Versuche zwischen dem Zeitpunkt der letzten erfolgreichen Anmeldung und dem der aktuellen Anmeldung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e02b0-112">Each time a user successfully logs in to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], information about the last successful login time, the last unsuccessful login time, and the number of attempts between the last successful and current login times is made available.</span></span> <span data-ttu-id="e02b0-113">Diese Anmeldestatistiken können angezeigt werden, indem die dynamische Verwaltungssicht [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="e02b0-113">These login statistics can be viewed by querying the [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) dynamic management view.</span></span>|  
|<span data-ttu-id="e02b0-114">DENY auf Tabellenebene sollte nicht durch GRANT auf Spaltenebene außer Kraft gesetzt werden</span><span class="sxs-lookup"><span data-stu-id="e02b0-114">That column GRANT should not override table DENY</span></span>|<span data-ttu-id="e02b0-115">Nachdem die Option Common Criteria-Kompatibilität aktiviert aktiviert wurde, hat DENY auf Tabellenebene Vorrang vor GRANT auf Spaltenebene.</span><span class="sxs-lookup"><span data-stu-id="e02b0-115">After the common criteria compliance enabled option is enabled, a table-level DENY takes precedence over a column-level GRANT.</span></span> <span data-ttu-id="e02b0-116">Wenn die Option nicht aktiviert ist, hat GRANT auf Spaltenebene Vorrang vor DENY auf Tabellenebene.</span><span class="sxs-lookup"><span data-stu-id="e02b0-116">When the option is not enabled, a column-level GRANT takes precedence over a table-level DENY.</span></span>|  
  
 <span data-ttu-id="e02b0-117">Die Option „Common Criteria-Kompatibilität aktiviert“ ist eine erweiterte Option.</span><span class="sxs-lookup"><span data-stu-id="e02b0-117">The common criteria compliance enabled option is an advanced option.</span></span> <span data-ttu-id="e02b0-118">Allgemeine Kriterien werden nur für die Enterprise Edition und die Datacenter Edition ausgewertet und zertifiziert.</span><span class="sxs-lookup"><span data-stu-id="e02b0-118">Common criteria is only evaluated and certified for the Enterprise edition and Datacenter edition.</span></span> <span data-ttu-id="e02b0-119">Informationen zum aktuellen Status der Common Criteria-Zertifizierung finden Sie auf der Website [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) (in Englisch).</span><span class="sxs-lookup"><span data-stu-id="e02b0-119">For the latest status of common criteria certification, see the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e02b0-120">Zusätzlich zur Aktivierung der Option Common Criteria-Kompatibilität aktiviert müssen Sie ein Skript herunterladen und ausführen, mit dem die Konfiguration von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Kompatibilität mit der Common Criteria-Auswertungssicherungsstufe 4+ (EAL4+) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e02b0-120">In addition to enabling the common criteria compliance enabled option, you also must download and run a script that finishes configuring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to comply with Common Criteria Evaluation Assurance Level 4+ (EAL4+).</span></span> <span data-ttu-id="e02b0-121">Sie können dieses Skript von der Website [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) (in Englisch) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e02b0-121">You can download this script from the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
 <span data-ttu-id="e02b0-122">Wenn Sie die Einstellung mithilfe der gespeicherten Systemprozedur sp_configure ändern, können Sie die Option Common Criteria-Kompatibilität aktiviert nur ändern, wenn für Erweiterte Optionen anzeigen der Wert 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e02b0-122">If you are using the sp_configure system stored procedure to change the setting, you can change common criteria compliance enabled only when show advanced options is set to 1.</span></span> <span data-ttu-id="e02b0-123">Diese Einstellung wird wirksam, nachdem der Server neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="e02b0-123">The setting takes effect after the server is restarted.</span></span> <span data-ttu-id="e02b0-124">Die möglichen Werte lauten 0 und 1:</span><span class="sxs-lookup"><span data-stu-id="e02b0-124">The possible values are 0 and 1:</span></span>  
  
-   <span data-ttu-id="e02b0-125">Mit 0 wird angegeben, dass die Common Criteria-Kompatibilität nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e02b0-125">0 indicates that common criteria compliance is not enabled.</span></span> <span data-ttu-id="e02b0-126">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="e02b0-126">This is the default.</span></span>  
  
-   <span data-ttu-id="e02b0-127">Mit 1 wird angegeben, dass die Common Criteria-Kompatibilität aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e02b0-127">1 indicates that common criteria compliance is enabled.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e02b0-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e02b0-128">Examples</span></span>  
 <span data-ttu-id="e02b0-129">Im folgenden Beispiel wird die Common Criteria-Kompatibilität aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e02b0-129">The following example enables common criteria compliance.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e02b0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e02b0-130">See Also</span></span>  
 [<span data-ttu-id="e02b0-131">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e02b0-131">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
