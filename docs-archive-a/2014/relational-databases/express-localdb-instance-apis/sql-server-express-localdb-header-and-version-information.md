---
title: SQL Server Express localdb-Header und Versionsinformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 138081852cf505b03265fd9c5f39eae6ed2af39b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622123"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a><span data-ttu-id="71ebc-102">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="71ebc-102">SQL Server Express LocalDB Header and Version Information</span></span>
  <span data-ttu-id="71ebc-103">Es gibt keine separate Headerdatei für die SQL Server Express LocalDB-Instanz-API. Die Signaturen und Fehlercodes der LocalDB-Funktion sind in der SQL Server Native Client-Headerdatei (sqlncli.h) definiert.</span><span class="sxs-lookup"><span data-stu-id="71ebc-103">There is no separate header file for the SQL Server Express LocalDB instance API; the LocalDB function signatures and error codes are defined in the SQL Server Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="71ebc-104">Zur Verwendung der LocalDB-Instanz-API müssen Sie die Headerdatei sqlncli.h in das Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="71ebc-104">To use the LocalDB instance API, you must include the sqlncli.h header file in your project.</span></span>  
  
## <a name="localdb-versioning"></a><span data-ttu-id="71ebc-105">LocalDB-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="71ebc-105">LocalDB Versioning</span></span>  
 <span data-ttu-id="71ebc-106">Die LocalDB-Installation verwendet pro Haupt-SQL Server-Version einen einzelnen Satz Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="71ebc-106">The LocalDB installation uses a single set of binaries per major SQL Server version.</span></span> <span data-ttu-id="71ebc-107">Diese LocalDB-Versionen werden gewartet und unabhängig gepatcht.</span><span class="sxs-lookup"><span data-stu-id="71ebc-107">These LocalDB versions are maintained and patched independently.</span></span> <span data-ttu-id="71ebc-108">Das bedeutet, dass der Benutzer angeben muss, welche LocalDB-Baselineversion (also Haupt-SQL Server-Version) er verwendet.</span><span class="sxs-lookup"><span data-stu-id="71ebc-108">This means that the user has to specify which LocalDB baseline release (that is, major SQL Server version) he or she will be using.</span></span> <span data-ttu-id="71ebc-109">Die Version wird im Standard Versions Format angegeben, das von der .NET Framework **System. Version** -Klasse definiert wird:</span><span class="sxs-lookup"><span data-stu-id="71ebc-109">The version is specified in the standard version format defined by the .NET Framework **System.Version** class:</span></span>  
  
 <span data-ttu-id="71ebc-110">*Hauptversion. neben Version [. Build [. Revision]]*</span><span class="sxs-lookup"><span data-stu-id="71ebc-110">*major.minor[.build[.revision]]*</span></span>  
  
 <span data-ttu-id="71ebc-111">Die ersten beiden Zahlen in der Versions Zeichenfolge (*Haupt* -und *neben*Version) sind obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="71ebc-111">The first two numbers in the version string (*major* and *minor*) are mandatory.</span></span> <span data-ttu-id="71ebc-112">Die letzten zwei Zahlen in der Versions Zeichenfolge (*Build* und *Revision*) sind optional und werden standardmäßig auf 0 (null) gesetzt, wenn der Benutzer Sie verlässt. Dies bedeutet Folgendes: Wenn der Benutzer nur "12,2" als localdb-Versionsnummer angibt, wird er so behandelt, als ob der Benutzer "12.2.0.0" angegeben hätte.</span><span class="sxs-lookup"><span data-stu-id="71ebc-112">The last two numbers in the version string (*build* and *revision*) are optional and default to zero if the user leaves them out. This means that if the user specifies only "12.2" as the LocalDB version number, it will be treated as if the user specified "12.2.0.0".</span></span>  
  
 <span data-ttu-id="71ebc-113">Die Version für die LocalDB-Installation ist im Registrierungsschlüssel MSSQLServer\CurrentVersion unter dem SQL Server-Instanz-Registrierungsschlüssel definiert. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71ebc-113">The version for the LocalDB installation is defined in the MSSQLServer\CurrentVersion registry key under the SQL Server instance registry key, for example:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 <span data-ttu-id="71ebc-114">Mehrere LocalDB-Versionen auf derselben Arbeitsstation werden gleichzeitig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="71ebc-114">Multiple LocalDB versions on the same workstation are supported side-by-side.</span></span> <span data-ttu-id="71ebc-115">Benutzercode verwendet jedoch immer die neueste verfügbare **sqluserinstance** -dll auf dem lokalen Computer, um eine Verbindung mit localdb-Instanzen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="71ebc-115">However, user code always uses the latest available **SQLUserInstance** DLL on the local computer to connect to LocalDB instances.</span></span>  
  
