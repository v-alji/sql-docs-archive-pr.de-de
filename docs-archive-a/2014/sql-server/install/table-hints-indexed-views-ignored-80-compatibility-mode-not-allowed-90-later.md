---
title: Tabellen Hinweise in indizierten Sicht Definitionen werden im 80-Kompatibilitätsmodus ignoriert und sind im 90-Modus oder später nicht zulässig | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf3cb2b06dc477d93c8fd42312b4835ded42afb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720800"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a><span data-ttu-id="60c9a-102">Tabellenhinweise in indizierten Sichtdefinitionen werden im Kompatibilitätsmodus 80 ignoriert und sind im Modus 90 oder höher nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="60c9a-102">Table hints in indexed view definitions are ignored in 80 compatibility mode and are not allowed in 90 mode or later</span></span>
  <span data-ttu-id="60c9a-103">Tabellenhinweise in den Definitionen indizierter Sichten sind im Kompatibilitätsmodus 90 oder höher nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="60c9a-103">Table hints in the definitions of indexed views are not permitted in the compatibility mode of 90 or later.</span></span> <span data-ttu-id="60c9a-104">Weitere Informationen hierzu finden Sie in den folgenden Themen in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation: "Entwerfen von indizierten Sichten" "Erstellen von indizierten Sichten" und "Abfragehinweis ([!INCLUDE[tsql](../../includes/tsql-md.md)])".</span><span class="sxs-lookup"><span data-stu-id="60c9a-104">For more information, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online: "Designing Indexed Views," "Creating Indexed Views," and "Query Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])."</span></span>  
  
## <a name="component"></a><span data-ttu-id="60c9a-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="60c9a-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="60c9a-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="60c9a-106">Corrective Action</span></span>  
 <span data-ttu-id="60c9a-107">Tabellenhinweise müssen aus den Definitionen indizierter Sichten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="60c9a-107">Table hints must be removed from the definitions of indexed views.</span></span> <span data-ttu-id="60c9a-108">Unabhängig vom verwendeten Kompatibilitätsmodus empfehlen wir, dass Sie die Anwendung testen.</span><span class="sxs-lookup"><span data-stu-id="60c9a-108">Regardless of which compatibility mode is used, we recommend that you test the application.</span></span> <span data-ttu-id="60c9a-109">Indem Sie die Anwendung testen, können Sie sicherstellen, dass sie korrekt funktioniert, wenn indizierte Sichten erstellt, aktualisiert oder Abfragen zugeordnet werden oder wenn auf sie zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="60c9a-109">By testing the application, you can make sure it performs as expected when indexed views are created, updated, and accessed, including when indexed views are matched to queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c9a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60c9a-110">See Also</span></span>  
 <span data-ttu-id="60c9a-111">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="60c9a-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="60c9a-112">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="60c9a-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
