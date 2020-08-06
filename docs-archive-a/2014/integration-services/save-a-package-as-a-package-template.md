---
title: Speichern eines Pakets als Paket Vorlage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30bddb5a343e7c7aef279bc66c25be30a2cf1a12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698426"
---
# <a name="save-a-package-as-a-package-template"></a><span data-ttu-id="d34c6-102">Speichern eines Pakets als Paketvorlage</span><span class="sxs-lookup"><span data-stu-id="d34c6-102">Save a Package as a Package Template</span></span>
  <span data-ttu-id="d34c6-103">In diesem Thema wird beschrieben, wie Sie beim Erstellen neuer Integration Services-Pakete in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]benutzerdefinierte Pakete als Vorlagen festlegen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="d34c6-103">This topic describes how to designate and use custom packages as templates when you create new Integration Services packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d34c6-104">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] verwendet standardmäßig eine Paketvorlage, die ein leeres Paket erstellt, wenn Sie einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt ein neues Paket hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d34c6-104">By default, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] uses a package template that creates an empty package when you add a new package to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="d34c6-105">Sie können diese Standardvorlage nicht ersetzen. Es können jedoch neue Vorlagen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d34c6-105">You cannot replace this default template, but you can add new templates.</span></span>  
  
 <span data-ttu-id="d34c6-106">Sie haben die Möglichkeit, mehrere Pakete als Vorlagen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d34c6-106">You can designate multiple packages to use as templates.</span></span> <span data-ttu-id="d34c6-107">Sie müssen zunächst benutzerdefinierte Pakete erstellen, bevor Sie diese als Vorlagen implementieren können.</span><span class="sxs-lookup"><span data-stu-id="d34c6-107">Before you can implement custom packages as templates, you must create the packages.</span></span>  
  
 <span data-ttu-id="d34c6-108">Wenn Sie benutzerdefinierte Pakete als Vorlagen zum Erstellen von Paketen verwenden, haben die neuen Pakete denselben Namen und GUID wie die Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d34c6-108">When you create package using custom packages as templates, the new packages have the same name and GUID as the template.</span></span> <span data-ttu-id="d34c6-109">Sie sollten den Wert der `Name`-Eigenschaft aktualisieren und einen neuen GUID für die `ID`-Eigenschaft generieren, um die Pakete voneinander zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d34c6-109">To differentiate among packages you should update the value of the `Name` property and generate a new GUID for the `ID` property.</span></span> <span data-ttu-id="d34c6-110">Weitere Informationen finden Sie unter [Erstellen von Paketen in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) und [Festlegen von Paketeigenschaften](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d34c6-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) and [Set Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a><span data-ttu-id="d34c6-111">So legen Sie ein benutzerdefiniertes Paket als Paketvorlage fest</span><span class="sxs-lookup"><span data-stu-id="d34c6-111">To designate a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="d34c6-112">Suchen Sie im Dateisystem nach dem Paket, welches Sie als Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d34c6-112">In the file system, locate the package that you want to use as template.</span></span>  
  
2.  <span data-ttu-id="d34c6-113">Kopieren Sie das Paket in den Ordner DataTransformationItems.</span><span class="sxs-lookup"><span data-stu-id="d34c6-113">Copy the package to the DataTransformationItems folder.</span></span> <span data-ttu-id="d34c6-114">Dieser Ordner befindet sich standardmäßig unter C:\Programme\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span><span class="sxs-lookup"><span data-stu-id="d34c6-114">By default this folder is in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
3.  <span data-ttu-id="d34c6-115">Wiederholen Sie die Schritte 1 und 2 für jedes als Vorlage zu verwendende Paket.</span><span class="sxs-lookup"><span data-stu-id="d34c6-115">Repeat steps 1 and 2 for each package that you want to use as a template.</span></span>  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a><span data-ttu-id="d34c6-116">So verwenden Sie ein benutzerdefiniertes Paket als Paketvorlage</span><span class="sxs-lookup"><span data-stu-id="d34c6-116">To use a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="d34c6-117">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, in dem Sie ein Paket erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d34c6-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="d34c6-118">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="d34c6-118">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="d34c6-119">Klicken Sie im Dialogfeld **Neues Element hinzufügen – \<project name>** auf das Paket, das Sie als Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d34c6-119">In the **Add New Item -\<project name>** dialog box, click the package that you want to use as a template.</span></span>  
  
     <span data-ttu-id="d34c6-120">Die Vorlagenliste enthält die Standardpaketvorlage mit der Bezeichnung Neues SSIS-Paket.</span><span class="sxs-lookup"><span data-stu-id="d34c6-120">The list of templates includes the default package template named New SSIS Package.</span></span> <span data-ttu-id="d34c6-121">Das Paketsymbol identifiziert die als Paketvorlage verwendbaren Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="d34c6-121">The package icon identifies templates that can be used as package templates.</span></span>  
  
4.  <span data-ttu-id="d34c6-122">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d34c6-122">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34c6-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d34c6-123">See Also</span></span>  
 <span data-ttu-id="d34c6-124">[Erstellen von Paketen in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d34c6-124">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 <span data-ttu-id="d34c6-125">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) (Integration Services-Pakete [SSIS])</span><span class="sxs-lookup"><span data-stu-id="d34c6-125">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md)</span></span>  
  
  
