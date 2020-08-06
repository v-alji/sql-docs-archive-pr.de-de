---
title: WITH Rows wird in CREATE STATISTICS-Anweisungen im Kompatibilitätsmodus 90 oder höher nicht unterstützt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH ROWS in CREATE STATISTICS statement
ms.assetid: 197b2ecf-a1a3-4a3a-a523-a0ee919c1dde
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d28a05e7cd025e213e2cebdce9d582a9df446fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617383"
---
# <a name="with-rows-is-not-supported-in-create-statistics-statements-in-the-compatibility-mode-of-90-or-later"></a><span data-ttu-id="7a60a-102">Im Kompatibilitätsmodus 90 oder höher wird WITH ROWS in CREATE STATISTICS-Anweisungen nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="7a60a-102">WITH ROWS is not supported in CREATE STATISTICS statements in the compatibility mode of 90 or later</span></span>
  <span data-ttu-id="7a60a-103">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausführen und der Kompatibilitätsmodus auf 90 oder höher festgelegt ist, wird die Angabe von WITH ROWS in CREATE STATISTICS-Anweisungen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7a60a-103">Specifying WITH ROWS in CREATE STATISTICS statements is not supported when you run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set to the compatibility mode of 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7a60a-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="7a60a-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="7a60a-105">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="7a60a-105">Corrective Action</span></span>  
 <span data-ttu-id="7a60a-106">Ändern Sie CREATE STATISTICS-Anweisungen, die in Zeilen einschließen, indem Sie mit Stichproben *Nummern* Zeilen angeben oder andere Optionen angeben, die der dokumentierten Syntax entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7a60a-106">Modify CREATE STATISTICS statements that include WITH ROWS by specifying WITH SAMPLE *number* ROWS, or by specifying other options that comply with the documented syntax.</span></span> <span data-ttu-id="7a60a-107">Weitere Informationen hierzu finden Sie im Thema "CREATE STATISTICS (Transact-SQL) in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7a60a-107">For more information, see the topic "CREATE STATISTICS (Transact-SQL) in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a60a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a60a-108">See Also</span></span>  
 <span data-ttu-id="7a60a-109">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7a60a-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="7a60a-110">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="7a60a-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
