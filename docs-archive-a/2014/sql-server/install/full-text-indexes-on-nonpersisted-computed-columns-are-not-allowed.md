---
title: Volltextindizes für nicht persistente berechnete Spalten sind nicht zulässig | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: cba737f7-b187-47d0-8458-23dc18d18aca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de153d45e2f652bfea6e9dce68428af84be68b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630501"
---
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a><span data-ttu-id="9da5a-102">Volltextindizes sind für nicht permanente berechnete Spalten nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="9da5a-102">Full-text indexes on nonpersisted, computed columns are not allowed</span></span>
  <span data-ttu-id="9da5a-103">Das Erstellen von Volltextindizes für nicht deterministische und unpräzise berechnete Spalten ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9da5a-103">You cannot create full-text indexes on nondeterministic and imprecise computed columns.</span></span> <span data-ttu-id="9da5a-104">Solche Spalten können nicht als Typspalten bzw. nicht als Volltextschlüsselspalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da5a-104">Such columns cannot be used as type columns or as full-text key columns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9da5a-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9da5a-105">Description</span></span>  
 <span data-ttu-id="9da5a-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] kann ein Volltextindex mit einer nicht deterministischen und unpräzise berechneten Spalte als Typspalte oder als Volltextschlüsselspalte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9da5a-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a full-text index can be created by using a nondeterministic and imprecise computed column as the type column or the full-text key column.</span></span> <span data-ttu-id="9da5a-107">Dies wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9da5a-107">This functionality is not supported.</span></span> <span data-ttu-id="9da5a-108">Beim Upgrade werden ältere, nicht kompatible und nicht unterstützte Volltextindizes deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9da5a-108">When you upgrade, older, incompatible, and unsupported full-text indexes are disabled.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9da5a-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="9da5a-109">Corrective Action</span></span>  
 <span data-ttu-id="9da5a-110">Um diese Volltextindizes zu aktivieren, ändern Sie die Spaltendefinitionen, sodass die Spalten deterministisch und präzise sind.</span><span class="sxs-lookup"><span data-stu-id="9da5a-110">To enable these full-text indexes, modify the column definitions so that the columns are deterministic and precise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da5a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9da5a-111">See Also</span></span>  
 [<span data-ttu-id="9da5a-112">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="9da5a-112">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
