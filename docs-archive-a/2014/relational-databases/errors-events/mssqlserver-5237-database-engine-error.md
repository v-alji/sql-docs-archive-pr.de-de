---
title: MSSQLSERVER_5237 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620886"
---
# <a name="mssqlserver_5237"></a><span data-ttu-id="3f390-102">MSSQLSERVER_5237</span><span class="sxs-lookup"><span data-stu-id="3f390-102">MSSQLSERVER_5237</span></span>
    
## <a name="details"></a><span data-ttu-id="3f390-103">Details</span><span class="sxs-lookup"><span data-stu-id="3f390-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f390-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3f390-104">Product Name</span></span>|<span data-ttu-id="3f390-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f390-105">SQL Server</span></span>|  
|<span data-ttu-id="3f390-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3f390-106">Event ID</span></span>|<span data-ttu-id="3f390-107">5237</span><span class="sxs-lookup"><span data-stu-id="3f390-107">5237</span></span>|  
|<span data-ttu-id="3f390-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3f390-108">Event Source</span></span>|<span data-ttu-id="3f390-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3f390-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3f390-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="3f390-110">Component</span></span>|<span data-ttu-id="3f390-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3f390-111">SQLEngine</span></span>|  
|<span data-ttu-id="3f390-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="3f390-112">Symbolic Name</span></span>|<span data-ttu-id="3f390-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span><span class="sxs-lookup"><span data-stu-id="3f390-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span></span>|  
|<span data-ttu-id="3f390-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3f390-114">Message Text</span></span>|<span data-ttu-id="3f390-115">Fehler bei der rowsetübergreifenden DBCC-Überprüfung für das 'NAME'-Objekt (Objekt-ID O_ID) aufgrund eines internen Abfragefehlers.</span><span class="sxs-lookup"><span data-stu-id="3f390-115">DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f390-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3f390-116">Explanation</span></span>  
 <span data-ttu-id="3f390-117">Ein interner Fehler ist aufgetreten, weil DBCC die Abfrage zum Überprüfen indizierter Sichten nicht ausführen konnte.</span><span class="sxs-lookup"><span data-stu-id="3f390-117">An internal error resulted in DBCC not being able to execute the query to check indexed views.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f390-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3f390-118">User Action</span></span>  
 <span data-ttu-id="3f390-119">Führen Sie den DBCC-Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3f390-119">Rerun the DBCC command.</span></span>  
  
  
