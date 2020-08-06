---
title: Cursor Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC applications, cursors
- cursors [ODBC], types
- ODBC cursors, types
ms.assetid: 3a916cc7-f352-42cb-8b83-f78e06cef991
author: rothja
ms.author: jroth
ms.openlocfilehash: 6937dbb9ce42cd5631201e0c97be42b211742ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616076"
---
# <a name="cursor-types"></a><span data-ttu-id="c0b43-102">Cursortypen</span><span class="sxs-lookup"><span data-stu-id="c0b43-102">Cursor Types</span></span>
  <span data-ttu-id="c0b43-103">ODBC definiert vier Cursor Typen, die von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c0b43-103">ODBC defines four cursor types supported by Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="c0b43-104">Diese Cursor unterscheiden sich in ihrer Fähigkeit, Änderungen am Resultset und in den von Ihnen genutzten Ressourcen zu erkennen, wie z. b. Arbeitsspeicher und Speicherplatz in **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="c0b43-104">These cursors vary in their ability to detect changes to the result set and in the resources they consume, such as memory and space in **tempdb**.</span></span> <span data-ttu-id="c0b43-105">Ein Cursor kann Änderungen an Zeilen nur dann erkennen, wenn er versucht, diese Zeilen erneut abzurufen. Es gibt keine Möglichkeit, wie die Datenquelle den Cursor über Änderungen an den derzeit abgerufenen Zeilen informieren könnte.</span><span class="sxs-lookup"><span data-stu-id="c0b43-105">A cursor can detect changes to rows only when it tries to refetch those rows; there is no way for the data source to notify the cursor of changes to the currently fetched rows.</span></span> <span data-ttu-id="c0b43-106">Die Fähigkeit eines Cursors, Änderungen, die nicht durch den Cursor vorgenommen wurden, zu erkennen, hängt außerdem von der Transaktionsisolationsstufe ab.</span><span class="sxs-lookup"><span data-stu-id="c0b43-106">A cursor's ability to detect changes that were not made through the cursor is also influenced by the transaction isolation level.</span></span>  
  
 <span data-ttu-id="c0b43-107">Die vier von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützten ODBC-Cursortypen sind:</span><span class="sxs-lookup"><span data-stu-id="c0b43-107">These are the four ODBC cursor types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="c0b43-108">Vorwärtscursor unterstützen keine Bildläufe, sondern ausschließlich das serielle Abrufen von Zeilen vom Anfang bis zum Ende des Cursors.</span><span class="sxs-lookup"><span data-stu-id="c0b43-108">Forward-only cursors do not support scrolling; they only support fetching rows serially from the start to the end of the cursor.</span></span>  
  
-   <span data-ttu-id="c0b43-109">Statische Cursor werden in **tempdb** erstellt, wenn der Cursor geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="c0b43-109">Static cursors are built in **tempdb** when the cursor is opened.</span></span> <span data-ttu-id="c0b43-110">Das Resultset wird immer angezeigt, wenn der Cursor geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="c0b43-110">They always display the result set as it was when the cursor was opened.</span></span> <span data-ttu-id="c0b43-111">Änderungen an den Daten werden nicht wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="c0b43-111">They never reflect changes to the data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0b43-112">: Statische Cursor sind immer schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c0b43-112">static cursors are always read-only.</span></span> <span data-ttu-id="c0b43-113">Da ein statischer Server Cursor als Arbeits Tabelle in **tempdb**erstellt wird, darf die Größe des Cursorresultsets die maximale Zeilengröße nicht überschreiten, die von zulässig ist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0b43-113">Because a static server cursor is built as a work table in **tempdb**, the size of the cursor result set cannot exceed the maximum row size allowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c0b43-114">In einem keysetgesteuerten Cursor werden Mitgliedschaft und Reihenfolge der Zeilen beim Öffnen des Cursors festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c0b43-114">Keyset-driven cursors have the membership and order of rows in the result set fixed when the cursor is opened.</span></span> <span data-ttu-id="c0b43-115">Änderungen an Nichtschlüsselspalten sind durch den Cursor sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c0b43-115">Changes to nonkey columns are visible through the cursor.</span></span>  
  
-   <span data-ttu-id="c0b43-116">Dynamische Cursor sind das Gegenteil von statischen Cursorn.</span><span class="sxs-lookup"><span data-stu-id="c0b43-116">Dynamic cursors are the opposite of static cursors.</span></span> <span data-ttu-id="c0b43-117">Dynamische Cursor spiegeln alle Änderungen an den Zeilen in den Resultsets wider.</span><span class="sxs-lookup"><span data-stu-id="c0b43-117">Dynamic cursors reflect all changes made to the rows in their result set.</span></span> <span data-ttu-id="c0b43-118">Die Datenwerte, Reihenfolge und Mitgliedschaft der Zeilen im Resultset können sich bei jedem Abrufvorgang ändern.</span><span class="sxs-lookup"><span data-stu-id="c0b43-118">The data values, order, and membership of the rows in the result set can change on each fetch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b43-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0b43-119">See Also</span></span>  
 [<span data-ttu-id="c0b43-120">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b43-120">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
