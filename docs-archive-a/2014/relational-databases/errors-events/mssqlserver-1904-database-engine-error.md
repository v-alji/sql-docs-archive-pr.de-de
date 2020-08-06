---
title: MSSQLSERVER_1904 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 568cfe7499c041c2ee6a8ac3698b31698171bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617076"
---
# <a name="mssqlserver_1904"></a><span data-ttu-id="52812-102">MSSQLSERVER_1904</span><span class="sxs-lookup"><span data-stu-id="52812-102">MSSQLSERVER_1904</span></span>
    
## <a name="details"></a><span data-ttu-id="52812-103">Details</span><span class="sxs-lookup"><span data-stu-id="52812-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52812-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="52812-104">Product Name</span></span>|<span data-ttu-id="52812-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="52812-105">SQL Server</span></span>|  
|<span data-ttu-id="52812-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="52812-106">Event ID</span></span>|<span data-ttu-id="52812-107">1904</span><span class="sxs-lookup"><span data-stu-id="52812-107">1904</span></span>|  
|<span data-ttu-id="52812-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="52812-108">Event Source</span></span>|<span data-ttu-id="52812-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="52812-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="52812-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="52812-110">Component</span></span>|<span data-ttu-id="52812-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="52812-111">SQLEngine</span></span>|  
|<span data-ttu-id="52812-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="52812-112">Symbolic Name</span></span>|<span data-ttu-id="52812-113">KEYCOUNT</span><span class="sxs-lookup"><span data-stu-id="52812-113">KEYCOUNT</span></span>|  
|<span data-ttu-id="52812-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="52812-114">Message Text</span></span>|<span data-ttu-id="52812-115">Das %S_MSG-Objekt '%.\*ls' in der '%.\*ls'-Tabelle weist %d Spaltennamen in der %S_MSG-Schlüsselliste auf.</span><span class="sxs-lookup"><span data-stu-id="52812-115">The %S_MSG '%.\*ls' on table '%.\*ls' has %d column names in %S_MSG key list.</span></span> <span data-ttu-id="52812-116">Die maximale Anzahl für Spaltenlisten von Index- oder Statistikschlüsseln beträgt % d.</span><span class="sxs-lookup"><span data-stu-id="52812-116">The maximum limit for index or statistics key column list is %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="52812-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="52812-117">Explanation</span></span>  
 <span data-ttu-id="52812-118">Die Schlüsselspaltenliste für den angegebenen Index bzw. die angegebenen Statistiken überschreitet die maximal zulässige Anzahl von Spalten.</span><span class="sxs-lookup"><span data-stu-id="52812-118">The key column list for the specified index or statistics exceeds the maximum number of columns allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="52812-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="52812-119">User Action</span></span>  
 <span data-ttu-id="52812-120">Ändern Sie die Schlüsselspaltenliste, sodass nur die maximal zulässige Anzahl von Spalten eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="52812-120">Modify the key column list to include no more than the specified maximum number of columns.</span></span>  
  
 <span data-ttu-id="52812-121">Ziehen Sie bei nicht gruppierten Indizes die Verwendung der INCLUDE-Klausel in der CREATE INDEX-Anweisung in Betracht, um dem Index Spalten als Nichtschlüsselspalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="52812-121">For nonclustered indexes, consider using the INCLUDE clause in the CREATE INDEX statement to add columns to the index as nonkey columns.</span></span> <span data-ttu-id="52812-122">Auf diese Weise können Sie vermeiden, dass die aktuelle Größenbeschränkung des Indexes von maximal 16 Schlüsselspalten überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="52812-122">This method avoids exceeding the current index size limitation of a maximum of 16 key columns.</span></span> <span data-ttu-id="52812-123">Weitere Informationen finden Sie unter [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="52812-123">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52812-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52812-124">See Also</span></span>  
 <span data-ttu-id="52812-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="52812-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="52812-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52812-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-statistics-transact-sql)  
  
  
