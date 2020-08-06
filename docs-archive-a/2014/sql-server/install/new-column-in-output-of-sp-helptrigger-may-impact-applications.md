---
title: Neue Spalte in der Ausgabe von sp_helptrigger kann sich auf Anwendungen auswirken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sp_helptrigger
ms.assetid: b7c42a8f-f2e0-4fa3-b046-3cf39c854c47
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b1f5e936843ed84a5c6b88e2f3685e7a4272bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621813"
---
# <a name="new-column-in-output-of-sp_helptrigger-may-impact-applications"></a><span data-ttu-id="ebca7-102">Neue Spalte in der Ausgabe von 'sp_helptrigger' kann möglicherweise Auswirkungen auf Anwendungen haben</span><span class="sxs-lookup"><span data-stu-id="ebca7-102">New column in output of sp_helptrigger may impact applications</span></span>
  <span data-ttu-id="ebca7-103">trigger_schemaias die letzte Spalte im Resultset zurück, das von der gespeicherten System Prozedur sp_helptrigger zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ebca7-103">trigger_schemaias the last column in the result set returned by the sp_helptrigger system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="ebca7-104">Um Informationen über Trigger zu erhalten, die für eine bestimmte Tabelle definiert wurden, starten Sie eine Abfrage der sys.triggers-Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="ebca7-104">To obtain information about triggers defined on a particular table, query the sys.triggers catalog view.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ebca7-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="ebca7-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="ebca7-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="ebca7-106">Corrective Action</span></span>  
 <span data-ttu-id="ebca7-107">Überprüfen Sie die Verwendung von sp_helptrigger in Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ebca7-107">Review the use of sp_helptrigger in applications.</span></span> <span data-ttu-id="ebca7-108">Sie müssen Ihre Anwendungen möglicherweise ändern, damit die zusätzliche Spalte hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebca7-108">You may need to modify your applications to accommodate the additional column.</span></span> <span data-ttu-id="ebca7-109">Alternativ können Sie auch die sys.triggers-Katalogsicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebca7-109">Alternatively, you can use the sys.triggers catalog view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebca7-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebca7-110">See Also</span></span>  
 <span data-ttu-id="ebca7-111">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="ebca7-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="ebca7-112">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="ebca7-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
