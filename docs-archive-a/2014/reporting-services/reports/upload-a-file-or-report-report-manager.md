---
title: Hochladen einer Datei oder eines Berichts (Berichts-Manager) | Microsoft-Dokumentation
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
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 119e2b22976dc227e017b81a59b698cf9eb7457f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615282"
---
# <a name="upload-a-file-or-report-report-manager"></a><span data-ttu-id="56081-102">Hochladen einer Datei oder eines Berichts (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="56081-102">Upload a File or Report (Report Manager)</span></span>
  <span data-ttu-id="56081-103">Der Berichts-Manager umfasst eine Uploadfunktion, sodass Sie Berichte, Modelle und andere Dateien zu einem Berichtsserver hinzufügen können, ohne diese Elemente von einer Clientanwendung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="56081-103">Report Manager provides an upload feature so that you can add reports, models, and other files to a report server without having to publish those items from a client application.</span></span> <span data-ttu-id="56081-104">Dateien, die Sie über das Dateisystem hochladen, werden als Elemente auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="56081-104">Files that you upload from the file system are stored as items on the report server.</span></span> <span data-ttu-id="56081-105">Die Speicherung erfolgt je nach Dateityp:</span><span class="sxs-lookup"><span data-stu-id="56081-105">The type of file you upload determines how it is stored:</span></span>  
  
-   <span data-ttu-id="56081-106">RDL-Dateien werden als Berichte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="56081-106">.rdl files are stored as reports.</span></span>  
  
-   <span data-ttu-id="56081-107">SMDL-Dateien werden als Berichtsmodelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="56081-107">.smdl files are stored as report models.</span></span>  
  
-   <span data-ttu-id="56081-108">Alle anderen Dateien, einschließlich freigegebener Datenquellendateien (RDS), werden als Ressourcen hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="56081-108">All other files, including shared data source (.rds) files, are uploaded as resources.</span></span> <span data-ttu-id="56081-109">Ressourcen werden nicht von einem Berichtsserver verarbeitet, können aber im Berichts-Manager angezeigt werden, wenn der Berichtsserver den MIME-Typ der Datei unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56081-109">Resources are not processed by a report server, but can be viewed in Report Manager if the report server supports the MIME type of the file.</span></span>  
  
### <a name="to-upload-a-file-or-report"></a><span data-ttu-id="56081-110">So laden Sie eine Datei oder einen Bericht hoch</span><span class="sxs-lookup"><span data-stu-id="56081-110">To upload a file or report</span></span>  
  
1.  <span data-ttu-id="56081-111">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="56081-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="56081-112">Navigieren Sie in Berichts-Manager zur Seite **Inhalt** .</span><span class="sxs-lookup"><span data-stu-id="56081-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="56081-113">Navigieren Sie zum Ordner, zu dem Sie ein Element hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="56081-113">Navigate to the folder to which you want to add an item.</span></span>  
  
3.  <span data-ttu-id="56081-114">Klicken Sie auf **Datei hochladen**.</span><span class="sxs-lookup"><span data-stu-id="56081-114">Click **Upload File**.</span></span>  
  
4.  <span data-ttu-id="56081-115">Klicken Sie auf **Durchsuchen** , um eine Datei zum Hochladen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="56081-115">Click **Browse** to select a file to upload.</span></span> <span data-ttu-id="56081-116">Sie können eine Berichtsdefinitionsdatei, ein Bild, ein Dokument oder jede andere Datei hochladen, die Sie auf einem Berichtsserver zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="56081-116">You can upload a report definition file, an image, a document, or any file that you want to make available on the report server.</span></span>  
  
5.  <span data-ttu-id="56081-117">Geben Sie einen Namen für das neue Element ein.</span><span class="sxs-lookup"><span data-stu-id="56081-117">Type a name for the new item.</span></span> <span data-ttu-id="56081-118">Ein Element darf Leerzeichen enthalten, jedoch nicht die folgenden reservierten Zeichen: ; ?</span><span class="sxs-lookup"><span data-stu-id="56081-118">An item name can include spaces, but cannot include the reserved characters: ; ?</span></span> <span data-ttu-id="56081-119">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="56081-119">: \@ & = + , $ / \* \< > |.</span></span>  
  
6.  <span data-ttu-id="56081-120">Wenn Sie ein vorhandenes Element durch ein neues ersetzen möchten, wählen Sie **Vorhandenes Element überschreiben**aus.</span><span class="sxs-lookup"><span data-stu-id="56081-120">If you want to replace an existing item with the new item, select **Overwrite item if it exists**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56081-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56081-121">See Also</span></span>  
 <span data-ttu-id="56081-122">[Erstellen, löschen oder Ändern einer freigegebenen Datenquelle &#40;Berichts-Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="56081-122">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="56081-123">[Die Inhaltsseite &#40;Berichts-Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="56081-123">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="56081-124">[Seite "Datei hochladen" &#40;Berichts-Manager&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="56081-124">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 [<span data-ttu-id="56081-125">Hochladen von Dateien in einen Ordner</span><span class="sxs-lookup"><span data-stu-id="56081-125">Upload Files to a Folder</span></span>](../report-server/upload-files-to-a-folder.md)  
  
  
