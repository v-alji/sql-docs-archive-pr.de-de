---
title: Optionen (Text-Editor-XML-Verschiedenes Seite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 1a9509f0-c663-4b31-b396-7f5dc4371651
author: rothja
ms.author: jroth
ms.openlocfilehash: d937368d30122442ccbc40372a6b8e1cabc141e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694689"
---
# <a name="options-text-editor---xml---miscellaneous-page"></a><span data-ttu-id="3db3d-102">Optionen (Text-Editor – XML – Seite „Sonstige“)</span><span class="sxs-lookup"><span data-stu-id="3db3d-102">Options (Text Editor - XML - Miscellaneous Page)</span></span>

<span data-ttu-id="3db3d-103">Im Dialogfeld **Optionen** können Sie die Einstellungen für die automatische Vervollständigung sowie die Schemaeinstellungen für den XML-Editor ändern.</span><span class="sxs-lookup"><span data-stu-id="3db3d-103">The **Options** dialog box lets you change the autocompletion and schema settings for the XML Editor.</span></span> <span data-ttu-id="3db3d-104">Diese Einstellungen sind verfügbar, wenn Sie im Menü **Extras** auf **Optionen**klicken. Erweitern Sie den Ordner **Text-Editor** , klicken Sie auf **XML** , und klicken Sie anschließend auf **Verschiedenes** .</span><span class="sxs-lookup"><span data-stu-id="3db3d-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, click **XML** and then click **Miscellaneous** .</span></span>  
  
## <a name="auto-insert"></a><span data-ttu-id="3db3d-105">Automatisch einfügen</span><span class="sxs-lookup"><span data-stu-id="3db3d-105">Auto Insert</span></span>  
 <span data-ttu-id="3db3d-106">**Tags schließen**</span><span class="sxs-lookup"><span data-stu-id="3db3d-106">**Close tags**</span></span>  
 <span data-ttu-id="3db3d-107">Der Text-Editor fügt beim Erstellen von XML-Elementen Endtags hinzu.</span><span class="sxs-lookup"><span data-stu-id="3db3d-107">The Text Editor adds close tags when authoring XML elements.</span></span> <span data-ttu-id="3db3d-108">Wenn das Anfangstag eines Elements ausgewählt ist, fügt der Editor das passende Endtag mit dem entsprechenden Namespacepräfix hinzu.</span><span class="sxs-lookup"><span data-stu-id="3db3d-108">If an element start tag is selected, the editor inserts the matching close tag, including a matching namespace prefix.</span></span> <span data-ttu-id="3db3d-109">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3db3d-109">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="3db3d-110">**Attributanführungszeichen**</span><span class="sxs-lookup"><span data-stu-id="3db3d-110">**Attribute quotes**</span></span>  
 <span data-ttu-id="3db3d-111">Beim Erstellen von XML-Attributen fügt der Editor die Zeichen `="``"` hinzu und fügt zwischen den Anführungszeichen ein Caretzeichen (**^** ) ein.</span><span class="sxs-lookup"><span data-stu-id="3db3d-111">When authoring XML attributes, the editor inserts the `="``"` characters and positions the caret (**^)** inside the quotation marks.</span></span> <span data-ttu-id="3db3d-112">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3db3d-112">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="3db3d-113">**Namespacedeklarationen**</span><span class="sxs-lookup"><span data-stu-id="3db3d-113">**Namespace declarations**</span></span>  
 <span data-ttu-id="3db3d-114">Der Editor fügt die benötigten Namespacedeklarationen automatisch an den entsprechenden Stellen ein.</span><span class="sxs-lookup"><span data-stu-id="3db3d-114">The editor automatically inserts namespace declarations wherever they are needed.</span></span> <span data-ttu-id="3db3d-115">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3db3d-115">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="3db3d-116">**Sonstige Markups (Kommentare, CDATA)**</span><span class="sxs-lookup"><span data-stu-id="3db3d-116">**Other markup (Comments, CDATA)**</span></span>  
 <span data-ttu-id="3db3d-117">Kommentare, CDATA, DOCTYPE, Verarbeitungsanweisungen sowie sonstige Markupelemente werden automatisch vervollständigt.</span><span class="sxs-lookup"><span data-stu-id="3db3d-117">Comments, CDATA, DOCTYPE, processing instructions, and other markup is autocompleted.</span></span> <span data-ttu-id="3db3d-118">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3db3d-118">This check box is selected by default.</span></span>  
  
## <a name="network"></a><span data-ttu-id="3db3d-119">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="3db3d-119">Network</span></span>  
 <span data-ttu-id="3db3d-120">**DTDs und Schemata automatisch herunterzuladen**</span><span class="sxs-lookup"><span data-stu-id="3db3d-120">**Automatically download DTDs and schemas**</span></span>  
 <span data-ttu-id="3db3d-121">Schemata und Dokumenttypdefinitionen (DTDs) werden automatisch von den HTTP-Adressen heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="3db3d-121">Schemas and document type definitions (DTDs) are automatically downloaded from HTTP locations.</span></span> <span data-ttu-id="3db3d-122">Diese Funktion verwendet System.Net mit aktivierter automatischer Proxyservererkennung.</span><span class="sxs-lookup"><span data-stu-id="3db3d-122">This feature uses System.Net with autoproxy server detection enabled.</span></span> <span data-ttu-id="3db3d-123">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3db3d-123">This check box is selected by default.</span></span>  
  
## <a name="outlining"></a><span data-ttu-id="3db3d-124">Gliedern</span><span class="sxs-lookup"><span data-stu-id="3db3d-124">Outlining</span></span>  
 <span data-ttu-id="3db3d-125">**Beim Öffnen von Dateien in Gliederungsmodus wechseln**</span><span class="sxs-lookup"><span data-stu-id="3db3d-125">**Enter outlining mode when files open**</span></span>  
 <span data-ttu-id="3db3d-126">Aktiviert die Gliederungsfunktion beim Öffnen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="3db3d-126">Turns on the outlining feature when a file is opened.</span></span> <span data-ttu-id="3db3d-127">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3db3d-127">This check box is selected by default.</span></span>  
  
## <a name="caching"></a><span data-ttu-id="3db3d-128">Caching</span><span class="sxs-lookup"><span data-stu-id="3db3d-128">Caching</span></span>  
 <span data-ttu-id="3db3d-129">**Schemas**</span><span class="sxs-lookup"><span data-stu-id="3db3d-129">**Schemas**</span></span>  
 <span data-ttu-id="3db3d-130">Gibt den Speicherort des Schemacaches an.</span><span class="sxs-lookup"><span data-stu-id="3db3d-130">Specifies the location of the schema cache.</span></span> <span data-ttu-id="3db3d-131">Mit der Schaltfläche Durchsuchen können Sie den Speicherort des aktuellen Schemacaches in einem neuen Fenster öffnen.</span><span class="sxs-lookup"><span data-stu-id="3db3d-131">The Browse button (...) opens the current schema cache location in a new window.</span></span> <span data-ttu-id="3db3d-132">Der Standard Speicherort lautet *\<Management Studio install directory>* \Xml\Schemas.</span><span class="sxs-lookup"><span data-stu-id="3db3d-132">The default location is *\<Management Studio install directory>* \Xml\Schemas.</span></span>  
