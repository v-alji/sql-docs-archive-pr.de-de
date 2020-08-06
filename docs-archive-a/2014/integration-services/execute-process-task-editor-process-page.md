---
title: Editor für den Task ' Prozess ausführen ' (Seite verarbeiten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ce8629be2c07ae4caac4586b266936a908e71499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694662"
---
# <a name="execute-process-task-editor-process-page"></a><span data-ttu-id="1688e-102">Editor für den Task 'Prozess ausführen' (Seite Verarbeiten)</span><span class="sxs-lookup"><span data-stu-id="1688e-102">Execute Process Task Editor (Process Page)</span></span>
  <span data-ttu-id="1688e-103">Auf der Seite **Verarbeiten** des Dialogfelds **Editor für den Task 'Prozess ausführen'** können Sie die Optionen konfigurieren, die den Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="1688e-103">Use the **Process** page of the **Execute Process Task Editor** dialog box to configure the options that execute the process.</span></span> <span data-ttu-id="1688e-104">Zu den Optionen gehören der Name der ausführbaren Datei, der Speicherort dieser Datei, die Argumente der Eingabeaufforderung und die Variablen für die Ein- und Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1688e-104">These options include the executable to run, its location, command prompt arguments, and the variables that provide input and capture output.</span></span>  
  
 <span data-ttu-id="1688e-105">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Execute Process Task](control-flow/execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="1688e-105">To learn about this task, see [Execute Process Task](control-flow/execute-process-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1688e-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1688e-106">Options</span></span>  
 <span data-ttu-id="1688e-107">**RequireFullFileName**</span><span class="sxs-lookup"><span data-stu-id="1688e-107">**RequireFullFileName**</span></span>  
 <span data-ttu-id="1688e-108">Geben Sie an, ob der Task fehlschlagen soll, wenn die ausführbare Datei am angegebenen Speicherort nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="1688e-108">Indicate whether the task should fail if the executable is not found at the specified location.</span></span>  
  
 <span data-ttu-id="1688e-109">**Ausführbare Datei**</span><span class="sxs-lookup"><span data-stu-id="1688e-109">**Executable**</span></span>  
 <span data-ttu-id="1688e-110">Geben Sie den Namen der ausführbaren Datei ein.</span><span class="sxs-lookup"><span data-stu-id="1688e-110">Type the name of the executable to run.</span></span>  
  
 <span data-ttu-id="1688e-111">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="1688e-111">**Arguments**</span></span>  
 <span data-ttu-id="1688e-112">Geben Sie Argumente für die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="1688e-112">Provide command prompt arguments.</span></span>  
  
 <span data-ttu-id="1688e-113">**WorkingDirectory**</span><span class="sxs-lookup"><span data-stu-id="1688e-113">**WorkingDirectory**</span></span>  
 <span data-ttu-id="1688e-114">Geben Sie den Pfad zu dem Ordner ein, in dem die ausführbare Datei enthalten ist, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , und suchen Sie den Ordner.</span><span class="sxs-lookup"><span data-stu-id="1688e-114">Type the path of the folder that contains the executable, or click the browse button **(...)** and locate the folder.</span></span>  
  
 <span data-ttu-id="1688e-115">**StandardInputVariable**</span><span class="sxs-lookup"><span data-stu-id="1688e-115">**StandardInputVariable**</span></span>  
 <span data-ttu-id="1688e-116">Wählen Sie eine Variable für die Bereitstellung der Eingabe zum Prozess aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1688e-116">Select a variable to provide the input to the process, or click \<**New variable...**> to create a new variable:</span></span>  
  
 <span data-ttu-id="1688e-117">**Verwandte Themen:**  [Variable hinzufügen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="1688e-117">**Related Topics:**  [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="1688e-118">**StandardOutputVariable**</span><span class="sxs-lookup"><span data-stu-id="1688e-118">**StandardOutputVariable**</span></span>  
 <span data-ttu-id="1688e-119">Wählen Sie eine Variable zum Erfassen der Ausgabe des Prozess aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1688e-119">Select a variable to capture the output of the process, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="1688e-120">**StandardErrorVariable**</span><span class="sxs-lookup"><span data-stu-id="1688e-120">**StandardErrorVariable**</span></span>  
 <span data-ttu-id="1688e-121">Wählen Sie eine Variable zum Erfassen der Fehlerausgabe des Prozessors aus, oder klicken Sie auf \<**New variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1688e-121">Select a variable to capture the error output of the processor, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="1688e-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span><span class="sxs-lookup"><span data-stu-id="1688e-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span></span>  
 <span data-ttu-id="1688e-123">Geben Sie an, ob beim Task ein Fehler auftritt, wenn der Prozessexitcode von dem unter **SuccessValue**angegebenen Wert abweicht.</span><span class="sxs-lookup"><span data-stu-id="1688e-123">Indicate whether the task fails if the process exit code is different from the value specified in **SuccessValue**.</span></span>  
  
 <span data-ttu-id="1688e-124">**SuccessValue**</span><span class="sxs-lookup"><span data-stu-id="1688e-124">**SuccessValue**</span></span>  
 <span data-ttu-id="1688e-125">Geben Sie den Wert an, der von der ausführbaren Datei zurückgegeben wird, um einen Erfolg zu melden.</span><span class="sxs-lookup"><span data-stu-id="1688e-125">Specify the value returned by the executable to indicate success.</span></span> <span data-ttu-id="1688e-126">Standardmäßig ist dieser Wert auf **0**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1688e-126">By default this value is set to **0**.</span></span>  
  
 <span data-ttu-id="1688e-127">**TimeOut**</span><span class="sxs-lookup"><span data-stu-id="1688e-127">**TimeOut**</span></span>  
 <span data-ttu-id="1688e-128">Geben Sie die Anzahl von Sekunden an, die der Prozess ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1688e-128">Specify the number of seconds that the process can run.</span></span> <span data-ttu-id="1688e-129">Durch den Wert **0** wird angezeigt, dass kein Timeoutwert verwendet wird und der Prozess so lange ausgeführt wird, bis er entweder abgeschlossen ist oder ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="1688e-129">A value of **0** indicates that no time-out value is used, and the process runs until it is completed or until an error occurs.</span></span>  
  
 <span data-ttu-id="1688e-130">**TerminateProcessAfterTimeOut**</span><span class="sxs-lookup"><span data-stu-id="1688e-130">**TerminateProcessAfterTimeOut**</span></span>  
 <span data-ttu-id="1688e-131">Geben Sie an, ob das Ende des Prozesses nach Ablauf des durch die Option **TimeOut** angegebenen Timeoutzeitraumes erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="1688e-131">Indicate whether the process is forced to end after the time-out period specified by the **TimeOut** option.</span></span> <span data-ttu-id="1688e-132">Diese Option ist nur verfügbar, wenn der Wert unter **TimeOut** nicht **0**ist.</span><span class="sxs-lookup"><span data-stu-id="1688e-132">This option is available only if **TimeOut** is not **0**.</span></span>  
  
 <span data-ttu-id="1688e-133">**WindowStyle**</span><span class="sxs-lookup"><span data-stu-id="1688e-133">**WindowStyle**</span></span>  
 <span data-ttu-id="1688e-134">Geben Sie die Fensteranordnung an, in der der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1688e-134">Specify the window style in which to run the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1688e-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1688e-135">See Also</span></span>  
 <span data-ttu-id="1688e-136">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1688e-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="1688e-137">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1688e-137">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
