---
title: Ändern der für Englisch (USA) und Englisch (Vereinigtes Königreich) verwendeten Wörtertrennung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 6b5d2177-db98-47f5-b32e-4b80a2f74ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3b759b90ec834dcb666f7862bfba3857f2fea0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618619"
---
# <a name="change-the-word-breaker-used-for-us-english-and-uk-english"></a><span data-ttu-id="c076c-102">Ändern der für Englisch (USA) und Englisch (Großbritannien) verwendeten Wörtertrennung</span><span class="sxs-lookup"><span data-stu-id="c076c-102">Change the Word Breaker Used for US English and UK English</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="c076c-103">installiert eine neue Version (Version 14.0.4999.1038) der Wörtertrennung und der Wortstammerkennung für Englisch, die die frühere Version dieser Komponenten (Version 12.0.6828.0) ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c076c-103">installs a new version (version 14.0.4999.1038) of the word breaker and stemmer for the English language, replacing the previous version of these components (version 12.0.6828.0).</span></span> <span data-ttu-id="c076c-104">Informationen zum geänderten Verhalten der neuen Komponenten finden Sie unter [Verhaltensänderungen der Volltextsuche](full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="c076c-104">For information about the changed behavior of the new components, see [Behavior Changes to Full-Text Search](full-text-search.md).</span></span> <span data-ttu-id="c076c-105">In diesem Thema wird beschrieben, wie von der neuen Version dieser Komponenten zur früheren Version gewechselt bzw. von der früheren Version zu der neuen Version zurückgewechselt wird.</span><span class="sxs-lookup"><span data-stu-id="c076c-105">This topic describes how to switch from the new version of these components to the previous version, or to switch back from the previous version to the new version.</span></span> <span data-ttu-id="c076c-106">Bei Clusterinstallationen sollten diese Änderungen auf allen primären und passiven Knoten vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c076c-106">For cluster installations, these changes should be made on all the primary and passive nodes.</span></span>  
  
 <span data-ttu-id="c076c-107">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wurden andere Wörtertrennungen verwendet, die durch andere CLSIDs für Englisch (USA) (LCID 1033) und Englisch (Großbritannien) (LCID 2057) dargestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c076c-107">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] used different word breakers represented by different CLSIDs for US English (LCID 1033) and UK English (LCID 2057).</span></span> <span data-ttu-id="c076c-108">In dieser Version verwenden beide LCIDs die gleichen Komponenten mit den gleichen CLSIDs, wie in der folgenden Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c076c-108">In this release, both LCIDs use the same components with the same CLSIDs, as shown in the following table:</span></span>  
  
