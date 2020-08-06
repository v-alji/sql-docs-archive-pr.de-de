---
title: Skripttask-Beispiele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], examples
- examples [Integration Services]
- SSIS Script task, examples
ms.assetid: b0dd77ee-ee11-4cd9-87aa-61dd67f2fe1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 920d2ee5cc2e64db1048d10522d9be644794e55b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701289"
---
# <a name="script-task-examples"></a><span data-ttu-id="1c8e7-102">Skripttask-Beispiele</span><span class="sxs-lookup"><span data-stu-id="1c8e7-102">Script Task Examples</span></span>
  <span data-ttu-id="1c8e7-103">Bei Skripttask handelt es sich um ein Mehrzwecktool, das Sie in einem Paket verwenden können, um nahezu alle Anforderungen zu erfüllen, die von den Tasks nicht erfüllt werden, die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-103">The Script task is a multi-purpose tool that you can use in a package to fill almost any requirement that is not met by the tasks included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="1c8e7-104">In diesem Thema werden Skripttaskcodebeispiele aufgeführt, in denen einige der verfügbaren Funktionen veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-104">This topic lists Script task code samples that demonstrate some of the available functionality.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c8e7-105">Wenn Sie Tasks erstellen möchten, die Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesen Skripttaskbeispielen als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-105">If you want to create tasks that you can more easily reuse across multiple packages, consider using the code in these Script task samples as the starting point for custom tasks.</span></span> <span data-ttu-id="1c8e7-106">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="1c8e7-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c8e7-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1c8e7-107">In This Section</span></span>  
  
