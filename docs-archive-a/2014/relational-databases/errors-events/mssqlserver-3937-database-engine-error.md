---
title: MSSQLSERVER_3937 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3937 (Database Engine error)
ms.assetid: 312d5bbe-c8de-42db-af4b-4ccb448ce6ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac466e6eb50ad4b7a8848a1159963cb0fd35e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699627"
---
# <a name="mssqlserver_3937"></a><span data-ttu-id="562c9-102">MSSQLSERVER_3937</span><span class="sxs-lookup"><span data-stu-id="562c9-102">MSSQLSERVER_3937</span></span>
    
## <a name="details"></a><span data-ttu-id="562c9-103">Details</span><span class="sxs-lookup"><span data-stu-id="562c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="562c9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="562c9-104">Product Name</span></span>|<span data-ttu-id="562c9-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="562c9-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="562c9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="562c9-106">Event ID</span></span>|<span data-ttu-id="562c9-107">3937</span><span class="sxs-lookup"><span data-stu-id="562c9-107">3937</span></span>|  
|<span data-ttu-id="562c9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="562c9-108">Event Source</span></span>|<span data-ttu-id="562c9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="562c9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="562c9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="562c9-110">Component</span></span>|<span data-ttu-id="562c9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="562c9-111">SQLEngine</span></span>|  
|<span data-ttu-id="562c9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="562c9-112">Symbolic Name</span></span>|<span data-ttu-id="562c9-113">XACT_FILESTREAM_ROLLBACK_ERROR</span><span class="sxs-lookup"><span data-stu-id="562c9-113">XACT_FILESTREAM_ROLLBACK_ERROR</span></span>|  
|<span data-ttu-id="562c9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="562c9-114">Message Text</span></span>|<span data-ttu-id="562c9-115">Fehler beim Benachrichtigen des FILESTREAM-Filtertreibers über das Rollback einer Transaktion.</span><span class="sxs-lookup"><span data-stu-id="562c9-115">An error occurred while trying to notify the FILESTREAM filter driver that a transaction was rolled back.</span></span> <span data-ttu-id="562c9-116">Fehlercode: 0x%0x.</span><span class="sxs-lookup"><span data-stu-id="562c9-116">Error code: 0x%0x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="562c9-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="562c9-117">Explanation</span></span>  
 <span data-ttu-id="562c9-118">Beim Ausgeben einer Rollbackbenachrichtigung für eine Transaktion wurde vom RsFx-Treiber ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="562c9-118">An error was returned by the RsFx driver when issuing a rollback notification for a transaction.</span></span> <span data-ttu-id="562c9-119">Dieser Fehler kann auftreten, wenn nicht genügend Ressourcen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="562c9-119">This is probably caused by a resource shortage.</span></span> <span data-ttu-id="562c9-120">Hierdurch kann ein geringfügiger Speicherverlust im RsFx-Filtertreiber entstehen, jedoch nur bis zum Ende des sqlservr.exe-Prozesses, durch den die Transaktion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="562c9-120">This can cause a small memory leak in the RsFx filter driver, but this will be freed when the sqlservr.exe process that created the transaction exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="562c9-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="562c9-121">User Action</span></span>  
  
