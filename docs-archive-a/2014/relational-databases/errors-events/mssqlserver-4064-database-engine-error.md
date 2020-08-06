---
title: MSSQLSERVER_4064 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621512"
---
# <a name="mssqlserver_4064"></a><span data-ttu-id="3008c-102">MSSQLSERVER_4064</span><span class="sxs-lookup"><span data-stu-id="3008c-102">MSSQLSERVER_4064</span></span>
    
## <a name="details"></a><span data-ttu-id="3008c-103">Details</span><span class="sxs-lookup"><span data-stu-id="3008c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3008c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3008c-104">Product Name</span></span>|<span data-ttu-id="3008c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3008c-105">SQL Server</span></span>|  
|<span data-ttu-id="3008c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3008c-106">Event ID</span></span>|<span data-ttu-id="3008c-107">4064</span><span class="sxs-lookup"><span data-stu-id="3008c-107">4064</span></span>|  
|<span data-ttu-id="3008c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3008c-108">Event Source</span></span>|<span data-ttu-id="3008c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3008c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3008c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="3008c-110">Component</span></span>|<span data-ttu-id="3008c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3008c-111">SQLEngine</span></span>|  
|<span data-ttu-id="3008c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="3008c-112">Symbolic Name</span></span>|<span data-ttu-id="3008c-113">DB_UFAIL_FATAL</span><span class="sxs-lookup"><span data-stu-id="3008c-113">DB_UFAIL_FATAL</span></span>|  
|<span data-ttu-id="3008c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3008c-114">Message Text</span></span>|<span data-ttu-id="3008c-115">Die Standarddatenbank des Benutzers kann nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="3008c-115">Cannot open user default database.</span></span> <span data-ttu-id="3008c-116">Fehler bei der Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="3008c-116">Login failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3008c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3008c-117">Explanation</span></span>  
 <span data-ttu-id="3008c-118">Der SQL Server-Anmeldename konnte aufgrund eines Problems mit der Standarddatenbank keine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="3008c-118">The SQL Server login was unable to connect because of a problem with its default database.</span></span> <span data-ttu-id="3008c-119">Entweder ist die Datenbank ungültig, oder der Anmeldename besitzt keine CONNECT-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3008c-119">Either the database itself is invalid or the login lacks CONNECT permission on the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3008c-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3008c-120">User Action</span></span>  
 <span data-ttu-id="3008c-121">Ändern Sie mit ALTER LOGIN die Standarddatenbank für den Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="3008c-121">Use ALTER LOGIN to change the login's default database.</span></span> <span data-ttu-id="3008c-122">Gewähren Sie dem Anmeldenamen eine CONNECT-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="3008c-122">Grant CONNECT permission to the login.</span></span>  
  
  
