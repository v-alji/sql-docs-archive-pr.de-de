---
title: Neuer Ordner (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9212fc68-f0a6-4f79-83c1-84baf4d1957e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 27c6a82c4911ba42215d4ab7dcafd666ddce5d54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620240"
---
# <a name="new-folder-page-report-manager"></a><span data-ttu-id="d7c91-102">Neuer Ordner (Seite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="d7c91-102">New Folder Page (Report Manager)</span></span>
  <span data-ttu-id="d7c91-103">Auf der Seite Neuer Ordner können Sie einen neuen Ordner in der Ordnerhierarchie des Berichtsservers erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7c91-103">Use the New Folder page to create a new folder in the report server folder hierarchy.</span></span> <span data-ttu-id="d7c91-104">Der erstellte Ordner ist ein virtueller Ordner, der in einer Berichtsserver-Datenbank gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d7c91-104">The folder that you create is a virtual folder that is stored in a report server database.</span></span> <span data-ttu-id="d7c91-105">Der Ordner wird nicht im Dateisystem des Computers erstellt.</span><span class="sxs-lookup"><span data-stu-id="d7c91-105">The folder is not created in the file system of your computer.</span></span>  
  
 <span data-ttu-id="d7c91-106">Ein Ordner wird direkt als Unterordner des aktuell ausgewählten Ordners erstellt.</span><span class="sxs-lookup"><span data-stu-id="d7c91-106">A folder is created in-place, as a subfolder of the folder that is currently selected.</span></span> <span data-ttu-id="d7c91-107">Ehe Sie einen Ordner erstellen, wechseln Sie zu dem Speicherort, an dem der Ordner erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7c91-107">Before creating a folder, you should navigate to the location where you want to create the folder.</span></span>  
  
 <span data-ttu-id="d7c91-108">Nachdem Sie einen Ordner erstellt haben, können Sie seinen Namen und die Beschreibung über die Seite Allgemeine Eigenschaften des Ordners ändern.</span><span class="sxs-lookup"><span data-stu-id="d7c91-108">After you create a folder, you can modify its name and description through the General properties page of the folder.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="d7c91-109">Navigation</span><span class="sxs-lookup"><span data-stu-id="d7c91-109">Navigation</span></span>  
 <span data-ttu-id="d7c91-110">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="d7c91-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-folder-page"></a><span data-ttu-id="d7c91-111">So öffnen Sie die Seite 'Neuer Ordner'</span><span class="sxs-lookup"><span data-stu-id="d7c91-111">To open the New Folder page</span></span>  
  
1.  <span data-ttu-id="d7c91-112">Öffnen Sie den Berichts-Manager, und navigieren Sie zu dem Ordner, in dem Sie einen neuen Ordner erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d7c91-112">Open Report Manager, and navigate to the folder in which you want to create a new folder.</span></span>  
  
2.  <span data-ttu-id="d7c91-113">Klicken Sie auf der Symbolleiste auf **Neuer Ordner**.</span><span class="sxs-lookup"><span data-stu-id="d7c91-113">In the toolbar, click **New Folder**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7c91-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d7c91-114">Options</span></span>  
 <span data-ttu-id="d7c91-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="d7c91-115">**Name**</span></span>  
 <span data-ttu-id="d7c91-116">Geben Sie den Namen des Ordners an.</span><span class="sxs-lookup"><span data-stu-id="d7c91-116">Specify the name of the folder.</span></span> <span data-ttu-id="d7c91-117">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7c91-117">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="d7c91-118">Er kann auch Leerzeichen und bestimmte Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7c91-118">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="d7c91-119">Folgende Zeichen können nicht beim Angeben eines Namens verwendet werden: ; ?</span><span class="sxs-lookup"><span data-stu-id="d7c91-119">Do not use the characters ; ?</span></span> <span data-ttu-id="d7c91-120">: \@ & = +, $/\* \< > | "oder/, wenn ein Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7c91-120">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="d7c91-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d7c91-121">**Description**</span></span>  
 <span data-ttu-id="d7c91-122">Geben Sie eine Beschreibung des Ordnerinhalts ein.</span><span class="sxs-lookup"><span data-stu-id="d7c91-122">Type a description of folder contents.</span></span> <span data-ttu-id="d7c91-123">Diese Beschreibung wird für Benutzer, die über die Berechtigung zum Zugreifen auf den Ordner verfügen, auf der Seite Inhalt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7c91-123">This description appears in the Contents page to users who have permission to access the folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c91-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7c91-124">See Also</span></span>  
 <span data-ttu-id="d7c91-125">[Erstellen, löschen oder Ändern eines Ordners &#40;Berichts-Manager&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d7c91-125">[Create, Delete, or Modify a Folder &#40;Report Manager&#41;](report-server/create-delete-or-modify-a-folder-report-manager.md) </span></span>  
 <span data-ttu-id="d7c91-126">[Allgemeine Eigenschaften (Seite), Ordner &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d7c91-126">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="d7c91-127">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d7c91-127">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="d7c91-128">[Die Inhaltsseite &#40;Berichts-Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d7c91-128">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="d7c91-129">[Berichts-Manager F1-Hilfe](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d7c91-129">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="d7c91-130">Allgemeine Eigenschaften (Seite), Ordner &#40;Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d7c91-130">General Properties Page, Folders &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/general-properties-page-folders-report-manager.md)  
  
  
