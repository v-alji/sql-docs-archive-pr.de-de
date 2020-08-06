---
title: Suchen von Text mit Platzhaltern
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
author: rothja
ms.author: jroth
ms.openlocfilehash: cc4e24c3dce73e46350b0c106429c42ab5f0edb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622520"
---
# <a name="search-text-with-wildcards"></a><span data-ttu-id="d6813-102">Suchen von Text mit Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="d6813-102">Search Text with Wildcards</span></span>
  <span data-ttu-id="d6813-103">Mit den folgenden Ausdrücken lassen sich Zeichen oder Ziffern im Feld **Suchen nach** im Dialogfeld [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Suchen und Ersetzen**in** ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d6813-103">The following expressions can replace characters or digits in the **Find what** field of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.</span></span>  
  
#### <a name="to-search-using-wildcards"></a><span data-ttu-id="d6813-104">So suchen Sie mit Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="d6813-104">To search using wildcards</span></span>  
  
1.  <span data-ttu-id="d6813-105">Um die Verwendung von Platzhaltern im Feld **Suchen nach** bei der Schnellsuche, **In Dateien suchen**, **Schnellersetzung**oder **In Dateien ersetzen** zu aktivieren, wählen Sie unter **Suchoptionen** nacheinander **Verwenden** und dann **Platzhalter**aus.</span><span class="sxs-lookup"><span data-stu-id="d6813-105">To enable the use of wildcards in the **Find what** field during Quick Find, **Find in Files**, **Quick Replace**, or **Replace in Files** operations, select the **Use** option under **Find Options** and then choose **Wildcards**.</span></span>  
  
2.  <span data-ttu-id="d6813-106">Die dreieckige Schaltfläche für die **Verweisliste** neben dem Feld **Suchen nach** ist jetzt aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d6813-106">The triangular **Reference List** button next to the **Find what** field then becomes available.</span></span> <span data-ttu-id="d6813-107">Klicken Sie auf diese Schaltfläche, um eine Liste der verfügbaren Platzhalter anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6813-107">Click this button to display a list of the available wildcards.</span></span> <span data-ttu-id="d6813-108">Wenn Sie ein Element aus der Liste für die **Verweisliste** auswählen, wird es in die **Suchen nach** -Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="d6813-108">When you choose any item from the **Reference List**, it is inserted into the **Find what** string.</span></span>  
  
 <span data-ttu-id="d6813-109">Die folgende Tabelle enthält eine Beschreibung der Platzhalter, die unter **Verweisliste**verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d6813-109">The following table describes the wildcards available in the **Reference List**.</span></span>  
  
|<span data-ttu-id="d6813-110">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="d6813-110">Expression</span></span>|<span data-ttu-id="d6813-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6813-111">Syntax</span></span>|<span data-ttu-id="d6813-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d6813-112">Description</span></span>|  
|----------------|------------|-----------------|  
|<span data-ttu-id="d6813-113">Ein einzelnes Zeichen</span><span class="sxs-lookup"><span data-stu-id="d6813-113">Any single character</span></span>|<span data-ttu-id="d6813-114">?</span><span class="sxs-lookup"><span data-stu-id="d6813-114">?</span></span>|<span data-ttu-id="d6813-115">Entspricht einem beliebigen einzelnen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d6813-115">Matches any single character.</span></span>|  
|<span data-ttu-id="d6813-116">Eine einzelne Ziffer</span><span class="sxs-lookup"><span data-stu-id="d6813-116">Any single digit</span></span>|#|<span data-ttu-id="d6813-117">Entspricht einer beliebigen einzelnen Ziffer.</span><span class="sxs-lookup"><span data-stu-id="d6813-117">Matches any single digit.</span></span> <span data-ttu-id="d6813-118">Beispiel: 7# entspricht Zahlen, die aus einer 7 bestehen, gefolgt von einer anderen Zahl, wie 71, nicht aber 17.</span><span class="sxs-lookup"><span data-stu-id="d6813-118">For example, 7# matches numbers that include 7 followed by another number, such as 71, but not 17.</span></span>|  
|<span data-ttu-id="d6813-119">Zeichen außerhalb des Zeichensatzes</span><span class="sxs-lookup"><span data-stu-id="d6813-119">Characters not in set</span></span>|<span data-ttu-id="d6813-120">[!</span><span class="sxs-lookup"><span data-stu-id="d6813-120">[!</span></span> <span data-ttu-id="d6813-121">]</span><span class="sxs-lookup"><span data-stu-id="d6813-121">]</span></span>|<span data-ttu-id="d6813-122">Entspricht einem einzelnen Zeichen, das nicht im Zeichensatz angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d6813-122">Matches any one character that is not specified in the set.</span></span>|  
|<span data-ttu-id="d6813-123">Ein oder mehrere Zeichen</span><span class="sxs-lookup"><span data-stu-id="d6813-123">One or more characters</span></span>|*|<span data-ttu-id="d6813-124">Entspricht einem oder mehreren Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d6813-124">Matches any one or more characters.</span></span> <span data-ttu-id="d6813-125">Beispiel: new\* entspricht einem beliebigen Text mit der Buchstabenfolge "new", z. B. newfile.txt.</span><span class="sxs-lookup"><span data-stu-id="d6813-125">For example, new\* matches any text that includes "new", such as newfile.txt.</span></span>|  
|<span data-ttu-id="d6813-126">Zeichensatz</span><span class="sxs-lookup"><span data-stu-id="d6813-126">Set of characters</span></span>|<span data-ttu-id="d6813-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="d6813-127">[ ]</span></span>|<span data-ttu-id="d6813-128">Entspricht einem einzelnen Zeichen, das im Zeichensatz angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d6813-128">Matches any one of the characters specified in the set.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6813-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6813-129">See Also</span></span>  
 <span data-ttu-id="d6813-130">[Suchen und Ersetzen](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="d6813-130">[Search and Replace](search-and-replace.md) </span></span>  
 [<span data-ttu-id="d6813-131">Suchen von Text mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="d6813-131">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
