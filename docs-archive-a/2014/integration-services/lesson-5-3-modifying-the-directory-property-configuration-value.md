---
title: 'Schritt 3: Ändern des Directory-Eigenschaftskonfigurationswertes | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a71a7a181322d60caca98da4ddf3261cbce99c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615433"
---
# <a name="step-3-modifying-the-directory-property-configuration-value"></a><span data-ttu-id="2895f-102">Schritt 3: Ändern des Konfigurationswerts der Directory-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2895f-102">Step 3: Modifying the Directory Property Configuration Value</span></span>
  <span data-ttu-id="2895f-103">In dieser Aufgabe ändern Sie die in der Datei SSISTutorial.dtsConfig gespeicherte Konfigurationseinstellung für die Wert-Eigenschaft der Variablen `User::varFolderName`auf Paketebene.</span><span class="sxs-lookup"><span data-stu-id="2895f-103">In this task, you will modify the configuration setting, stored in the SSISTutorial.dtsConfig file, for the Value property of the package-level variable `User::varFolderName`.</span></span> <span data-ttu-id="2895f-104">Die Variable aktualisiert die Verzeichnis-Eigenschaft des Foreach-Schleifencontainers.</span><span class="sxs-lookup"><span data-stu-id="2895f-104">The variable updates the Directory property of the Foreach Loop container.</span></span> <span data-ttu-id="2895f-105">Der geänderte Wert verweist auf den `New Sample Data` Ordner, den Sie in der vorherigen Aufgabe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2895f-105">The modified value will point to the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="2895f-106">Nachdem Sie die Konfigurationseinstellung geändert und das Paket ausgeführt haben, wird die Verzeichnis-Eigenschaft durch die Variable aktualisiert. Dabei wird der durch die Konfigurationsdatei aufgefüllte Wert anstelle des Verzeichniswerts verwendet, der ursprünglich im Paket konfiguriert war.</span><span class="sxs-lookup"><span data-stu-id="2895f-106">After you modify the configuration setting and run the package, the Directory property will be updated by the variable, using the value populated from the configuration file instead of the directory value originally configured in the package.</span></span>  
  
### <a name="to-modify-the-configuration-setting-of-the-directory-property"></a><span data-ttu-id="2895f-107">So ändern Sie die Konfigurationseinstellung der Directory-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2895f-107">To modify the configuration setting of the Directory property</span></span>  
  
1.  <span data-ttu-id="2895f-108">Suchen und öffnen Sie in Editor oder einem beliebigen anderen Texteditor die Konfigurationsdatei SSISTutorial.dtsConfig, die Sie mithilfe des Paketkonfigurations-Assistenten in der vorhergehenden Aufgabe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2895f-108">In Notepad or any other text editor, locate and open the SSISTutorial.dtsConfig configuration file that you created by using the Package Configuration Wizard in the previous task.</span></span>  
  
2.  <span data-ttu-id="2895f-109">Ändern Sie den Wert des Elements " **konfigurierte** Wert" so, dass es mit dem Pfad des `New Sample Data` Ordners, den Sie in der vorherigen Aufgabe erstellt haben, entspricht.</span><span class="sxs-lookup"><span data-stu-id="2895f-109">Change the value of the **ConfiguredValue** element to match the path of the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="2895f-110">Schließen Sie den Pfad nicht in Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="2895f-110">Do not surround the path in quotes.</span></span> <span data-ttu-id="2895f-111">Wenn `New Sample Data` sich der Ordner auf der Stamm Ebene Ihres Laufwerks befindet (z. b. C: \\ ), sollte das aktualisierte XML dem folgenden Beispiel ähneln:</span><span class="sxs-lookup"><span data-stu-id="2895f-111">If the `New Sample Data` folder is at the root level of your drive (for example, C:\\), the updated XML should be similar to the following sample:</span></span>  
  
     `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
     <span data-ttu-id="2895f-112">Die Überschriften Informationen, `GeneratedBy` , `GeneratedFromPackageID` und **GeneratedDate** unterscheiden sich natürlich in Ihrer Datei.</span><span class="sxs-lookup"><span data-stu-id="2895f-112">The heading information, `GeneratedBy`, `GeneratedFromPackageID`, and **GeneratedDate** will be different in your file, of course.</span></span> <span data-ttu-id="2895f-113">Achten Sie insbesondere auf das `Configuration`-Element.</span><span class="sxs-lookup"><span data-stu-id="2895f-113">The element to note is the `Configuration` element.</span></span> <span data-ttu-id="2895f-114">Die `Value`-Eigenschaft der `User::varFolderName`-Variablen enthält nun den Wert C:\New Sample Data.</span><span class="sxs-lookup"><span data-stu-id="2895f-114">The `Value` property of the variable, `User::varFolderName`, now contains C:\New Sample Data.</span></span>  
  
3.  <span data-ttu-id="2895f-115">Speichern Sie die Änderung, und schließen Sie dann den Texteditor.</span><span class="sxs-lookup"><span data-stu-id="2895f-115">Save the change, and then close the text editor.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2895f-116">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="2895f-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2895f-117">Schritt 4: Testen des Tutorialpakets aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="2895f-117">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](../integration-services/lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
  
