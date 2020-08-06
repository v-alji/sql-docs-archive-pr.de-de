---
title: Paketeigenschaften (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b386bf4e75ff784cd8d4a96363515786d242d2a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616641"
---
# <a name="package-properties-dialog-box"></a><span data-ttu-id="7c256-102">Paketeigenschaften (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="7c256-102">Package Properties Dialog Box</span></span>
  <span data-ttu-id="7c256-103">Im Dialogfeld **Paketeigenschaften** können Sie Eigenschaften für Pakete anzeigen, die auf dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7c256-103">Use the **Package Properties** dialog box to view properties for packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="7c256-104">Weitere Informationen finden Sie unter [Integration Services-Server &#40;SSIS&#41;](integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7c256-104">For more information, see [Integration Services &#40;SSIS&#41; Server](integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="7c256-105">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="7c256-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="7c256-106">Öffnen des Dialogfelds "Paketeigenschaften"</span><span class="sxs-lookup"><span data-stu-id="7c256-106">Open the Package Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="7c256-107">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="7c256-107">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-package-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="7c256-108">Öffnen des Dialogfelds "Paketeigenschaften"</span><span class="sxs-lookup"><span data-stu-id="7c256-108">Open the Package Properties dialog box</span></span>  
  
1.  <span data-ttu-id="7c256-109">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="7c256-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="7c256-110">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Instanz her, die die SSISDB-Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="7c256-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="7c256-111">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c256-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="7c256-112">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="7c256-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="7c256-113">Erweitern Sie den Ordner mit dem Paket, für das Sie die Eigenschaften anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7c256-113">Expand the folder that contains the package you want to view properties for.</span></span>  
  
5.  <span data-ttu-id="7c256-114">Klicken Sie mit der rechten Maustaste auf das Paket, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="7c256-114">Right-click the package, and then select **Properties**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="7c256-115">Konfigurieren der Optionen</span><span class="sxs-lookup"><span data-stu-id="7c256-115">Configure the Options</span></span>  
 <span data-ttu-id="7c256-116">Auf der Seite **Allgemein** können Sie die Eigenschaften des ausgewählten Pakets anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c256-116">Use the **General** page to view the properties of the selected package.</span></span>  
  
 <span data-ttu-id="7c256-117">Alle Eigenschaften auf der Seite **Allgemein** sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7c256-117">All properties on the **General** page are read-only.</span></span>  
  
 <span data-ttu-id="7c256-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="7c256-118">**Name**</span></span>  
 <span data-ttu-id="7c256-119">Zeigt den Namen des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="7c256-119">Displays the name of the package.</span></span>  
  
 <span data-ttu-id="7c256-120">**Bezeichner**</span><span class="sxs-lookup"><span data-stu-id="7c256-120">**Identifier**</span></span>  
 <span data-ttu-id="7c256-121">Listet die ID des Pakets auf.</span><span class="sxs-lookup"><span data-stu-id="7c256-121">Lists the package ID.</span></span>  
  
 <span data-ttu-id="7c256-122">**Einstiegspunkt**</span><span class="sxs-lookup"><span data-stu-id="7c256-122">**Entry Point**</span></span>  
 <span data-ttu-id="7c256-123">Der Wert `True` gibt an, dass das Paket direkt gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="7c256-123">The value of `True` indicates that the package is started directly.</span></span> <span data-ttu-id="7c256-124">Der Wert `False` gibt an, dass das Paket von einem anderen Paket mit dem Task "Paket ausführen" gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="7c256-124">The value of `False` indicates that the package is started by another package using the Execute Package task.</span></span> <span data-ttu-id="7c256-125">Standardwert: `True`.</span><span class="sxs-lookup"><span data-stu-id="7c256-125">The default value is `True`.</span></span>  
  
 <span data-ttu-id="7c256-126">Sie können diese Eigenschaft in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] für das übergeordnete Paket und die untergeordneten Pakete festlegen, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket und anschließend auf **Einstiegspunktpaket**klicken.</span><span class="sxs-lookup"><span data-stu-id="7c256-126">You set this property in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for both the parent package and the child packages by right-clicking the package in Solution Explorer and then clicking **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="7c256-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7c256-127">**Description**</span></span>  
 <span data-ttu-id="7c256-128">Zeigt die optionale Beschreibung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="7c256-128">Displays the optional description of the package.</span></span>  
  
  
