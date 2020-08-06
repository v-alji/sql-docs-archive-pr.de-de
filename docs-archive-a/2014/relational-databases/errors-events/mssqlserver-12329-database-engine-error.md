---
title: MSSQLSERVER_12329 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7576e32946ce0a453637273c449bbff20e5b6fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618044"
---
# <a name="mssqlserver_12329"></a><span data-ttu-id="01b61-102">MSSQLSERVER_12329</span><span class="sxs-lookup"><span data-stu-id="01b61-102">MSSQLSERVER_12329</span></span>
    
## <a name="details"></a><span data-ttu-id="01b61-103">Details</span><span class="sxs-lookup"><span data-stu-id="01b61-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01b61-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="01b61-104">Product Name</span></span>|<span data-ttu-id="01b61-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="01b61-105">SQL Server</span></span>|  
|<span data-ttu-id="01b61-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="01b61-106">Event ID</span></span>|<span data-ttu-id="01b61-107">12329</span><span class="sxs-lookup"><span data-stu-id="01b61-107">12329</span></span>|  
|<span data-ttu-id="01b61-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="01b61-108">Event Source</span></span>|<span data-ttu-id="01b61-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="01b61-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="01b61-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="01b61-110">Component</span></span>|<span data-ttu-id="01b61-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="01b61-111">SQLEngine</span></span>|  
|<span data-ttu-id="01b61-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="01b61-112">Symbolic Name</span></span>|<span data-ttu-id="01b61-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="01b61-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span></span>|  
|<span data-ttu-id="01b61-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="01b61-114">Message Text</span></span>|<span data-ttu-id="01b61-115">Die Datentypen char(n) und varchar(n), die Sortierungen mit einer anderen Codepage als 1252 verwenden, werden bei *construct* nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01b61-115">The data types char(n) and varchar(n) using a collation that has a code page other than 1252 are not supported with  *construct*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01b61-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="01b61-116">Explanation</span></span>  
 <span data-ttu-id="01b61-117">Verwenden Sie die Datentypen char(n) und varchar(n) nicht mit Sortierungen, die eine andere Codepage als 1252 verwenden.</span><span class="sxs-lookup"><span data-stu-id="01b61-117">Do not use the data types char(n) and varchar(n) using a collation that has a code page other than 1252.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01b61-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="01b61-118">User Action</span></span>  
 <span data-ttu-id="01b61-119">Die folgende unerwartete Situation kann zu diesem Fehler führen:</span><span class="sxs-lookup"><span data-stu-id="01b61-119">One unexpected situation that can generate this error is:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
 <span data-ttu-id="01b61-120">Verwenden Sie stattdessen:</span><span class="sxs-lookup"><span data-stu-id="01b61-120">Use this instead:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  
  
