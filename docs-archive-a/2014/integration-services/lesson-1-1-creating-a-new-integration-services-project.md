---
title: 'Schritt 1: Erstellen eines neuen Integration Services-Projekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f14521b5-941e-443b-8f5e-385f98e37fbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d6d16d7febcdecb01eb7a93167c2a18d225a9c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618146"
---
# <a name="step-1-creating-a-new-integration-services-project"></a><span data-ttu-id="ddeec-102">Schritt 1: Erstellen eines neuen Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="ddeec-102">Step 1: Creating a New Integration Services Project</span></span>
  <span data-ttu-id="ddeec-103">Der erste Schritt beim Erstellen eines Pakets in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ist das Erstellen eines [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekts.</span><span class="sxs-lookup"><span data-stu-id="ddeec-103">The first step in creating a package in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="ddeec-104">Dieses Projekt enthält die Vorlagen für die Objekte, die Sie in einer Datentransformationslösung verwenden: Datenquellen, Datenquellensichten und Pakete.</span><span class="sxs-lookup"><span data-stu-id="ddeec-104">This project includes the templates for the objects - data sources, data source views, and packages - that you use in a data transformation solution.</span></span>  
  
 <span data-ttu-id="ddeec-105">Die Pakete, die Sie in diesem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Lernprogramm erstellen, interpretieren die Werte gebietsschemabezogener Daten.</span><span class="sxs-lookup"><span data-stu-id="ddeec-105">The packages that you will create in this [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial interpret the values of locale-sensitive data.</span></span> <span data-ttu-id="ddeec-106">Wenn Ihr Computer nicht für die Verwendung der Ländereinstellung Englisch (USA) konfiguriert ist, müssen Sie zusätzliche Eigenschaften im Paket festlegen.</span><span class="sxs-lookup"><span data-stu-id="ddeec-106">If your computer is not configured to use the regional option English (United States), you need to set additional properties in the package.</span></span> <span data-ttu-id="ddeec-107">Die Pakete, die Sie in den Lektionen 2 bis 5 verwenden, werden aus dem in Lektion 1 erstellten Paket kopiert, sodass Sie keine gebietsschemabezogenen Eigenschaften in dem kopierten Paket aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="ddeec-107">The packages that you use in lessons 2 through 5 are copied from the package created in lesson 1, and you need not update locale-sensitive properties in the copied packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddeec-108">Dieses Lernprogramm erfordert Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="ddeec-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
>   
>  <span data-ttu-id="ddeec-109">Weitere Informationen zum Installieren von SQL Server Data Tools finden Sie unter [Herunterladen von SQL Server Data Tools](https://msdn.microsoft.com/data/hh297027).</span><span class="sxs-lookup"><span data-stu-id="ddeec-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://msdn.microsoft.com/data/hh297027).</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="ddeec-110">So erstellen Sie ein neues Integration Services-Projekt</span><span class="sxs-lookup"><span data-stu-id="ddeec-110">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="ddeec-111">Zeigen Sie im Menü **Start** auf **Alle Programme**, dann auf **Microsoft SQL Server**, und klicken Sie auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ddeec-111">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, and click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="ddeec-112">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt** , um ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddeec-112">On the **File** menu, point to **New**, and click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="ddeec-113">Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Business Intelligence** unter **Installierte Vorlagen**, und wählen Sie im Bereich **Vorlagen** die Option **Integration Services-Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="ddeec-113">In the **New Project** dialog box, expand the **Business Intelligence** node under **Installed Templates**, and select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="ddeec-114">Ändern Sie im Feld **Name** den Standardnamen in **SSIS Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="ddeec-114">In the **Name** box, change the default name to **SSIS Tutorial**.</span></span> <span data-ttu-id="ddeec-115">Deaktivieren Sie optional das Kontrollkästchen **Projektmappenverzeichnis erstellen** .</span><span class="sxs-lookup"><span data-stu-id="ddeec-115">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="ddeec-116">Akzeptieren Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen** , um nach dem Ordner zu suchen, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ddeec-116">Accept the default location, or click **Browse** to browse to locate the folder you want to use.</span></span> <span data-ttu-id="ddeec-117">Klicken Sie im Dialogfeld **Projektspeicherort** auf den Ordner und anschließend auf **Ordner auswählen**.</span><span class="sxs-lookup"><span data-stu-id="ddeec-117">In the **Project Location** dialog box, click the folder and click **Select Folder**.</span></span>  
  
6.  <span data-ttu-id="ddeec-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddeec-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="ddeec-119">Standardmäßig wird ein leeres Paket mit dem Namen **Package.dtsx**erstellt und Ihrem Projekt unter SSIS-Pakete hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ddeec-119">By default, an empty package, titled **Package.dtsx**, will be created and added to your project under SSIS Packages.</span></span>  
  
7.  <span data-ttu-id="ddeec-120">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Package.dtsx**, klicken Sie auf **Umbenennen**, und benennen Sie das Standardpaket in **Lesson 1.dtsx**um.</span><span class="sxs-lookup"><span data-stu-id="ddeec-120">In **Solution Explorer** toolbar, right-click **Package.dtsx**, click **Rename**, and rename the default package to **Lesson 1.dtsx**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ddeec-121">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ddeec-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ddeec-122">Schritt 2: Hinzufügen und Konfigurieren eines Verbindungs-Managers für Flatfiles</span><span class="sxs-lookup"><span data-stu-id="ddeec-122">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
  
