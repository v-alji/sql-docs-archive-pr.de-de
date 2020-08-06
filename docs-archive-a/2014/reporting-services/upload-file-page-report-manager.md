---
title: Datei hochladen (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7bb3166f-9374-4449-b66a-ffb77298507d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de03c6c6bd03cbe083d5e1edfd320264d2cc3bde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719405"
---
# <a name="upload-file-page-report-manager"></a><span data-ttu-id="208af-102">Datei hochladen (Seite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="208af-102">Upload File Page (Report Manager)</span></span>
  <span data-ttu-id="208af-103">Mithilfe der Seite Datei hochladen können Sie eine Datei aus dem Dateisystem in der Berichtsserver-Datenbank veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="208af-103">Use the Upload File page to publish a file from the file system into the report server database.</span></span> <span data-ttu-id="208af-104">Hochgeladene Dateien werden als Elemente in der Ordnerhierarchie des Berichtsservers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="208af-104">Uploaded files are represented as items in the report server folder hierarchy.</span></span>  
  
-   <span data-ttu-id="208af-105">Hochgeladene RDL-Dateien werden als Berichte auf einem Berichtsserver veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="208af-105">Uploaded .rdl files are published to a report server as reports.</span></span>  
  
-   <span data-ttu-id="208af-106">Hochgeladene SMDL-Dateien werden als Berichtsmodelle veröffentlicht, wenn sie Informationen zur Datenquellensicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="208af-106">Uploaded .smdl files are published as report models if they contain data source view information.</span></span> <span data-ttu-id="208af-107">Wenn ein Verweis auf eine Datenquellensicht fehlt, tritt beim Hochladen ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="208af-107">If they are missing a data source view reference, an error occurs during the upload.</span></span> <span data-ttu-id="208af-108">Datenquellen Sicht-Informationen fehlen möglicherweise, wenn Sie eine SMDL-Datei aus einem [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Berichts Modellprojekt hochladen.</span><span class="sxs-lookup"><span data-stu-id="208af-108">Data source view information might be missing if you upload an .smdl file from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] report model project.</span></span> <span data-ttu-id="208af-109">In Berichtsmodellprojekten werden die Informationen zu Datenquellensichten in einer separaten Datei gespeichert und nicht in der SMDL-Datei selbst.</span><span class="sxs-lookup"><span data-stu-id="208af-109">In report model projects, data source view information is stored in a separate file rather than in the .smdl file itself.</span></span>  
  
     <span data-ttu-id="208af-110">Modelldateien, die Informationen zu Datenquellensichten enthalten (und daher erfolgreich hochgeladen werden können), sind jene, die zuvor auf einen Berichtsserver veröffentlicht und dann vom Server in eine Datei im Dateisystem gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="208af-110">Model files that do contain data source view information (and can therefore be successfully uploaded) are those that have been previously published to a report server and then saved from the server to a file on the file system.</span></span> <span data-ttu-id="208af-111">Wenn Sie die Seite mit den allgemeinen Eigenschaften eines Modells öffnen und auf **Bearbeiten** klicken, um das Modell zu öffnen, können Sie es in einer Datei speichern und dann als neues Modell auf den Berichtsserver hochladen.</span><span class="sxs-lookup"><span data-stu-id="208af-111">If you open the General Properties page of a model and click **Edit** to open the model, you can save it to a file and then upload it as a new model on the report server.</span></span> <span data-ttu-id="208af-112">Die SMDL-Datei, die Sie hochladen, enthält alle Informationen, die zum Veröffentlichen des Modell notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="208af-112">The .smdl file that you subsequently upload will have all of information that is necessary for model publication.</span></span>  
  
-   <span data-ttu-id="208af-113">Alle anderen Dateitypen, die Sie hochladen, werden als Ressourcen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="208af-113">All other file types that you upload are stored as resources.</span></span> <span data-ttu-id="208af-114">Dies schließt RDS-Dateien ein, die Verbindungsinformationen für Berichtsdatenquellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="208af-114">This includes .rds files that contain report data source connection information.</span></span> <span data-ttu-id="208af-115">Durch das Hochladen einer RDS-Datei wird kein freigegebenes Datenquellenelement auf dem Berichtsserver erzeugt.</span><span class="sxs-lookup"><span data-stu-id="208af-115">Uploading an .rds file does not produce a shared data source item on the report server.</span></span>  
  
 <span data-ttu-id="208af-116">Wenn Sie ein Element hochladen, wird es in den aktuellen Ordner eingefügt.</span><span class="sxs-lookup"><span data-stu-id="208af-116">When you upload an item, it is placed in the current folder.</span></span> <span data-ttu-id="208af-117">Nach Abschluss des Uploadvorgangs können Sie das Element an einen anderen Speicherort verschieben.</span><span class="sxs-lookup"><span data-stu-id="208af-117">After the upload is complete, you can move the item to a different location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="208af-118">Diese Funktion ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="208af-118">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="208af-119">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="208af-119">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="208af-120">Navigation</span><span class="sxs-lookup"><span data-stu-id="208af-120">Navigation</span></span>  
 <span data-ttu-id="208af-121">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="208af-121">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-upload-file-page"></a><span data-ttu-id="208af-122">So öffnen Sie die Seite "Datei hochladen"</span><span class="sxs-lookup"><span data-stu-id="208af-122">To open the Upload File page</span></span>  
  
1.  <span data-ttu-id="208af-123">Öffnen Sie den Berichts-Manager, und navigieren Sie zu dem Ordner, in den Sie eine Datei hochladen möchten.</span><span class="sxs-lookup"><span data-stu-id="208af-123">Open Report Manager, and navigate to the folder in which you want to upload a file.</span></span>  
  
2.  <span data-ttu-id="208af-124">Klicken Sie auf der Symbolleiste auf **Datei hochladen**.</span><span class="sxs-lookup"><span data-stu-id="208af-124">In the toolbar, click **Upload File**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="208af-125">Tastatur</span><span class="sxs-lookup"><span data-stu-id="208af-125">Options</span></span>  
 <span data-ttu-id="208af-126">**Hochzuladende Datei**</span><span class="sxs-lookup"><span data-stu-id="208af-126">**File to Upload**</span></span>  
 <span data-ttu-id="208af-127">Zeigt den vollqualifizierten Pfad der Datei an, die Sie aus dem Dateisystem kopieren.</span><span class="sxs-lookup"><span data-stu-id="208af-127">Displays the fully qualified path to the file you are copying from the file system.</span></span>  
  
 <span data-ttu-id="208af-128">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="208af-128">**Browse**</span></span>  
 <span data-ttu-id="208af-129">Klicken Sie auf diese Schaltfläche, um eine Datei aus dem Dateisystem auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="208af-129">Click to choose a file from the file system.</span></span>  
  
 <span data-ttu-id="208af-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="208af-130">**Name**</span></span>  
 <span data-ttu-id="208af-131">Geben Sie den Namen der Datei ein, der im Namespace des Berichtsservers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="208af-131">Type the name of the file, as it will appear in the report server namespace.</span></span> <span data-ttu-id="208af-132">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="208af-132">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="208af-133">Er kann auch Leerzeichen und bestimmte Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="208af-133">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="208af-134">Folgende Zeichen können nicht beim Angeben eines Namens verwendet werden: ; ?</span><span class="sxs-lookup"><span data-stu-id="208af-134">Do not use the characters ; ?</span></span> <span data-ttu-id="208af-135">: \@ & = +, $ \* \< > | "oder/, wenn ein Elementname angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="208af-135">: \@ & = + , $ \* \< > | " or / when specifying an item name.</span></span>  
  
 <span data-ttu-id="208af-136">**Vorhandenes Element überschreiben**</span><span class="sxs-lookup"><span data-stu-id="208af-136">**Overwrite item if it exists**</span></span>  
 <span data-ttu-id="208af-137">Aktivieren Sie dieses Kontrollkästchen, wenn Sie ein vorhandenes Element durch eine neuere Version ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="208af-137">Select this check box if you want to replace an existing item with a newer version.</span></span> <span data-ttu-id="208af-138">Um eine vorhandene Version zu überschreiben, muss der Name des neuen Elements genau mit dem Namen des vorhandenen Elements übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="208af-138">To overwrite an existing version, the name of the new item and the existing item must be an exact match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208af-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="208af-139">See Also</span></span>  
 <span data-ttu-id="208af-140">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="208af-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="208af-141">[Die Inhaltsseite &#40;Berichts-Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="208af-141">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="208af-142">[Berichts-Manager F1-Hilfe](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="208af-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="208af-143">Hochladen von Dateien in einen Ordner</span><span class="sxs-lookup"><span data-stu-id="208af-143">Upload Files to a Folder</span></span>](report-server/upload-files-to-a-folder.md)  
  
  
