---
title: Option „replay“ (Distributed Replay-Verwaltungstool) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
author: stevestein
ms.author: sstein
ms.openlocfilehash: a3114d7c2a2a7908e4e010fbf5d80c7d332d264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724309"
---
# <a name="replay-option-distributed-replay-administration-tool"></a><span data-ttu-id="a9512-102">Option Wiedergabe (Verwaltungstool Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="a9512-102">Replay Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="a9512-103">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay Verwaltungs Tool, `DReplay.exe` , ist ein Befehlszeilen Tool, das Sie für die Kommunikation mit dem verteilten Replay-Controller verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a9512-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="a9512-104">In diesem Thema werden die **replay** -Befehlszeilenoption und die entsprechende Syntax beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9512-104">This topic describes the **replay** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="a9512-105">Die **replay** -Option initiiert die Ereigniswiedergabephase, in der der Controller Wiedergabedaten an die angegebenen Clients weiterleitet, die verteilte Wiedergabe startet und die Clients synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="a9512-105">The **replay** option initiates the event replay stage, in which the controller dispatches replay data to the specified clients, launches the distributed replay and synchronizes the clients.</span></span> <span data-ttu-id="a9512-106">Optional kann jeder Client, der an der Wiedergabe teilnimmt, die Wiedergabeaktivität aufzeichnen und eine Ergebnisdatei der Ablaufverfolgung lokal speichern.</span><span class="sxs-lookup"><span data-stu-id="a9512-106">Optionally, each client participating in the replay can record the replay activity and save a result trace file locally.</span></span>

 <span data-ttu-id="a9512-107">![Artikellinksymbol](../../database-engine/media/topic-link.gif "Symbol für Themenlink") Weitere Informationen zu den Syntaxkonventionen für das Verwaltungstool finden Sie unter [Transact-SQL-Syntaxkonventionen &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a9512-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="a9512-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9512-108">Syntax</span></span>

```

      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]
    [-starget_server] -wclients [-cconfig_file]
    [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="a9512-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9512-109">Parameters</span></span>
 <span data-ttu-id="a9512-110">**-m** *Controller* gibt den Computernamen des Controllers an.</span><span class="sxs-lookup"><span data-stu-id="a9512-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="a9512-111">Sie können mit "`localhost`" oder "`.`" auf den lokalen Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="a9512-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="a9512-112">Wenn der **-m** -Parameter nicht angegeben ist, wird der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9512-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="a9512-113">**-d** *controller_working_dir* gibt das Verzeichnis auf dem Controller an, in dem die zwischen Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-113">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="a9512-114">Der **-d** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9512-114">The **-d** parameter is required.</span></span>

 <span data-ttu-id="a9512-115">Es gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="a9512-115">The following requirements apply:</span></span>

-   <span data-ttu-id="a9512-116">Das Verzeichnis muss sich auf dem Controller befinden.</span><span class="sxs-lookup"><span data-stu-id="a9512-116">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="a9512-117">Sie müssen den vollständigen Pfad angeben, der mit einem Laufwerkbuchstaben beginnen muss (z. B. `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="a9512-117">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="a9512-118">Der Pfad darf nicht mit einem umgekehrten Schrägstrich ("`\`") enden.</span><span class="sxs-lookup"><span data-stu-id="a9512-118">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="a9512-119">UNC-Pfade werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9512-119">UNC paths are not supported.</span></span>

 <span data-ttu-id="a9512-120">**-o** Erfasst die Wiedergabe Aktivität der Clients und speichert Sie in einer Ergebnisdatei der Ablauf Verfolgung in dem Pfad, der vom- `<ResultDirectory>` Element in der Client Konfigurationsdatei angegeben wird `DReplayClient.xml` .</span><span class="sxs-lookup"><span data-stu-id="a9512-120">**-o** Captures the clients' replay activity and saves it to a result trace file in the path specified by the `<ResultDirectory>` element in the client configuration file, `DReplayClient.xml`.</span></span>

 <span data-ttu-id="a9512-121">Wenn der **-o** -Parameter nicht angegeben wird, wird die Ergebnisdatei der Ablaufverfolgung nicht generiert.</span><span class="sxs-lookup"><span data-stu-id="a9512-121">When the **-o** parameter is not specified, the result trace file is not generated.</span></span> <span data-ttu-id="a9512-122">Die Konsolenausgabe gibt am Ende der Wiedergabe Zusammenfassungsinformationen zurück, es sind jedoch keine weiteren Wiedergabestatistiken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9512-122">The console output returns summary information at the end of replay, but no other replay statistics are available.</span></span>

 <span data-ttu-id="a9512-123">**-s** *target_server* gibt die Ziel Instanz von an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , für die die verteilte Arbeitsauslastung wiedergegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9512-123">**-s** *target_server* Specifies the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that the distributed workload should be replayed against.</span></span> <span data-ttu-id="a9512-124">Sie müssen diesen Parameter im folgenden Format angeben: **server_name[\instance name]** .</span><span class="sxs-lookup"><span data-stu-id="a9512-124">You must specify this parameter in the format **server_name[\instance name]**.</span></span>

 <span data-ttu-id="a9512-125">Sie können den Zielserver nicht mit "`localhost`" oder "`.`" angeben.</span><span class="sxs-lookup"><span data-stu-id="a9512-125">You cannot use "`localhost`" or "`.`" as the target server.</span></span>

 <span data-ttu-id="a9512-126">Der **-s** -Parameter ist nicht erforderlich, wenn das `<Server>` -Element im `<ReplayOptions>` -Abschnitt der Wiedergabekonfigurationsdatei `DReplay.exe.replay.config`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-126">The **-s** parameter is not required if the `<Server>` element is specified in the `<ReplayOptions>` section of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="a9512-127">Wenn der **-s** -Parameter verwendet wird, wird das `<Server>` -Element im `<ReplayOptions>` -Abschnitt der Wiedergabekonfigurationsdatei ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a9512-127">If the **-s** parameter is used, the `<Server>` element in the `<ReplayOptions>` section of the replay configuration file will be ignored.</span></span>

 <span data-ttu-id="a9512-128">**-w** *Clients* dieser erforderliche Parameter ist eine durch Trennzeichen getrennte Liste (ohne Leerzeichen), die die Computernamen von Clients angibt, die an der verteilten Wiedergabe teilnehmen sollen.</span><span class="sxs-lookup"><span data-stu-id="a9512-128">**-w** *clients* This required parameter is a comma-separated list (without spaces) that specifies the computer names of clients that should participate in the distributed replay.</span></span> <span data-ttu-id="a9512-129">IP-Adressen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a9512-129">IP addresses are not allowed.</span></span> <span data-ttu-id="a9512-130">Beachten Sie, dass die Clients bereits beim Controller registriert sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a9512-130">Be aware that the clients must already be registered with the controller.</span></span>

> [!NOTE]
>  <span data-ttu-id="a9512-131">Jeder Client wird beim Starten des Clientdiensts bei dem Controller registriert, der in der Clientkonfigurationsdatei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a9512-131">Each client registers with the controller that is specified in the client configuration file when the client service starts.</span></span>

 <span data-ttu-id="a9512-132">der **-c-** *Config_file* ist der vollständige Pfad der Wiedergabe Konfigurationsdatei. wird verwendet, um den Speicherort anzugeben, an dem er an einem anderen Speicherort gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-132">**-c** *config_file* Is the full path of the replay configuration file; used to specify the location when it is stored in a different location.</span></span>

 <span data-ttu-id="a9512-133">Der **-c** -Parameter ist nicht erforderlich, wenn Sie die Standardwerte der Wiedergabekonfigurationsdatei `DReplay.exe.replay.config`verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a9512-133">The **-c** parameter is not required if you want to use the default values of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="a9512-134">**-f** *status_interval* gibt die Häufigkeit (in Sekunden) an, mit der der Status angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-134">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="a9512-135">Wenn **-f** nicht angegeben wird, ist das Standardintervall 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="a9512-135">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="a9512-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a9512-136">Examples</span></span>
 <span data-ttu-id="a9512-137">In diesem Beispiel wird ein Großteil des Verhaltens der verteilten Wiedergabe von der geänderten Wiedergabekonfigurationsdatei `DReplay.exe.replay.config`abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a9512-137">In this example, the distributed replay derives much of its behavior from a modified replay configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="a9512-138">Der **-m** -Parameter gibt an, dass ein Computer mit dem Namen `controller1` als Controller fungiert.</span><span class="sxs-lookup"><span data-stu-id="a9512-138">The **-m** parameter specifies that a computer named `controller1` acts as the controller.</span></span> <span data-ttu-id="a9512-139">Der Computername muss angegeben werden, wenn der Controllerdienst auf einem anderen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-139">The computer name must be specified when the controller service is running on a different computer.</span></span>

-   <span data-ttu-id="a9512-140">Der **-d** -Parameter gibt den Speicherort der Zwischendatei auf dem Controller im Verzeichnis an ( `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="a9512-140">The **-d** parameter specifies the location of the intermediate file on the controller, `c:\WorkingDir`.</span></span>

-   <span data-ttu-id="a9512-141">Der **-o** -Parameter legt fest, dass jeder angegebene Client die Wiedergabeaktivität aufzeichnet und in einer Ergebnisdatei der Ablaufverfolgung speichert.</span><span class="sxs-lookup"><span data-stu-id="a9512-141">The **-o** parameter specifies that each specified client capture the replay activity and save it to a result trace file.</span></span> <span data-ttu-id="a9512-142">Hinweis: Mit dem `<ResultTrace>`-Element in der Konfigurationsdatei kann angegeben werden, ob Zeilenanzahl und Resultset aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a9512-142">Note: The `<ResultTrace>` element in the configuration file can be used to specify if row count and result set be recorded.</span></span>

-   <span data-ttu-id="a9512-143">Der **-w** -Parameter gibt an, dass die Computer `client1` bis `client4` als Clients an der verteilten Wiedergabe teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="a9512-143">The **-w** parameter specifies that computers `client1` through `client4` participate as clients in the distributed replay.</span></span>

-   <span data-ttu-id="a9512-144">Der **-c** -Parameter wird verwendet, um auf die geänderte Konfigurationsdatei `DReplay.exe.replay.config`zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="a9512-144">The **-c** parameter is used to point to the modified configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="a9512-145">Der **-s** -Parameter ist nicht erforderlich, da das `<Server>` -Element im `<ReplayOptions>` -Element der Wiedergabekonfigurationsdatei `DReplay.exe.replay.config`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-145">The **-s** parameter is not required because the `<Server>` element is specified in the `<ReplayOptions>` element of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="a9512-146">Die Ereigniswiedergabephase wird mit der folgenden Syntax initiiert, wenn das Verwaltungstool und der Controller nicht auf demselben Computer ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a9512-146">The event replay stage is initiated with the following syntax, when the administration tool is run from a different computer than the controller:</span></span>

```
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config
```

 <span data-ttu-id="a9512-147">Um einen synchronen Sequenzierungsmodus anzugeben, wird das `<SequencingMode>` -Element der Datei `DReplay.exe.replay.config` auf den Wert `synchronization`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9512-147">To specify a synchronous sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `synchronization`.</span></span> <span data-ttu-id="a9512-148">Der `<ResultTrace>` -Abschnitt der Wiedergabekonfigurationsdatei wurde geändert, um anzugeben, dass die Zeilenanzahl aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a9512-148">The `<ResultTrace>` section of the replay configuration file is modified to specify that row count be recorded.</span></span> <span data-ttu-id="a9512-149">Diese Änderungen werden im folgenden XML-Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9512-149">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance</Server>
        <SequencingMode>synchronization</SequencingMode>
        <ConnectTimeScale></ConnectTimeScale>
        <ThinkTimeScale></ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

 <span data-ttu-id="a9512-150">Um einen Belastungssequenzierungsmodus anzugeben, wird das `<SequencingMode>` -Element der Datei `DReplay.exe.replay.config` auf den Wert `stress`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9512-150">To specify a stress sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `stress`.</span></span> <span data-ttu-id="a9512-151">Das `<ConnectTimeScale>` -Element und das `<ThinkTimeScale>` -Element werden auf den Wert `50` festgelegt (um 50 Prozent anzugeben).</span><span class="sxs-lookup"><span data-stu-id="a9512-151">The `<ConnectTimeScale>` and `<ThinkTimeScale>` elements are set to the value `50` (to specify 50 percent).</span></span> <span data-ttu-id="a9512-152">Weitere Informationen zu Verbindungszeit und Reaktionszeit finden Sie unter [Konfigurieren von Distributed Replay](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="a9512-152">For more information about connect time and think time, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span> <span data-ttu-id="a9512-153">Diese Änderungen werden im folgenden XML-Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9512-153">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance_name</Server>
        <SequencingMode>stress</SequencingMode>
        <ConnectTimeScale>50</ConnectTimeScale>
        <ThinkTimeScale>50</ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="a9512-154">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a9512-154">Permissions</span></span>
 <span data-ttu-id="a9512-155">Sie müssen das Verwaltungstool als interaktiver Benutzer mit einem lokalen Benutzerkonto oder Domänenbenutzerkonto ausführen.</span><span class="sxs-lookup"><span data-stu-id="a9512-155">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="a9512-156">Um ein lokales Benutzerkonto zu verwenden, müssen das Verwaltungstool und der Controller auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a9512-156">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="a9512-157">Weitere Informationen finden Sie unter [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="a9512-157">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9512-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9512-158">See Also</span></span>
 <span data-ttu-id="a9512-159">Wiedergeben von Ablauf [Verfolgungs Daten](replay-trace-data.md) [Überprüfen Sie die Wiedergabe Ergebnisse](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Konfigurieren Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forums](https://social.technet.microsoft.com/Forums/sl/sqldru/) [mithilfe Distributed Replay zum Auslastungs Test Ihres SQL Server-Teils 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [mithilfe Distributed Replay zum Auslastungs Test SQL Server-Teil 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span><span class="sxs-lookup"><span data-stu-id="a9512-159">[Replay Trace Data](replay-trace-data.md) [Review the Replay Results](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [Using Distributed Replay to Load Test Your SQL Server - Part 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [Using Distributed Replay to Load Test Your SQL Server - Part 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span></span>


