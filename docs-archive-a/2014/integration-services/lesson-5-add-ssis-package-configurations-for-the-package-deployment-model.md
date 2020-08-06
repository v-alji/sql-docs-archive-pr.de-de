---
title: 'Lektion 5: Hinzufügen von Paket Konfigurationen für das Paket Bereitstellungs Modell | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c10dd54-67cb-4b63-9e4d-aa6ff0452ecb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee03d624ac7144cf6aef0829bcb7835fe5af9c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696985"
---
# <a name="lesson-5-adding-package-configurations-for-the-package-deployment-model"></a><span data-ttu-id="1b864-102">Lektion 5: Hinzufügen von Paketkonfigurationen für das Paketbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="1b864-102">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>
  <span data-ttu-id="1b864-103">Mithilfe von Paketkonfigurationen können Sie Laufzeiteigenschaften und -variablen von außerhalb der Entwicklungsumgebung festlegen.</span><span class="sxs-lookup"><span data-stu-id="1b864-103">Package configurations let you set run-time properties and variables from outside of the development environment.</span></span> <span data-ttu-id="1b864-104">Mithilfe von Konfigurationen können Sie Pakete entwickeln, die flexibel und einfach bereitzustellen sowie zu verteilen sind.</span><span class="sxs-lookup"><span data-stu-id="1b864-104">Configurations allow you to develop packages that are flexible and easy to both deploy and distribute.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="1b864-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] stellt die folgenden Konfigurationstypen bereit:</span><span class="sxs-lookup"><span data-stu-id="1b864-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offers the following configuration types:</span></span>  
  
-   <span data-ttu-id="1b864-106">XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="1b864-106">XML configuration file</span></span>  
  
-   <span data-ttu-id="1b864-107">Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="1b864-107">Environment variable</span></span>  
  
-   <span data-ttu-id="1b864-108">Registrierungseintrag</span><span class="sxs-lookup"><span data-stu-id="1b864-108">Registry entry</span></span>  
  
-   <span data-ttu-id="1b864-109">Variable für das übergeordnete Paket</span><span class="sxs-lookup"><span data-stu-id="1b864-109">Parent package variable</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="1b864-110">-Tabelle</span><span class="sxs-lookup"><span data-stu-id="1b864-110">table</span></span>  
  
 <span data-ttu-id="1b864-111">In dieser Lektion ändern Sie das einfache [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, das Sie in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) erstellt haben, um das Paketbereitstellungsmodell und die Paketkonfigurationen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="1b864-111">In this lesson, you will modify the simple [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you created in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) to use the Package Deployment Model and take advantage of package configurations.</span></span> <span data-ttu-id="1b864-112">Sie können auch das abgeschlossene Paket aus Lektion 4 kopieren, das im Lieferumfang der Lernprogramme enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1b864-112">You can also copy the completed Lesson 4 package that is included with the tutorial.</span></span> <span data-ttu-id="1b864-113">Mithilfe des Paketkonfigurations-Assistenten erstellen Sie eine XML-Konfiguration, von der die `Directory`-Eigenschaft des Foreach-Schleifencontainers mithilfe einer Variablen auf Paketebene aktualisiert wird, die der Directory-Eigenschaft zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1b864-113">Using the Package Configuration Wizard, you will create an XML configuration that updates the `Directory` property of the Foreach Loop container by using a package-level variable mapped to the Directory property.</span></span> <span data-ttu-id="1b864-114">Nach dem Erstellen der Konfigurationsdatei ändern Sie den Wert der Variablen von außerhalb der Entwicklungsumgebung und legen die geänderte Eigenschaft als Zeiger auf einen neuen Beispieldatenordner fest.</span><span class="sxs-lookup"><span data-stu-id="1b864-114">Once you have created the configuration file, you will modify the value of the variable from outside of the development environment and point the modified property to a new sample data folder.</span></span> <span data-ttu-id="1b864-115">Wenn Sie das Paket erneut ausführen, füllt die Konfigurationsdatei den Wert der Variablen auf, und die Variable aktualisiert wiederum die- `Directory` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1b864-115">When you run the package again, the configuration file populates the value of the variable, and the variable in turn updates the `Directory` property.</span></span> <span data-ttu-id="1b864-116">Im Ergebnis iteriert das Paket durch die Dateien im neuen Datenordner, und nicht durch die Dateien im Originalordner, der im Paket hartcodiert war.</span><span class="sxs-lookup"><span data-stu-id="1b864-116">As a result, the package iterates through the files in the new data folder, rather than iterating through the files in the original folder that was hard-coded in the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b864-117">Dieses Lernprogramm erfordert die **AdventureWorksDW2012** -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="1b864-117">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="1b864-118">Weitere Informationen zum Installieren und Bereitstellen von **AdventureWorksDW2012**finden Sie unter [Reporting Services Produktbeispiel-Projekt auf CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="1b864-118">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="1b864-119">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="1b864-119">Lesson Tasks</span></span>  
 <span data-ttu-id="1b864-120">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="1b864-120">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="1b864-121">Schritt 1: Kopieren des Pakets aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="1b864-121">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
-   [<span data-ttu-id="1b864-122">Schritt 2: Aktivieren und Konfigurieren von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="1b864-122">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
-   [<span data-ttu-id="1b864-123">Schritt 3: Ändern des Konfigurationswerts der Directory-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1b864-123">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
-   [<span data-ttu-id="1b864-124">Schritt 4: Testen des Tutorialpakets aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="1b864-124">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="1b864-125">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="1b864-125">Start the Lesson</span></span>  
  
-   [<span data-ttu-id="1b864-126">Schritt 1: Kopieren des Pakets aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="1b864-126">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
  
