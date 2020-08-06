---
title: Problembehandlung von proxybasierten Multiserveraufträgen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19de975ef5e1f22c93cec72a5014a01da5b03dd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699147"
---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a><span data-ttu-id="7a58f-102">Problembehandlung von proxybasierten Multiserveraufträgen</span><span class="sxs-lookup"><span data-stu-id="7a58f-102">Troubleshoot Multiserver Jobs That Use Proxies</span></span>
  <span data-ttu-id="7a58f-103">Verteilte Aufträge mit Schritten, die einem Proxy zugeordnet sind, werden unter dem Kontext des Proxykontos auf dem Zielserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a58f-103">Distributed jobs whose steps are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="7a58f-104">Wenn Auftragsschritte, die Proxykonten verwenden, beim Herunterladen vom Masterserver einen Fehler erzeugen, überprüfen Sie die **error_message** -Spalte in der **sysdownloadlist** -Tabelle der **msdb** -Datenbank auf folgende Fehlermeldungen:</span><span class="sxs-lookup"><span data-stu-id="7a58f-104">If job steps that use proxy accounts fail when downloaded from the master server, check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="7a58f-105">"Für den Auftragsschritt ist ein Proxykonto erforderlich, das Proxyabgleichen ist auf dem Zielserver aber deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="7a58f-105">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="7a58f-106">Um diesen Fehler zu beheben, legen Sie den Wert für **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft SQL Server\MSSQL.** _ \<n_> **\Sqlserveragent\allowdownloader-djobstomatchproxyname** Registrierungs Unterschlüssel auf **1 (true)**.</span><span class="sxs-lookup"><span data-stu-id="7a58f-106">To resolve this error, set the **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.**_\<n_>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** registry subkey to **1 (true)**.</span></span> <span data-ttu-id="7a58f-107">Dieser Unterschlüssel ist standardmäßig auf **0** () festgelegt `false` .</span><span class="sxs-lookup"><span data-stu-id="7a58f-107">By default, this subkey is set to **0** (`false`).</span></span> <span data-ttu-id="7a58f-108">Der Wert von **MSSQL.**\<*n*></span><span class="sxs-lookup"><span data-stu-id="7a58f-108">The value of **MSSQL.**\<*n*></span></span> <span data-ttu-id="7a58f-109">ist der Instanzname. z. b. **MSSQL. 1** oder **MSSQL. 3**.</span><span class="sxs-lookup"><span data-stu-id="7a58f-109">is the instance name; for example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
-   <span data-ttu-id="7a58f-110">"Proxy nicht gefunden."</span><span class="sxs-lookup"><span data-stu-id="7a58f-110">"Proxy not found."</span></span>  
  
     <span data-ttu-id="7a58f-111">Zum Beheben dieses Fehlers stellen Sie sicher, dass auf dem Zielserver ein Proxykonto vorhanden ist, das den gleichen Namen wie das Proxykonto des Masterservers hat, unter dem der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7a58f-111">To resolve this error, make sure a proxy account exists on the target server with the same name as the master server proxy account under which the job step runs.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a58f-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a58f-112">See Also</span></span>  
 [<span data-ttu-id="7a58f-113">Erstellen einer Multiserverumgebung</span><span class="sxs-lookup"><span data-stu-id="7a58f-113">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
  
  
