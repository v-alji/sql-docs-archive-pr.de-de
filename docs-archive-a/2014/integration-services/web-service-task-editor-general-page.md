---
title: Editor für den Task ' Webdienst ' (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621568"
---
# <a name="web-service-task-editor-general-page"></a><span data-ttu-id="59a12-102">Editor für den Task 'Webdienst' (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="59a12-102">Web Service Task Editor (General Page)</span></span>
  <span data-ttu-id="59a12-103">Auf der Seite **Allgemein** des Dialogfelds **Editor für den Task 'Webdienst'** können Sie einen HTTP-Verbindungs-Manager und den Speicherort der WSDL-Datei (Web Services Description Language) angeben, die der Task „Webdienst“ verwendet, den Task „Webdienst“ beschreiben und die WSDL-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="59a12-103">Use the **General** page of the **Web Services Task Editor** dialog box to specify an HTTP connection manager, specify the location of the Web Services Description Language (WSDL) file the Web Service task uses, describe the Web Services task, and download the WSDL file.</span></span>  
  
 <span data-ttu-id="59a12-104">Weitere Informationen zu diesem Task finden Sie unter [Webdienst (Task)](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="59a12-104">For more information about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="59a12-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="59a12-105">Options</span></span>  
 <span data-ttu-id="59a12-106">**HTTPConnection**</span><span class="sxs-lookup"><span data-stu-id="59a12-106">**HTTPConnection**</span></span>  
 <span data-ttu-id="59a12-107">Wählen Sie einen Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="59a12-107">Select a connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="59a12-108">Der HTTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="59a12-108">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="59a12-109">Er unterstützt keine Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="59a12-109">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="59a12-110">**Verwandte Themen:**  [HTTP-Verbindungs-Manager](connection-manager/http-connection-manager.md), [HTTP-Verbindungs-Manager-Editor &#40;Seite „Server“&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span><span class="sxs-lookup"><span data-stu-id="59a12-110">**Related Topics:**  [HTTP Connection Manager](connection-manager/http-connection-manager.md), [HTTP Connection Manager Editor &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span></span>  
  
 <span data-ttu-id="59a12-111">**WSDLFile**</span><span class="sxs-lookup"><span data-stu-id="59a12-111">**WSDLFile**</span></span>  
 <span data-ttu-id="59a12-112">Geben Sie den vollqualifizierten Pfad der auf dem Computer lokalen WSDL-Datei an, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(…)** , um nach dieser Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="59a12-112">Type the fully qualified path of a WSDL file that is local to the computer, or click the browse button **(...)** and locate this file.</span></span>  
  
 <span data-ttu-id="59a12-113">Wenn Sie die WSDL-Datei bereits manuell auf den Computer heruntergeladen haben, wählen Sie diese Datei aus.</span><span class="sxs-lookup"><span data-stu-id="59a12-113">If you have already manually downloaded the WSDL file to the computer, select this file.</span></span> <span data-ttu-id="59a12-114">Wenn die WSDL-Datei jedoch noch nicht heruntergeladen wurde, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="59a12-114">However, if the WSDL file has not yet been downloaded, follow these steps:</span></span>  
  
-   <span data-ttu-id="59a12-115">Erstellen Sie eine leere Datei mit der Dateinamenerweiterung WSDL.</span><span class="sxs-lookup"><span data-stu-id="59a12-115">Create an empty file that has the ".wsdl" file name extension.</span></span>  
  
-   <span data-ttu-id="59a12-116">Wählen Sie diese leere Datei für die Option **WSDLFile** aus.</span><span class="sxs-lookup"><span data-stu-id="59a12-116">Select this empty file for the **WSDLFile** option.</span></span>  
  
-   <span data-ttu-id="59a12-117">Legen Sie den Wert von **overwrite tewsdlfile** auf fest, `True` damit die leere Datei mit der tatsächlichen WSDL-Datei überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="59a12-117">Set the value of **OverwriteWSDLFile** to `True` to enable the empty file to be overwritten with the actual WSDL file.</span></span>  
  
-   <span data-ttu-id="59a12-118">Klicken Sie auf **WSDL herunterladen** , um die tatsächliche WSDL-Datei herunterzuladen und die leere Datei zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="59a12-118">Click **Download WSDL** to download the actual WSDL file and overwrite the empty file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="59a12-119">Die Option **WSDL herunterladen** wird erst aktiviert, wenn Sie den Namen einer vorhandenen lokalen Datei im Feld **WSDLFile** angeben.</span><span class="sxs-lookup"><span data-stu-id="59a12-119">The **Download WSDL** option is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
 <span data-ttu-id="59a12-120">**OverwriteWSDLFile**</span><span class="sxs-lookup"><span data-stu-id="59a12-120">**OverwriteWSDLFile**</span></span>  
 <span data-ttu-id="59a12-121">Geben Sie an, ob die WSDL-Datei für den Task Webdienst überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="59a12-121">Indicate whether the WSDL file for the Web Service task can be overwritten.</span></span>  
  
 <span data-ttu-id="59a12-122">Wenn Sie die WSDL-Datei mithilfe der Schaltfläche **WSDL herunter** laden herunterladen möchten, legen Sie diesen Wert auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="59a12-122">If you intend to download the WSDL file by using the **Download WSDL** button, set this value to `True`.</span></span>  
  
 <span data-ttu-id="59a12-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="59a12-123">**Name**</span></span>  
 <span data-ttu-id="59a12-124">Geben Sie einen eindeutigen Namen für den Task Webdienst an.</span><span class="sxs-lookup"><span data-stu-id="59a12-124">Provide a unique name for the Web Service task.</span></span> <span data-ttu-id="59a12-125">Dieser Name wird im Tasksymbol als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="59a12-125">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59a12-126">Tasknamen müssen innerhalb eines Pakets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="59a12-126">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="59a12-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="59a12-127">**Description**</span></span>  
 <span data-ttu-id="59a12-128">Geben Sie eine Beschreibung des Tasks Webdienst ein.</span><span class="sxs-lookup"><span data-stu-id="59a12-128">Type a description of the Web Service task.</span></span>  
  
 <span data-ttu-id="59a12-129">**WSDL herunterladen**</span><span class="sxs-lookup"><span data-stu-id="59a12-129">**Download WSDL**</span></span>  
 <span data-ttu-id="59a12-130">Lädt die WSDL-Datei herunter.</span><span class="sxs-lookup"><span data-stu-id="59a12-130">Download the WSDL file.</span></span>  
  
 <span data-ttu-id="59a12-131">Diese Schaltfläche wird erst aktiviert, wenn Sie den Namen einer vorhandenen lokalen Datei im Feld **WSDLFile** angeben.</span><span class="sxs-lookup"><span data-stu-id="59a12-131">This button is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a12-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59a12-132">See Also</span></span>  
 <span data-ttu-id="59a12-133">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="59a12-133">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="59a12-134">[Editor für den Task ' Webdienst ' &#40;Eingabe Seite&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="59a12-134">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 <span data-ttu-id="59a12-135">[Editor für den Task ' Webdienst ' &#40;Ausgabe Seite&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="59a12-135">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="59a12-136">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="59a12-136">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
