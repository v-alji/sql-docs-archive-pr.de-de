---
title: MSSQL_ENG018456 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018456 error
ms.assetid: 3daa8144-d81f-445a-b6c3-4bb3e9fd1526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b05ca549781215e0c4f247110fee87f6def56f04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717968"
---
# <a name="mssql_eng018456"></a><span data-ttu-id="477a3-102">MSSQL_ENG018456</span><span class="sxs-lookup"><span data-stu-id="477a3-102">MSSQL_ENG018456</span></span>
    
## <a name="message-details"></a><span data-ttu-id="477a3-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="477a3-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="477a3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="477a3-104">Product Name</span></span>|<span data-ttu-id="477a3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="477a3-105">SQL Server</span></span>|  
|<span data-ttu-id="477a3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="477a3-106">Event ID</span></span>|<span data-ttu-id="477a3-107">18456</span><span class="sxs-lookup"><span data-stu-id="477a3-107">18456</span></span>|  
|<span data-ttu-id="477a3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="477a3-108">Event Source</span></span>|<span data-ttu-id="477a3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="477a3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="477a3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="477a3-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="477a3-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="477a3-111">Symbolic Name</span></span>||  
|<span data-ttu-id="477a3-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="477a3-112">Message Text</span></span>|<span data-ttu-id="477a3-113">Fehler bei der Anmeldung für den Benutzer '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="477a3-113">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="477a3-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="477a3-114">Explanation</span></span>  
 <span data-ttu-id="477a3-115">Der Fehler MSSQL_ENG018456 wird ausgelöst, wenn ein Anmeldeversuch einen Fehler erzeugt.</span><span class="sxs-lookup"><span data-stu-id="477a3-115">Error MSSQL_ENG018456 is raised whenever a login attempt fails.</span></span> <span data-ttu-id="477a3-116">Enthält die Fehlermeldung das Konto **distributor_admin** (Fehler bei der Anmeldung des Benutzers 'distributor_admin'.), liegt das Problem an einem Konto, das durch die Replikation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="477a3-116">If the error message includes the account **distributor_admin** (Login failed for user 'distributor_admin'.), the issue is with an account used by replication.</span></span> <span data-ttu-id="477a3-117">Die Replikation erstellt einen Remoteserver **repl_distributor**, der die Kommunikation zwischen dem Verteiler und dem Verleger ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="477a3-117">Replication creates a remote server, **repl_distributor**, which allows communication between the Distributor and Publisher.</span></span> <span data-ttu-id="477a3-118">Die Anmeldung **distributor_admin** wird diesem Remoteserver zugeordnet und muss ein gültiges Kennwort besitzen.</span><span class="sxs-lookup"><span data-stu-id="477a3-118">The login **distributor_admin** is associated with this remote server and must have a valid password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="477a3-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="477a3-119">User Action</span></span>  
 <span data-ttu-id="477a3-120">Stellen Sie sicher, dass Sie ein Kennwort für dieses Konto angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="477a3-120">Ensure that you have specified a password for this account.</span></span> <span data-ttu-id="477a3-121">Weitere Informationen finden Sie unter [Schützen des Verteilers](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="477a3-121">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477a3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="477a3-122">See Also</span></span>  
 [<span data-ttu-id="477a3-123">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="477a3-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
