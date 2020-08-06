---
title: Hochladen von Dateien in einen Ordner | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
- files [Reporting Services]
- folders [Reporting Services], uploading files to
ms.assetid: 2f99a288-d4aa-4c64-b310-e457a2aef2c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfb595ed6059436d17cb82262f5d1975a8397dbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617615"
---
# <a name="upload-files-to-a-folder"></a><span data-ttu-id="cab98-102">Hochladen von Dateien in einen Ordner</span><span class="sxs-lookup"><span data-stu-id="cab98-102">Upload Files to a Folder</span></span>
  <span data-ttu-id="cab98-103">Sie können Dateien vom Dateisystem hochladen und in einer Berichtsserver-Datenbank als verwaltete Elemente speichern.</span><span class="sxs-lookup"><span data-stu-id="cab98-103">You can upload files from the file system and store them as managed items in a report server database.</span></span> <span data-ttu-id="cab98-104">Vom Dateityp hängt es ab, was beim Hochladen einer Datei passiert.</span><span class="sxs-lookup"><span data-stu-id="cab98-104">What happens when you upload a file depends on the file type.</span></span>

-   <span data-ttu-id="cab98-105">Das Hochladen einer RDL-Datei entspricht dem Veröffentlichen eines Berichts.</span><span class="sxs-lookup"><span data-stu-id="cab98-105">Uploading an .rdl file is equivalent to publishing a report.</span></span>

-   <span data-ttu-id="cab98-106">Beim Hochladen anderer Dateien werden diese als einzelne binäre Objekte der Berichtsserver-Datenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cab98-106">Uploading any other file adds it to the report server database as a single binary object.</span></span> <span data-ttu-id="cab98-107">Diese Dateien werden auf einem Berichtsserver als Ressource veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="cab98-107">These files are published to a report server as a resource.</span></span> <span data-ttu-id="cab98-108">Ressourcen können einen beliebigen Dateityp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cab98-108">Resources can be any file type.</span></span> <span data-ttu-id="cab98-109">Falls die Dateierweiterung einem bekannten MIME-Typ entspricht, wird ein Symbol für diesen MIME-Typ zur Identifizierung des Ressourcentyps verwendet.</span><span class="sxs-lookup"><span data-stu-id="cab98-109">If the file extension matches a known MIME type, an icon for that MIME type is used to identify the resource type.</span></span> <span data-ttu-id="cab98-110">Andernfalls wird ein allgemeines Dateisymbol zum Anzeigen einer Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="cab98-110">Otherwise, a generic file icon indicates a resource.</span></span>

