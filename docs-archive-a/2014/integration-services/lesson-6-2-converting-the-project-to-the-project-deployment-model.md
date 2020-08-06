---
title: 'Schritt 2: Konvertieren des Projekts in das Projektbereitstellungsmodell | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7b879b2bea4afd58a48cdfc6f0890353fe6758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609309"
---
# <a name="step-2-converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="3f17e-102">Schritt 2: Konvertieren des Projekts in das Projektbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="3f17e-102">Step 2: Converting the Project to the Project Deployment Model</span></span>
  <span data-ttu-id="3f17e-103">In dieser Aufgabe verwenden Sie den Konvertierungs-Assistenten von Integration Services-Projekt, um das Projekt in das Projektbereitstellungsmodell zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3f17e-103">In this task, you will use the Integration Services Project Conversion Wizard to convert the project to the Project Deployment Model.</span></span>  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="3f17e-104">Konvertieren des Projekts in das Projektbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="3f17e-104">Converting the Project to the Project Deployment Model</span></span>  
  
1.  <span data-ttu-id="3f17e-105">Klicken Sie im Menü „Projekt“ auf „Paketbereitstellungsmodell konvertieren“.</span><span class="sxs-lookup"><span data-stu-id="3f17e-105">On the Project Menu, click Convert to Project Deployment Model.</span></span>  
  
2.  <span data-ttu-id="3f17e-106">Überprüfen Sie die Schritte der Konvertierungs-Assistent von Integration Services-Einführungsseite und klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-106">On the Integration Services Project Conversion Wizard Introduction page, review the steps then click Next.</span></span>  
  
3.  <span data-ttu-id="3f17e-107">Klicken Sie auf der Seite zur Paketauswahl in die Paketliste, deaktivieren Sie alle Kontrollkästchen außer Lektion 6.dtsx, und klicken Sie dann auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-107">On the Select Packages page, in the Packages list, clear all checkboxes except Lesson 6.dtsx then click Next.</span></span>  
  
4.  <span data-ttu-id="3f17e-108">Klicken Sie auf der Projekteigenschaftenseite auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-108">On the Specify Project Properties page, click Next.</span></span>  
  
5.  <span data-ttu-id="3f17e-109">Klicken Sie auf der Seite Task 'Paket ausführen' aktualisieren auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-109">On the Update Execute Package Task page click Next.</span></span>  
  
6.  <span data-ttu-id="3f17e-110">Stellen Sie auf auf der Konfigurationsauswahlseite sicher, dass das Paket Lektion 6.dtsx in der Konfigurationsliste ausgewählt ist, und klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-110">On the Select Configurations page, make sure the Lesson 6.dtsx package is selected in the Configurations list, then click Next.</span></span>  
  
7.  <span data-ttu-id="3f17e-111">Stellen Sie auf der Seite zum Erstellen von Parametern sicher, dass das Paket Lektion 6.dtsx ausgewählt ist, und der Bereich in der Konfigurationseigenschaftsliste auf Paket festgelegt ist, und klicken Sie dann auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-111">On the Create Parameters page make sure the Lesson 6.dtsx package is selected, and the Scope is set to Package, in the Configuration Properties List, then Click Next.</span></span>  
  
8.  <span data-ttu-id="3f17e-112">Stellen Sie auf der Seite zur Konfiguration der Parameter sicher, dass die Werte für den Namen und den Wert demselben Namen und Wert entsprechen, den Sie in der Lektion 5 für den Variablen- und Konfigurationswert angegeben haben, und klicken Sie dann auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="3f17e-112">On the Configure Parameters page verify that the values for Name and Value are the same name and value specified in Lesson 5 for the variable and configuration value, then click Next.</span></span>  
  
9. <span data-ttu-id="3f17e-113">Beachten Sie auf der Überprüfungsseite im Zusammenfassungsbereich, dass der Assistent die Informationen aus der Konfigurationsdatei verwendet hat, um die zu konvertierenden Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3f17e-113">On the Review page, in the Summary pane, notice that the wizard has used the information from the configuration file to set the Properties to be converted.</span></span>  
  
10. <span data-ttu-id="3f17e-114">Klicken Sie auf Konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3f17e-114">Click Convert.</span></span>  
  
     <span data-ttu-id="3f17e-115">Beim Abschluss der Konvertierung einer Nachricht wird eine Warnung angezeigt, das die Änderungen nicht gespeichert werden, bis das Projekt in Visual Studio gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3f17e-115">When the conversion completes a message is displayed warning that the changes are not saved until the project is saved in Visual Studio.</span></span> <span data-ttu-id="3f17e-116">Klicken Sie im Warnungsdialogfeld auf OK.</span><span class="sxs-lookup"><span data-stu-id="3f17e-116">Click OK on the warning dialog.</span></span>  
  
11. <span data-ttu-id="3f17e-117">Klicken Sie im Konvertierungs-Assistenten des Integration Services-Projekts auf Schließen.</span><span class="sxs-lookup"><span data-stu-id="3f17e-117">On the Integration Services Project Conversion Wizard click Close.</span></span>  
  
12. <span data-ttu-id="3f17e-118">Klicken Sie in SQL Server Data Tools auf das Menü "Datei", klicken Sie auf "Speichern", um das konvertierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3f17e-118">In SQL Server Data Tools, click the File menu, then click Save to save the converted package.</span></span>  
  
13. <span data-ttu-id="3f17e-119">Klicken Sie auf der Registerkarte "Parameter", und stellen Sie sicher, dass das Paket jetzt einen Parameter für VarFolderName enthält und der Wert denselben Pfad für den Ordner der neuen Beispieldaten aus der Lektion 5-Konfigurationsdatei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3f17e-119">Click the Parameters Tab and verify that the package now contains a parameter for VarFolderName and that the value is the same path specified for the New Sample Data folder from the Lesson 5 configuration file.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3f17e-120">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="3f17e-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3f17e-121">Schritt 3: Testen des Pakets aus Lektion 6</span><span class="sxs-lookup"><span data-stu-id="3f17e-121">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
  
