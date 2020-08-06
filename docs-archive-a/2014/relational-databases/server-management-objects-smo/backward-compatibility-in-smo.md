---
title: Abwärtskompatibilität in SMO | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 2f986436-aaf2-4eaf-9809-df849d97d4fb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73b6f4eebccf23850ccf08ec95ccb59dbc5c6293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617916"
---
# <a name="backward-compatibility-in-smo"></a><span data-ttu-id="dd163-102">Abwärtskompatibilität in SMO</span><span class="sxs-lookup"><span data-stu-id="dd163-102">Backward Compatibility in SMO</span></span>
  <span data-ttu-id="dd163-103">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] geschriebene SMO-Anwendungen können mithilfe von SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="dd163-103">SMO applications that were written using previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be recompiled by using SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="migrating-smo-applications"></a><span data-ttu-id="dd163-104">Migrieren von SMO-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="dd163-104">Migrating SMO Applications</span></span>  
 <span data-ttu-id="dd163-105">Verweise auf SMO-DLLs in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] müssen entfernt werden, während Verweise auf die in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] enthaltenen neuen SMO-DLLs eingeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="dd163-105">References to SMO dlls in older versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed, and references to the new SMO dlls that are provided with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be included.</span></span>  
  
 <span data-ttu-id="dd163-106">Sie müssen mindestens einen Verweis auf folgende Dateien einschließen:</span><span class="sxs-lookup"><span data-stu-id="dd163-106">Minimally, you would reference the following:</span></span>  
  
-   <span data-ttu-id="dd163-107">Microsoft.SqlServer.ConnectionInfo</span><span class="sxs-lookup"><span data-stu-id="dd163-107">Microsoft.SqlServer.ConnectionInfo</span></span>  
  
-   <span data-ttu-id="dd163-108">Microsoft.SqlServer.Smo</span><span class="sxs-lookup"><span data-stu-id="dd163-108">Microsoft.SqlServer.Smo</span></span>  
  
-   <span data-ttu-id="dd163-109">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="dd163-109">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
 <span data-ttu-id="dd163-110">Diese Dateien sind für Verbindungsklassen, SMO-Hilfsprogrammklassen und Foundation Classes erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd163-110">These files are required for connection classes, SMO utility classes, and foundation classes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd163-111">Die Datei SmoEnum.dll wurde entfernt. Folglich müssen Verweise darauf aus dem SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Projekt entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="dd163-111">SmoEnum.dll has been removed so references to it must be removed from the SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] project.</span></span>  
  
 <span data-ttu-id="dd163-112">Da sich die Namespaces ebenfalls geändert haben, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="dd163-112">The namespaces have also changed, so you can use the following:</span></span>  
  
##### <a name="for-visual-c"></a><span data-ttu-id="dd163-113">Für Visual C#</span><span class="sxs-lookup"><span data-stu-id="dd163-113">For Visual C#</span></span>  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
```  
  
##### <a name="for-visual-basic"></a><span data-ttu-id="dd163-114">Für Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd163-114">For Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
```  
  
 <span data-ttu-id="dd163-115">Wenn im Code URN-Funktionen wie `Server.GetSqlSmoObject(Urn)` verwendet werden, müssen Sie eine Verknüpfung mit dem Microsoft.SqlServer.Management.Sdk.Sfc-Namespace herstellen.</span><span class="sxs-lookup"><span data-stu-id="dd163-115">If your code uses Urn functionality, such as `Server.GetSqlSmoObject(Urn)`, you must link to the Microsoft.SqlServer.Management.Sdk.Sfc namespace.</span></span>  
  
 <span data-ttu-id="dd163-116">Wenn im Code das Transfer-Objekt direkt verwendet wird, müssen Sie eine Verknüpfung mit dem Microsoft.SqlServer.Management.SmoExtended-Namespace herstellen.</span><span class="sxs-lookup"><span data-stu-id="dd163-116">If your code uses the Transfer object directly, you will have to link to the Microsoft.SqlServer.Management.SmoExtended namespace.</span></span>  
  
 <span data-ttu-id="dd163-117">Wenn Sie Code migrieren, müssen Sie ihn ggf. ändern.</span><span class="sxs-lookup"><span data-stu-id="dd163-117">When you migrate code, you might have to modify the code.</span></span> <span data-ttu-id="dd163-118">Dies liegt daran, dass einige [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] - und [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] -Funktionen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]als veraltet markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dd163-118">This is because several [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] features have been deprecated in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dd163-119">Weitere Informationen zu veralteten Funktionen finden Sie unter [veraltet Datenbank-Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Online Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="dd163-119">For more information about deprecated features, see [Deprecated Database Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
