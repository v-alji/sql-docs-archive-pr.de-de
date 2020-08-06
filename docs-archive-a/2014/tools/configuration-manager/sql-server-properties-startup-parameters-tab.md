---
title: SQL Server Eigenschaften (Registerkarte "Startparameter") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 16942624-5374-446c-8de4-ee6ed34d6e94
author: stevestein
ms.author: sstein
ms.openlocfilehash: 66c4b71433face008ba78af93579cf175fb4bed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617333"
---
# <a name="sql-server-properties-startup-parameters-tab"></a><span data-ttu-id="989d5-102">SQL Server-Eigenschaften (Registerkarte "Startparameter")</span><span class="sxs-lookup"><span data-stu-id="989d5-102">SQL Server Properties (Startup Parameters Tab)</span></span>
  <span data-ttu-id="989d5-103">Verwenden Sie dieses Dialogfeld, um Startparameter für [!INCLUDE[ssDE](../../includes/ssde-md.md)]hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="989d5-103">Use this dialog box to add or remove startup parameters for the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="989d5-104">Startparameter können große Auswirkungen auf die Leistung von [!INCLUDE[ssDE](../../includes/ssde-md.md)] haben.</span><span class="sxs-lookup"><span data-stu-id="989d5-104">Startup parameters can have a large effect on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] performance.</span></span> <span data-ttu-id="989d5-105">Lesen Sie vor dem Hinzufügen oder Ändern von Startparametern das Thema "Verwenden der Startoptionen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="989d5-105">Before adding or changing startup parameters, see the topic "Using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Service Startup Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="989d5-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="989d5-106">Options</span></span>  
 <span data-ttu-id="989d5-107">**Startparameter angeben**</span><span class="sxs-lookup"><span data-stu-id="989d5-107">**Specify a startup parameter**</span></span>  
 <span data-ttu-id="989d5-108">Um einen Parameter hinzuzufügen, geben Sie den Parameter ein, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="989d5-108">To add a parameter, type the parameter, and then click **Add**.</span></span>  
  
 <span data-ttu-id="989d5-109">Um einen der erforderlichen Parameter zu ändern, wählen Sie den Parameter im Feld **Vorhandene Parameter** aus, ändern Sie die Werte im Feld **Startparameter angeben** , und klicken Sie dann auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="989d5-109">To modify one of the required parameters, select the parameter in the **Existing parameters** box, change the values in the **Specify a startup parameter** box, and then click **Update**.</span></span>  
  
 <span data-ttu-id="989d5-110">**Vorhandene Parameter**</span><span class="sxs-lookup"><span data-stu-id="989d5-110">**Existing parameters**</span></span>  
 <span data-ttu-id="989d5-111">Um einen Parameter zu entfernen, wählen Sie den Parameter aus, und klicken Sie anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="989d5-111">To remove a parameter, select a parameter, and then click **Remove**.</span></span>  
  
## <a name="parameter-format"></a><span data-ttu-id="989d5-112">Parameterformat</span><span class="sxs-lookup"><span data-stu-id="989d5-112">Parameter Format</span></span>  
 <span data-ttu-id="989d5-113">Geben Sie kein Trennzeichen zwischen Parametern ein.</span><span class="sxs-lookup"><span data-stu-id="989d5-113">Do not enter a separator between parameters.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="989d5-114">-Konfigurations-Manager fügt das Trennzeichen automatisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="989d5-114">Configuration Manager automatically adds the separator.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="989d5-115">-Konfigurations-Manager erzwingt die folgenden Parameteranforderungen.</span><span class="sxs-lookup"><span data-stu-id="989d5-115">Configuration Manager enforces the following parameter requirements.</span></span>  
  
-   <span data-ttu-id="989d5-116">Führende und nachfolgende Leerzeichen jedes Startparameters werden abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="989d5-116">Leading and trailing spaces are trimmed from any startup parameter.</span></span>  
  
-   <span data-ttu-id="989d5-117">Alle Startparameter beginnen mit „–“ (Bindestrich), und der zweite Wert ist ein Buchstabe.</span><span class="sxs-lookup"><span data-stu-id="989d5-117">All startup parameters start with a - (dash) and the second value is a letter.</span></span>  
  
