---
title: Sqllocaldb-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- SqlLocalDB utility [SQL Server]
- local database runtime utility
- LocalDB, SqlLocalDB Utility
ms.assetid: d785cdb7-1ea0-4871-bde9-1ae7881190f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfb95cea4365d56c296d14fcc09046cd7eddc0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694917"
---
# <a name="sqllocaldb-utility"></a><span data-ttu-id="1b93e-102">SqlLocalDB-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="1b93e-102">SqlLocalDB Utility</span></span>
  <span data-ttu-id="1b93e-103">Verwenden `SqlLocalDB` Sie das Hilfsprogramm, um eine Instanz von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)] **localdb**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b93e-103">Use the `SqlLocalDB` utility to create an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)]**LocalDB**.</span></span> <span data-ttu-id="1b93e-104">Das- `SqlLocalDB` Hilfsprogramm (SqlLocalDB.exe) ist ein einfaches Befehlszeilen Tool, mit dem Benutzer und Entwickler eine Instanz von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **localdb**erstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="1b93e-104">The `SqlLocalDB` utility (SqlLocalDB.exe) is a simple command line tool to enable users and developers to create and manage an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="1b93e-105">Weitere Informationen zur Verwendung von **localdb**finden Sie unter [SQL Server 2014 Express localdb](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span><span class="sxs-lookup"><span data-stu-id="1b93e-105">For information about how to use **LocalDB**, see [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b93e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b93e-106">Syntax</span></span>  
  
