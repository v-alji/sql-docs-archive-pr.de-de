---
title: Assistent zum Importieren von Projekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.importprojectwizard.f1
ms.assetid: 9247ad6c-4bd1-43ab-b347-583181cb9917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81a990995d7e98c21b61f484372d31c9a1773102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618193"
---
# <a name="import-project-wizard"></a><span data-ttu-id="ea839-102">Assistent zum Importieren von Projekten</span><span class="sxs-lookup"><span data-stu-id="ea839-102">Import Project Wizard</span></span>
  <span data-ttu-id="ea839-103">Verwenden Sie den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Assistenten zum Importieren von Projekten, um ein neues Integration Services-Projekt auf der Grundlage eines vorhandenen Projekts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea839-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Import Project Wizard create a new Integration Services project based on an existing one.</span></span> <span data-ttu-id="ea839-104">Importieren Sie Projekte, die bereits im [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Katalog bereitgestellt wurden, oder importieren Sie Projekte aus einer Projektbereitstellungsdatei (mit der Erweiterung „.ispac“).</span><span class="sxs-lookup"><span data-stu-id="ea839-104">Import projects that have already been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog or import projects from a project deployment file (.ispac extension).</span></span>  
  
### <a name="to-create-a-project-based-on-a-project-in-ispac-file-or-in-catalog"></a><span data-ttu-id="ea839-105">So erstellen Sie ein Projekt auf Grundlage eines Projekts in einer ISPAC-Datei oder im Katalog</span><span class="sxs-lookup"><span data-stu-id="ea839-105">To create a project based on a project in .ispac file or in catalog</span></span>  
  
1.  <span data-ttu-id="ea839-106">Klicken Sie auf **Datei**, zeigen Sie auf **neu**, und klicken Sie auf Projekt.</span><span class="sxs-lookup"><span data-stu-id="ea839-106">Click **File**, point to **New**, and click Project.</span></span>  
  
2.  <span data-ttu-id="ea839-107">Erweitern Sie **Business Intelligence**, und klicken Sie auf **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="ea839-107">Expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="ea839-108">Wählen Sie im mittleren Bereich den **Integration Services-Assistent zum Importieren** aus, geben Sie einen **Namen** für die Projektmappe bzw. das Projekt ein, geben Sie den **Ordner** für das Projekt an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea839-108">Select **Integration Services Import Wizard** in the middle pane, type a **name** for the solution, project, and specify the **folder** for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ea839-109">Daraufhin sollte der **Integration Services-Assistent zum Importieren von Projekten**angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea839-109">You should see the **Integration Services Import Project Wizard**.</span></span> <span data-ttu-id="ea839-110">Dieser Assistent erstellt ein neues Integration Services-Projekt auf der Grundlage eines vorhandenen Projekts.</span><span class="sxs-lookup"><span data-stu-id="ea839-110">This wizard creates a new Integration Services project based on an existing one</span></span>  
  
4.  <span data-ttu-id="ea839-111">Klicken Sie auf der Seite **Einführung** auf **Weiter** , um die Seite **Quelle auswählen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea839-111">Click **Next** on the **Introduction** page to see the **Select Source** page.</span></span>  
  
5.  <span data-ttu-id="ea839-112">Geben Sie an, ob Sie das Projekt aus einer ISPAC-Datei oder einem Katalog importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ea839-112">Specify whether you want to import project from an .ispac file or from a catalog.</span></span>  
  
    -   <span data-ttu-id="ea839-113">Wenn Sie die Option **Projektbereitstellungsdatei** aktivieren, geben Sie den Pfad zur ISPAC-Datei an.</span><span class="sxs-lookup"><span data-stu-id="ea839-113">If you select **Project deployment file** option, specify the path to the .ispac file.</span></span>  
  
    -   <span data-ttu-id="ea839-114">Wenn Sie die Option **Integration Services-Katalog** aktivieren, geben Sie den Namen der Datenbankserverinstanz an, auf der der Katalog vorhanden ist, und den Pfad zum Projekt im Katalog.</span><span class="sxs-lookup"><span data-stu-id="ea839-114">If you select **Integration Services Catalog** option, specify the name of database server instance on which the catalog exists, and the path to the project in the catalog.</span></span>  
  
6.  <span data-ttu-id="ea839-115">Klicken Sie auf der Seite **Quelle auswählen** auf **Weiter** , um die Seite **Überprüfen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea839-115">Click **Next** on the **Select Source** page to see the **Review** page.</span></span> <span data-ttu-id="ea839-116">Überprüfen Sie die auf der Seite angezeigten Informationen zum Importvorgang, die der Assistent ausführen wird.</span><span class="sxs-lookup"><span data-stu-id="ea839-116">Review the information displayed on the page about the import operation the wizard is going to perform.</span></span>  
  
7.  <span data-ttu-id="ea839-117">Klicken Sie auf **Importieren** , um ein neues Integration Services-Projekt auf Grundlage des Projekts, das Sie ausgewählt haben, zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea839-117">Click **Import** to create a new Integration Services project based on the one you selected.</span></span>  
  
8.  <span data-ttu-id="ea839-118">Die Seite **Ergebnisse** sollte die Ergebnisse des Importvorgangs anzeigen, den der Assistent ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="ea839-118">The **Results** page should display the results from import operation the wizard performed.</span></span> <span data-ttu-id="ea839-119">Klicken Sie auf **Bericht speichern** , um den Bericht in einer XML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ea839-119">Click **Save Report** to save the report to an XML file.</span></span>  
  
9. <span data-ttu-id="ea839-120">Klicken Sie auf **Schließen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ea839-120">Click **Close** to close the wizard.</span></span>  
  
  