## <a name="required-parameters"></a><span data-ttu-id="989d5-118">Erforderliche Parameter</span><span class="sxs-lookup"><span data-stu-id="989d5-118">Required Parameters</span></span>  
 <span data-ttu-id="989d5-119">Die folgenden Parameter sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="989d5-119">The following parameters are required.</span></span> <span data-ttu-id="989d5-120">Sie können geändert, jedoch nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="989d5-120">They can be changed but not removed.</span></span>  
  
-   <span data-ttu-id="989d5-121">„-d“ ist der Pfad der Datei **master.mdf** (die Datendatei der Masterdatenbank).</span><span class="sxs-lookup"><span data-stu-id="989d5-121">-d is the path of the **master.mdf** file (the master database data file).</span></span>  
  
-   <span data-ttu-id="989d5-122">„-l“ ist der Pfad der Datei **master.ldf** (die Protokolldatei der Masterdatenbank).</span><span class="sxs-lookup"><span data-stu-id="989d5-122">-l is the path of the **master.ldf** file (the master database log file).</span></span>  
  
-   <span data-ttu-id="989d5-123">„-e“ ist der Pfad der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokolldateien.</span><span class="sxs-lookup"><span data-stu-id="989d5-123">-e is the path of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log files.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="989d5-124">Wenn die Dateipfadparameter falsch sind, wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] möglicherweise nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="989d5-124">If the file path parameters are incorrect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not start.</span></span>  
  
 <span data-ttu-id="989d5-125">Weitere Informationen zum Verschieben der master-Datenbank finden Sie im Thema "Verschieben von Systemdatenbanken" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="989d5-125">For more information about how to move the master database, see the topic "Moving System Databases" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="989d5-126">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="989d5-126">Optional Parameters</span></span>  
 <span data-ttu-id="989d5-127">Alle unterstützten Startparameter sind im Thema "Verwenden der Startoptionen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="989d5-127">All of the supported startup parameters are described in the topic "Using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Service Startup Options," in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="989d5-128">Der Startparameter -T*trace#* gibt an, dass beim Starten einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein angegebenes Ablaufverfolgungsflag (*trace#* ) aktiviert sein muss.</span><span class="sxs-lookup"><span data-stu-id="989d5-128">A startup parameter of -T*trace#* indicates that an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be started with a specified trace flag (*trace#*) in effect.</span></span> <span data-ttu-id="989d5-129">Ablaufverfolgungsflags werden verwendet, um den Server mit nicht standardmäßigem Verhalten zu starten.</span><span class="sxs-lookup"><span data-stu-id="989d5-129">Trace flags are used to start the server with nonstandard behavior.</span></span> <span data-ttu-id="989d5-130">Weitere Informationen zu Ablaufverfolgungsflags finden Sie im Thema „Ablaufverfolgungsflags ([!INCLUDE[tsql](../../includes/tsql-md.md)])“ in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="989d5-130">For more information about trace flags, see the topic "Trace Flags ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="989d5-131">Möglicherweise treffen Sie auf zusätzliche nicht dokumentierte Startparameter und Ablaufverfolgungsflags, die im Internet beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="989d5-131">You might see additional undocumented startup parameters and trace flags described on the Internet.</span></span> <span data-ttu-id="989d5-132">Nicht dokumentierte Startparameter und Ablaufverfolgungsflags werden erstellt, um ungewöhnliche Probleme zu behandeln oder bestimmte für Tests erforderliche Bedingungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="989d5-132">Undocumented startup parameters and trace flags are created to address uncommon problems or to force certain conditions required for testing.</span></span> <span data-ttu-id="989d5-133">Die Verwendung von nicht dokumentierten Startparametern kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="989d5-133">Using undocumented startup parameters can have unexpected results.</span></span> <span data-ttu-id="989d5-134">Verwenden Sie nicht dokumentierte Parameter nur, wenn Sie von Microsoft Support Services dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="989d5-134">Do not use undocumented parameters unless directed by Microsoft Customer Support Services.</span></span>  
  
 <span data-ttu-id="989d5-135">In der folgenden Liste werden einige allgemeine optionale Parameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="989d5-135">The following list describes some common optional parameters.</span></span>  
  
