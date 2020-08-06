---
title: Aktualisieren einer Ressource (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0fca59e476c2820b715ff46729784edc562f74d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617616"
---
# <a name="update-a-resource-report-manager"></a><span data-ttu-id="874e0-102">Aktualisieren einer Ressource (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="874e0-102">Update a Resource (Report Manager)</span></span>
  <span data-ttu-id="874e0-103">Sie können eine Ressource aktualisieren, indem Sie sie durch eine neuere Version ersetzen.</span><span class="sxs-lookup"><span data-stu-id="874e0-103">You can update a resource by replacing it with a newer version.</span></span> <span data-ttu-id="874e0-104">Ressourcen sind auf einem Berichtsserver gespeicherte Elemente, die den Inhalt aus einer Datei enthalten, die Sie hochladen.</span><span class="sxs-lookup"><span data-stu-id="874e0-104">Resources are items stored on a report server that contain content from a file that you upload.</span></span> <span data-ttu-id="874e0-105">Sie können eine vorhandene Ressource ersetzen, indem Sie neue oder andere Dateiinhalte in die vorhandene Ressource importieren.</span><span class="sxs-lookup"><span data-stu-id="874e0-105">You can replace an existing resource by importing new or different file content into the existing resource.</span></span> <span data-ttu-id="874e0-106">Das Aktualisieren einer Ressource bietet eine Möglichkeit, den Inhalt zu aktualisieren und dabei die vorhandenen Eigenschaften und Sicherheitseinstellungen auf der Ressource beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="874e0-106">Updating a resource provides a way to update content while preserving existing properties and security settings on the resource.</span></span>  
  
### <a name="to-update-a-resource"></a><span data-ttu-id="874e0-107">So aktualisieren Sie eine Ressource</span><span class="sxs-lookup"><span data-stu-id="874e0-107">To update a resource</span></span>  
  
1.  <span data-ttu-id="874e0-108">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="874e0-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="874e0-109">Navigieren Sie im Berichts-Manager zu der Ressource, die Sie aktualisieren möchten, oder suchen Sie danach.</span><span class="sxs-lookup"><span data-stu-id="874e0-109">In Report Manager, navigate to or search for the resource you want to update.</span></span>  
  
3.  <span data-ttu-id="874e0-110">Klicken Sie auf die Ressource, um sie auf der Seite **Anzeigen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="874e0-110">Click the resource to open it in the **View** page.</span></span>  
  
4.  <span data-ttu-id="874e0-111">Klicken Sie auf **Eigenschaften** , um die Eigenschaftenseite **Allgemein** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="874e0-111">Click **Properties** to open the **General** properties page.</span></span>  
  
5.  <span data-ttu-id="874e0-112">Klicken Sie auf **Ersetzen** , um die Seite **Ressource importieren** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="874e0-112">Click **Replace** to open the **Import Resource** page.</span></span>  
  
6.  <span data-ttu-id="874e0-113">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="874e0-113">Click **Browse**.</span></span>  
  
7.  <span data-ttu-id="874e0-114">Wählen Sie die Datei aus, durch die Sie die aktuelle Ressource ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="874e0-114">Select the file that you want to use to replace the current resource.</span></span> <span data-ttu-id="874e0-115">Sie können eine aktualisierte Version der Ressourcendatei verwenden oder eine Datei mit einem anderen Namen oder Dateityp angeben.</span><span class="sxs-lookup"><span data-stu-id="874e0-115">You can use an updated version of the resource file, or specify a file with a different name or file type.</span></span>  
  
8.  <span data-ttu-id="874e0-116">Klicken Sie auf **OK** , um die Ressourcendatei hochzuladen, schließen Sie die Seite **Ressource importieren** , und speichern Sie die Änderungen auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="874e0-116">Click **OK** to upload the resource file, close the **Import Resource** page, and save your changes to the report server.</span></span>  
  
 <span data-ttu-id="874e0-117">Wenn die Ressource, die Sie aktualisieren, ein Bild enthält, das in einem Bericht verwendet wird, müssen Sie den Bericht aktualisieren, um das aktualisierte Bild anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="874e0-117">If the resource you are updating contains an image that is used in a report, you need to refresh the report to see the updated image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874e0-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="874e0-118">See Also</span></span>  
 <span data-ttu-id="874e0-119">[Die Inhaltsseite &#40;Berichts-Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="874e0-119">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="874e0-120">[Seite "Datei hochladen" &#40;Berichts-Manager&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="874e0-120">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 <span data-ttu-id="874e0-121">[Hochladen von Dateien in einen Ordner](upload-files-to-a-folder.md) </span><span class="sxs-lookup"><span data-stu-id="874e0-121">[Upload Files to a Folder](upload-files-to-a-folder.md) </span></span>  
 [<span data-ttu-id="874e0-122">Berichts-Manager (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="874e0-122">Report Manager F1 Help</span></span>](../report-manager-f1-help.md)  
  
  