```  
SqlLocalDB.exe   
{  
      [ create   | c ] <instance-name><instance-version> [-s ]  
    | [ delete   | d ] <instance-name>  
    | [ start    | s ] <instance-name>  
    | [ stop     | p ] <instance-name>  [ -i ] [ -k ]  
    | [ share    | h ] ["<user_SID>" | "<user_account>" ] "<private-name>""<shared-name>"  
    | [ unshare  | u ] "<shared-name>"  
    | [ info     | i ] <instance-name>  
    | [ versions | v ]  
    | [ trace    | t ] [ on | off ]  
    | [ help     | -? ]  
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b93e-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="1b93e-107">Arguments</span></span>  
 <span data-ttu-id="1b93e-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [ **-s** ]</span><span class="sxs-lookup"><span data-stu-id="1b93e-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [**-s** ]</span></span>  
 <span data-ttu-id="1b93e-109">Erstellt eine neue Instanz von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="1b93e-109">Creates a new of instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="1b93e-110">`SqlLocalDB`verwendet die Version der [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] Binärdateien, die durch das-Argument angegeben sind *\<instance-version>* .</span><span class="sxs-lookup"><span data-stu-id="1b93e-110">`SqlLocalDB` uses the version of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binaries specified by *\<instance-version>* argument.</span></span> <span data-ttu-id="1b93e-111">Die Versionsnummer wird im numerischen Format mit mindestens einer Dezimalzahl angegeben.</span><span class="sxs-lookup"><span data-stu-id="1b93e-111">The version number is specified in numeric format with at least one decimal.</span></span> <span data-ttu-id="1b93e-112">Die Nebenversionsnummern (Service Packs) sind optional.</span><span class="sxs-lookup"><span data-stu-id="1b93e-112">The minor version numbers (service packs) are optional.</span></span> <span data-ttu-id="1b93e-113">Beispielsweise werden die folgenden zwei Versionsnummern akzeptiert: 11.0 oder 11.0.1186.</span><span class="sxs-lookup"><span data-stu-id="1b93e-113">For example the following two version numbers are both acceptable: 11.0, or 11.0.1186.</span></span> <span data-ttu-id="1b93e-114">Die angegebene Version muss auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="1b93e-114">The specified version must be installed on the computer.</span></span> <span data-ttu-id="1b93e-115">Wenn nicht angegeben, wird standardmäßig die Version des `SqlLocalDB` Hilfsprogramms verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b93e-115">If not specified, the version number defaults to the version of the `SqlLocalDB` utility.</span></span> <span data-ttu-id="1b93e-116">Durch Hinzufügen von **-s** wird die neue Instanz von **LocalDB**gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b93e-116">Adding **-s** starts the new instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="1b93e-117">[ **share** | **h** ]</span><span class="sxs-lookup"><span data-stu-id="1b93e-117">[ **share** | **h** ]</span></span>  
 <span data-ttu-id="1b93e-118">Gibt die angegebene private Instanz von **LocalDB** mithilfe des angegebenen freigegebenen Namens frei.</span><span class="sxs-lookup"><span data-stu-id="1b93e-118">Shares the specified private instance of **LocalDB** using the specified shared name.</span></span> <span data-ttu-id="1b93e-119">Wenn die Benutzer-SID oder der Kontoname weggelassen wird, wird standardmäßig der aktuelle Benutzer verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b93e-119">If the user SID or account name is omitted, it defaults to the current user.</span></span>  
  
 <span data-ttu-id="1b93e-120">[ **unshared** | **u** ]</span><span class="sxs-lookup"><span data-stu-id="1b93e-120">[ **unshared** | **u** ]</span></span>  
 <span data-ttu-id="1b93e-121">Beendet die Freigabe der angegebenen freigegebenen Instanz von **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="1b93e-121">Stops the sharing of the specified shared instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="1b93e-122">[ **delete** | **d** ] *\<instance-name>*</span><span class="sxs-lookup"><span data-stu-id="1b93e-122">[ **delete** | **d** ] *\<instance-name>*</span></span>  
 <span data-ttu-id="1b93e-123">Löscht die angegebene Instanz von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="1b93e-123">Deletes the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span>  
  
 <span data-ttu-id="1b93e-124">[ **start** | **s** ] " *\<instance-name>* "</span><span class="sxs-lookup"><span data-stu-id="1b93e-124">[ **start** | **s** ] "*\<instance-name>*"</span></span>  
 <span data-ttu-id="1b93e-125">Startet die angegebene Instanz von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="1b93e-125">Starts the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="1b93e-126">Bei Erfolg gibt die Anweisung die Named Pipe-Adresse von **LocalDB**zurück.</span><span class="sxs-lookup"><span data-stu-id="1b93e-126">When successful the statement returns the named pipe address of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="1b93e-127">[ **stop** | **p** ] *\<instance-name>* [ **-i** ] [ **-k** ]</span><span class="sxs-lookup"><span data-stu-id="1b93e-127">[ **stop** | **p** ] *\<instance-name>* [**-i** ] [**-k** ]</span></span>  
 <span data-ttu-id="1b93e-128">Beendet die angegebene Instanz von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="1b93e-128">Stops the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="1b93e-129">Durch Hinzufügen von **-i** wird das Herunterfahren der Instanz mit der `NOWAIT` Option angefordert</span><span class="sxs-lookup"><span data-stu-id="1b93e-129">Adding **-i** requests the instance shutdown with the `NOWAIT` option.</span></span> <span data-ttu-id="1b93e-130">Durch Hinzufügen von **-k** wird der Instanzprozess ohne Kontaktieren abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="1b93e-130">Adding **-k** kills the instance process without contacting it.</span></span>  
  
 <span data-ttu-id="1b93e-131">[ **info** | **i** ] [ *\<instance-name>* ]</span><span class="sxs-lookup"><span data-stu-id="1b93e-131">[ **info** | **i** ] [ *\<instance-name>* ]</span></span>  
 <span data-ttu-id="1b93e-132">Listet alle Instanzen von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** auf, die im Besitz des aktuellen Benutzers sind.</span><span class="sxs-lookup"><span data-stu-id="1b93e-132">Lists all instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** owned by the current user.</span></span>  
  
 <span data-ttu-id="1b93e-133">*\<instance-name>* gibt den Namen, die Version, den Zustand („Wird ausgeführt“ oder „Beendet“) und die letzte Startzeit für die angegebene Instanz von [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** und den lokalen Pipenamen von **LocalDB** zurück.</span><span class="sxs-lookup"><span data-stu-id="1b93e-133">*\<instance-name>* returns the name, version, state (Running or Stopped), last start time for the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**, and the local pipe name of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="1b93e-134">[ **trace** | **t** ] **on** | **off**</span><span class="sxs-lookup"><span data-stu-id="1b93e-134">[ **trace** | **t** ] **on** | **off**</span></span>  
 <span data-ttu-id="1b93e-135">**Trace on** aktiviert die Ablauf Verfolgung für die `SqlLocalDB` API-Aufrufe für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1b93e-135">**trace on** enables tracing for the `SqlLocalDB` API calls for the current user.</span></span> <span data-ttu-id="1b93e-136">**trace off** deaktiviert die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="1b93e-136">**trace off** disables tracing.</span></span>  
  
 <span data-ttu-id="1b93e-137">**-?**</span><span class="sxs-lookup"><span data-stu-id="1b93e-137">**-?**</span></span>  
 <span data-ttu-id="1b93e-138">Gibt kurze Beschreibungen der einzelnen `SqlLocalDB` Optionen zurück.</span><span class="sxs-lookup"><span data-stu-id="1b93e-138">Returns brief descriptions of each `SqlLocalDB` option.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b93e-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1b93e-139">Remarks</span></span>  
 <span data-ttu-id="1b93e-140">Für das *instance name* -Argument müssen die Regeln für [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Bezeichner befolgt werden, oder das Argument muss in doppelte Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1b93e-140">The *instance name* argument must follow the rules for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers or it must be enclosed in double quotes.</span></span>  
  
 <span data-ttu-id="1b93e-141">Bei der Ausführung von „SqlLocalDB“ ohne Argumente wird der Hilfetext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b93e-141">Executing SqlLocalDB without arguments returns the help text.</span></span>  
  
 <span data-ttu-id="1b93e-142">Vorgänge, die keine Startvorgänge sind, können nur für eine Instanz ausgeführt werden, die zum derzeit angemeldeten Benutzer gehört.</span><span class="sxs-lookup"><span data-stu-id="1b93e-142">Operations other than start can only be performed on an instance belonging to currently logged in user.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1b93e-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1b93e-143">Examples</span></span>  
  
### <a name="a-creating-an-instance-of-localdb"></a><span data-ttu-id="1b93e-144">A.</span><span class="sxs-lookup"><span data-stu-id="1b93e-144">A.</span></span> <span data-ttu-id="1b93e-145">Erstellen einer Instanz von LocalDB</span><span class="sxs-lookup"><span data-stu-id="1b93e-145">Creating an Instance of LocalDB</span></span>  
 <span data-ttu-id="1b93e-146">Im folgenden Beispiel wird mithilfe der [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **-Binärdateien eine Instanz von** LocalDB `DEPARTMENT` namens [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] erstellt und die Instanz gestartet.</span><span class="sxs-lookup"><span data-stu-id="1b93e-146">The following example creates an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** named `DEPARTMENT` using the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] binaries and starts the instance.</span></span>  
  
```  
SqlLocalDB.exe create "DEPARTMENT" 12.0 -s  
```  
  
### <a name="b-working-with-a-shared-instance-of-localdb"></a><span data-ttu-id="1b93e-147">B.</span><span class="sxs-lookup"><span data-stu-id="1b93e-147">B.</span></span> <span data-ttu-id="1b93e-148">Verwenden einer freigegebenen Instanz von LocalDB</span><span class="sxs-lookup"><span data-stu-id="1b93e-148">Working with a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="1b93e-149">Öffnen Sie eine Eingabeaufforderung unter Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1b93e-149">Open a command prompt using Administrator privileges.</span></span>  
  
```  
SqlLocalDB.exe create "DeptLocalDB"  
SqlLocalDB.exe share "DeptLocalDB" "DeptSharedLocalDB"  
SqlLocalDB.exe start "DeptLocalDB"  
SqlLocalDB.exe info "DeptLocalDB"  
REM The previous statement outputs the Instance pipe name for the next step  
sqlcmd -S np:\\.\pipe\LOCALDB#<use your pipe name>\tsql\query  
CREATE LOGIN NewLogin WITH PASSWORD = 'Passw0rd!!@52';   
GO  
CREATE USER NewLogin;  
GO  
EXIT  
```  
  
 <span data-ttu-id="1b93e-150">Führen Sie den folgenden Code aus, um unter Verwendung des **-Anmeldenamens eine Verbindung zur freigegebenen** LocalDB `NewLogin` -Instanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="1b93e-150">Execute the following code to connect to the shared instance of **LocalDB** using the `NewLogin` login.</span></span>  
  
```  
sqlcmd -S (localdb)\.\DeptSharedLocalDB -U NewLogin -P Passw0rd!!@52  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b93e-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b93e-151">See Also</span></span>  
 [<span data-ttu-id="1b93e-152">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="1b93e-152">SQL Server 2014 Express LocalDB</span></span>](../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
  
