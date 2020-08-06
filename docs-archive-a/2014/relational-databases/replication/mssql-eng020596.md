---
title: MSSQL_ENG020596 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b1c61f3683442e0d474ff36a65c89446dbd7bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622581"
---
# <a name="mssql_eng020596"></a><span data-ttu-id="aedcd-102">MSSQL_ENG020596</span><span class="sxs-lookup"><span data-stu-id="aedcd-102">MSSQL_ENG020596</span></span>
    
## <a name="message-details"></a><span data-ttu-id="aedcd-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="aedcd-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aedcd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="aedcd-104">Product Name</span></span>|<span data-ttu-id="aedcd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aedcd-105">SQL Server</span></span>|  
|<span data-ttu-id="aedcd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="aedcd-106">Event ID</span></span>|<span data-ttu-id="aedcd-107">20596</span><span class="sxs-lookup"><span data-stu-id="aedcd-107">20596</span></span>|  
|<span data-ttu-id="aedcd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="aedcd-108">Event Source</span></span>|<span data-ttu-id="aedcd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aedcd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aedcd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="aedcd-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="aedcd-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="aedcd-111">Symbolic Name</span></span>||  
|<span data-ttu-id="aedcd-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="aedcd-112">Message Text</span></span>|<span data-ttu-id="aedcd-113">Nur '%s' und Mitglieder der db_owner-Rolle können den anonymen Agent löschen.</span><span class="sxs-lookup"><span data-stu-id="aedcd-113">Only '%s' or members of db_owner can drop the anonymous agent.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aedcd-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="aedcd-114">Explanation</span></span>  
 <span data-ttu-id="aedcd-115">Sie besitzen nicht die erforderlichen Berechtigungen, um den Agent für das anonyme Abonnement zu löschen.</span><span class="sxs-lookup"><span data-stu-id="aedcd-115">You do not have sufficient permissions to drop the agent for the anonymous subscription.</span></span> <span data-ttu-id="aedcd-116">Der Anmeldename, der zum Aufrufen von [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) verwendet wird, muss Mitglied der festen **sysadmin**-Serverrolle auf dem Verteiler bzw. Mitglied der festen **db_owner**-Datenbankrolle in der Verteilungsdatenbank sein, oder der Benutzer muss derjenige sein, der die erstmalige Ausführung des Agents initialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="aedcd-116">The login used when calling [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) must be a member of the **sysadmin** fixed server role at the Distributor or **db_owner** fixed database role in the distribution database, or the user must be the one that initiated the first run of the agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aedcd-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="aedcd-117">User Action</span></span>  
 <span data-ttu-id="aedcd-118">Melden Sie sich mit den entsprechenden Anmeldeinformationen an, und führen Sie **sp_dropanonymousagent**aus.</span><span class="sxs-lookup"><span data-stu-id="aedcd-118">Login with the appropriate credentials, and execute **sp_dropanonymousagent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedcd-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aedcd-119">See Also</span></span>  
 [<span data-ttu-id="aedcd-120">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="aedcd-120">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
