---
title: Kopieren eines Pakets in SQL Server Data Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], copying
- copying packages
- regenerating package GUID
- updating package properties
ms.assetid: 03edc659-e76d-48c0-a749-5f1899b6b507
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bd6ed4dd66ee4755181f5df6f3c1b5466b3f26b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618837"
---
# <a name="copy-a-package-in-sql-server-data-tools"></a><span data-ttu-id="ab304-102">Kopieren eines Pakets in SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="ab304-102">Copy a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="ab304-103">In diesem Thema wird beschrieben, wie Sie ein neues [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Paket durch Kopieren eines vorhandenen Pakets erstellen und wie Sie die Eigenschaften `Name` und `GUID` des neuen Pakets aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ab304-103">This topic describes how to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package by copying an existing package, and how to update the `Name` and `GUID` properties of the new package.</span></span>  
  
### <a name="to-copy-a-package"></a><span data-ttu-id="ab304-104">So kopieren Sie ein Paket</span><span class="sxs-lookup"><span data-stu-id="ab304-104">To copy a package</span></span>  
  
1.  <span data-ttu-id="ab304-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, das Sie kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ab304-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to copy.</span></span>  
  
2.  <span data-ttu-id="ab304-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket.</span><span class="sxs-lookup"><span data-stu-id="ab304-106">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="ab304-107">Stellen Sie entweder sicher, dass das zu kopierende Paket im Projektmappen-Explorer ausgewählt ist oder dass die Registerkarte im SSIS-Designer, in dem das Paket enthalten ist, aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ab304-107">Verify either the package to copy is selected in Solution Explorer or the tab in SSIS Designer that contains the package is the active tab</span></span>  
  
4.  <span data-ttu-id="ab304-108">Zeigen Sie im Menü **Datei** auf **Speichern \<package name> unter**.</span><span class="sxs-lookup"><span data-stu-id="ab304-108">On the **File** menu, click **Save \<package name> As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab304-109">Das Paket muss im SSIS-Designer geöffnet sein, bevor im Menü **Datei** die Option **Speichern unter** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ab304-109">The package must be opened in SSIS Designer before the **Save As** option appears on the **File** menu.</span></span>  
  
5.  <span data-ttu-id="ab304-110">Suchen Sie optional nach einem anderen Ordner.</span><span class="sxs-lookup"><span data-stu-id="ab304-110">Optionally, browse to a different folder.</span></span>  
  
6.  <span data-ttu-id="ab304-111">Aktualisieren Sie den Namen der Paketdatei.</span><span class="sxs-lookup"><span data-stu-id="ab304-111">Update the name of the package file.</span></span> <span data-ttu-id="ab304-112">Stellen Sie sicher, dass die Dateierweiterung DTSX beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ab304-112">Make sure that you retain the .dtsx file extension.</span></span>  
  
7.  <span data-ttu-id="ab304-113">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ab304-113">Click **Save**.</span></span>  
  
8.  <span data-ttu-id="ab304-114">Wählen Sie an der Eingabeaufforderung aus, ob der Name des Paketobjekts zur Übereinstimmung mit dem Dateinamen aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab304-114">At the prompt, choose whether to update the name of the package object to match the file name.</span></span> <span data-ttu-id="ab304-115">Wenn Sie auf **Ja**klicken, `Name` wird die-Eigenschaft des Pakets aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ab304-115">If you click **Yes**, the `Name` property of the package is updated.</span></span> <span data-ttu-id="ab304-116">Das neue Paket wird dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt hinzugefügt und im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ab304-116">The new package is added to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
9. <span data-ttu-id="ab304-117">Klicken Sie optional in den Hintergrund der Registerkarte **Ablaufsteuerung** , und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ab304-117">Optionally, click in the background of the **Control Flow** tab, and the click **Properties**.</span></span>  
  
10. <span data-ttu-id="ab304-118">Klicken Sie im Eigenschaftenfenster auf den Wert der ID-Eigenschaft, und klicken Sie anschließend in der Dropdownliste auf **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="ab304-118">In the Properties window, click the value of the ID property, and then in the drop-down list click **\<Generate New ID>**.</span></span>  
  
11. <span data-ttu-id="ab304-119">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das neue Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ab304-119">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab304-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab304-120">See Also</span></span>  
 <span data-ttu-id="ab304-121">[Speichern einer Kopie eines Pakets](../../2014/integration-services/save-a-copy-of-a-package.md) </span><span class="sxs-lookup"><span data-stu-id="ab304-121">[Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md) </span></span>  
 <span data-ttu-id="ab304-122">[Erstellen von Paketen in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ab304-122">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 <span data-ttu-id="ab304-123">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) (Integration Services-Pakete [SSIS])</span><span class="sxs-lookup"><span data-stu-id="ab304-123">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md)</span></span>  
  
  
