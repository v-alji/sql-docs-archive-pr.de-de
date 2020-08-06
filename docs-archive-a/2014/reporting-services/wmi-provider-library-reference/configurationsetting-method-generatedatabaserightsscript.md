---
title: 'GenerateDatabaseRightsScript-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseRightsScript method
ms.assetid: f2e6dcc9-978f-4c2c-bafe-36c330247fd0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 768e73d13d3b06f7913c3c816fded1b28c56199f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722406"
---
# <a name="generatedatabaserightsscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9aa80-102">GenerateDatabaseRightsScript-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="9aa80-102">GenerateDatabaseRightsScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9aa80-103">Generiert ein SQL-Skript, das verwendet werden kann, um einem Benutzer Berechtigungen für die Berichtsserver-Datenbank sowie für andere Datenbanken zu gewähren, die für das Ausführen eines Berichtsservers erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9aa80-103">Generates a SQL Script that can be used to grant a user rights to the report server database and other databases required for a report server to run.</span></span> <span data-ttu-id="9aa80-104">Es wird erwartet, dass der Aufrufer eine Verbindung mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankserver herstellt und das Skript ausführt.</span><span class="sxs-lookup"><span data-stu-id="9aa80-104">The caller is expected to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and execute the script.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa80-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9aa80-105">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseRightsScript(ByVal UserName As String, _  
    ByVal DatabaseName As String, ByVal IsRemote As Boolean, _  
    ByVal IsWindowsUser As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseRightsScript(string UserName, string DatabaseName, bool IsRemote, bool IsWindowsUser, out string Script,   
out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aa80-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9aa80-106">Parameters</span></span>  
 <span data-ttu-id="9aa80-107">*UserName*</span><span class="sxs-lookup"><span data-stu-id="9aa80-107">*UserName*</span></span>  
 <span data-ttu-id="9aa80-108">Der Benutzername oder die Windows-Sicherheits-ID (SID) des Benutzers, dem durch das Skript Berechtigungen erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9aa80-108">The user name or Windows security identifier (SID) of the user to which the script will grant rights.</span></span>  
  
 <span data-ttu-id="9aa80-109">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="9aa80-109">*DatabaseName*</span></span>  
 <span data-ttu-id="9aa80-110">Der Name der Datenbank, für die dem Benutzer durch das Skript Zugriff gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="9aa80-110">The database name to which the script will grant access to the user.</span></span>  
  
 <span data-ttu-id="9aa80-111">*IsRemote*</span><span class="sxs-lookup"><span data-stu-id="9aa80-111">*IsRemote*</span></span>  
 <span data-ttu-id="9aa80-112">Ein boolescher Wert, der angibt, ob es sich vom Berichtsserver aus gesehen um eine Remotedatenbank handelt.</span><span class="sxs-lookup"><span data-stu-id="9aa80-112">A Boolean value to indicating whether the database is remote from the report server.</span></span>  
  
 <span data-ttu-id="9aa80-113">*IsWindowsUser*</span><span class="sxs-lookup"><span data-stu-id="9aa80-113">*IsWindowsUser*</span></span>  
 <span data-ttu-id="9aa80-114">Ein boolescher Wert, der angibt, ob der angegebene Benutzername für einen Windows-Benutzer oder einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer steht.</span><span class="sxs-lookup"><span data-stu-id="9aa80-114">A Boolean value indicating whether the specified user name is a Windows user or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="9aa80-115">*Skript*</span><span class="sxs-lookup"><span data-stu-id="9aa80-115">*Script*</span></span>  
 <span data-ttu-id="9aa80-116">[out] Eine Zeichenfolge, die das generierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Skript enthält</span><span class="sxs-lookup"><span data-stu-id="9aa80-116">[out] A string containing the generated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span>  
  
 <span data-ttu-id="9aa80-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="9aa80-117">*HRESULT*</span></span>  
 <span data-ttu-id="9aa80-118">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="9aa80-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aa80-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9aa80-119">Return Value</span></span>  
 <span data-ttu-id="9aa80-120">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9aa80-120">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="9aa80-121">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="9aa80-121">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="9aa80-122">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9aa80-122">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9aa80-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9aa80-123">Remarks</span></span>  
 <span data-ttu-id="9aa80-124">Wenn *DatabaseName* leer ist, wird *IsRemote* ignoriert und der Wert aus der Konfigurationsdatei des Berichtsservers als Datenbankname verwendet.</span><span class="sxs-lookup"><span data-stu-id="9aa80-124">If *DatabaseName* is empty then *IsRemote* is ignored and the report server configuration file value is used for the database name.</span></span>  
  
 <span data-ttu-id="9aa80-125">Wenn *IsWindowsUser* auf festgelegt ist `true` , muss *username* das Format \<domain> \\<username aufweisen \> .</span><span class="sxs-lookup"><span data-stu-id="9aa80-125">If *IsWindowsUser* is set to `true`, *UserName* should be in the format \<domain>\\<username\>.</span></span>  
  
 <span data-ttu-id="9aa80-126">Wenn *IsWindowsUser* auf festgelegt ist `true` , werden dem Benutzer durch das generierte Skript Anmelde Berechtigungen für erteilt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , wobei die Berichts Server-Datenbank als Standarddatenbank festgelegt und die **RSExec** -Rolle für die Berichts Server-Datenbank, die temporäre Berichts Server-Datenbank, die Master-Datenbank und die msdb-Systemdatenbank erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="9aa80-126">When *IsWindowsUser* is set to `true`, the generated script grants login rights to the user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], setting the report server database as the default database, and grants the **RSExec** role on the report server database, the report server temporary database, the master database and the MSDB system database.</span></span>  
  
 <span data-ttu-id="9aa80-127">Wenn *IsWindowsUser* auf festgelegt ist `true` , akzeptiert die Methode standardmäßige Windows-SIDs als Eingabe.</span><span class="sxs-lookup"><span data-stu-id="9aa80-127">When *IsWindowsUser* is set to `true`, the method accepts standard Windows SIDs as input.</span></span> <span data-ttu-id="9aa80-128">Wird eine standardmäßige Windows-SID oder ein Dienstkontoname bereitgestellt, wird diese bzw. dieser in eine Benutzernamen-Zeichenfolge übersetzt.</span><span class="sxs-lookup"><span data-stu-id="9aa80-128">When a standard Windows SID or service account name is supplied, it is translated to a user name string.</span></span> <span data-ttu-id="9aa80-129">Falls es sich bei der Datenbank um eine lokale Datenbank handelt, wird das Konto in die richtige lokalisierte Darstellung des Kontos übersetzt.</span><span class="sxs-lookup"><span data-stu-id="9aa80-129">If the database is local, the account is translated to the correct localized representation of the account.</span></span> <span data-ttu-id="9aa80-130">Bei einer Remotedatenbank wird das Konto als das Konto des Computers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9aa80-130">If the database is remote, the account is represented as the computer's account.</span></span>  
  
 <span data-ttu-id="9aa80-131">In der folgenden Tabelle sind Konten, die übersetzt werden, und ihre Remotedarstellung aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9aa80-131">The following table shows accounts that are translated and their remote representation.</span></span>  
  
