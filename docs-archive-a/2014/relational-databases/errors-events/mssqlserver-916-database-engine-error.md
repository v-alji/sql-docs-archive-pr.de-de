---
title: MSSQLSERVER_916 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 916 (Database Engine error)
ms.assetid: 73eb6581-99fe-49a5-9b42-e239d7ffe27f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ee67c1e2f67c3c7903c67082ec3793d9d9820061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617039"
---
# <a name="mssqlserver_916"></a><span data-ttu-id="797e1-102">MSSQLSERVER_916</span><span class="sxs-lookup"><span data-stu-id="797e1-102">MSSQLSERVER_916</span></span>
    
## <a name="details"></a><span data-ttu-id="797e1-103">Details</span><span class="sxs-lookup"><span data-stu-id="797e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="797e1-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="797e1-104">Product Name</span></span>|<span data-ttu-id="797e1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="797e1-105">SQL Server</span></span>|  
|<span data-ttu-id="797e1-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="797e1-106">Event ID</span></span>|<span data-ttu-id="797e1-107">916</span><span class="sxs-lookup"><span data-stu-id="797e1-107">916</span></span>|  
|<span data-ttu-id="797e1-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="797e1-108">Event Source</span></span>|<span data-ttu-id="797e1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="797e1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="797e1-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="797e1-110">Component</span></span>|<span data-ttu-id="797e1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="797e1-111">SQLEngine</span></span>|  
|<span data-ttu-id="797e1-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="797e1-112">Symbolic Name</span></span>|<span data-ttu-id="797e1-113">NOTUSER</span><span class="sxs-lookup"><span data-stu-id="797e1-113">NOTUSER</span></span>|  
|<span data-ttu-id="797e1-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="797e1-114">Message Text</span></span>|<span data-ttu-id="797e1-115">Der Serverprinzipal „%.\*ls“ kann unter dem aktuellen Sicherheitskontext nicht auf die „%.\*ls“-Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="797e1-115">The server principal "%.\*ls" is not able to access the database "%.\*ls" under the current security context.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="797e1-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="797e1-116">Explanation</span></span>  
 <span data-ttu-id="797e1-117">Unter diesem Anmeldenamen sind keine ausreichenden Berechtigungen verfügbar, um eine Verbindung mit der benannten Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="797e1-117">The login does not have sufficient permissions to connect to the named database.</span></span> <span data-ttu-id="797e1-118">Anmeldenamen, unter denen eine Verbindung mit dieser Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hergestellt werden kann, die jedoch keine bestimmten Berechtigungen in einer Datenbank aufweisen, erhalten die Berechtigungen des Gastbenutzers.</span><span class="sxs-lookup"><span data-stu-id="797e1-118">Logins that can connect to this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but that do not have specific permissions in a database receive the permissions of the guest user.</span></span> <span data-ttu-id="797e1-119">Dies ist eine Sicherheitsmaßnahme, um zu verhindern, dass Benutzer in einer Datenbank eine Verbindung mit anderen Datenbanken herstellen, für die sie keine Rechte besitzen.</span><span class="sxs-lookup"><span data-stu-id="797e1-119">This is a security measure to prevent users in one database from connecting to other databases where they do not have privileges.</span></span> <span data-ttu-id="797e1-120">Diese Fehlermeldung kann ausgegeben werden, wenn der Gastbenutzer keine CONNECT-Berechtigung für die benannte Datenbank hat und die TRUSTWORTHY-Eigenschaft nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="797e1-120">This error message can occur when the guest user does not have CONNECT permission to the named database and the trustworthy property is not set.</span></span> <span data-ttu-id="797e1-121">Diese Fehlermeldung kann ausgegeben werden, wenn der Gastbenutzer keine CONNECT-Berechtigung für die benannte Datenbank hat.</span><span class="sxs-lookup"><span data-stu-id="797e1-121">This error message can occur when the guest user does not have CONNECT permission to the named database.</span></span>  
  
 <span data-ttu-id="797e1-122">Wenn die CONNECT-Berechtigung für die msdb-Datenbank verweigert oder aufgehoben wird, kann [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] diese Fehlermeldung erhalten, wenn der Objekt-Explorer versucht, den richtlinienbasierten Verwaltungsstatus der einzelnen Datenbanken anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="797e1-122">When CONNECT permission to the msdb database is denied or revoked, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] can receive this error when Object Explorer tries to show the Policy Based Management status of each database.</span></span> <span data-ttu-id="797e1-123">Der Objekt-Explorer verwendet die Berechtigungen des aktuellen Anmeldenamens, um diese Informationen aus der msdb-Datenbank abzufragen, wodurch der Fehler verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="797e1-123">Object Explorer uses the permissions of the current login to query the msdb database for this information, which causes the error.</span></span> <span data-ttu-id="797e1-124">Die folgende Fehlermeldung wird ebenfalls ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="797e1-124">The following error message also occurs:</span></span>  
  
 <span data-ttu-id="797e1-125">Fehler beim Abrufen von Daten für diese Anforderung.</span><span class="sxs-lookup"><span data-stu-id="797e1-125">Failed to retrieve data for this request.</span></span> <span data-ttu-id="797e1-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span><span class="sxs-lookup"><span data-stu-id="797e1-126">(Microsoft.SqlServer.Management.Sdk.Sfc)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="797e1-127">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="797e1-127">User Action</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="797e1-128">Bevor Sie diese Sicherheitsmaßnahme umgehen, sollten Sie sichergehen, dass Sie genau wissen, wie Benutzer in den verschiedenen Datenbanken authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="797e1-128">Before circumventing this security measure be sure to have a clear understanding of users are authenticated in various databases.</span></span> <span data-ttu-id="797e1-129">Mithilfe der folgenden Methoden können Benutzer, die über Berechtigungen für eine Datenbank verfügen, eine Verbindung mit anderen Datenbanken herstellen. Auf diese Weise können Daten für böswillige Benutzer offen gelegt werden.</span><span class="sxs-lookup"><span data-stu-id="797e1-129">The following methods may allow users that have permissions in one database to connect to other databases which could expose data to a malicious user.</span></span> <span data-ttu-id="797e1-130">Wenn enthaltene Datenbanken aktiviert sind, können Datenbankbesitzer in einer Datenbank über die folgenden Schritte Zugriff auf andere Datenbanken auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gewähren.</span><span class="sxs-lookup"><span data-stu-id="797e1-130">When contained databases are enabled, the following steps can allow database owners in one database to grant access to other database on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="797e1-131">Sie können auf eine der folgenden Arten eine Verbindung mit der Datenbank herstellen:</span><span class="sxs-lookup"><span data-stu-id="797e1-131">You can connect to the database in one of the following ways:</span></span>  
  
