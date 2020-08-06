---
title: 'Befehlszeilen-Verwaltungs Tool: SqlLocalDB.exe | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d21a6a8879e981e52bd2e7d3bd05a37e65d8cf4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609229"
---
# <a name="command-line-management-tool-sqllocaldbexe"></a><span data-ttu-id="08116-102">Verwaltungstool für Befehlszeilen: SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="08116-102">Command-Line Management Tool: SqlLocalDB.exe</span></span>
  <span data-ttu-id="08116-103">SqlLocalDB.exe ist ein einfaches Tool, das dem Benutzer die einfache Verwaltung der LocalDB-Instanzen in der Befehlszeile ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="08116-103">SqlLocalDB.exe is a simple tool that enables the user to easily manage LocalDB instances from the command line.</span></span> <span data-ttu-id="08116-104">Es wird als einfacher Wrapper um die LocalDB Instanz-API implementiert.</span><span class="sxs-lookup"><span data-stu-id="08116-104">It is implemented as a simple wrapper around the LocalDB instance API.</span></span> <span data-ttu-id="08116-105">Wie in vielen ähnlichen SQL Server-Tools (zum Beispiel SQLCMD) werden Parameter als Befehlszeilenargumente an SqlLocalDB übergeben, und die Ausgabe wird an die Konsole gesendet.</span><span class="sxs-lookup"><span data-stu-id="08116-105">As in many similar SQL Server tools (for example, SQLCMD), parameters are passed to SqlLocalDB as command-line arguments and output is sent to the console.</span></span>  
  
 <span data-ttu-id="08116-106">SqlLocalDB ermöglicht Entwicklern die Verwendung von LocalDB, ohne Code zum Aufrufen der API schreiben zu müssen und ohne von anderen Tools abhängig zu sein, die dies erledigen müssten.</span><span class="sxs-lookup"><span data-stu-id="08116-106">SqlLocalDB enables developers to use LocalDB without having to write code to call the API or depend on other tools to do it for them.</span></span>  
  
## <a name="sqllocaldb-options"></a><span data-ttu-id="08116-107">SqlLocalDB-Optionen</span><span class="sxs-lookup"><span data-stu-id="08116-107">SqlLocalDB Options</span></span>  
 <span data-ttu-id="08116-108">SqlLocalDB unterstützt die folgenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="08116-108">SqlLocalDB supports the following options.</span></span>  
  
|<span data-ttu-id="08116-109">Option</span><span class="sxs-lookup"><span data-stu-id="08116-109">Option</span></span>|<span data-ttu-id="08116-110">Funktionsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="08116-110">What it does</span></span>|  
|------------|------------------|  
|`-?`|<span data-ttu-id="08116-111">Druckt Hilfetext.</span><span class="sxs-lookup"><span data-stu-id="08116-111">Prints help text.</span></span>|  
|`create&#124;c "instance name" [version-number] [-s]`|<span data-ttu-id="08116-112">Erstellt eine neue LocalDB-Instanz mit einem angegebenen Namen und einer Version.</span><span class="sxs-lookup"><span data-stu-id="08116-112">Creates a new LocalDB instance with a specified name and version.</span></span><br /><br /> <span data-ttu-id="08116-113">Wenn der [Versionsnummer]-Parameter weggelassen wird, wird standardmäßig die SqlLocalDB-Buildversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="08116-113">If the [version-number] parameter is omitted, it defaults to the SqlLocalDB build version.</span></span><br /><br /> <span data-ttu-id="08116-114">-s startet die neue LocalDB-Instanz nach dem Erstellen.</span><span class="sxs-lookup"><span data-stu-id="08116-114">-s starts the new LocalDB instance after it is created.</span></span>|  
|`delete&#124;d "instance name"`|<span data-ttu-id="08116-115">Löscht die LocalDB-Instanz mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="08116-115">Deletes the LocalDB instance with the specified name.</span></span>|  
|`start&#124;s "instance name"`|<span data-ttu-id="08116-116">Startet die LocalDB-Instanz mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="08116-116">Starts the LocalDB instance with the specified name.</span></span>|  
|`stop&#124;p "instance name" [-i&#124;-k]`|<span data-ttu-id="08116-117">Beendet die LocalDB-Instanz mit dem angegebenen Namen, nachdem die Ausführung aktueller Abfragen beendet wird.</span><span class="sxs-lookup"><span data-stu-id="08116-117">Stops the LocalDB instance with the specified name, after current queries finish running.</span></span><br /><br /> <span data-ttu-id="08116-118">-i fordert das Herunterfahren der LocalDB-Instanz mit der NOWAIT-Option an.</span><span class="sxs-lookup"><span data-stu-id="08116-118">-i requests the LocalDB instance shutdown with the NOWAIT option.</span></span><br /><br /> <span data-ttu-id="08116-119">-k bricht den LocalDB-Instanzprozess ohne Kontaktieren ab.</span><span class="sxs-lookup"><span data-stu-id="08116-119">-k kills the LocalDB instance process without contacting it.</span></span>|  
|`share&#124;h ["owner SID or account"] "private name" "shared name"`|<span data-ttu-id="08116-120">Gibt die angegebene private Instanz mithilfe des angegebenen freigegebenen Namens frei.</span><span class="sxs-lookup"><span data-stu-id="08116-120">Shares the specified private instance using the specified shared name.</span></span> <span data-ttu-id="08116-121">Wenn die Benutzer-SID oder der Kontoname weggelassen wird, wird standardmäßig der aktuelle Benutzer verwendet.</span><span class="sxs-lookup"><span data-stu-id="08116-121">If the user SID or account name is omitted, it defaults to the current user.</span></span>|  
|`unshare&#124;u "shared name"`|<span data-ttu-id="08116-122">Hebt die Freigabe der angegebenen freigegebenen LocalDB-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="08116-122">Unshares the specified shared LocalDB instance.</span></span>|  
|`info&#124;i`|<span data-ttu-id="08116-123">Listet alle vorhandenen LocalDB-Instanzen im Besitz des aktuellen Benutzers und aller freigegebenen LocalDB-Instanzen auf.</span><span class="sxs-lookup"><span data-stu-id="08116-123">Lists all existing LocalDB instances that are owned by the current user and all shared LocalDB instances.</span></span>|  
|`info&#124;i "instance name"`|<span data-ttu-id="08116-124">Druckt die Informationen zur angegebenen LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="08116-124">Prints the information about the specified LocalDB instance.</span></span>|  
|`versions&#124;v`|<span data-ttu-id="08116-125">Listet alle auf dem Computer installierten LocalDB-Versionen auf.</span><span class="sxs-lookup"><span data-stu-id="08116-125">Lists all LocalDB versions installed on the computer.</span></span>|  
|||  
|`trace&#124;t on&#124;off`|<span data-ttu-id="08116-126">Aktiviert und deaktiviert die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="08116-126">Turns tracing on and off.</span></span>|  
  
 <span data-ttu-id="08116-127">SqlLocalDB behandelt Leerzeichen als Trennzeichen. Sie müssen die Instanznamen mit Anführungszeichen umschließen, die Leerzeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="08116-127">SqlLocalDB treats spaces as delimiters; you must surround the instance names that contain spaces and special characters with quotes.</span></span> <span data-ttu-id="08116-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="08116-128">For example:</span></span>  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