|<span data-ttu-id="9aa80-132">Konto/SID, das bzw. die übersetzt wird</span><span class="sxs-lookup"><span data-stu-id="9aa80-132">Account / SID that is translated</span></span>|<span data-ttu-id="9aa80-133">Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="9aa80-133">Common Name</span></span>|<span data-ttu-id="9aa80-134">Remotename</span><span class="sxs-lookup"><span data-stu-id="9aa80-134">Remote Name</span></span>|  
|---------------------------------------|-----------------|-----------------|  
|<span data-ttu-id="9aa80-135">(S-1-5-18)</span><span class="sxs-lookup"><span data-stu-id="9aa80-135">(S-1-5-18)</span></span>|<span data-ttu-id="9aa80-136">Lokales System</span><span class="sxs-lookup"><span data-stu-id="9aa80-136">Local System</span></span>|<span data-ttu-id="9aa80-137">\<Domain>\\<Computername\>$</span><span class="sxs-lookup"><span data-stu-id="9aa80-137">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="9aa80-138">.\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="9aa80-138">.\LocalSystem</span></span>|<span data-ttu-id="9aa80-139">Lokales System</span><span class="sxs-lookup"><span data-stu-id="9aa80-139">Local System</span></span>|<span data-ttu-id="9aa80-140">\<Domain>\\<Computername\>$</span><span class="sxs-lookup"><span data-stu-id="9aa80-140">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="9aa80-141">ComputerName\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="9aa80-141">ComputerName\LocalSystem</span></span>|<span data-ttu-id="9aa80-142">Lokales System</span><span class="sxs-lookup"><span data-stu-id="9aa80-142">Local System</span></span>|<span data-ttu-id="9aa80-143">\<Domain>\\<Computername\>$</span><span class="sxs-lookup"><span data-stu-id="9aa80-143">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="9aa80-144">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="9aa80-144">LocalSystem</span></span>|<span data-ttu-id="9aa80-145">Lokales System</span><span class="sxs-lookup"><span data-stu-id="9aa80-145">Local System</span></span>|<span data-ttu-id="9aa80-146">\<Domain>\\<Computername\>$</span><span class="sxs-lookup"><span data-stu-id="9aa80-146">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="9aa80-147">(S-1-5-20)</span><span class="sxs-lookup"><span data-stu-id="9aa80-147">(S-1-5-20)</span></span>|<span data-ttu-id="9aa80-148">Netzwerkdienst</span><span class="sxs-lookup"><span data-stu-id="9aa80-148">Network Service</span></span>|<span data-ttu-id="9aa80-149">\<Domain>\\<Computername\>$</span><span class="sxs-lookup"><span data-stu-id="9aa80-149">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="9aa80-150">NT AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="9aa80-150">NT AUTHORITY\NetworkService</span></span>|<span data-ttu-id="9aa80-151">Netzwerkdienst</span><span class="sxs-lookup"><span data-stu-id="9aa80-151">Network Service</span></span>|<span data-ttu-id="9aa80-152">\<Domain>\\<Computername\>$</span><span class="sxs-lookup"><span data-stu-id="9aa80-152">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="9aa80-153">(S-1-5-19)</span><span class="sxs-lookup"><span data-stu-id="9aa80-153">(S-1-5-19)</span></span>|<span data-ttu-id="9aa80-154">Lokaler Dienst</span><span class="sxs-lookup"><span data-stu-id="9aa80-154">Local Service</span></span>|<span data-ttu-id="9aa80-155">Fehler – siehe unten.</span><span class="sxs-lookup"><span data-stu-id="9aa80-155">Error - see below.</span></span>|  
|<span data-ttu-id="9aa80-156">NT AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="9aa80-156">NT AUTHORITY\LocalService</span></span>|<span data-ttu-id="9aa80-157">Lokaler Dienst</span><span class="sxs-lookup"><span data-stu-id="9aa80-157">Local Service</span></span>|<span data-ttu-id="9aa80-158">Fehler – siehe unten.</span><span class="sxs-lookup"><span data-stu-id="9aa80-158">Error - see below.</span></span>|  
  
 <span data-ttu-id="9aa80-159">Wenn Sie unter [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)]ein integriertes Konto verwenden und es sich bei der Berichtsserver-Datenbank um eine Remotedatenbank handelt, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9aa80-159">On [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], if you are using a built-in account and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="9aa80-160">Falls das integrierte `LocalService`-Konto angegeben wird und es sich bei der Berichtsserver-Datenbank um eine Remotedatenbank handelt, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9aa80-160">If the `LocalService` built-in account is specified and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="9aa80-161">Wenn *IsWindowsUser* auf true festgelegt ist und der in *UserName* bereitgestellte Wert übersetzt werden muss, bestimmt der WMI-Anbieter, ob sich die Berichtsserver-Datenbank auf demselben Computer oder auf einem Remotecomputer befindet.</span><span class="sxs-lookup"><span data-stu-id="9aa80-161">When *IsWindowsUser* is true and the value supplied in *UserName* needs to be translated, the WMI provider determines whether the report server database is located on the same computer or on a remote computer.</span></span> <span data-ttu-id="9aa80-162">Um zu bestimmen, ob es sich um eine lokale Installation handelt, wertet der WMI-Anbieter die DatabaseServerName-Eigenschaft anhand der folgenden Werteliste aus.</span><span class="sxs-lookup"><span data-stu-id="9aa80-162">To determine if the installation is local, the WMI provider evaluates the DatabaseServerName property against the following list of values.</span></span> <span data-ttu-id="9aa80-163">Wenn eine Übereinstimmung gefunden wird, handelt es sich um eine lokale Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9aa80-163">If a match is found, the database is local.</span></span> <span data-ttu-id="9aa80-164">Andernfalls ist es eine Remotedatenbank.</span><span class="sxs-lookup"><span data-stu-id="9aa80-164">Otherwise, it is remote.</span></span> <span data-ttu-id="9aa80-165">Bei dem Vergleich wird Groß- und Kleinschreibung nicht unterschieden.</span><span class="sxs-lookup"><span data-stu-id="9aa80-165">The comparison is case-insensitive.</span></span>  
  
