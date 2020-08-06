---
title: Volltextindizes für Master-, tempdb-und Model-Datenbanken werden nicht unterstützt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: f7992965-42c1-4eb8-a7fb-afb38b67c740
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fbd5e3133ed87fed9bdaf6d668df62c6471df766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630502"
---
# <a name="full-text-indexes-on-master-tempdb-and-model-databases-are-not-supported"></a><span data-ttu-id="6feed-102">Volltextindizes werden für die Datenbanken 'master', 'tempdb' und 'model' nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="6feed-102">Full-text indexes on master, tempdb and model databases are not supported</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6feed-103">lässt keine Volltextindizes für Systemdatenbanken zu.</span><span class="sxs-lookup"><span data-stu-id="6feed-103">does not allow full-text indexes on any system database.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6feed-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6feed-104">Description</span></span>  
 <span data-ttu-id="6feed-105">Bei [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] wurden Volltextindizes für die Datenbanken master, tempdb und model unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6feed-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], full-text indexes were supported on the master, tempdb, and model databases.</span></span>  
  
 <span data-ttu-id="6feed-106">Alle voll Text Kataloge in den Datenbanken Master, tempdb und Model werden während des Upgrades entfernt.</span><span class="sxs-lookup"><span data-stu-id="6feed-106">Any full-text catalogs in the master, tempdb, and model databases are removed during the upgrade.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6feed-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6feed-107">See Also</span></span>  
 [<span data-ttu-id="6feed-108">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="6feed-108">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