|<span data-ttu-id="989d5-136">Parameter</span><span class="sxs-lookup"><span data-stu-id="989d5-136">Parameter</span></span>|<span data-ttu-id="989d5-137">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="989d5-137">Short description</span></span>|  
|---------------|-----------------------|  
|<span data-ttu-id="989d5-138">-M</span><span class="sxs-lookup"><span data-stu-id="989d5-138">-m</span></span>|<span data-ttu-id="989d5-139">Startet eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im Einzelbenutzermodus.</span><span class="sxs-lookup"><span data-stu-id="989d5-139">Starts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode.</span></span>|  
|<span data-ttu-id="989d5-140">-T1204</span><span class="sxs-lookup"><span data-stu-id="989d5-140">-T1204</span></span>|<span data-ttu-id="989d5-141">Gibt die an einem Deadlock beteiligten Ressourcen und Sperrentypen sowie den aktuell betroffenen Befehl zurück.</span><span class="sxs-lookup"><span data-stu-id="989d5-141">Returns the resources and types of locks participating in a deadlock and also the current command affected.</span></span>|  
|<span data-ttu-id="989d5-142">-T1224</span><span class="sxs-lookup"><span data-stu-id="989d5-142">-T1224</span></span>|<span data-ttu-id="989d5-143">Deaktiviert die Sperrenausweitung basierend auf der Anzahl von Sperren.</span><span class="sxs-lookup"><span data-stu-id="989d5-143">Disables lock escalation based on the number of locks.</span></span>|  
|<span data-ttu-id="989d5-144">-T3608</span><span class="sxs-lookup"><span data-stu-id="989d5-144">-T3608</span></span>|<span data-ttu-id="989d5-145">Verhindert, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatisch gestartet wird und andere Datenbanken als die master-Datenbank wiederhergestellt werden</span><span class="sxs-lookup"><span data-stu-id="989d5-145">Prevents [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from automatically starting and recovering any database except the master database.</span></span>|  
|<span data-ttu-id="989d5-146">-T7806</span><span class="sxs-lookup"><span data-stu-id="989d5-146">-T7806</span></span>|<span data-ttu-id="989d5-147">Aktiviert eine dedizierte Administratorverbindung (Dedicated Administrator Connection, DAC) in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="989d5-147">Enables a dedicated administrator connection (DAC) on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="989d5-148">Einige optionale Parameter können Serververhalten ändern und die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="989d5-148">Some optional parameters can change server behavior and may affect performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="989d5-149">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="989d5-149">Permissions</span></span>  
 <span data-ttu-id="989d5-150">Die Verwendung dieser Seite ist auf Benutzer beschränkt, die die entsprechenden Einträge in der Registrierung ändern können.</span><span class="sxs-lookup"><span data-stu-id="989d5-150">Use of this page is restricted to users who can change the related entries in the registry.</span></span> <span data-ttu-id="989d5-151">Dazu gehören folgende Benutzer.</span><span class="sxs-lookup"><span data-stu-id="989d5-151">This includes the following users.</span></span>  
  
-   <span data-ttu-id="989d5-152">Mitglieder der lokalen Administratorgruppe.</span><span class="sxs-lookup"><span data-stu-id="989d5-152">Members of the local administrators group.</span></span>  
  
-   <span data-ttu-id="989d5-153">Das Domänenkonto, das von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] für die Ausführung unter einem Domänenkonto konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="989d5-153">The domain account that is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to run under a domain account.</span></span>  
  
## <a name="books-online-references"></a><span data-ttu-id="989d5-154">Referenzen in der Onlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="989d5-154">Books Online References</span></span>  
 <span data-ttu-id="989d5-155">Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Startparametern finden Sie in „Vorgehensweise: Konfigurieren von Serverstartoptionen ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager)“ in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="989d5-155">For additional information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup parameters, see "How to: Configure Server Startup Options ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  