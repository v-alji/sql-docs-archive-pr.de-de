---
title: Editor für den Task ' Webdienst ' (Seite Ausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621563"
---
# <a name="web-service-task-editor-output-page"></a><span data-ttu-id="20aa1-102">Editor für den Task 'Webdienst' (Seite Ausgabe)</span><span class="sxs-lookup"><span data-stu-id="20aa1-102">Web Service Task Editor (Output Page)</span></span>
  <span data-ttu-id="20aa1-103">Verwenden Sie die Seite **Ausgabe** des Dialogfelds **Editor für den Task 'Webdienst'** , um anzugeben, wo das durch die Webmethode zurückgegebene Ergebnis gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20aa1-103">Use the **Output** page of the **Web Service Task Editor** dialog box to specify where to store the result returned by the Web method.</span></span>  
  
 <span data-ttu-id="20aa1-104">Weitere Informationen zu diesem Task finden Sie unter [Webdienst (Task)](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="20aa1-104">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="20aa1-105">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="20aa1-105">Static Options</span></span>  
 <span data-ttu-id="20aa1-106">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="20aa1-106">**OutputType**</span></span>  
 <span data-ttu-id="20aa1-107">Wählt den Speichertyp, der beim Speichern der Ergebnisse verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="20aa1-107">Select the storage type to use when storing the results.</span></span> <span data-ttu-id="20aa1-108">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="20aa1-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="20aa1-109">Wert</span><span class="sxs-lookup"><span data-stu-id="20aa1-109">Value</span></span>|<span data-ttu-id="20aa1-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20aa1-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="20aa1-111">**File Connection**</span><span class="sxs-lookup"><span data-stu-id="20aa1-111">**File Connection**</span></span>|<span data-ttu-id="20aa1-112">Speichert die Ergebnisse in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="20aa1-112">Store the results in a file.</span></span> <span data-ttu-id="20aa1-113">Wenn Sie diesen Wert auswählen, wird die dynamische Option **Datei**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20aa1-113">Selecting this value displays the dynamic option, **File**.</span></span>|  
|<span data-ttu-id="20aa1-114">**Variable**</span><span class="sxs-lookup"><span data-stu-id="20aa1-114">**Variable**</span></span>|<span data-ttu-id="20aa1-115">Speichert die Ergebnisse in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="20aa1-115">Store the results in a variable.</span></span> <span data-ttu-id="20aa1-116">Wenn Sie diesen Wert auswählen, wird die dynamische Option **Variable**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20aa1-116">Selecting this value displays the dynamic option, **Variable**.</span></span>|  
  
## <a name="outputtype-dynamic-options"></a><span data-ttu-id="20aa1-117">OutputType (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="20aa1-117">OutputType Dynamic Options</span></span>  
  
### <a name="outputtype--file-connection"></a><span data-ttu-id="20aa1-118">OutputType = File Connection</span><span class="sxs-lookup"><span data-stu-id="20aa1-118">OutputType = File Connection</span></span>  
 <span data-ttu-id="20aa1-119">**File**</span><span class="sxs-lookup"><span data-stu-id="20aa1-119">**File**</span></span>  
 <span data-ttu-id="20aa1-120">Wählen Sie einen Dateiverbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New Connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20aa1-120">Select a File connection manager in the list or click \<**New Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="20aa1-121">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="20aa1-121">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="outputtype--variable"></a><span data-ttu-id="20aa1-122">OutputType = Variable</span><span class="sxs-lookup"><span data-stu-id="20aa1-122">OutputType = Variable</span></span>  
 <span data-ttu-id="20aa1-123">**Variable**</span><span class="sxs-lookup"><span data-stu-id="20aa1-123">**Variable**</span></span>  
 <span data-ttu-id="20aa1-124">Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New Variable...**>, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20aa1-124">Select a variable in the list or click \<**New Variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="20aa1-125">**Verwandte Themen:**  [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md), [Hinzufügen von Variablen](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="20aa1-125">**Related Topics:**  [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20aa1-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20aa1-126">See Also</span></span>  
 <span data-ttu-id="20aa1-127">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="20aa1-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="20aa1-128">[Editor für den Task ' Webdienst ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="20aa1-128">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="20aa1-129">[Editor für den Task ' Webdienst ' &#40;Eingabe Seite&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="20aa1-129">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 [<span data-ttu-id="20aa1-130">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="20aa1-130">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