### <a name="example-topics"></a><span data-ttu-id="1c8e7-108">Beispielthemen</span><span class="sxs-lookup"><span data-stu-id="1c8e7-108">Example Topics</span></span>  
 <span data-ttu-id="1c8e7-109">Dieser Abschnitt enthält Codebeispiele, die verschiedene Einsatzbereiche der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klassen veranschaulichen, die Sie in einen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Skripttask integrieren können:</span><span class="sxs-lookup"><span data-stu-id="1c8e7-109">This section contains code examples that demonstrate various uses of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that you can incorporate into an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task:</span></span>  
  
 [<span data-ttu-id="1c8e7-110">Erkennen einer leeren flachen Datei mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-110">Detecting an Empty Flat File with the Script Task</span></span>](../extending-packages-scripting-task-examples/detecting-an-empty-flat-file-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-111">Überprüft eine Flatfile auf vorhandene Datenzeilen, und speichert das Ergebnis in einer Variablen zur Verzweigung der Ablaufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-111">Checks a flat file to determine whether it contains rows of data, and saves the result to a variable for use in control flow branching.</span></span>  
  
 [<span data-ttu-id="1c8e7-112">Erfassen einer Liste für die ForEach-Schleife mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-112">Gathering a List for the ForEach Loop with the Script Task</span></span>](../extending-packages-scripting-task-examples/gathering-a-list-for-the-foreach-loop-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-113">Erstellt eine Liste mit Dateien, die benutzerspezifische Kriterien erfüllen, und füllt eine Variable für den späteren Gebrauch durch den Foreach from-Variablenenumerator.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-113">Gathers a list of files that meet user-specified criteria, and populates a variable for later use by the Foreach from Variable Enumerator.</span></span>  
  
 [<span data-ttu-id="1c8e7-114">Abfragen des Active Directory mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-114">Querying the Active Directory with the Script Task</span></span>](../extending-packages-scripting-task-examples/querying-the-active-directory-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-115">Ruft Benutzerinformationen von Active Directory basierend auf dem Wert einer [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Variable ab, indem im System.DirectoryServices-Namespace Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-115">Retrieves user information from Active Directory based on the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, by using classes in the System.DirectoryServices namespace.</span></span>  
  
 [<span data-ttu-id="1c8e7-116">Überwachen von Leistungsindikatoren mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-116">Monitoring Performance Counters with the Script Task</span></span>](../extending-packages-scripting-task-examples/monitoring-performance-counters-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-117">Erstellt einen benutzerdefinierten Leistungsindikator, mit dem der Ausführungsfortschritt eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakets überprüft werden kann, indem im System.Diagnostics-Namespace Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-117">Creates a custom performance counter that can be used to track the execution progress of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, by using classes in the System.Diagnostics namespace.</span></span>  
  
 [<span data-ttu-id="1c8e7-118">Arbeiten mit Bildern mithilfe des Skripttasks</span><span class="sxs-lookup"><span data-stu-id="1c8e7-118">Working with Images with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-119">Komprimiert Bilder in das JPEG-Format und erstellt aus ihnen Miniaturbilder, indem im System.Drawing-Namespace Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-119">Compresses images into the JPEG format and creates thumbnail images from them, by using classes in the System.Drawing namespace.</span></span>  
  
 [<span data-ttu-id="1c8e7-120">Suchen installierter Drucker mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-120">Finding Installed Printers with the Script Task</span></span>](../extending-packages-scripting-task-examples/finding-installed-printers-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-121">Sucht installierte Drucker, die ein bestimmtes Papierformat unterstützen, indem im System.Drawing.Printing-Namespace Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-121">Locates installed printers that support a specific paper size, by using classes in the System.Drawing.Printing namespace.</span></span>  
  
 [<span data-ttu-id="1c8e7-122">Senden einer HTML-E-Mail mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-122">Sending an HTML Mail Message with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-an-html-mail-message-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-123">Sendet eine Mail-Nachricht im HTML-Format anstatt im Nur-Text-Format.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-123">Sends a mail message in HTML format instead of plain text format.</span></span>  
  
 [<span data-ttu-id="1c8e7-124">Arbeiten mit Excel-Dateien mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-124">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-125">Listet die Arbeitsblätter in einer Excel-Datei auf und überprüft das Vorhandensein eines bestimmten Arbeitsblatts.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-125">Lists the worksheets in an Excel file and checks for the existence of a specific worksheet.</span></span>  
  
 [<span data-ttu-id="1c8e7-126">Senden mit dem Skripttask an eine private Remotemeldungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="1c8e7-126">Sending to a Remote Private Message Queue with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-to-a-remote-private-message-queue-with-the-script-task.md)  
 <span data-ttu-id="1c8e7-127">Sendet eine Meldung an eine private Remotenachrichten-Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-127">Sends a message to a remote private message queue.</span></span>  
  
### <a name="other-examples"></a><span data-ttu-id="1c8e7-128">Weitere Beispiele</span><span class="sxs-lookup"><span data-stu-id="1c8e7-128">Other Examples</span></span>  
 <span data-ttu-id="1c8e7-129">Die folgenden Themen enthalten ebenfalls Codebeispiele, die mit dem Skripttask verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="1c8e7-129">The following topics also contain code examples for use with the Script task:</span></span>  
  
 [<span data-ttu-id="1c8e7-130">Verwenden von Variablen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-130">Using Variables in the Script Task</span></span>](../extending-packages-scripting/task/using-variables-in-the-script-task.md)  
 <span data-ttu-id="1c8e7-131">Fordert vom Benutzer eine Bestätigung an, ob das Paket weiterhin ausgeführt werden soll, basierend auf dem Wert einer Paketvariablen, der die in einer anderen Variablen festgelegte Begrenzung überschreiten kann.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-131">Asks the user for confirmation of whether the package should continue to run, based on the value of a package variable that may exceed the limit specified in another variable.</span></span>  
  
 [<span data-ttu-id="1c8e7-132">Herstellen einer Verbindung zu Datenquellen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-132">Connecting to Data Sources in the Script Task</span></span>](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md)  
 <span data-ttu-id="1c8e7-133">Ruft eine Verbindung oder Verbindungsinformationen von Verbindungs-Managern ab, die im Paket definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-133">Retrieves a connection or connection information from connection managers defined in the package.</span></span>  
  
 [<span data-ttu-id="1c8e7-134">Auslösen von Ereignissen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-134">Raising Events in the Script Task</span></span>](../extending-packages-scripting/task/raising-events-in-the-script-task.md)  
 <span data-ttu-id="1c8e7-135">Gibt einen Fehler, eine Warnung oder eine Meldung basierend auf dem Status der Internetverbindung auf dem Server aus.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-135">Raises an error, a warning, or an informational message based on the status of the Internet connection on the server.</span></span>  
  
 [<span data-ttu-id="1c8e7-136">Protokollieren im Skripttask</span><span class="sxs-lookup"><span data-stu-id="1c8e7-136">Logging in the Script Task</span></span>](../extending-packages-scripting/task/logging-in-the-script-task.md)  
 <span data-ttu-id="1c8e7-137">Protokolliert die Anzahl der Elemente, die vom Task zu aktivierten Protokollanbietern verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-137">Logs the number of items processed by the task to enabled log providers.</span></span>  
  
<span data-ttu-id="1c8e7-138">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="1c8e7-138">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1c8e7-139">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="1c8e7-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1c8e7-140">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="1c8e7-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1c8e7-141">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c8e7-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
