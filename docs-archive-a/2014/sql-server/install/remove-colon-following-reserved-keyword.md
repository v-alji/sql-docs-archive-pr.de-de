---
title: Doppelpunkt nach reserviertem Schlüsselwort entfernen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reserved keywords
ms.assetid: 4f23f7e4-7b4d-4e19-86c9-7527bb8b107d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fc6882439338509a3c716129d9504f209ab1e555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726493"
---
# <a name="remove-colon-following-reserved-keyword"></a><span data-ttu-id="daf1d-102">Entfernen des Doppelpunkts hinter einem reservierten Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="daf1d-102">Remove colon following reserved keyword</span></span>
  <span data-ttu-id="daf1d-103">Der Upgrade Advisor hat ein Skript erkannt, das einen Doppelpunkt (:) hinter einem reservierten Schlüsselwort enthält.</span><span class="sxs-lookup"><span data-stu-id="daf1d-103">The Upgrade Advisor detected a script that contains a colon (:) following a reserved keyword.</span></span> <span data-ttu-id="daf1d-104">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wurde diese Syntax ignoriert, und die Anweisungen wurden erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="daf1d-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this syntax is ignored and the statements execute successfully.</span></span> <span data-ttu-id="daf1d-105">Jetzt führt diese Syntax zum Fehlschlagen der Anweisung, wenn der Datenbank-Kompatibilitätsmodus auf 100 oder höher festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="daf1d-105">Now, this syntax causes the statement to fail when the database compatibility mode is set to 100 or later.</span></span>  
  
 <span data-ttu-id="daf1d-106">Benutzerdatenbanken behalten ihren Kompatibilitätsmodus bei.</span><span class="sxs-lookup"><span data-stu-id="daf1d-106">User databases maintain their compatibility mode.</span></span>  
  
## <a name="component"></a><span data-ttu-id="daf1d-107">Komponente</span><span class="sxs-lookup"><span data-stu-id="daf1d-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="daf1d-108">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="daf1d-108">Corrective Action</span></span>  
 <span data-ttu-id="daf1d-109">Bevor Sie zum Datenbank-Kompatibilitätsmodus 100 oder höher wechseln, ändern Sie die Skripts, indem Sie Doppelpunkte hinter reservierten Schlüsselwörtern entfernen.</span><span class="sxs-lookup"><span data-stu-id="daf1d-109">Before you change the database compatibility mode to 100 or later, modify your scripts by removing colons that follow reserved keywords.</span></span> <span data-ttu-id="daf1d-110">Weitere Informationen finden Sie unter "sp_dbcmptlevel" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="daf1d-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf1d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daf1d-111">See Also</span></span>  
 <span data-ttu-id="daf1d-112">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="daf1d-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="daf1d-113">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="daf1d-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
