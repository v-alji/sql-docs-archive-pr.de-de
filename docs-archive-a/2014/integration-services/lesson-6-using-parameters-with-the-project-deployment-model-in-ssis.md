---
title: 'Lektion 6: Verwenden von Parametern mit dem Projekt Bereitstellungs Modell | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9216f18c-1762-4f2d-8c22-bd0ab7107555
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4bdc6b9dfc019822d6cf1bd9ec7d89ffcc5ea5e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615432"
---
# <a name="lesson-6-using-parameters-with-the-project-deployment-model"></a><span data-ttu-id="53262-102">Lektion 6: Verwenden von Parametern mit dem Projektbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="53262-102">Lesson 6: Using Parameters with the Project Deployment Model</span></span>
  <span data-ttu-id="53262-103">In SQL Server 2012 wird ein neues Bereitstellungsmodell eingeführt, mit dem Sie Projekte auf dem Integration Services-Server bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="53262-103">SQL Server 2012 introduces a new deployment model where you can deploy your projects to the Integration Services server.</span></span> <span data-ttu-id="53262-104">Der Integration Services-Server ermöglicht es Ihnen, Pakete zu verwalten und auszuführen sowie Laufzeitwerte für Pakete zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="53262-104">The Integration Services server enables you to manage and run packages, and to configure runtime values for packages.</span></span>  
  
 <span data-ttu-id="53262-105">In dieser Lektion ändern Sie das Paket, das Sie in [Lektion 5: Hinzufügen von Paket Konfigurationen für das Paket Bereitstellungs Modell](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) erstellt haben, um das Projekt Bereitstellungs Modell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="53262-105">In this lesson, you will modify the package that you created in [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) to use the Project Deployment Model.</span></span> <span data-ttu-id="53262-106">Sie ersetzen den Konfigurationswert durch einen Parameter, um den Speicherort der Beispieldaten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="53262-106">You replace the configuration value with a parameter to specify the sample data location.</span></span> <span data-ttu-id="53262-107">Sie können auch das abgeschlossene Paket aus Lektion 5 kopieren, das im Lieferumfang der Lernprogramme enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="53262-107">You can also copy the completed Lesson 5 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="53262-108">Mithilfe des Assistenten zum Konvertieren von Integration Services-Projekten konvertieren Sie das Projekt in das Projektbereitstellungsmodell und verwenden einen Parameter anstelle eines Konfigurationswerts, um die Directory-Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="53262-108">Using the Integration Services Project Configuration Wizard, you will convert the project to the Project Deployment Model and use a Parameter rather than a configuration value to set the Directory property.</span></span> <span data-ttu-id="53262-109">Diese Lektion enthält einen Teil der Schritte, die Sie ausführen müssen, um vorhandene SSIS-Pakete in das neue Projektbereitstellungsmodell zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="53262-109">This lesson partially covers the steps you would follow to convert existing SSIS packages to the new Project Deployment Model.</span></span>  
  
 <span data-ttu-id="53262-110">Wenn Sie das Paket erneut ausführen, verwendet der Integration Services-Dienst den Parameter, um den Wert der Variablen aufzufüllen, und die Variable aktualisiert wiederum die Directory-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="53262-110">When you run the package again, the Integration Services service uses the parameter to populate the value of the variable, and the variable in turn updates the Directory property.</span></span> <span data-ttu-id="53262-111">Deshalb durchläuft das Paket die Dateien im neuen, durch den Parameterwert angegebenen Datenordner anstatt in dem Ordner, der in der Paketkonfigurationsdatei festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="53262-111">As a result, the package iterates through the files in the new data folder specified by the parameter value rather than the folder that was set in the package configuration file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53262-112">Dieses Lernprogramm erfordert die **AdventureWorksDW2012** -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="53262-112">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="53262-113">Weitere Informationen zur Installation und Bereitstellung von **AdventureWorksDW2012**finden Sie unter [Überlegungen zum Installieren der SQL Server-Beispiele und -Beispieldatenbanken](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span><span class="sxs-lookup"><span data-stu-id="53262-113">For more information about how to install and deploy **AdventureWorksDW2012**, see [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="53262-114">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="53262-114">Lesson Tasks</span></span>  
 <span data-ttu-id="53262-115">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="53262-115">This lesson contains the following tasks:</span></span>  
  
1.  [<span data-ttu-id="53262-116">Schritt 1: Kopieren des Pakets aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="53262-116">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
2.  [<span data-ttu-id="53262-117">Schritt 2: Konvertieren des Projekts in das Projektbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="53262-117">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
3.  [<span data-ttu-id="53262-118">Schritt 3: Testen des Pakets aus Lektion 6</span><span class="sxs-lookup"><span data-stu-id="53262-118">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
4.  [<span data-ttu-id="53262-119">Schritt 4: Bereitstellen des Pakets aus Lektion 6</span><span class="sxs-lookup"><span data-stu-id="53262-119">Step 4: Deploying the Lesson 6 Package</span></span>](lesson-6-4-deploying-the-lesson-6-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="53262-120">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="53262-120">Start the Lesson</span></span>  
 [<span data-ttu-id="53262-121">Schritt 1: Kopieren des Pakets aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="53262-121">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
  
