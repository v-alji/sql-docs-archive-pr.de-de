---
title: Entpacken eines DAC-Pakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- wizard [DAC], unpack
- data-tier application [SQL Server], unpack
- How to [DAC], unpack
- unpack DAC
ms.assetid: 697b69b3-f157-4e22-ac4e-f65c5fc2d0ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ba0930f79a47696a6c9a9c1bfe028316601f64b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622677"
---
# <a name="unpack-a-dac-package"></a><span data-ttu-id="d121c-102">Entpacken eines DAC-Pakets</span><span class="sxs-lookup"><span data-stu-id="d121c-102">Unpack a DAC Package</span></span>
  <span data-ttu-id="d121c-103">Verwenden Sie das Dialogfeld Datenebenenanwendung entpacken, um die Skripts und die Dateien aus einem Datenebenenanwendungs-Paket (DAC) zu entzippen.</span><span class="sxs-lookup"><span data-stu-id="d121c-103">Use the Unpack Data-tier Application dialog box to unzip the scripts and files from a data-tier application (DAC) package.</span></span> <span data-ttu-id="d121c-104">Die Skripts und Dateien werden in einem Ordner abgelegt, in dem sie überprüft werden können, bevor das Paket für die Bereitstellung der DAC in einem Produktionssystem verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d121c-104">The scripts and files are placed in a folder where they can be reviewed before the package is used to deploy the DAC into a production system.</span></span> <span data-ttu-id="d121c-105">Der Inhalt einer DAC kann auch mit dem Inhalt eines anderen Pakets verglichen werden, das in einen anderen Ordner entpackt wurde.</span><span class="sxs-lookup"><span data-stu-id="d121c-105">The contents of one DAC can also be compared with the contents of another package unpacked to another folder.</span></span>  
  