## <a name="locating-the-sqluserinstance-dll"></a><span data-ttu-id="71ebc-116">Suchen der SQLUserInstance-DLL</span><span class="sxs-lookup"><span data-stu-id="71ebc-116">Locating the SQLUserInstance DLL</span></span>  
 <span data-ttu-id="71ebc-117">Zum Auffinden der **sqluserinstance** -dll verwendet der Client Anbieter den folgenden Registrierungsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="71ebc-117">To locate the **SQLUserInstance** DLL, the client provider uses the following registry key:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 <span data-ttu-id="71ebc-118">Unter diesem Schlüssel befindet sich eine Liste Schlüssel, einer für jede Version der auf dem Computer installierten LocalDB.</span><span class="sxs-lookup"><span data-stu-id="71ebc-118">Under this key there is a list of keys, one for each version of LocalDB installed on the computer.</span></span> <span data-ttu-id="71ebc-119">Jeder dieser Schlüssel wird mit der localdb-Versionsnummer im Format benannt *\<major-version>* .*\<minor-version>*</span><span class="sxs-lookup"><span data-stu-id="71ebc-119">Each of these keys is named with the LocalDB version number in the format *\<major-version>*.*\<minor-version>*</span></span> <span data-ttu-id="71ebc-120">(der Schlüssel für hat z [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] . b. den Namen 12,0.)</span><span class="sxs-lookup"><span data-stu-id="71ebc-120">(for example, the key for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is named 12.0).</span></span> <span data-ttu-id="71ebc-121">Unter jedem Versionsschlüssel dort ist ein `InstanceAPIPath`-Name-Wert-Paar, das den vollständigen Pfad zur mit dieser Version installierten SQLUserInstance.dll-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="71ebc-121">Under each version key there is an `InstanceAPIPath` name-value pair that defines the full path to the SQLUserInstance.dll file installed with that version.</span></span> <span data-ttu-id="71ebc-122">Im folgenden Beispiel werden die Registrierungseinträge für einen Computer gezeigt, auf dem die LocalDB-Versionen 11.0 und 12.0 installiert sind:</span><span class="sxs-lookup"><span data-stu-id="71ebc-122">The following example shows the registry entries for a computer that has LocalDB versions 11.0 and 12.0 installed:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 <span data-ttu-id="71ebc-123">Der Client Anbieter muss die neueste Version unter allen installierten Versionen suchen und die DLL-Datei **sqluserinstance** aus dem zugeordneten `InstanceAPIPath` Wert laden.</span><span class="sxs-lookup"><span data-stu-id="71ebc-123">The client provider must find the latest version among all installed versions and load the **SQLUserInstance** DLL file from the associated `InstanceAPIPath` value.</span></span>  
  
