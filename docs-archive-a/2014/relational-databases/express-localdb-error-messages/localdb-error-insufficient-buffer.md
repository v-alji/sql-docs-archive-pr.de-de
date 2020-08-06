---
title: LOCALDB_ERROR_INSUFFICIENT_BUFFER | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: ff67bda8-7e5c-4b06-8d7b-9985b6059a98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 934683cfca1a9a9c0596071824c21a0045e6ebab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622129"
---
# <a name="localdb_error_insufficient_buffer"></a><span data-ttu-id="d9062-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d9062-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>
    
## <a name="details"></a><span data-ttu-id="d9062-103">Details</span><span class="sxs-lookup"><span data-stu-id="d9062-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9062-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d9062-104">Product Name</span></span>|<span data-ttu-id="d9062-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d9062-105">SQL Server</span></span>|  
|<span data-ttu-id="d9062-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d9062-106">Event ID</span></span>|<span data-ttu-id="d9062-107">276</span><span class="sxs-lookup"><span data-stu-id="d9062-107">276</span></span>|  
|<span data-ttu-id="d9062-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d9062-108">Event Source</span></span>|<span data-ttu-id="d9062-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="d9062-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="d9062-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d9062-110">Component</span></span>|<span data-ttu-id="d9062-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="d9062-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="d9062-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d9062-112">Message Text</span></span>|<span data-ttu-id="d9062-113">Der an die API-Methode der lokalen Datenbankinstanz übergebene Puffer ist nicht groß genug.</span><span class="sxs-lookup"><span data-stu-id="d9062-113">The buffer passed to the Local Database instance API method has insufficient size.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d9062-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d9062-114">Explanation</span></span>  
 <span data-ttu-id="d9062-115">Der Eingabepuffer ist zu kurz. Abschneiden wurde nicht angefordert.</span><span class="sxs-lookup"><span data-stu-id="d9062-115">The input buffer is too short, and truncation was not requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9062-116">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d9062-116">User Action</span></span>  
 <span data-ttu-id="d9062-117">Stellen Sie einen Puffer von der angegebenen Größe bereit.</span><span class="sxs-lookup"><span data-stu-id="d9062-117">Provide a buffer of the specified size.</span></span>  
  
  
