---
title: Ungültiger Named Pipe Name kann das Upgrade blockieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- invalid named pipes [SQL Server]
- named pipes
ms.assetid: 58c2199c-4fdf-4d43-ac1c-842703344b75
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bacfd3d097d7cccb0a5780328c4db95dc5afc733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724390"
---
# <a name="invalid-named-pipe-name-can-block-upgrade"></a><span data-ttu-id="52957-102">Ungültiger Named Pipe-Name kann Upgrade blockieren</span><span class="sxs-lookup"><span data-stu-id="52957-102">Invalid named pipe name can block upgrade</span></span>
  <span data-ttu-id="52957-103">Das Upgrade schlägt fehl, wenn das Named Pipes-Protokoll falsch konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="52957-103">Upgrade fails if the named pipes protocol is incorrectly configured.</span></span>  
  
## <a name="component"></a><span data-ttu-id="52957-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="52957-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="52957-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="52957-105">Description</span></span>  
 <span data-ttu-id="52957-106">Während des Upgrades startet das Setup Programm die [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] Instanz mit Shared Memory-Unterstützung, einer Named Pipe, die nur lokale Verbindungen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="52957-106">During upgrade, the Setup program starts the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] instance with shared memory support, a named pipe that only accepts local connections.</span></span> <span data-ttu-id="52957-107">Wenn der auf dem Server angegebene Pipename nicht leer ist, muss er mit der Zeichenfolge " \\ \\ .\pipe" beginnen, \\ um gültig zu sein.</span><span class="sxs-lookup"><span data-stu-id="52957-107">If the pipe name specified on the server is not blank, it must begin with the string "\\\\.\pipe\\" to be valid.</span></span> <span data-ttu-id="52957-108">Wenn der Named Pipe-Name nicht gültig ist, startet [!INCLUDE[ssDE](../../includes/ssde-md.md)] nicht, und das Setup schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="52957-108">If the pipe name is not valid, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will not start, and setup will fail.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="52957-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="52957-109">Corrective Action</span></span>  
 <span data-ttu-id="52957-110">Verwenden Sie das \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Netzwerk Hilfsprogramm\*\* , um einen gültigen Pipenamen anzugeben, und führen Sie dann das Setup aus.</span><span class="sxs-lookup"><span data-stu-id="52957-110">Use the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Utility** to supply a valid pipe name, and then run Setup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52957-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52957-111">See Also</span></span>  
 <span data-ttu-id="52957-112">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="52957-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="52957-113">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="52957-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
