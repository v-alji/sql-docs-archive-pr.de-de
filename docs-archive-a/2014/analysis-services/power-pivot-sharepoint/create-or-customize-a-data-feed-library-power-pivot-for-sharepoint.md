---
title: Erstellen oder Anpassen einer datenfeedbibliothek (PowerPivot für SharePoint) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data feed library
- data feeds [Analysis Services with SharePoint]
ms.assetid: 699fbeb9-42ab-436b-beba-214db51ea3dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: b86f63c1af094ea9e8a2a1149debeac387bccbf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698582"
---
# <a name="create-or-customize-a-data-feed-library-powerpivot-for-sharepoint"></a><span data-ttu-id="4f4aa-102">Erstellen oder Anpassen einer Datenfeedbibliothek (PowerPivot für SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4f4aa-102">Create or Customize a Data Feed Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="4f4aa-103">Eine *Datenfeedbibliothek* ist eine zweckgebundene SharePoint-Bibliothek, mit der Sie Atom-Datendienstdokumente (.atomsvc) registrieren und freigeben können.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-103">A *data feed library* is a special-purpose SharePoint library that enables you to register and share Atom data service documents (.atomsvc).</span></span> <span data-ttu-id="4f4aa-104">Diese Dokumente enthalten XML-Datenfeeds in [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] -Arbeitsmappen oder anderen Clientanwendungen, die das Atom-Datenfeedformat unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-104">These documents provide XML data feeds to [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks or other client applications that support the Atom data feed format.</span></span> <span data-ttu-id="4f4aa-105">Eine Datenfeedbibliothek unterscheidet sich von anderen SharePoint-Bibliotheken, da sie folgende Möglichkeiten bietet:</span><span class="sxs-lookup"><span data-stu-id="4f4aa-105">A data feed library is different from other SharePoint libraries because it gives you the ability to:</span></span>

-   <span data-ttu-id="4f4aa-106">Erstellen oder Bearbeiten eines *Datendienstdokuments*, das zum Angeben einer HTTP-Verbindung mit einem bestimmten Feed verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-106">Create or edit a *data service document*, used to specify an HTTP connection to a specific feed.</span></span>

-   <span data-ttu-id="4f4aa-107">Freigeben und Verwalten von Datendienstdokumenten an einem zentralen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-107">Share and manage data service documents in a central location.</span></span>

