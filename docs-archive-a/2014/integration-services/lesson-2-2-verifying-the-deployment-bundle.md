---
title: 'Schritt 2: Überprüfen des Bereitstellungspakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f452a87154175ac05a050761d8f12b6bfe61cd8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609317"
---
# <a name="step-2-verifying-the-deployment-bundle"></a><span data-ttu-id="99611-102">Schritt 2: Überprüfen des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="99611-102">Step 2: Verifying the Deployment Bundle</span></span>
  <span data-ttu-id="99611-103">In Lektion 1 haben Sie das Deployment Tutorial-Projekt erstellt und dem Projekt Pakete und Hilfsdateien hinzugefügt; in der vorherigen Aufgabe haben Sie ein Bereitstellungsprogramm für das Projekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="99611-103">In lesson 1, you created the Deployment Tutorial project and added packages and ancillary files to the project; in the previous task you built a deployment utility for the project.</span></span>  
  
 <span data-ttu-id="99611-104">In dieser Aufgabe überprüfen Sie den Inhalt des Bereitstellungspakets.</span><span class="sxs-lookup"><span data-stu-id="99611-104">In this task, you will verify the contents of the deployment bundle.</span></span> <span data-ttu-id="99611-105">Das Bereitstellungspaket ist der Ordner, den Sie auf den Zielcomputer kopieren und zum Installieren der Pakete verwenden.</span><span class="sxs-lookup"><span data-stu-id="99611-105">The deployment bundle is the folder that you will copy to the destination computer and use to install packages.</span></span> <span data-ttu-id="99611-106">Wenn Sie den Standardwert, bin\Deployment, als Speicherort des Bereitstellungshilfsprogramms verwendet haben, entspricht das Bereitstellungspaket dem Ordner „Bin\Deployment“ im Ordner „Deployment Tutorial“ des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekts.</span><span class="sxs-lookup"><span data-stu-id="99611-106">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a><span data-ttu-id="99611-107">So überprüfen Sie den Inhalt des Bereitstellungspakets</span><span class="sxs-lookup"><span data-stu-id="99611-107">To verify the content of deployment bundle</span></span>  
  
1.  <span data-ttu-id="99611-108">Suchen Sie den Ordner bin\Deployment auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="99611-108">Locate the bin\Deployment folder on your computer.</span></span>  
  
2.  <span data-ttu-id="99611-109">Überprüfen Sie, ob die folgenden Dateien vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="99611-109">Verify that the following files are present:</span></span>  
  
    -   <span data-ttu-id="99611-110">DataTransfer.dtsx</span><span class="sxs-lookup"><span data-stu-id="99611-110">DataTransfer.dtsx</span></span>  
  
    -   <span data-ttu-id="99611-111">datatransferconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="99611-111">datatransferconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="99611-112">Deployment Tutorial.SSISDeploymentManifest</span><span class="sxs-lookup"><span data-stu-id="99611-112">Deployment Tutorial.SSISDeploymentManifest</span></span>  
  
    -   <span data-ttu-id="99611-113">LoadXMLData.dtsx</span><span class="sxs-lookup"><span data-stu-id="99611-113">LoadXMLData.dtsx</span></span>  
  
    -   <span data-ttu-id="99611-114">loadxmldataconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="99611-114">loadxmldataconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="99611-115">NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="99611-115">NewCustomers.txt</span></span>  
  
    -   <span data-ttu-id="99611-116">orders.xml</span><span class="sxs-lookup"><span data-stu-id="99611-116">orders.xml</span></span>  
  
    -   <span data-ttu-id="99611-117">orders.xsd</span><span class="sxs-lookup"><span data-stu-id="99611-117">orders.xsd</span></span>  
  
    -   <span data-ttu-id="99611-118">Readme.txt</span><span class="sxs-lookup"><span data-stu-id="99611-118">Readme.txt</span></span>  
  
3.  <span data-ttu-id="99611-119">Klicken Sie mit der rechten Maustaste auf Deployment Tutorial.SSISDeploymentManifest, zeigen Sie auf **Öffnen mit**, und klicken Sie anschließend auf **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="99611-119">Right-click Deployment Tutorial.SSISDeploymentManifest, point **to Open With**, and then click **Internet Explorer**.</span></span> <span data-ttu-id="99611-120">Sie können die Datei auch in einem Texteditor, wie z. B. dem Editor, öffnen.</span><span class="sxs-lookup"><span data-stu-id="99611-120">You can also open the file in a text editor such as Notepad.</span></span> <span data-ttu-id="99611-121">Der XML-Code für die Datei sollte folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="99611-121">The XML code of the file should be the following:</span></span>  
  
     `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  <span data-ttu-id="99611-122">Vergewissern Sie sich, dass der Wert des `AllowConfigurationChanges` -Attributs **true** ist und der XML-Code ein- `Package` Element für jedes der beiden Pakete enthält, ein `MiscellaneousFile` -Element für jede der vier nicht-Paketdateien und ein- `ConfigurationFile` Element für jede der beiden XML-Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="99611-122">Verify that the value of the `AllowConfigurationChanges` attribute is **true** and the XML includes a `Package` element for each of the two packages, a `MiscellaneousFile` element for each of the four non-package files, and a `ConfigurationFile` element for each of the two XML configuration files.</span></span>  
  
5.  <span data-ttu-id="99611-123">Beenden Sie Internet Explorer oder den Texteditor.</span><span class="sxs-lookup"><span data-stu-id="99611-123">Exit Internet Explorer or the text editor.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="99611-124">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="99611-124">Next Lesson</span></span>  
 [<span data-ttu-id="99611-125">Lektion 3: Installieren von Paketen</span><span class="sxs-lookup"><span data-stu-id="99611-125">Lesson 3: Installing Packages</span></span>](../integration-services/lesson-3-install-ssis-package.md)  
  
<span data-ttu-id="99611-126">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="99611-126">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="99611-127">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="99611-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="99611-128">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="99611-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="99611-129">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="99611-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