|<span data-ttu-id="9aa80-166">Wert von "DatabaseServerName"</span><span class="sxs-lookup"><span data-stu-id="9aa80-166">Value of DatabaseServerName</span></span>|<span data-ttu-id="9aa80-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9aa80-167">Example</span></span>|  
|---------------------------------|-------------|  
|<span data-ttu-id="9aa80-168">„.“</span><span class="sxs-lookup"><span data-stu-id="9aa80-168">"."</span></span>||  
|<span data-ttu-id="9aa80-169">„(local)“</span><span class="sxs-lookup"><span data-stu-id="9aa80-169">"(local)"</span></span>||  
|<span data-ttu-id="9aa80-170">„LOCAL“</span><span class="sxs-lookup"><span data-stu-id="9aa80-170">"LOCAL"</span></span>||  
|<span data-ttu-id="9aa80-171">localhost</span><span class="sxs-lookup"><span data-stu-id="9aa80-171">localhost</span></span>||  
|\<Machinename>|<span data-ttu-id="9aa80-172">testlab14</span><span class="sxs-lookup"><span data-stu-id="9aa80-172">testlab14</span></span>|  
|\<MachineFQDN>|<span data-ttu-id="9aa80-173">example.redmond.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9aa80-173">example.redmond.microsoft.com</span></span>|  
|\<IPAddress>|<span data-ttu-id="9aa80-174">180.012.345,678</span><span class="sxs-lookup"><span data-stu-id="9aa80-174">180.012.345,678</span></span>|  
  
 <span data-ttu-id="9aa80-175">Wenn *IsWindowsUser* auf festgelegt ist `true` , ruft der WMI-Anbieter LookupAccountName auf, um die sid für das Konto zu erhalten, und ruft dann LookupAccountSid auf, um den Namen zu erhalten, der in das Skript eingefügt werden soll [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9aa80-175">When *IsWindowsUser* is set to `true`, the WMI provider calls LookupAccountName to get the SID for the account and then calls LookupAccountSID to get the name to put in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span> <span data-ttu-id="9aa80-176">Hierdurch wird sichergestellt, dass der verwendete Kontoname die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Überprüfung erfolgreich durchläuft.</span><span class="sxs-lookup"><span data-stu-id="9aa80-176">This ensures that the account name used will pass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validation.</span></span>  
  
 <span data-ttu-id="9aa80-177">Wenn *IsWindowsUser* auf festgelegt ist `false` , gewährt das generierte Skript die **RSExec** -Rolle für die Berichts Server-Datenbank, die temporäre Berichts Server-Datenbank und die msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9aa80-177">When *IsWindowsUser* is set to `false`, the generated script grants the **RSExec** role on the report server database, the report server temporary database, and the MSDB database.</span></span>  
  
 <span data-ttu-id="9aa80-178">Wenn *IsWindowsUser* auf festgelegt ist `false` , muss der SQL Server Benutzer bereits im vorhanden sein, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] damit das Skript erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9aa80-178">When *IsWindowsUser* is set to `false`, the SQL Server user must already exist on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the script to run successfully.</span></span>  
  
 <span data-ttu-id="9aa80-179">Wenn für den Berichtsserver keine Berichtsserver-Datenbank angegeben ist, wird bei einem Aufruf von GrantRightsToDatabaseUser ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9aa80-179">If the report server does not have a report server database specified, calling GrantRightsToDatabaseUser returns an error.</span></span>  
  
 <span data-ttu-id="9aa80-180">Das generierte Skript unterstützt [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 und [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9aa80-180">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aa80-181">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9aa80-181">Requirements</span></span>  
 <span data-ttu-id="9aa80-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aa80-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa80-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9aa80-183">See Also</span></span>  
 [<span data-ttu-id="9aa80-184">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="9aa80-184">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
