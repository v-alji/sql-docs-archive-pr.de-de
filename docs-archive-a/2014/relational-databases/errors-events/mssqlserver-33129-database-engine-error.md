---
title: MSSQLSERVER_33129 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7735889dce8bfc33e624115e8245f8a02f46b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617056"
---
# <a name="mssqlserver_33129"></a><span data-ttu-id="13a6b-102">MSSQLSERVER_33129</span><span class="sxs-lookup"><span data-stu-id="13a6b-102">MSSQLSERVER_33129</span></span>
    
## <a name="details"></a><span data-ttu-id="13a6b-103">Details</span><span class="sxs-lookup"><span data-stu-id="13a6b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13a6b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="13a6b-104">Product Name</span></span>|<span data-ttu-id="13a6b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="13a6b-105">SQL Server</span></span>|  
|<span data-ttu-id="13a6b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="13a6b-106">Event ID</span></span>|<span data-ttu-id="13a6b-107">33129</span><span class="sxs-lookup"><span data-stu-id="13a6b-107">33129</span></span>|  
|<span data-ttu-id="13a6b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="13a6b-108">Event Source</span></span>|<span data-ttu-id="13a6b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="13a6b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="13a6b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="13a6b-110">Component</span></span>|<span data-ttu-id="13a6b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="13a6b-111">SQLEngine</span></span>|  
|<span data-ttu-id="13a6b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="13a6b-112">Symbolic Name</span></span>|<span data-ttu-id="13a6b-113">SEC_CANNOT_DISABLE_WIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="13a6b-113">SEC_CANNOT_DISABLE_WIN_GROUP</span></span>|  
|<span data-ttu-id="13a6b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="13a6b-114">Message Text</span></span>|<span data-ttu-id="13a6b-115">Kann ALTER_LOGIN mit dem DISABLE-Argument nicht dazu verwenden, den Zugriff auf eine Windows-Gruppe zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="13a6b-115">Cannot use ALTER_LOGIN with the DISABLE argument to deny access to a Windows group.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="13a6b-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="13a6b-116">Explanation</span></span>  
 <span data-ttu-id="13a6b-117">Diese Meldung wird angezeigt, wenn Sie versuchen, den Anmeldenamen einer Windows-Gruppe zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="13a6b-117">This message occurs when attempting to disable the login of a Windows Group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13a6b-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="13a6b-118">User Action</span></span>  
 <span data-ttu-id="13a6b-119">Der Anmeldename einer Windows-Gruppe kann nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="13a6b-119">The login of a Windows Group cannot be disabled.</span></span> <span data-ttu-id="13a6b-120">Um die Zugriffsberechtigung einer Windows-Gruppe vorübergehend zu entfernen, heben Sie die CONNECT-Berechtigung des Anmeldenamens für die Windows-Gruppe mit REVOKE auf.</span><span class="sxs-lookup"><span data-stu-id="13a6b-120">To temporarily remove access permission granted to a Windows Group, REVOKE the CONNECT permission of the login for the Windows Group.</span></span> <span data-ttu-id="13a6b-121">Windows-Benutzer haben möglicherweise weiterhin über ihren individuellen Anmeldenamen oder eine andere Windows-Gruppe Zugriff.</span><span class="sxs-lookup"><span data-stu-id="13a6b-121">Windows users might still have access through their individual login or through another Windows Group.</span></span> <span data-ttu-id="13a6b-122">Im folgenden Beispiel wird die Verbindungsberechtigung für die Gruppe "Accounting" der Domäne WESTCOAST aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="13a6b-122">The following example revokes the connect permission to the Accounting Group of the WESTCOAST domain.</span></span>  
  
```sql  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
  
