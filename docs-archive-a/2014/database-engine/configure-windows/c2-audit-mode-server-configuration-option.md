---
title: C2-Überwachungsmodus (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], C2 Audit Mode option
- C2 auditing
- C2 Audit Mode option
- recording attempts
ms.assetid: 5a8d73a6-c4f6-4967-ba11-ecbcfc90b9cc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3407a2a94a43adb2d3d3b52994093d6ed0c2e684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724186"
---
# <a name="c2-audit-mode-server-configuration-option"></a><span data-ttu-id="6171a-102">C2-Überwachungsmodus (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="6171a-102">c2 audit mode Server Configuration Option</span></span>
  <span data-ttu-id="6171a-103">Der C2-Überwachungsmodus kann durch [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit der Option **c2 audit mode** in **sp_configure**konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6171a-103">C2 audit mode can be configured through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or with the **c2 audit mode** option in **sp_configure**.</span></span> <span data-ttu-id="6171a-104">Das Auswählen dieser Option konfiguriert den Server so, dass sowohl fehlgeschlagene als auch erfolgreiche Zugriffsversuche auf Anweisungen und Objekte aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="6171a-104">Selecting this option will configure the server to record both failed and successful attempts to access statements and objects.</span></span> <span data-ttu-id="6171a-105">Diese Informationen können Sie bei der Profilierung der Systemaktivität unterstützen und mögliche Verletzungen der Sicherheitsrichtlinien nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="6171a-105">This information can help you profile system activity and track possible security policy violations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="6171a-106">Der C2-Sicherheitsstandard wurde durch Common Criteria Certification ersetzt.</span><span class="sxs-lookup"><span data-stu-id="6171a-106">The C2 security standard has been superseded by Common Criteria Certification.</span></span> <span data-ttu-id="6171a-107">Weitere Informationen finden Sie unter [Common Criteria-Kompatibilität aktiviert (Serverkonfigurationsoption)](common-criteria-compliance-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="6171a-107">See the [common criteria compliance enabled Server Configuration Option](common-criteria-compliance-enabled-server-configuration-option.md).</span></span>  
  
## <a name="audit-log-file"></a><span data-ttu-id="6171a-108">Überwachungsprotokolldatei</span><span class="sxs-lookup"><span data-stu-id="6171a-108">Audit Log File</span></span>  
 <span data-ttu-id="6171a-109">Die C2-Überwachungsmodusdaten werden in einer Datei im Standarddatenverzeichnis der Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6171a-109">C2 audit mode data is saved in a file in the default data directory of the instance.</span></span> <span data-ttu-id="6171a-110">Wenn die Überwachungsprotokolldatei ihre maximale Größe von 200 Megabyte (MB) erreicht hat, erstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine neue Datei, schließt die alte Datei und schreibt alle neuen Überwachungsdatensätze in die neue Datei.</span><span class="sxs-lookup"><span data-stu-id="6171a-110">If the audit log file reaches its size limit of 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will create a new file, close the old file, and write all new audit records to the new file.</span></span> <span data-ttu-id="6171a-111">Dieser Prozess wird fortgesetzt, bis das Überwachungsdatenverzeichnis voll ist oder die Überwachung deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6171a-111">This process will continue until the audit data directory fills up or auditing is turned off.</span></span> <span data-ttu-id="6171a-112">Um den Status einer C2-Ablaufverfolgung zu bestimmen, fragen Sie die sys.traces-Katalogsicht ab.</span><span class="sxs-lookup"><span data-stu-id="6171a-112">To determine the status of a C2 trace, query the sys.traces catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6171a-113">Mit dem C2-Überwachungsmodus wird eine große Menge an Ereignisinformationen in der Protokolldatei gespeichert, die rasch anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="6171a-113">C2 audit mode saves a large amount of event information to the log file, which can grow quickly.</span></span> <span data-ttu-id="6171a-114">Wenn im Datenverzeichnis, in dem die Protokolle gespeichert werden, nicht mehr genügend Speicherplatz vorhanden ist, fährt sich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selbst herunter.</span><span class="sxs-lookup"><span data-stu-id="6171a-114">If the data directory in which logs are being saved runs out of space, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will shut itself down.</span></span> <span data-ttu-id="6171a-115">Wenn ein automatischer Start der Überwachung festgelegt ist, müssen Sie entweder die Instanz mit dem **-f** -Flag (das die Überwachung umgeht) neu starten oder zusätzlichen Speicherplatz für das Überwachungsprotokoll freigeben.</span><span class="sxs-lookup"><span data-stu-id="6171a-115">If auditing is set to start automatically, you must either restart the instance with the **-f** flag (which bypasses auditing), or free up additional disk space for the audit log.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="6171a-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6171a-116">Permissions</span></span>  
 <span data-ttu-id="6171a-117">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="6171a-117">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6171a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6171a-118">Example</span></span>  
 <span data-ttu-id="6171a-119">Im folgenden Beispiel wird der C2-Überwachungsmodus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6171a-119">The following example turns on C2 audit mode.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
sp_configure 'c2 audit mode', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6171a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6171a-120">See Also</span></span>  
 <span data-ttu-id="6171a-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6171a-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="6171a-122">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6171a-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="6171a-123">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6171a-123">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