1.  <span data-ttu-id="d121c-106">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="d121c-106">**Before you begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="d121c-107">**So entpacken Sie ein DAC-Paket mit:**  [dem Dialogfeld „Unpack Data-Tier Application Dialog“ (Datenebenenanwendung entpacken)](#UnpackDACDial), [dem Untersuchen des Inhalts eines DAC-Pakets](#ExamDACPack)</span><span class="sxs-lookup"><span data-stu-id="d121c-107">**To unpack a DAC, using:**  [Unpack Data-tier Application Dialog](#UnpackDACDial), [Examine the Contents of a DAC Package](#ExamDACPack)</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d121c-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d121c-108">Security</span></span>  
 <span data-ttu-id="d121c-109">Das Bereitstellen eines DAC-Pakets aus unbekannten oder nicht vertrauenswürdigen Quellen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d121c-109">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="d121c-110">Solche DACs können schädlichen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code ausführt oder Fehler verursacht, indem er das Schema ändert.</span><span class="sxs-lookup"><span data-stu-id="d121c-110">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="d121c-111">Bevor Sie eine DAC aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, sollten Sie sie auf einer isolierten [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Testinstanz bereitstellen, die DAC entpacken und den Code, z. B. gespeicherte Prozeduren oder anderen benutzerdefinierten Code, untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d121c-111">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
##  <a name="unpack-data-tier-application-dialog"></a><a name="UnpackDACDial"></a> <span data-ttu-id="d121c-112">Datenebenenanwendung entpacken</span><span class="sxs-lookup"><span data-stu-id="d121c-112">Unpack Data-tier Application Dialog</span></span>  
 <span data-ttu-id="d121c-113">**So entpacken Sie eine DAC-Paketdatei**</span><span class="sxs-lookup"><span data-stu-id="d121c-113">**To Unpack a DAC Package File**</span></span>  
  
-   <span data-ttu-id="d121c-114">Navigieren Sie im **Windows-Explorer**zum Speicherort einer DAC-Paketdatei (.dacpac).</span><span class="sxs-lookup"><span data-stu-id="d121c-114">In **Windows Explorer**, navigate to the location of a DAC package (.dacpac) file.</span></span>  
  
-   <span data-ttu-id="d121c-115">Öffnen Sie das Dialogfeld "Datenebenenanwendung entpacken" mit einer dieser beiden Methoden:</span><span class="sxs-lookup"><span data-stu-id="d121c-115">Use one of these two methods to open the Unpack Data-tier Application dialog:</span></span>  
  
    1.  <span data-ttu-id="d121c-116">Klicken Sie mit der rechten Maustaste auf die DAC-Paketdatei (.dacpac), und wählen Sie **Entpacken**aus.</span><span class="sxs-lookup"><span data-stu-id="d121c-116">Right-click the DAC package (.dacpac) file and select **Unpack**.</span></span>  
  
    2.  <span data-ttu-id="d121c-117">Doppelklicken Sie auf die DAC-Paketdatei.</span><span class="sxs-lookup"><span data-stu-id="d121c-117">Double-click the DAC package file.</span></span>  
  
-   <span data-ttu-id="d121c-118">Schließen Sie die Dialogfelder ab:</span><span class="sxs-lookup"><span data-stu-id="d121c-118">Complete the dialogs:</span></span>  
  
    -   [<span data-ttu-id="d121c-119">DAC-Paketdatei für Microsoft SQL Server entpacken</span><span class="sxs-lookup"><span data-stu-id="d121c-119">Unpack Microsoft SQL Server DAC Package File</span></span>](#Unpack)  
  
    -   [<span data-ttu-id="d121c-120">Nach Ordner suchen</span><span class="sxs-lookup"><span data-stu-id="d121c-120">Browse for Folder</span></span>](#Browse)  
  
###  <a name="unpack-microsoft-sql-server-dac-package-file"></a><a name="Unpack"></a> <span data-ttu-id="d121c-121">DAC-Paketdatei für Microsoft SQL Server entpacken</span><span class="sxs-lookup"><span data-stu-id="d121c-121">Unpack Microsoft SQL Server DAC Package File</span></span>  
 <span data-ttu-id="d121c-122">Verwenden Sie diese Seite, um den Zielordner anzugeben, in dem die entpackten Dateien abgelegt werden sollen, und führen Sie dann den Entpackungsvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="d121c-122">Use this page to specify the destination folder in which to place the unpacked files, and then run the unpack operation.</span></span>  
  
 <span data-ttu-id="d121c-123">**Dateien werden in diesen Ordner entpackt:** – Geben Sie den vollständigen Pfad zum Ordner der entpackten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="d121c-123">**Files will be unpacked to this folder:** - Specify the full path to the folder for the unpacked files.</span></span> <span data-ttu-id="d121c-124">Wenn der Ordner vorhanden ist und Sie den vollständigen Pfad kennen, geben Sie den Pfad im Feld ein.</span><span class="sxs-lookup"><span data-stu-id="d121c-124">If the folder exists and you know the full path, type the path in the box.</span></span> <span data-ttu-id="d121c-125">Klicken Sie andernfalls auf die Schaltfläche **Durchsuchen** , um zu einem Ordner zu navigieren oder einen neuen Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d121c-125">If not, click the **Browse** button to navigate to a folder or create a new folder.</span></span>  
  
 <span data-ttu-id="d121c-126">**Durchsuchen** – Öffnet die Seite **Nach Ordner suchen** , wo Sie einen Ordner auswählen können, indem Sie in der Dateihierarchie navigieren oder einen neuen Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="d121c-126">**Browse** - Opens the **Browse for Folder** page where you can choose a folder by navigating the file hierarchy, or create a new folder.</span></span>  
  
 <span data-ttu-id="d121c-127">**Entpacken** – Startet den Entpackungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="d121c-127">**Unpack** - Starts the unpack operation.</span></span>  
  
 <span data-ttu-id="d121c-128">**Abbrechen** – Schließt das Dialogfeld, ohne das DAC-Paket zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="d121c-128">**Cancel** - Terminates the dialog box without unpacking the DAC package.</span></span>  
  
###  <a name="browse-for-folder"></a><a name="Browse"></a> <span data-ttu-id="d121c-129">Nach Ordner suchen</span><span class="sxs-lookup"><span data-stu-id="d121c-129">Browse for Folder</span></span>  
 <span data-ttu-id="d121c-130">Verwenden Sie diese Seite, um den Zielordner für den Entpackungsvorgang auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d121c-130">Use this page to choose the destination folder for the unpack operation.</span></span> <span data-ttu-id="d121c-131">Optional können Sie auch einen neuen Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="d121c-131">Optionally, you can also create a new folder.</span></span>  
  
 <span data-ttu-id="d121c-132">**Ordnerliste** – Zeigt die Dateihierarchie für den Computer an.</span><span class="sxs-lookup"><span data-stu-id="d121c-132">**Folder list** - Displays the file hierarchy for your computer.</span></span> <span data-ttu-id="d121c-133">Erweitern Sie die Knoten, um zum Ordner zu navigieren, in den das DAC-Paket entpackt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d121c-133">Expand the nodes to navigate to the folder in which to unpack the DAC package.</span></span> <span data-ttu-id="d121c-134">Klicken Sie auf den Ordner und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d121c-134">Click on the folder and then click **OK**.</span></span>  
  
 <span data-ttu-id="d121c-135">**Neuen Ordner erstellen** – Öffnet ein Dialogfeld, in dem Sie den Namen für einen neuen Ordner angeben können, der in dem Ordner erstellt werden soll, den Sie gerade in der Ordnerhierarchie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="d121c-135">**Make New Folder** - Opens a dialog in which you can specify the name for a new folder to be created in the folder you have currently selected in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="d121c-136">**OK** – Legt den Ordnerpfad fest, den Sie im Feld **Dateien werden in diesen Ordner entpackt** der Seite **DAC-Paketdatei entpacken** ausgewählt haben, und wechselt wieder zu dieser Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="d121c-136">**OK** - Places the path to the folder you selected in the **Files will be unpacked to this folder** box of the **Unpack DAC Package File** page and returns you to that page.</span></span>  
  
 <span data-ttu-id="d121c-137">**Abbrechen** – Schließt das Dialogfeld, ohne einen Ordner auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d121c-137">**Cancel** - Terminates the dialog box without selecting a folder.</span></span>  
  
##  <a name="examine-the-contents-of-a-dac-package"></a><a name="ExamDACPack"></a> <span data-ttu-id="d121c-138">Untersuchen des Inhalts eines DAC-Pakets</span><span class="sxs-lookup"><span data-stu-id="d121c-138">Examine the Contents of a DAC Package</span></span>  
 <span data-ttu-id="d121c-139">Nachdem Sie das Paket entpackt haben, können Sie die vom Dialogfeld **Datenebenenanwendung entpacken** erzeugten Dateien untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d121c-139">After unpacking the package, you can examine the files produced by the **Unpack Data-tier Application** dialog.</span></span> <span data-ttu-id="d121c-140">Das Dialogfeld erstellt die folgenden Dateien im ausgewählten Zielordner:</span><span class="sxs-lookup"><span data-stu-id="d121c-140">The dialog box builds the following files in the selected destination folder:</span></span>  
  
1.  <span data-ttu-id="d121c-141">Ein Transact-SQL-Skript, das die Anweisungen zum Erstellen der in der DAC definierten Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="d121c-141">A Transact-SQL script that contains the statements for creating the objects defined in the DAC.</span></span> <span data-ttu-id="d121c-142">Der Dateiname ist *DACName*.sql, wobei *DACName* der Name der DAC ist.</span><span class="sxs-lookup"><span data-stu-id="d121c-142">The file name is *DACName*.sql, where *DACName* is the name of the DAC.</span></span>  
  
2.  <span data-ttu-id="d121c-143">Alle XML-Dateien aus dem Paket.</span><span class="sxs-lookup"><span data-stu-id="d121c-143">All XML files from the package.</span></span>  
  
3.  <span data-ttu-id="d121c-144">Alle Dateien, die sich im Bereich für zusätzliche Dateien der DAC befinden, z. B. vor oder nach der Bereitstellung der DAC auszuführende Dateien.</span><span class="sxs-lookup"><span data-stu-id="d121c-144">All files from the Extra Files section of the DAC, such as the DAC pre-deployment or post-deployment files.</span></span>  
  
 <span data-ttu-id="d121c-145">Weitere Informationen finden Sie unter [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="d121c-145">For more information, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d121c-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d121c-146">See Also</span></span>  
 <span data-ttu-id="d121c-147">[Datenebenenanwendungen](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d121c-147">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="d121c-148">[Bereitstellen einer Datenebenenanwendung](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="d121c-148">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="d121c-149">Upgrade einer Datenebenenanwendung</span><span class="sxs-lookup"><span data-stu-id="d121c-149">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
  
  
