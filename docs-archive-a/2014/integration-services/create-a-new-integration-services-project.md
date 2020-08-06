---
title: Erstellen eines neuen Integration Services Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 1e23f259-0401-4333-ab4f-89809aae63b1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f62d3ac2d33bb51a0ccc3b77d9f8b5ec0f52b345
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616620"
---
# <a name="create-a-new-integration-services-project"></a><span data-ttu-id="560e1-102">Erstellen eines neuen SQL Server Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="560e1-102">Create a New Integration Services Project</span></span>
  <span data-ttu-id="560e1-103">Mit diesem Verfahren wird ein neues Projekt und eine neue [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projektmappe erstellt.</span><span class="sxs-lookup"><span data-stu-id="560e1-103">This procedure creates a new project and a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] solution.</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="560e1-104">So erstellen Sie ein neues Integration Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="560e1-104">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="560e1-105">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="560e1-105">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="560e1-106">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="560e1-106">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="560e1-107">Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **Vorlagen** die Vorlage **Integration Services-Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="560e1-107">In the **New Project** dialog box, in the **Templates** pane, select the **Integration Services Project** template.</span></span>  
  
     <span data-ttu-id="560e1-108">Die **Integration Services-Projekt** -Vorlage erstellt ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, das ein einzelnes, leeres Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="560e1-108">The **Integration Services Project** template creates an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains a single, empty package.</span></span>  
  
4.  <span data-ttu-id="560e1-109">(Optional) Bearbeiten Sie den Projektnamen und den Speicherort.</span><span class="sxs-lookup"><span data-stu-id="560e1-109">(Optional) Edit the project name and the location.</span></span>  
  
     <span data-ttu-id="560e1-110">Der Projektmappenname wird automatisch aktualisiert und an den Projektnamen angepasst.</span><span class="sxs-lookup"><span data-stu-id="560e1-110">The solution name is automatically updated to match the project name.</span></span>  
  
5.  <span data-ttu-id="560e1-111">Um einen separaten Ordner für die Projektmappendatei zu erstellen, aktivieren Sie das Kontrollkästchen **Projektmappenverzeichnis erstellen**.</span><span class="sxs-lookup"><span data-stu-id="560e1-111">To create a separate folder for the solution file, select **Create directory for solution**.</span></span> <span data-ttu-id="560e1-112">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="560e1-112">This is the default option.</span></span>  
  
6.  <span data-ttu-id="560e1-113">Wenn die Software für die Quellcodeverwaltung auf dem Computer installiert ist, wählen Sie **Zur Quellcodeverwaltung hinzufügen**  aus, um das Projekt der Quellcodeverwaltung zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="560e1-113">If source control software is installed on the computer, select **Add to source control**  to associate the project with source control.</span></span>  
  
7.  <span data-ttu-id="560e1-114">Falls es sich bei der Software für die Quellcodeverwaltung um [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe handelt, wird das Dialogfeld **Visual SourceSafe-Anmeldung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="560e1-114">If the source control software is [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, the **Visual SourceSafe Login** dialog box opens.</span></span> <span data-ttu-id="560e1-115">Stellen Sie im Dialogfeld **Visual SourceSafe-Anmeldung**einen Benutzernamen, ein Kennwort und den Namen der [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="560e1-115">In **Visual SourceSafe Login**, provide a user name, a password, and the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database.</span></span> <span data-ttu-id="560e1-116">Klicken Sie auf **Durchsuchen** , um die Datenbank zu suchen.</span><span class="sxs-lookup"><span data-stu-id="560e1-116">Click **Browse** to locate the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="560e1-117">Klicken Sie im Menü **Extras** auf **Optionen**, und erweitern Sie den Knoten **Quellcodeverwaltung**, um das ausgewählte Quellcodeverwaltungs-Plug-In anzuzeigen und zu ändern und um die Umgebung für die Quellcodeverwaltung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="560e1-117">To view and change the selected source control plug-in and to configure the source control environment, click **Options** on the **Tools** menu, and then expand the **Source Control** node.</span></span>  
  
8.  <span data-ttu-id="560e1-118">Klicken **Sie auf** **OK** , um die Projekt Mappe dem Projektmappen-Explorer hinzuzufügen und das Projekt der Projekt Mappe hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="560e1-118">Click **OK** to add the solution to **Solution Explore**r and add the project to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560e1-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="560e1-119">See Also</span></span>  
 <span data-ttu-id="560e1-120">[Integration Services &#40;SSIS-&#41;-Projekte](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="560e1-120">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="560e1-121">Hinzufügen oder Entfernen eines Integration Services-Projekts in einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="560e1-121">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
