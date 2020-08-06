---
title: Zurückgeben von Ergebnissen aus dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], status information
- ExecutionValue property
- status information [Integration Services]
- TaskResult property
- SSIS Script task, status information
ms.assetid: ac06805b-c2db-44bd-af5c-5a0debe36dd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bef3e93644377f715b5ad24e0a53df053197a03a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700017"
---
# <a name="returning-results-from-the-script-task"></a><span data-ttu-id="39b13-102">Zurückgeben von Ergebnissen aus dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="39b13-102">Returning Results from the Script Task</span></span>
  <span data-ttu-id="39b13-103">Der Skripttask verwendet die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>- und die optionale <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>-Eigenschaft, um Statusinformationen an die [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Laufzeit zurückzugeben, die zur Bestimmung des Pfads des Workflows nach Abschluss des Skripttasks verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="39b13-103">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> and the optional <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> properties to return status information to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime that can be used to determine the path of the workflow after the Script task has finished.</span></span>  
  
## <a name="taskresult"></a><span data-ttu-id="39b13-104">TaskResult</span><span class="sxs-lookup"><span data-stu-id="39b13-104">TaskResult</span></span>  
 <span data-ttu-id="39b13-105">Die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>-Eigenschaft berichtet, ob der Task erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="39b13-105">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> property reports whether the task succeeded or failed.</span></span> <span data-ttu-id="39b13-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39b13-106">For example:</span></span>  
  
 `Dts.TaskResult = ScriptResults.Success`  
  
## <a name="executionvalue"></a><span data-ttu-id="39b13-107">ExecutionValue</span><span class="sxs-lookup"><span data-stu-id="39b13-107">ExecutionValue</span></span>  
 <span data-ttu-id="39b13-108">Die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>-Eigenschaft gibt optional ein benutzerdefiniertes Objekt zurück, das das erfolgreiche Ausführen oder Fehlschlagen des Skripttasks misst oder weitere Informationen darüber liefert.</span><span class="sxs-lookup"><span data-stu-id="39b13-108">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property optionally returns a user-defined object that quantifies or provides more information about the success or failure of the Script task.</span></span> <span data-ttu-id="39b13-109">Der FTP-Task verwendet beispielsweise die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>-Eigenschaft, um die Anzahl von übertragenen Dateien zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="39b13-109">For example, the FTP task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property to return the number of files transferred.</span></span> <span data-ttu-id="39b13-110">Der Task „SQL ausführen“ gibt die Anzahl von Zeilen zurück, auf die sich der Task ausgewirkt hat.</span><span class="sxs-lookup"><span data-stu-id="39b13-110">The Execute SQL task returns the number of rows affected by the task.</span></span> <span data-ttu-id="39b13-111">Der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> kann auch verwendet werden, um den Pfad des Workflows zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="39b13-111">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> can also be used to determine the path of the workflow.</span></span> <span data-ttu-id="39b13-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39b13-112">For example:</span></span>  
  
 `Dim rowsAffected as Integer`  
  
 `...`  
  
 `rowsAffected = 1000`  
  
 `Dts.ExecutionValue = rowsAffected`  
  
<span data-ttu-id="39b13-113">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="39b13-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="39b13-114">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="39b13-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="39b13-115">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="39b13-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="39b13-116">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="39b13-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