-   <span data-ttu-id="4f4aa-108">Visuelle Identifizierung von Datendienst Dokumenten durch ein Symbol, damit Dienst Dokumente leicht von anderen in derselben Bibliothek gespeicherten Dokumenten unterschieden werden können: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span><span class="sxs-lookup"><span data-stu-id="4f4aa-108">Visually identify data service documents by an icon, so that you can easily distinguish service documents from other documents stored in the same library: ![GMNI_IconDataFeed](../media/gmni-icondatafeed.gif "GMNI_IconDataFeed")</span></span>

 <span data-ttu-id="4f4aa-109">Eine Datenfeedbibliothek enthält immer Datendienstdokumente (ATOMSVC-Dateien) und nie den Datenfeed selbst.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-109">A data feed library always contains data service document (.atomsvc) files, and never the data feed itself.</span></span> <span data-ttu-id="4f4aa-110">Im Gegensatz zu einem Datenfeed, der aus statischen XML-Daten besteht, gibt das Datendienstdokument eine URL zu einem Dienst oder einer Anwendung an, der bzw. die auf Anforderung einen Feed generiert, und stellt wiederverwendbare Verbindungsinformationen für wiederholbare Importvorgänge bereit.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-110">Unlike a data feed, which consists of static XML data, the data service document specifies a URL to a service or application that generates a feed upon request, providing reusable connection information for repeatable import operations.</span></span>

 <span data-ttu-id="4f4aa-111">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="4f4aa-111">This topic contains the following sections:</span></span>

 [<span data-ttu-id="4f4aa-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4f4aa-112">Prerequisites</span></span>](#prereq)

 [<span data-ttu-id="4f4aa-113">Erstellen einer neuen Datenfeedbibliothek</span><span class="sxs-lookup"><span data-stu-id="4f4aa-113">Create a New Data Feed Library</span></span>](#createlib)

 [<span data-ttu-id="4f4aa-114">Hinzufügen des Inhaltstyps für Datenfeeds zu einer Bibliothek</span><span class="sxs-lookup"><span data-stu-id="4f4aa-114">Add the Data Feed Content Type to Any Library</span></span>](#addtolib)

##  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="4f4aa-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4f4aa-115">Prerequisites</span></span>
 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] <span data-ttu-id="4f4aa-116">-Funktion muss für die Websites aktiviert werden, für die Sie die Datenfeedbibliothek erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-116">feature integration must be activated for the sites for which you are creating the data feed library.</span></span> <span data-ttu-id="4f4aa-117">Wenn der Vorlagentyp für Datenfeedbibliotheken nicht verfügbar ist, liegt dies höchstwahrscheinlich daran, dass diese Voraussetzung nicht erfüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-117">If the data feed library template type is not available, the most likely cause is that this prerequisite has not been met.</span></span> <span data-ttu-id="4f4aa-118">Weitere Informationen finden Sie unter [Aktivieren der Power Pivot-Funktions Integration für Website Sammlungen in der zentral Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="4f4aa-118">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>

 <span data-ttu-id="4f4aa-119">Sie müssen Websitebesitzer sein, um die Bibliothek erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-119">You must be a site owner to create the library.</span></span>

##  <a name="create-a-new-data-feed-library"></a><a name="createlib"></a><span data-ttu-id="4f4aa-120">Erstellen einer neuen datenfeedbibliothek</span><span class="sxs-lookup"><span data-stu-id="4f4aa-120">Create a New Data Feed Library</span></span>
 <span data-ttu-id="4f4aa-121">Das Erstellen einer Datenfeedbibliothek ist der erste Schritt zur Aktivierung von Datenfeeds für [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] Arbeitsmappen.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-121">Creating a data feed library is the first step to enabling data feeds for [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks.</span></span> <span data-ttu-id="4f4aa-122">Da eine Datenfeedbibliothek Anwendungs- und Verwaltungsseiten für Datendienstdokumente bereitstellt, muss diese Bibliothek vorhanden sein, bevor Sie ein neues Dokument erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-122">Because a data feed library provides application and management pages for data service documents, you must have this library in place before you can create a new document.</span></span>

 <span data-ttu-id="4f4aa-123">Eine Datenfeedbibliothek basiert auf einer integrierten Vorlage und einem vorkonfigurierten *Inhaltstyp für Datendienstdokumente* , der Eigenschaften und Verhaltensweisen für ein Datendienstdokument definiert.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-123">A data feed library is based on a built-in template and a preconfigured *data service document content type* that defines properties and behaviors for a data service document.</span></span>

1.  <span data-ttu-id="4f4aa-124">Klicken Sie in der oberen linken Ecke der Seite auf **Websiteaktionen** .</span><span class="sxs-lookup"><span data-stu-id="4f4aa-124">Click **Site Actions** at the top left corner of the page.</span></span>

2.  <span data-ttu-id="4f4aa-125">Klicken Sie auf **Weitere Optionen**...</span><span class="sxs-lookup"><span data-stu-id="4f4aa-125">Click **More Options**...</span></span>

3.  <span data-ttu-id="4f4aa-126">Klicken Sie unter Bibliotheken auf **Datenfeedbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-126">Under Libraries, click **Data Feed Library**.</span></span>

4.  <span data-ttu-id="4f4aa-127">Geben Sie Namen, Beschreibung, Start- und Versionseinstellungen ein.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-127">Type the name, description, launch, and version preferences.</span></span> <span data-ttu-id="4f4aa-128">Geben Sie auch beschreibende Informationen an, um Benutzern die Identifikation dieser Bibliothek als Speicherort für Datendienstdokumente zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-128">Include descriptive information to help users identify this library as storage for data service documents.</span></span>

5.  <span data-ttu-id="4f4aa-129">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-129">Click **Create**.</span></span>

 <span data-ttu-id="4f4aa-130">Im Schnellstart-Navigationsbereich für die aktuelle Website wird ein Link zur Datenfeedbibliothek angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-130">A link to the data feed library will appear in the navigation Quick Launch pane for the current site.</span></span>

 <span data-ttu-id="4f4aa-131">Nachdem Sie eine Bibliothek erstellt haben, können Sie mit ihrer Hilfe Datendienstdokumente erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-131">After you create a library, you can use it to create data service documents.</span></span> <span data-ttu-id="4f4aa-132">Weitere Informationen finden Sie unter [Verwenden von Daten Feeds &#40;PowerPivot für SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="4f4aa-132">For more information, see [Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md).</span></span>

##  <a name="add-the-data-feed-content-type-to-any-library"></a><a name="addtolib"></a><span data-ttu-id="4f4aa-133">Hinzufügen des Inhaltstyps für Datenfeeds zu einer Bibliothek</span><span class="sxs-lookup"><span data-stu-id="4f4aa-133">Add the Data Feed Content Type to Any Library</span></span>
 <span data-ttu-id="4f4aa-134">Wenn Sie keine dedizierte Datenfeedbibliothek erstellen, aber trotzdem Datendienstdokumente von einer SharePoint-Website erstellen und verwalten möchten, können Sie den Inhaltstyp für Datendienstdokumente für eine beliebige Bibliothek manuell hinzufügen und konfigurieren, die Sie zum Freigeben von Datendienstdokumenten (ATOMSVC-Dateien) verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-134">If you do not want to create a dedicated data feed library, but you still want to create and manage data service documents from a SharePoint site, you can manually add and configure the data service document content type for any library that you will use to share data service document (.atomsvc) files.</span></span>

 <span data-ttu-id="4f4aa-135">Sie müssen mindestens über die Listenverwaltungsberechtigung verfügen, um einen Inhaltstyp hinzuzufügen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-135">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="4f4aa-136">Diese Berechtigung ist in die Berechtigungsebene "Entwerfen" und höher integriert.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-136">This permission is built into the Design permission level and above.</span></span>

 <span data-ttu-id="4f4aa-137">Die folgenden Schritte müssen für jede Bibliothek wiederholt werden, in der Sie Dokumente für die Datenfeedregistrierung erstellen oder bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-137">The following steps must be repeated for each library in which you want to create or edit data feed registration documents.</span></span>

#### <a name="step-1-enable-content-type-management"></a><span data-ttu-id="4f4aa-138">Schritt 1: Aktivieren der Inhaltstypverwaltung</span><span class="sxs-lookup"><span data-stu-id="4f4aa-138">Step 1: Enable Content Type Management</span></span>

1.  <span data-ttu-id="4f4aa-139">Öffnen Sie die Dokumentbibliothek, für die Sie mehrere Inhaltstypen aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-139">Open the document library for which you want to enable multiple content types.</span></span>

2.  <span data-ttu-id="4f4aa-140">Klicken Sie im SharePoint-Menüband in den Bibliothekstools auf **Bibliothek**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-140">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>

3.  <span data-ttu-id="4f4aa-141">Klicken Sie auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-141">Click **Settings**.</span></span>

4.  <span data-ttu-id="4f4aa-142">Klicken Sie auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-142">Click **Library Settings**.</span></span>

5.  <span data-ttu-id="4f4aa-143">Klicken Sie unter Allgemeine Einstellungen auf **Erweiterte Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-143">In General Settings, click **Advanced settings**.</span></span>

6.  <span data-ttu-id="4f4aa-144">Klicken Sie unter Inhaltstypen im Abschnitt Verwaltung von Inhaltstypen zulassen?</span><span class="sxs-lookup"><span data-stu-id="4f4aa-144">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="4f4aa-145">auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-145">section, click **Yes**.</span></span>

7.  <span data-ttu-id="4f4aa-146">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-146">Click **OK**.</span></span>

#### <a name="step-2-add-the-data-service-document-content-type"></a><span data-ttu-id="4f4aa-147">Schritt 2: Fügen Sie einen Inhaltstyp für Datendienstdokumente hinzu</span><span class="sxs-lookup"><span data-stu-id="4f4aa-147">Step 2: Add the Data Service Document Content Type</span></span>

1.  <span data-ttu-id="4f4aa-148">Klicken Sie im Abschnitt Inhaltstypen auf **Aus vorhandenen Websiteinhaltstypen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-148">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="4f4aa-149">Falls diese Seite nicht angezeigt wird, wechseln Sie zurück zur Website und klicken unter Bibliothekstools auf **Bibliothek** und dann auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-149">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>

2.  <span data-ttu-id="4f4aa-150">Klicken Sie unter Inhaltstypen auf **Aus vorhandenen Websiteinhaltstypen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-150">In Content Types, click **Add from existing site content types**.</span></span>

3.  <span data-ttu-id="4f4aa-151">Wählen Sie unter Websiteinhaltstypen auswählen aus: die Option **Business Intelligence**aus.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-151">In Select site content types from:, select **Business Intelligence**.</span></span>

4.  <span data-ttu-id="4f4aa-152">Klicken Sie in der Liste der verfügbaren Websiteinhaltstypen auf **Datendienstdokumente**und dann auf **Hinzufügen** , um den ausgewählten Inhaltstyp in die Liste der hinzuzufügenden Inhaltstypen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-152">In Available Site Content Types, click **Data Service Document**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>

5.  <span data-ttu-id="4f4aa-153">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-153">Click **OK**.</span></span>

#### <a name="step-3-verify-data-service-document-configuration"></a><span data-ttu-id="4f4aa-154">Schritt 3: Überprüfen der Datendienstdokumentkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4f4aa-154">Step 3: Verify Data Service Document Configuration</span></span>

1.  <span data-ttu-id="4f4aa-155">Öffnen Sie die Homepage der Website.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-155">Open the site home page.</span></span>

2.  <span data-ttu-id="4f4aa-156">Öffnen Sie die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-156">Open the library.</span></span>

3.  <span data-ttu-id="4f4aa-157">Klicken Sie im SharePoint-Menüband auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-157">On the SharePoint ribbon, click **Documents**.</span></span>

4.  <span data-ttu-id="4f4aa-158">Klicken Sie auf den Pfeil nach unten in Neues Dokument, und wählen Sie **Datendienstdokument**aus.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-158">Click the down arrow on New Document, and select **Data Service Document**.</span></span> <span data-ttu-id="4f4aa-159">Die Seite Neues Datendienstdokument sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4f4aa-159">The New Data Service Document page should appear.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f4aa-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f4aa-160">See Also</span></span>
 <span data-ttu-id="4f4aa-161">[Verwenden von Datenfeeds &#40;PowerPivot für SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Löschen einer Power Pivot-datenfeedbibliothek](delete-a-power-pivot-data-feed-library.md) [Power Pivot-Server Verwaltung und-Konfiguration in](power-pivot-server-administration-and-configuration-in-central-administration.md) [Power Pivot-Daten Feeds](power-pivot-data-feeds.md) der zentral Administration</span><span class="sxs-lookup"><span data-stu-id="4f4aa-161">[Use Data Feeds &#40;PowerPivot for SharePoint&#41;](use-data-feeds-power-pivot-for-sharepoint.md) [Delete a PowerPivot Data Feed Library](delete-a-power-pivot-data-feed-library.md) [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) [PowerPivot Data Feeds](power-pivot-data-feeds.md)</span></span>


