---
title: Umbenennen einer mehrdimensionalen Datenbank (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- renaming databases
ms.assetid: 15fdaec7-f3e4-44d9-9b78-1a1d78c484e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3974e7671aff5d1cba22b10563bbc85a129a1dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619404"
---
# <a name="rename-a-multidimensional-database-analysis-services"></a><span data-ttu-id="33b17-102">Umbenennen einer mehrdimensionalen Datenbank (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="33b17-102">Rename a Multidimensional Database (Analysis Services)</span></span>
  <span data-ttu-id="33b17-103">Die Art und Weise, in der Sie den Namen einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank ändern, hängt davon ab, wie Sie eine Verbindung mit der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="33b17-103">The manner in which you change the name of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database depends upon how you connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="33b17-104">Zum Ändern des Namens einer vorhandenen Datenbank müssen Sie die Verbindung im Onlinemodus herstellen.</span><span class="sxs-lookup"><span data-stu-id="33b17-104">To change the name of an existing database, you must connect in online mode.</span></span> <span data-ttu-id="33b17-105">Zum Ändern des Namens der Datenbank, in die Objekte in einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt instanziiert werden, müssen Sie die Verbindung im Projektmodus herstellen.</span><span class="sxs-lookup"><span data-stu-id="33b17-105">To change the name of the database into which objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project will be instantiated, you must connect in project mode.</span></span>  
  
### <a name="to-change-the-database-name-in-online-mode"></a><span data-ttu-id="33b17-106">So ändern Sie den Datenbanknamen im Onlinemodus</span><span class="sxs-lookup"><span data-stu-id="33b17-106">To change the database name in online mode</span></span>  
  
1.  <span data-ttu-id="33b17-107">Stellen Sie mithilfe von [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]eine direkte Verbindung mit der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="33b17-107">Using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], connect directly to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="33b17-108">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die Datenbank, und klicken Sie anschließend auf **Datenbank bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="33b17-108">In Solution Explorer, right-click the database and then click **Edit Database**.</span></span>  
  
3.  <span data-ttu-id="33b17-109">Ändern Sie im Textfeld **Datenbankname** den Namen der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="33b17-109">In the **Database name** text box, change the database name.</span></span>  
  
4.  <span data-ttu-id="33b17-110">Klicken Sie auf der Symbolleiste auf **Speichern** oder **Alle speichern** , klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** oder **Alle speichern** , oder schließen Sie den Datenbank-Designer \*\*\*\* , und klicken Sie bei entsprechender Aufforderung auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="33b17-110">Click **Save** or **Save All** on the toolbar, click **Save Selected Items** or **Save All** on the **File** menu, or close the **Database Designer** and then click **Save** when prompted.</span></span>  
  
     <span data-ttu-id="33b17-111">Der Datenbankname wird in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz aktualisiert, und das Datenbankobjekt im Projektmappen-Explorer wird aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="33b17-111">The database name is updated in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the database object in Solution Explorer is refreshed.</span></span>  
  
### <a name="to-change-the-database-name-in-project-mode"></a><span data-ttu-id="33b17-112">So ändern Sie den Datenbanknamen im Projektmodus</span><span class="sxs-lookup"><span data-stu-id="33b17-112">To change the database name in project mode</span></span>  
  
1.  <span data-ttu-id="33b17-113">Öffnen Sie das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt.</span><span class="sxs-lookup"><span data-stu-id="33b17-113">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="33b17-114">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="33b17-114">In Solution Explorer, right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="33b17-115">Klicken Sie im Dialogfeld **Eigenschaftenseiten** im Abschnitt **Konfigurationseigenschaften** auf **Bereitstellung** .</span><span class="sxs-lookup"><span data-stu-id="33b17-115">In the **Property Pages** dialog box, click **Deployment** in the **Configuration Properties** section.</span></span>  
  
4.  <span data-ttu-id="33b17-116">Ändern Sie die **Database** -Eigenschaft in den neuen Datenbanknamen.</span><span class="sxs-lookup"><span data-stu-id="33b17-116">Change the **Database** property to the new database name.</span></span>  
  
     <span data-ttu-id="33b17-117">Bei der nächsten Bereitstellung des [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekts wird es mit diesem neuen Datenbanknamen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="33b17-117">The next time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is deployed, it will be deployed to this new database name.</span></span> <span data-ttu-id="33b17-118">Wenn eine Datenbank mit diesem Namen bereits vorhanden ist, wird sie überschrieben.</span><span class="sxs-lookup"><span data-stu-id="33b17-118">If this database already exists, it will be overwritten.</span></span>  
  
### <a name="to-change-the-database-name-using-sql-server-management-studio"></a><span data-ttu-id="33b17-119">So ändern Sie den Datenbanknamen mithilfe von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33b17-119">To change the database name using SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="33b17-120">Klicken Sie mit der rechten Maustaste auf die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank, und bearbeiten Sie die Eigenschaft „Name“.</span><span class="sxs-lookup"><span data-stu-id="33b17-120">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and edit the Name property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b17-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33b17-121">See Also</span></span>  
 <span data-ttu-id="33b17-122">[Konfigurieren von Server Eigenschaften in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="33b17-122">[Configure Server Properties in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span></span>  
 <span data-ttu-id="33b17-123">[&#40;Analysis Services Eigenschaften für mehrdimensionale Datenbanken festlegen&#41;](set-multidimensional-database-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="33b17-123">[Set Multidimensional Database Properties &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="33b17-124">[Konfigurieren von Analysis Services Projekteigenschaften &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="33b17-124">[Configure Analysis Services Project Properties &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span></span>  
 [<span data-ttu-id="33b17-125">Bereitstellen von Analysis Services-Projekten &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="33b17-125">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  