-   <span data-ttu-id="797e1-132">Gewähren Sie spezifischen Anmeldezugriff für die benannte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="797e1-132">Grant the specific login access to the named database.</span></span> <span data-ttu-id="797e1-133">Im folgenden Beispiel wird dem Anmeldenamen `Adventure-Works\Larry` Zugriff auf die `msdb`-Datenbank gewährt.</span><span class="sxs-lookup"><span data-stu-id="797e1-133">The following example grants the login `Adventure-Works\Larry` access to the `msdb` database.</span></span>  
  
     <span data-ttu-id="797e1-134">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="797e1-134">USE msdb ;</span></span>  
  
     <span data-ttu-id="797e1-135">GO</span><span class="sxs-lookup"><span data-stu-id="797e1-135">GO</span></span>  
  
     <span data-ttu-id="797e1-136">GRANT CONNECT TO [AdventureWorks\Larry] ;</span><span class="sxs-lookup"><span data-stu-id="797e1-136">GRANT CONNECT TO [Adventure-Works\Larry] ;</span></span>  
  
-   <span data-ttu-id="797e1-137">Gewähren Sie dem Gastbenutzer für die in der Fehlermeldung genannte Datenbank die CONNECT-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="797e1-137">Grant the CONNECT permission to the database named in the error message for the guest user.</span></span> <span data-ttu-id="797e1-138">Im folgenden Beispiel wird die `CONNECT`-Berechtigung für die `msdb`-Datenbank dem Benutzer `guest` erteilt.</span><span class="sxs-lookup"><span data-stu-id="797e1-138">The following example grants the `CONNECT` permission to the `msdb` database for the user `guest`.</span></span>  
  
     <span data-ttu-id="797e1-139">USE msdb ;</span><span class="sxs-lookup"><span data-stu-id="797e1-139">USE msdb ;</span></span>  
  
     <span data-ttu-id="797e1-140">GO</span><span class="sxs-lookup"><span data-stu-id="797e1-140">GO</span></span>  
  
     <span data-ttu-id="797e1-141">GRANT CONNECT TO guest ;</span><span class="sxs-lookup"><span data-stu-id="797e1-141">GRANT CONNECT TO guest ;</span></span>  
  
-   <span data-ttu-id="797e1-142">Aktivieren Sie die TRUSTWORTHY-Eigenschaft für die Datenbank, die den Benutzer authentifiziert hat.</span><span class="sxs-lookup"><span data-stu-id="797e1-142">Enable the TRUSTWORTHY property on the database that has authenticated the user.</span></span>  
  
     `ALTER DATABASE AdventureWorks SET TRUSTWORTHY ON;`  
  
  
