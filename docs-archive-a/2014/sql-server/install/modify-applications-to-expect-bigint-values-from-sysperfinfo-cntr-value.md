---
title: Ändern Sie die Anwendungen so, dass bigint-Werte von sysperfinfo. cntr_value erwartet werden. Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sysperfinfo
- bigint values [SQL Server]
ms.assetid: b0345303-6e9a-4078-8148-6e1bce207b8c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 108a9b981debc95e182b16847c39a03d4b242088
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724377"
---
# <a name="modify-applications-to-expect-bigint-values-from-sysperfinfocntr_value"></a><span data-ttu-id="5d0e2-102">Ändern von Anwendungen, damit bigint-Werte von 'sysperfinfo.cntr_value' erwartet werden</span><span class="sxs-lookup"><span data-stu-id="5d0e2-102">Modify applications to expect bigint values from sysperfinfo.cntr_value</span></span>
  <span data-ttu-id="5d0e2-103">sysperfinfo gibt einen `bigint` Wert für die cntr_value Spalte zurück.</span><span class="sxs-lookup"><span data-stu-id="5d0e2-103">sysperfinfo returns a `bigint` value for the cntr_value column.</span></span>  
  
## <a name="component"></a><span data-ttu-id="5d0e2-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="5d0e2-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="5d0e2-105">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="5d0e2-105">Corrective Action</span></span>  
 <span data-ttu-id="5d0e2-106">Durch Ändern der Anwendungen, die sysperfinfo verwenden, können Sie sicherstellen, dass sie die `bigint`-Werte der cntr_value-Spalte verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="5d0e2-106">Modify applications that use sysperfinfo to ensure that they can handle the `bigint` values of the cntr_value column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d0e2-107">sysperfinfo ist eine Kompatibilitäts Ansicht.</span><span class="sxs-lookup"><span data-stu-id="5d0e2-107">sysperfinfo is a compatibility view.</span></span> <span data-ttu-id="5d0e2-108">Sie sollten stattdessen die dynamische Verwaltungssicht sys.dm_os_performance_counter verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d0e2-108">You should use the sys.dm_os_performance_counter dynamic management view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0e2-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d0e2-109">See Also</span></span>  
 <span data-ttu-id="5d0e2-110">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="5d0e2-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="5d0e2-111">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="5d0e2-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