### <a name="wow64-mode-on-64-bit-windows"></a><span data-ttu-id="71ebc-124">WOW64-Modus unter 64-Bit-Windows</span><span class="sxs-lookup"><span data-stu-id="71ebc-124">WOW64 Mode on 64-bit Windows</span></span>  
 <span data-ttu-id="71ebc-125">64-Bit-Installationen von LocalDB weisen einen zusätzlichen Satz Registrierungsschlüssel auf, der 32-Bit-Anwendungen, die im WOW64 (Windows-32-on-Windows-64)-Modus ausgeführt werden, die Verwendung von LocalDB ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="71ebc-125">64-bit installations of LocalDB will have an additional set of registry keys to allow 32-bit applications running in Windows-32-on-Windows-64 (WOW64) mode to use LocalDB.</span></span> <span data-ttu-id="71ebc-126">Insbesondere unter 64-Bit-Windows erstellt LocalDB-MSI die folgenden Registrierungsschlüssel:</span><span class="sxs-lookup"><span data-stu-id="71ebc-126">Specifically, on 64-bit Windows, the LocalDB MSI will create the following registry keys:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 <span data-ttu-id="71ebc-127">64-Bit-Programme, die den `Installed Versions` Schlüssel lesen, sehen Werte, die auf 64-Bit-Versionen der **sqluserinstance** -dll verweisen, während 32-Bit-Programme (die auf 64-Bit-Fenstern im WOW64-Modus ausgeführt werden) automatisch an einen `Installed Versions` Schlüssel in der Hive umgeleitet werden `Wow6432Node` .</span><span class="sxs-lookup"><span data-stu-id="71ebc-127">64-bit programs reading the `Installed Versions` key will see values pointing to 64-bit versions of the **SQLUserInstance** DLL, while 32-bit programs (running on 64-bit Windows in WOW64 mode) will be automatically redirected to an `Installed Versions` key located under the `Wow6432Node` hive.</span></span> <span data-ttu-id="71ebc-128">Dieser Schlüssel enthält Werte, die auf 32-Bit-Versionen der **sqluserinstance** -dll verweisen.</span><span class="sxs-lookup"><span data-stu-id="71ebc-128">This key contains values pointing to 32-bit versions of the **SQLUserInstance** DLL.</span></span>  
  
## <a name="using-localdb_define_proxy_functions"></a><span data-ttu-id="71ebc-129">Verwenden von LOCALDB_DEFINE_PROXY_FUNCTIONS</span><span class="sxs-lookup"><span data-stu-id="71ebc-129">Using LOCALDB_DEFINE_PROXY_FUNCTIONS</span></span>  
 <span data-ttu-id="71ebc-130">Die API der localdb-Instanz definiert eine Konstante mit dem Namen LOCALDB_DEFINE_PROXY_FUNCTIONS, die das erkennen und Laden der **sqluserinstance** -dll automatisiert.</span><span class="sxs-lookup"><span data-stu-id="71ebc-130">The LocalDB instance API defines a constant named LOCALDB_DEFINE_PROXY_FUNCTIONS that automates the discovery and loading of the **SqlUserInstance** DLL.</span></span>  
  
 <span data-ttu-id="71ebc-131">Der durch diese Konstante aktivierte Abschnitt des Codes stellt eine Implementierung der Proxys für jede der LocalDB-APIs bereit.</span><span class="sxs-lookup"><span data-stu-id="71ebc-131">The section of code enabled by this constant provides an implementation of proxies for each of the LocalDB APIs.</span></span> <span data-ttu-id="71ebc-132">In den Proxy Implementierungen wird eine gemeinsame Funktion verwendet, um eine Bindung an Einstiegspunkte in der zuletzt installierten **sqluserinstance** -DLL herzustellen, und dann die Anforderungen weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="71ebc-132">The proxy implementations use a common function to bind to entry points in the latest installed **SqlUserInstance** DLL, and then forward the requests.</span></span>  
  
 <span data-ttu-id="71ebc-133">Die Proxyfunktionen werden nur aktiviert, wenn die Konstante LOCALDB_DEFINE_PROXY_FUNCTIONS vor dem Einfügen der Datei sqlncli.h im Benutzercode definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="71ebc-133">The proxy functions are enabled only if the constant LOCALDB_DEFINE_PROXY_FUNCTIONS is defined in the user code before including the sqlncli.h file.</span></span> <span data-ttu-id="71ebc-134">Die Konstante darf in nur einem Quellenmodul (CPP-Datei) definiert werden, da sie externe Funktionsnamen für alle API-Einstiegspunkte definiert.</span><span class="sxs-lookup"><span data-stu-id="71ebc-134">The constant should be defined in only one source module (.cpp file) because it defines external function names for all of the API entry points.</span></span> <span data-ttu-id="71ebc-135">Sie stellt eine Implementierung der Proxys für alle LocalDB-APIs bereit.</span><span class="sxs-lookup"><span data-stu-id="71ebc-135">It provides an implementation of proxies for each of the LocalDB APIs.</span></span>  
  
 <span data-ttu-id="71ebc-136">Im folgenden Codebeispiel wird gezeigt, wie das Makro vom systemeigenen C++-Code verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="71ebc-136">The following code example shows how to use the macro from the native C++ code:</span></span>  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
...  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
...  
}  
...  
  
```  
  
  
