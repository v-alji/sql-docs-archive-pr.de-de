---
title: Editor für den Task Fehlermeldungen übertragen (Seite Meldungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0d626f01e05a30777810b26880da5aedc3e7ad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630712"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a><span data-ttu-id="d88b4-102">Editor für den Task Fehlermeldungen übertragen (Seite Meldungen)</span><span class="sxs-lookup"><span data-stu-id="d88b4-102">Transfer Error Messages Task Editor (Messages Page)</span></span>
  <span data-ttu-id="d88b4-103">Verwenden Sie die Seite **Meldungen** im Dialogfeld **Editor für den Task „Fehlermeldungen übertragen“** , um die Eigenschaften für das Kopieren von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Fehlermeldungen von einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in eine andere anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d88b4-103">Use the **Messages** page of the **Transfer Error Messages Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user-defined error messages from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="d88b4-104">Weitere Informationen zu diesem Task finden Sie unter [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span><span class="sxs-lookup"><span data-stu-id="d88b4-104">For more information about this task, see [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d88b4-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d88b4-105">Options</span></span>  
 <span data-ttu-id="d88b4-106">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="d88b4-106">**SourceConnection**</span></span>  
 <span data-ttu-id="d88b4-107">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Quellserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d88b4-107">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="d88b4-108">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="d88b4-108">**DestinationConnection**</span></span>  
 <span data-ttu-id="d88b4-109">Wählen Sie in der Liste einen SMO-Verbindungs-Manager aus, oder klicken Sie auf **\<New connection...>** , um eine neue Verbindung mit dem Zielserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d88b4-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="d88b4-110">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="d88b4-110">**IfObjectExists**</span></span>  
 <span data-ttu-id="d88b4-111">Wählen Sie aus, ob der Task vorhandene benutzerdefinierte Fehlermeldungen überschreiben, vorhandene Meldungen auslassen oder einen Fehler erzeugen soll, wenn auf dem Zielserver bereits Meldungen desselben Namens vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d88b4-111">Select whether the task should overwrite existing user-defined error messages, skip existing messages, or fail if error messages of the same name already exist on the destination server.</span></span>  
  
 <span data-ttu-id="d88b4-112">**TransferAllErrorMessages**</span><span class="sxs-lookup"><span data-stu-id="d88b4-112">**TransferAllErrorMessages**</span></span>  
 <span data-ttu-id="d88b4-113">Wählen Sie aus, ob der Task alle oder nur die angegebenen benutzerdefinierten Meldungen vom Quell- auf den Zielserver kopieren soll.</span><span class="sxs-lookup"><span data-stu-id="d88b4-113">Select whether the task should copy all or only the specified user-defined messages from the source server to the destination server.</span></span>  
  
 <span data-ttu-id="d88b4-114">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="d88b4-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="d88b4-115">Wert</span><span class="sxs-lookup"><span data-stu-id="d88b4-115">Value</span></span>|<span data-ttu-id="d88b4-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d88b4-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d88b4-117">**True**</span><span class="sxs-lookup"><span data-stu-id="d88b4-117">**True**</span></span>|<span data-ttu-id="d88b4-118">Alle benutzerdefinierten Meldungen kopieren.</span><span class="sxs-lookup"><span data-stu-id="d88b4-118">Copy all user-defined messages.</span></span>|  
|<span data-ttu-id="d88b4-119">**False**</span><span class="sxs-lookup"><span data-stu-id="d88b4-119">**False**</span></span>|<span data-ttu-id="d88b4-120">Nur die angegebenen benutzerdefinierten Meldungen kopieren.</span><span class="sxs-lookup"><span data-stu-id="d88b4-120">Copy only the specified user-defined messages.</span></span>|  
  
 <span data-ttu-id="d88b4-121">**ErrorMessagesList**</span><span class="sxs-lookup"><span data-stu-id="d88b4-121">**ErrorMessagesList**</span></span>  
 <span data-ttu-id="d88b4-122">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um die zu kopierenden Fehlermeldungen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d88b4-122">Click the browse button **(...)** to select the error messages to copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d88b4-123">Sie müssen **SourceConnection** angeben, bevor Sie eine zu kopierende Fehlermeldung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="d88b4-123">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
 <span data-ttu-id="d88b4-124">**ErrorMessageLanguagesList**</span><span class="sxs-lookup"><span data-stu-id="d88b4-124">**ErrorMessageLanguagesList**</span></span>  
 <span data-ttu-id="d88b4-125">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um die Sprachen auszuwählen, für die benutzerdefinierte Fehlermeldungen auf den Zielserver kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="d88b4-125">Click the browse button **(...)** to select the languages for which to copy user-defined error messages to the destination server.</span></span> <span data-ttu-id="d88b4-126">Auf dem Zielserver muss eine Version der Meldung in us_english (Codepage 1033) vorhanden sein, bevor Sie andere Sprachversionen auf den Server übertragen können.</span><span class="sxs-lookup"><span data-stu-id="d88b4-126">A us_english (code page 1033) version of the message must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d88b4-127">Sie müssen **SourceConnection** angeben, bevor Sie eine zu kopierende Fehlermeldung auswählen können.</span><span class="sxs-lookup"><span data-stu-id="d88b4-127">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88b4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d88b4-128">See Also</span></span>  
 <span data-ttu-id="d88b4-129">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d88b4-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d88b4-130">[Integration Services-Tasks](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d88b4-130">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="d88b4-131">[Editor für den Task Fehlermeldungen übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d88b4-131">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d88b4-132">[SMO-Verbindungs-Manager](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d88b4-132">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="d88b4-133">[Editor für den Task Fehlermeldungen übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d88b4-133">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="d88b4-134">SMO-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="d88b4-134">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
