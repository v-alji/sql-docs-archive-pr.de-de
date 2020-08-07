---
title: Option „preprocess“ (Distributed Replay-Verwaltungstool) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 9b5012fd-233e-4a25-a2e1-585c63b70502
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7f168d45b03473d958e202bd75116f4519d2fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615730"
---
# <a name="preprocess-option-distributed-replay-administration-tool"></a><span data-ttu-id="35197-102">Vorverarbeitungsoption (Verwaltungstool "Distributed Replay")</span><span class="sxs-lookup"><span data-stu-id="35197-102">Preprocess Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="35197-103">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Verwaltungs Tool, `DReplay.exe` , ist ein Befehlszeilen Tool, das Sie für die Kommunikation mit dem verteilten Replay-Controller verwenden können.</span><span class="sxs-lookup"><span data-stu-id="35197-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="35197-104">In diesem Thema werden die Befehlszeilenoption **preprocess** und die entsprechende Syntax beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35197-104">This topic describes the **preprocess** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="35197-105">Die **preprocess** -Option initiiert die Vorverarbeitungsphase.</span><span class="sxs-lookup"><span data-stu-id="35197-105">The **preprocess** option initiates the preprocess stage.</span></span> <span data-ttu-id="35197-106">In dieser Phase bereitet der Controller die Eingabedaten der Ablaufverfolgung für die Wiedergabe anhand des Zielservers vor.</span><span class="sxs-lookup"><span data-stu-id="35197-106">During this stage, the controller prepares the input trace data for replay against the target server.</span></span>

 <span data-ttu-id="35197-107">![Artikellinksymbol](../../database-engine/media/topic-link.gif "Symbol für Themenlink") Weitere Informationen zu den Syntaxkonventionen für das Verwaltungstool finden Sie unter [Transact-SQL-Syntaxkonventionen &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="35197-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="35197-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="35197-108">Syntax</span></span>

```

      dreplay preprocess [-mcontroller] -iinput_trace_file
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="35197-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="35197-109">Parameters</span></span>
 <span data-ttu-id="35197-110">**-m** *Controller* gibt den Computernamen des Controllers an.</span><span class="sxs-lookup"><span data-stu-id="35197-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="35197-111">Sie können mit "`localhost`" oder "`.`" auf den lokalen Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="35197-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="35197-112">Wenn der **-m** -Parameter nicht angegeben ist, wird der lokale Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="35197-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="35197-113">**-i** *input_trace_file* gibt den vollständigen Pfad der Eingabedatei der Ablauf Verfolgung auf dem Controller an, z `D:\Mytrace.trc` . b..</span><span class="sxs-lookup"><span data-stu-id="35197-113">**-i** *input_trace_file* Specifies the full path of the input trace file on the controller, such as `D:\Mytrace.trc`.</span></span> <span data-ttu-id="35197-114">Der **-i** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35197-114">The **-i** parameter is required.</span></span>

 <span data-ttu-id="35197-115">Wenn Rolloverdateien im gleichen Verzeichnis vorhanden sind, werden sie geladen und automatisch verwendet.</span><span class="sxs-lookup"><span data-stu-id="35197-115">If there are rollover files in the same directory, they will be loaded and used automatically.</span></span> <span data-ttu-id="35197-116">Die Dateien müssen der Dateirollover-Benennungskonvention folgen, z.B.: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="35197-116">The files must follow the file rollover naming convention, for example: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span></span>

> [!NOTE]
>  <span data-ttu-id="35197-117">Wenn Sie das Verwaltungstool auf einem anderen Computer als dem Controller verwenden, müssen Sie die Eingabedateien der Ablaufverfolgung auf den Controller kopieren, damit ein lokaler Pfad für diesen Parameter verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="35197-117">If you are using the administration tool on a different computer than the controller, you will need to copy the input trace files to the controller so that a local path can be used for this parameter.</span></span>

 <span data-ttu-id="35197-118">**-d** *controller_working_dir* gibt das Verzeichnis auf dem Controller an, in dem die zwischen Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="35197-118">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="35197-119">Der **-d** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35197-119">The **-d** parameter is required.</span></span>

 <span data-ttu-id="35197-120">Es gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="35197-120">The following requirements apply:</span></span>

-   <span data-ttu-id="35197-121">Das Verzeichnis muss sich auf dem Controller befinden.</span><span class="sxs-lookup"><span data-stu-id="35197-121">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="35197-122">Sie müssen den vollständigen Pfad angeben, der mit einem Laufwerkbuchstaben beginnen muss (z. B. `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="35197-122">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="35197-123">Der Pfad darf nicht mit einem umgekehrten Schrägstrich ("`\`") enden.</span><span class="sxs-lookup"><span data-stu-id="35197-123">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="35197-124">UNC-Pfade werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35197-124">UNC paths are not supported.</span></span>

 <span data-ttu-id="35197-125">der **-c-** *Config_file* ist der vollständige Pfad der Vorverarbeitungs Konfigurationsdatei. wird verwendet, um den Speicherort der Vorverarbeitungs Konfigurationsdatei anzugeben, wenn Sie an einem anderen Speicherort gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="35197-125">**-c** *config_file* Is the full path of the preprocess configuration file; used to specify the location of the preprocess configuration file when stored in a different location.</span></span> <span data-ttu-id="35197-126">Dieser Parameter kann ein UNC-Pfad sein oder ein lokales Verzeichnis auf dem Computer angeben, auf dem Sie das Verwaltungstool ausführen.</span><span class="sxs-lookup"><span data-stu-id="35197-126">This parameter can be a UNC path, or can reside locally on the computer where you run the administration tool.</span></span>

 <span data-ttu-id="35197-127">Der **-c** -Parameter ist nicht erforderlich, wenn keine Filterung benötigt wird oder wenn Sie die maximale Leerlaufzeit nicht ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="35197-127">The **-c** parameter is not required if no filtering is needed, or if you do not want to modify the maximum idle time.</span></span>

 <span data-ttu-id="35197-128">Ohne den **-c** -Parameter wird die Standardkonfigurationsdatei für die Vorverarbeitung verwendet: `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="35197-128">Without the **-c** parameter, the default preprocess configuration file, `DReplay.exe.preprocess.config`, is used.</span></span>

 <span data-ttu-id="35197-129">**-f** *status_interval* gibt die Häufigkeit (in Sekunden) für die Anzeige von Statusmeldungen an.</span><span class="sxs-lookup"><span data-stu-id="35197-129">**-f** *status_interval* Specifies the frequency (in seconds) at which to display status messages.</span></span>

 <span data-ttu-id="35197-130">Wenn **-f** nicht angegeben wird, ist das Standardintervall 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="35197-130">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="35197-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="35197-131">Examples</span></span>
 <span data-ttu-id="35197-132">In diesem Beispiel wird die Vorverarbeitungsphase mit allen Standardeinstellungen initiiert.</span><span class="sxs-lookup"><span data-stu-id="35197-132">In this example, the preprocess stage is initiated with all of the default settings.</span></span> <span data-ttu-id="35197-133">Der Wert `localhost` gibt an, dass der Controllerdienst auf demselben Computer wie das Verwaltungstool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="35197-133">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span> <span data-ttu-id="35197-134">Der *input_trace_file* -Parameter gibt den Speicherort der Eingabedaten der Ablaufverfolgung an: `c:\mytrace.trc`.</span><span class="sxs-lookup"><span data-stu-id="35197-134">The *input_trace_file* parameter specifies the location of the input trace data, `c:\mytrace.trc`.</span></span> <span data-ttu-id="35197-135">Da keine Filterung der Ablaufverfolgungsdatei erfolgt, muss der **-c** -Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="35197-135">Because there is no trace file filtering involved, the **-c** parameter does have to be specified.</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir
```

 <span data-ttu-id="35197-136">In diesem Beispiel wird die Vorverarbeitungsphase initiiert, und es wird eine geänderte Vorverarbeitungskonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="35197-136">In this example, the preprocess stage is initiated and a modified preprocess configuration file is specified.</span></span> <span data-ttu-id="35197-137">Im Gegensatz zum vorherigen Beispiel wird der **-c** -Parameter verwendet, um auf die geänderte Konfigurationsdatei zu zeigen, wenn Sie diese an einem anderen Speicherort gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="35197-137">Unlike the previous example, the **-c** parameter is used to point to the modified configuration file, if you have stored it in a different location.</span></span> <span data-ttu-id="35197-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35197-138">For example:</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir -c c:\DReplay.exe.preprocess.config
```

 <span data-ttu-id="35197-139">Der geänderten Vorverarbeitungskonfigurationsdatei wird eine Filterbedingung hinzugefügt, die während der verteilten Wiedergabe Systemsitzungen herausfiltert.</span><span class="sxs-lookup"><span data-stu-id="35197-139">In the modified preprocess configuration file, a filter condition is added that filters out system sessions during distributed replay.</span></span> <span data-ttu-id="35197-140">Der Filter wird durch Ändern des `<PreprocessModifiers>` -Elements in der Vorverarbeitungskonfigurationsdatei `DReplay.exe.preprocess.config`hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="35197-140">The filter is added by modifying the `<PreprocessModifiers>` element in the preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span>

 <span data-ttu-id="35197-141">Im folgenden Beispiel wird die geänderte Konfigurationsdatei gezeigt:</span><span class="sxs-lookup"><span data-stu-id="35197-141">The following shows an example of the modified configuration file:</span></span>

```
<?xml version='1.0'?>
<Options>
    <PreprocessModifiers>
        <IncSystemSession>No</IncSystemSession>
        <MaxIdleTime>-1</MaxIdleTime>
    </PreprocessModifiers>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="35197-142">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35197-142">Permissions</span></span>
 <span data-ttu-id="35197-143">Sie müssen das Verwaltungstool als interaktiver Benutzer mit einem lokalen Benutzerkonto oder Domänenbenutzerkonto ausführen.</span><span class="sxs-lookup"><span data-stu-id="35197-143">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="35197-144">Um ein lokales Benutzerkonto zu verwenden, müssen das Verwaltungstool und der Controller auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="35197-144">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="35197-145">Weitere Informationen finden Sie unter [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="35197-145">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35197-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35197-146">See Also</span></span>
 <span data-ttu-id="35197-147">[Vorbereiten der Eingabedaten der Ablauf Verfolgung](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Konfigurieren Distributed Replay](configure-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="35197-147">[Prepare the Input Trace Data](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md)</span></span>