|<span data-ttu-id="c076c-109">LCID</span><span class="sxs-lookup"><span data-stu-id="c076c-109">LCID</span></span>|<span data-ttu-id="c076c-110">Von früheren Versionen installierte Wörtertrennung</span><span class="sxs-lookup"><span data-stu-id="c076c-110">Word breaker installed by previous versions</span></span><br /><br /> <span data-ttu-id="c076c-111">Version 12.0.6828.0</span><span class="sxs-lookup"><span data-stu-id="c076c-111">version 12.0.6828.0</span></span>|<span data-ttu-id="c076c-112">Von früheren Versionen installierte Wortstammerkennung</span><span class="sxs-lookup"><span data-stu-id="c076c-112">Stemmer installed by previous versions</span></span>|<span data-ttu-id="c076c-113">Von dieser Version installierte Wörtertrennung</span><span class="sxs-lookup"><span data-stu-id="c076c-113">Word breaker installed by this version</span></span><br /><br /> <span data-ttu-id="c076c-114">Version 14.0.4999.1038</span><span class="sxs-lookup"><span data-stu-id="c076c-114">version 14.0.4999.1038</span></span>|<span data-ttu-id="c076c-115">Von dieser Version installierte Wortstammerkennung</span><span class="sxs-lookup"><span data-stu-id="c076c-115">Stemmer installed by this version</span></span>|  
|----------|-------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------|---------------------------------------|  
|<span data-ttu-id="c076c-116">1033</span><span class="sxs-lookup"><span data-stu-id="c076c-116">1033</span></span><br /><span data-ttu-id="c076c-117">(Englisch (USA))</span><span class="sxs-lookup"><span data-stu-id="c076c-117">(US English)</span></span>|<span data-ttu-id="c076c-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span><span class="sxs-lookup"><span data-stu-id="c076c-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span></span>|<span data-ttu-id="c076c-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="c076c-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="c076c-120">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="c076c-120">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="c076c-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="c076c-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
|<span data-ttu-id="c076c-122">2057</span><span class="sxs-lookup"><span data-stu-id="c076c-122">2057</span></span><br /><span data-ttu-id="c076c-123">(Englisch (Großbritannien))</span><span class="sxs-lookup"><span data-stu-id="c076c-123">(UK English)</span></span>|<span data-ttu-id="c076c-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span><span class="sxs-lookup"><span data-stu-id="c076c-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span></span>|<span data-ttu-id="c076c-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="c076c-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="c076c-126">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="c076c-126">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="c076c-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="c076c-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
  
 <span data-ttu-id="c076c-128">Bei den in diesem Thema beschriebenen Komponenten handelt es sich um DLL-Dateien, die im `MSSQL\Binn` -Ordner für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz installiert sind.</span><span class="sxs-lookup"><span data-stu-id="c076c-128">The components described in this topic are DLL files that are installed in the `MSSQL\Binn` folder for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="c076c-129">Der vollständige Pfad ist in der Regel `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span><span class="sxs-lookup"><span data-stu-id="c076c-129">The full path is typically `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span></span>  
  
 <span data-ttu-id="c076c-130">Weitere Informationen zur Wörtertrennung und Wortstammerkennung finden Sie unter [Konfigurieren und Verwalten von Wörtertrennungen und Wortstammerkennungen für die Suche](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="c076c-130">For more information about word breakers and stemmers, see [Configure and Manage Word Breakers and Stemmers for Search](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="switching-from-the-current-english-word-breaker-to-the-previous-english-word-breakers"></a><span data-ttu-id="c076c-131">Wechseln von der aktuellen englischen Wörtertrennung zu den vorherigen englischen Wörtertrennungen</span><span class="sxs-lookup"><span data-stu-id="c076c-131">Switching from the current English word breaker to the previous English word breakers</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-us-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="c076c-132">So wechseln Sie von der aktuellen Version der Wörtertrennung für Englisch (USA) zur früheren Version</span><span class="sxs-lookup"><span data-stu-id="c076c-132">To switch from the current version of the US English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="c076c-133">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="c076c-133">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="c076c-134">Fügen Sie mithilfe der folgenden Schritte für die COM ClassIDs für die Schnittstellen der früheren Wörtertrennung für Englisch (USA) und die Wortstammerkennung für LCID 1033 neue Schlüssel hinzu:</span><span class="sxs-lookup"><span data-stu-id="c076c-134">Use the following steps to add new keyS for the COM ClassIDs for the previous US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="c076c-135">Fügen Sie einen neuen Schlüssel mit dem Wert **{188D6CC5-CB03-4C01-912E-47D21295D77E}** für die frühere Wörtertrennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-135">Add a new key with the value **{188D6CC5-CB03-4C01-912E-47D21295D77E}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="c076c-136">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts zu **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-136">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="c076c-137">Fügen Sie einen neuen Schlüssel mit dem Wert **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** für die frühere Wortstammerkennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-137">Add a new key with the value **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="c076c-138">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts zu **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-138">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="c076c-139">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\Language\enu**.</span><span class="sxs-lookup"><span data-stu-id="c076c-139">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span></span>  
  
4.  <span data-ttu-id="c076c-140">Aktualisieren Sie den **WBreakerClass**-Schlüsselwert zu **{188D6CC5-CB03-4C01-912E-47D21295D77E}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-140">Update the **WBreakerClass** key value to **{188D6CC5-CB03-4C01-912E-47D21295D77E}**.</span></span>  
  
5.  <span data-ttu-id="c076c-141">Aktualisieren Sie den **StemmerClass** -Schlüsselwert zu **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-141">Update the **StemmerClass** key value to **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="c076c-142">Starten Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="c076c-142">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-uk-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="c076c-143">So wechseln Sie von der aktuellen Version der Wörtertrennung für Englisch (Vereinigtes Königreich) zur früheren Version</span><span class="sxs-lookup"><span data-stu-id="c076c-143">To switch from the current version of the UK English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="c076c-144">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="c076c-144">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="c076c-145">Fügen Sie mithilfe der folgenden Schritte für die COM ClassIDs für die früheren Schnittstellen der Wörtertrennung für Englisch (Vereinigtes Königreich) und Wortstammerkennung für LCID 2057 einen neuen Schlüssel hinzu:</span><span class="sxs-lookup"><span data-stu-id="c076c-145">Use the following steps to add a new key for the COM ClassIDs for the previous UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="c076c-146">Fügen Sie einen neuen Schlüssel mit dem Wert **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** für die frühere Wörtertrennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-146">Add a new key with the value **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="c076c-147">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts zu **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-147">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="c076c-148">Fügen Sie einen neuen Schlüssel mit dem Wert **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** für die frühere Wortstammerkennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-148">Add a new key with the value **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="c076c-149">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts zu **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-149">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="c076c-150">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="c076c-150">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="c076c-151">Aktualisieren Sie den **WBreakerClass**-Schlüsselwert zu **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-151">Update the **WBreakerClass** key value to **{173C97E2-AEBE-437C-9445-01B237ABF2F6}**.</span></span>  
  
5.  <span data-ttu-id="c076c-152">Aktualisieren Sie den **StemmerClass** -Schlüsselwert zu **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-152">Update the **StemmerClass** key value to **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="c076c-153">Starten Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="c076c-153">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="switching-back-from-the-previous-english-word-breakers-to-the-current-english-word-breaker"></a><span data-ttu-id="c076c-154">Zurückwechseln von der aktuellen englischen Wörtertrennung zu der früheren englischen Wörtertrennung</span><span class="sxs-lookup"><span data-stu-id="c076c-154">Switching back from the previous English word breakers to the current English word breaker</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-us-english-word-breaker-to-the-current-version"></a><span data-ttu-id="c076c-155">So wechseln Sie von der früheren Version der Wörtertrennung für Englisch (USA) zu der aktuellen Version zurück</span><span class="sxs-lookup"><span data-stu-id="c076c-155">To switch back from the previous version of the US English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="c076c-156">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="c076c-156">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="c076c-157">Wenn die folgenden Schlüssel nicht vorhanden sind, gehen Sie folgendermaßen vor, um einen neuen Schlüssel für die COM ClassIDs für die Schnittstellen der aktuellen Wörtertrennung für Englisch (USA) und die Wortstammerkennung für LCID 1033 hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="c076c-157">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="c076c-158">Fügen Sie einen neuen Schlüssel mit dem Wert **{9faed859-0b30-4434-ae65-412e14a16fb8}** für die aktuelle Wörtertrennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-158">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="c076c-159">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts in **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-159">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="c076c-160">Fügen Sie einen neuen Schlüssel mit dem Wert **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** für die aktuelle Wortstammerkennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-160">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="c076c-161">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts in **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-161">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="c076c-162">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="c076c-162">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="c076c-163">Aktualisieren Sie den **WBreakerClass**-Schlüsselwert in **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-163">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="c076c-164">Aktualisieren Sie den **StemmerClass** -Schlüsselwert in **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-164">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="c076c-165">Starten Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="c076c-165">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-uk-english-word-breaker-to-the-current-version"></a><span data-ttu-id="c076c-166">So wechseln Sie von der früheren Version der Wörtertrennung für Englisch (Vereinigtes Königreich) zu der aktuellen Version zurück</span><span class="sxs-lookup"><span data-stu-id="c076c-166">To switch back from the previous version of the UK English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="c076c-167">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="c076c-167">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="c076c-168">Wenn die folgenden Schlüssel nicht vorhanden sind, gehen Sie folgendermaßen vor, um einen neuen Schlüssel für die COM ClassIDs für die Schnittstellen der aktuellen Wörtertrennung für Englisch (Vereinigtes Königreich) und die Wortstammerkennung für LCID 2057 hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="c076c-168">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="c076c-169">Fügen Sie einen neuen Schlüssel mit dem Wert **{9faed859-0b30-4434-ae65-412e14a16fb8}** für die aktuelle Wörtertrennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-169">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="c076c-170">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts in **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-170">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="c076c-171">Fügen Sie einen neuen Schlüssel mit dem Wert **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** für die aktuelle Wortstammerkennung hinzu.</span><span class="sxs-lookup"><span data-stu-id="c076c-171">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="c076c-172">Aktualisieren Sie die (standardmäßigen) Daten dieses Schlüsselwerts in **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="c076c-172">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="c076c-173">Navigieren Sie in der Registrierung zu folgendem Knoten: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzstamm\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="c076c-173">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="c076c-174">Aktualisieren Sie den **WBreakerClass**-Schlüsselwert in **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-174">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="c076c-175">Aktualisieren Sie den **StemmerClass** -Schlüsselwert in **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="c076c-175">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="c076c-176">Starten Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="c076c-176">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c076c-177">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c076c-177">See Also</span></span>  
 <span data-ttu-id="c076c-178">[Wiederherstellen der von der Suche verwendeten Wörtertrennungen auf die vorherige Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span><span class="sxs-lookup"><span data-stu-id="c076c-178">[Revert the Word Breakers Used by Search to the Previous Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span></span>  
 [<span data-ttu-id="c076c-179">Verhaltensänderungen der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="c076c-179">Behavior Changes to Full-Text Search</span></span>](full-text-search.md)  
  
  