> [!NOTE]
>  <span data-ttu-id="cab98-111">Sie können eine RDS-Datei (report data source, Berichtsdatenquelle) nicht hochladen, um eine freigegebene Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cab98-111">You cannot upload a report data source (.rds) file to create a shared data source.</span></span> <span data-ttu-id="cab98-112">Eine RDS-Datei wird nur im Berichts-Designer verwendet.</span><span class="sxs-lookup"><span data-stu-id="cab98-112">An .rds file is used only in Report Designer.</span></span> <span data-ttu-id="cab98-113">Die Datei kann den Inhalt für ein freigegebenes Datenquellenelement, das Sie mithilfe des Berichts-Managers definieren und verwalten, nicht bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cab98-113">It cannot provide the content for a shared data source item that you define and manage through Report Manager.</span></span> <span data-ttu-id="cab98-114">Als Alternative zum Hochladen können Sie ein Skript schreiben, das eine freigegebene, auf einer RDS-Datei basierende Datenquelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="cab98-114">As an alternative to uploading, you can write a script that creates a shared data source based on a .rds file.</span></span>

 <span data-ttu-id="cab98-115">Die maximale Dateigröße für hochgeladene Elemente wird von [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cab98-115">The maximum file size for uploaded items is determined by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="cab98-116">Standardmäßig beträgt die maximale Dateigröße 4 Megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="cab98-116">By default, the maximum size is 4 megabytes (MB).</span></span>

 <span data-ttu-id="cab98-117">Dateien, die Sie in eine Berichtsserver-Datenbank hochladen, werden in der Ordnerhierarchie anhand der folgenden Symbole dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cab98-117">Visually, files that you upload to a report server database are represented in the folder hierarchy with the following icons.</span></span>

 <span data-ttu-id="cab98-118">![Berichts Symbol](../media/hlp-16doc.gif "Berichtssymbol") (Berichts Symbol)</span><span class="sxs-lookup"><span data-stu-id="cab98-118">![Report icon](../media/hlp-16doc.gif "Report icon") report icon</span></span>

 <span data-ttu-id="cab98-119">![Modell Symbol](../media/model-icon.gif "Modell (Symbol)") Berichts Modell (Symbol)</span><span class="sxs-lookup"><span data-stu-id="cab98-119">![Model icon](../media/model-icon.gif "Model icon") report model icon</span></span>

 <span data-ttu-id="cab98-120">Allgemeines ![Ressourcen Symbol (Allgemeines Ressourcen](../media/hlp-16file.gif "allgemeines Ressourcensymbol") Symbol)</span><span class="sxs-lookup"><span data-stu-id="cab98-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon") generic resource icon</span></span>

 <span data-ttu-id="cab98-121">Beim Hochladen einer Datei wird diese stets im aktuell ausgewählten Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cab98-121">When you upload a file, it is always placed in the folder that is currently selected.</span></span> <span data-ttu-id="cab98-122">Sie können zu dem Ordner navigieren, in dem das Element zuerst gespeichert werden soll. Oder Sie laden eine Datei hoch und verschieben diese dann später an den endgültigen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="cab98-122">You can navigate to the folder that you want to contain the item first, or you can upload a file and then move it to a final location later.</span></span>

 <span data-ttu-id="cab98-123">Laden Sie Dateien mit dem Berichts-Manager hoch.</span><span class="sxs-lookup"><span data-stu-id="cab98-123">To upload a file, use Report Manager.</span></span> <span data-ttu-id="cab98-124">Ob Sie Dateien auf einen Berichtsserver hochladen können, hängt von den Tasks ab, die zu der Rollenzuweisung gehören.</span><span class="sxs-lookup"><span data-stu-id="cab98-124">Whether you can upload files to a report server depends on tasks that are part of your role assignment.</span></span> <span data-ttu-id="cab98-125">Falls Sie die Standardsicherheit verwenden, können lokale Administratoren Elemente zu einem Berichtsserver hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cab98-125">If you are using default security, local administrators can add items to a report server.</span></span> <span data-ttu-id="cab98-126">Wenn Meine Berichte aktiviert ist, hat jeder Benutzer, der über einen Ordner Meine Berichte verfügt, die Berechtigung, Elemente in diesen Ordner hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="cab98-126">If My Reports is enabled, any user who has a My Reports folder has permission to upload items to that folder.</span></span> <span data-ttu-id="cab98-127">Wenn Sie benutzerdefinierte Rollenzuweisungen verwenden, muss die Rollenzuweisung Aufgaben für die Ordnerverwaltung enthalten.</span><span class="sxs-lookup"><span data-stu-id="cab98-127">If you use custom role assignments, the role assignment must include tasks that support folder management.</span></span>

|<span data-ttu-id="cab98-128">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="cab98-128">To do this</span></span>|<span data-ttu-id="cab98-129">Einzubindende Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cab98-129">Include these tasks</span></span>|
|----------------|-------------------------|
|<span data-ttu-id="cab98-130">Eine RDL-Datei in einen Ordner hochladen</span><span class="sxs-lookup"><span data-stu-id="cab98-130">Upload an .rdl file to a folder</span></span>|<span data-ttu-id="cab98-131">Berichte verwalten</span><span class="sxs-lookup"><span data-stu-id="cab98-131">Manage reports</span></span>|
|<span data-ttu-id="cab98-132">Eine beliebige Datei als binäres Objekt hochladen</span><span class="sxs-lookup"><span data-stu-id="cab98-132">Upload any file as a binary object</span></span>|<span data-ttu-id="cab98-133">Ressourcen verwalten</span><span class="sxs-lookup"><span data-stu-id="cab98-133">Manage resources</span></span>|
|<span data-ttu-id="cab98-134">Die Inhalte eines Ordners anzeigen</span><span class="sxs-lookup"><span data-stu-id="cab98-134">View the contents of a folder</span></span>|<span data-ttu-id="cab98-135">Ressourcen anzeigen, Berichte anzeigen</span><span class="sxs-lookup"><span data-stu-id="cab98-135">View resources, View reports</span></span>|

## <a name="see-also"></a><span data-ttu-id="cab98-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cab98-136">See Also</span></span>
 <span data-ttu-id="cab98-137">[Berichts-Manager &#40;SSRS-&#41; im einheitlichen Modus].. /Report-Manager-SSRS-Native-Mode.MD) [Erteilen von Berechtigungen für Berichts Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Aufgaben und Berechtigungen](../security/tasks-and-permissions.md) im einheitlichen Modus [&#40;Berichts-Manager eine Datei oder einen Bericht&#41;](../reports/upload-a-file-or-report-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="cab98-137">[Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md) [Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Tasks and Permissions](../security/tasks-and-permissions.md) [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span></span>


