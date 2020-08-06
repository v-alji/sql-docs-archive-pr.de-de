---
title: Wörter Trennungen und Filter für die voll Text Suche wurden in SQL Server 2005 und SQL Server 2008 erheblich verbessert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 8d06bda9-0bbf-4baa-b270-07b1c1f640eb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d2e7d3b8da56b407d3937b05cd980c3f8a4eb0c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621851"
---
# <a name="full-text-search-word-breakers-and-filters-significantly-improved-in-sql-server-2005-and-sql-server-2008"></a><span data-ttu-id="bec66-102">Die Wörtertrennung und Filter der Volltextsuche wurden in SQL Server 2005 und SQL Server 2008 erheblich verbessert</span><span class="sxs-lookup"><span data-stu-id="bec66-102">Full-Text Search word breakers and filters significantly improved in SQL Server 2005 and SQL Server 2008</span></span>
  <span data-ttu-id="bec66-103">Die Wörtertrennung und die Filter haben sich deutlich geändert.</span><span class="sxs-lookup"><span data-stu-id="bec66-103">The word breakers and filters were significantly changed.</span></span> <span data-ttu-id="bec66-104">Es wurden zusätzliche Verbesserungen an der Wörtertrennung vorgenommen, einschließlich verbesserter Sprachabdeckung und Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="bec66-104">Additional improvements have been made to word breakers, including enhanced language coverage and reliability.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bec66-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bec66-105">Description</span></span>  
 <span data-ttu-id="bec66-106">Die von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Volltextsuche verwendete Wörtertrennung und ihre Filter wurden umfassend überarbeitet, um Verbesserungen in der Funktionalität und der Zuverlässigkeit zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="bec66-106">Word breakers and filters used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Full-Text Search have been significantly modified to achieve improvements in functionality and reliability.</span></span> <span data-ttu-id="bec66-107">In bestimmten Fällen können Änderungen an der Wörtertrennung beeinflussen, wie manche Daten mit Token versehen werden.</span><span class="sxs-lookup"><span data-stu-id="bec66-107">In some specific cases, changes to the word breakers can impact how some data is tokenized.</span></span> <span data-ttu-id="bec66-108">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] erstellte Token unterscheiden sich möglicherweise von früheren Token, die in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] oder [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bec66-108">Tokens created in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] may be different from earlier tokens created in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="bec66-109">Weitere Informationen zu Wörter Trennungen finden Sie unter [Konfigurieren und Verwalten von Wörter Trennungen und Wort](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md)Stamm Erkennungen für die Suche.</span><span class="sxs-lookup"><span data-stu-id="bec66-109">For information about word breakers, see [Configure and Manage Word Breakers and Stemmers for Search](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec66-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bec66-110">See Also</span></span>  
 [<span data-ttu-id="bec66-111">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="bec66-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
