---
title: Importieren eines Integration Services Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3301c328-b0f5-4517-915c-93713413e453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a98219f3a04d11e086957d64a62e7c64cd51418
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609333"
---
# <a name="import-an-integration-services-project"></a><span data-ttu-id="06df5-102">Importieren eines Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="06df5-102">Import an Integration Services Project</span></span>
  <span data-ttu-id="06df5-103">Erstellen Sie mithilfe des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-**Assistenten zum Importieren von Projekten** ein Projekt aus einer vorhandenen Bereitstellungsdatei (ISPAC-Datei) oder aus einem Projekt, das für den Integration Services-Katalog bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="06df5-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]**Import Project Wizard** to create a project from an existing deployment file (.ispac) or from a project deployed to Integration services catalog.</span></span> <span data-ttu-id="06df5-104">Diese Funktion ist besonders nützlich, wenn Sie das Originalexemplar des Projekts nicht haben, aber ein Projekt aus einer ISPAC-Datei oder einem SSISDB-Katalog erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="06df5-104">This feature is especially useful when you do not have the original copy of the project but you want to create one from an .ispac file or SSISDB catalog.</span></span>  
  
### <a name="to-import-a-project"></a><span data-ttu-id="06df5-105">So importieren Sie ein Projekt</span><span class="sxs-lookup"><span data-stu-id="06df5-105">To Import a Project</span></span>  
  
1.  <span data-ttu-id="06df5-106">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]Klicken Sie in **New**im  >  Menü **Datei** auf neues**Projekt** .</span><span class="sxs-lookup"><span data-stu-id="06df5-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New** > **Project** on the **File** menu.</span></span>  
  
2.  <span data-ttu-id="06df5-107">Erweitern Sie im Bereich **Installierte Vorlagen** des Fensters **Neues Projekt\*\*\*\*Business Intelligence**, und klicken Sie auf **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="06df5-107">In the **Installed Templates** area of the **New Project** window, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="06df5-108">Wählen Sie **Integration Services-Assistent zum Importieren von Projekten** aus der Liste der Projekttypen aus.</span><span class="sxs-lookup"><span data-stu-id="06df5-108">Select **Integration Services Import Project Wizard** from the project types list.</span></span>  
  
4.  <span data-ttu-id="06df5-109">Geben Sie einen Namen für das neu zu erstellende Projekt im Textfeld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="06df5-109">Type a name for the new project to be created in the **Name** text box.</span></span>  
  
5.  <span data-ttu-id="06df5-110">Geben Sie den Pfad oder Speicherort für das Projekt im Textfeld **Speicherort** ein, oder klicken Sie auf **Durchsuchen** , um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="06df5-110">Type the path or location for the project in the **Location** text box, or click **Browse** to select one.</span></span>  
  
6.  <span data-ttu-id="06df5-111">Geben Sie einen Namen für die Projektmappe im Textfeld **Projektmappenname** ein.</span><span class="sxs-lookup"><span data-stu-id="06df5-111">Type a name for the solution in the **Solution name** text box.</span></span>  
  
7.  <span data-ttu-id="06df5-112">Klicken Sie auf **OK** , um das Dialogfeld **Integration Services-Assistent zum Importieren von Projekten** zu starten.</span><span class="sxs-lookup"><span data-stu-id="06df5-112">Click **OK** to launch the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
8.  <span data-ttu-id="06df5-113">Klicken Sie auf **Weiter** , um zur Seite **Quelle auswählen** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="06df5-113">Click **Next** to switch to the **Select Source** page.</span></span>  
  
9. <span data-ttu-id="06df5-114">Wenn Sie aus einer **ISPAC-Datei** importieren, geben Sie den Pfad einschließlich Dateinamen im Textfeld **Pfad** ein.</span><span class="sxs-lookup"><span data-stu-id="06df5-114">If you are importing from an **.ispac** file, type the path including file name in the **Path** text box.</span></span> <span data-ttu-id="06df5-115">Klicken Sie auf **Durchsuchen** , um zu dem Ordner zu navigieren, in dem die Projektmappe gespeichert werden soll. Geben Sie den Dateinamen im Textfeld **Dateiname** ein, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="06df5-115">Click **Browse** to navigate to the folder where you want the solution to be stored and type file name in the **File name** text box, and click **Open**.</span></span>  
  
     <span data-ttu-id="06df5-116">Wenn Sie aus einem **Integration Services-Katalog**importieren, geben Sie den Datenbankinstanznamen im Textfeld **Servername** ein, oder klicken Sie auf **Durchsuchen** und wählen Sie die Datenbankinstanz aus, die den Katalog enthält.</span><span class="sxs-lookup"><span data-stu-id="06df5-116">If you are importing from an **Integration Services Catalog**, type the database instance name in the **Server name** text box or click **Browse** and select the database instance that contains the catalog.</span></span>  
  
     <span data-ttu-id="06df5-117">Klicken Sie auf **Durchsuchen** neben dem Textfeld **Pfad** , erweitern Sie den Ordner im Katalog, wählen Sie das Projekt aus, das Sie importieren möchten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="06df5-117">Click **Browse** next to **Path** text box, expand folder in the catalog, select the project you want to import, and click **OK**.</span></span>  
  
     <span data-ttu-id="06df5-118">Klicken Sie auf **Weiter** , um zur Seite **///Überprüfen** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="06df5-118">Click **Next** to switch to the **Review** page.</span></span>  
  
10. <span data-ttu-id="06df5-119">Überprüfen Sie die Informationen, und klicken Sie auf **Importieren** , um ein Projekt auf Grundlage des vorhandenen Projekts zu erstellen, das Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="06df5-119">Review the information and click **Import** to create a project based on the existing project you selected.</span></span>  
  
11. <span data-ttu-id="06df5-120">Optional: Klicken Sie auf **Bericht speichern** , um die Ergebnisse in einer Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="06df5-120">Optional: click **Save Report** to save the results to a file</span></span>  
  
12. <span data-ttu-id="06df5-121">Klicken Sie auf **Schließen** , um das Dialogfeld **Integration Services-Assistent zum Importieren von Projekten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="06df5-121">Click **Close** to close the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
  
