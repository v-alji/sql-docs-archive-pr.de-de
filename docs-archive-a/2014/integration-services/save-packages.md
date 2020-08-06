---
title: Speichern von Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 17c1de2c-637f-45c2-a148-79294bae0af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 102e2c3eab001c230722bf3485d6ea9731aa99a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722905"
---
# <a name="save-packages"></a><span data-ttu-id="6ac5a-102">Speichern von Paketen</span><span class="sxs-lookup"><span data-stu-id="6ac5a-102">Save Packages</span></span>
  <span data-ttu-id="6ac5a-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] erstellen Sie Pakete mithilfe des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers und speichern diese als XML-Dateien (DTSX-Dateien) im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] you build packages by using [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and save the packages to the file system as XML files (.dtsx files).</span></span> <span data-ttu-id="6ac5a-104">Sie können auch Kopien der Paket-XML-Datei in der msdb-Datenbank in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] oder im Paketspeicher speichern.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-104">You can also save copies of the package XML file to the msdb database in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="6ac5a-105">Der Paketspeicher stellt die Ordner im Dateisystempfad dar, die von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-105">The package store represents the folders in the file system location that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
 <span data-ttu-id="6ac5a-106">Wenn Sie ein Paket im Dateisystem speichern, können Sie es später mit [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nach [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bzw. in den Paketspeicher importieren.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-106">If you save a package to the file system, you can later use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service to import the package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="6ac5a-107">Weitere Informationen finden Sie unter [Import und Export von Paketen &#40;SSIS-Dienst&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="6ac5a-107">For more information, see [Import and Export Packages &#40;SSIS Service&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span></span>  
  
 <span data-ttu-id="6ac5a-108">Darüber hinaus können Sie mit dem Eingabeaufforderungs-Hilfsprogramm **dtutil**ein Paket zwischen dem Dateisystem und msdb kopieren.</span><span class="sxs-lookup"><span data-stu-id="6ac5a-108">You can also use a command prompt utility, **dtutil**, to copy a package between the file system and msdb.</span></span> <span data-ttu-id="6ac5a-109">Weitere Informationen finden Sie unter [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="6ac5a-109">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-save-a-package"></a><span data-ttu-id="6ac5a-110">So speichern Sie ein Paket</span><span class="sxs-lookup"><span data-stu-id="6ac5a-110">To save a package</span></span>  
  
-   [<span data-ttu-id="6ac5a-111">Speichern eines Pakets im Datei System</span><span class="sxs-lookup"><span data-stu-id="6ac5a-111">Save a Package to the File System</span></span>](../../2014/integration-services/save-a-package-to-the-file-system.md)  
  
-   [<span data-ttu-id="6ac5a-112">Speichern einer Kopie eines Pakets</span><span class="sxs-lookup"><span data-stu-id="6ac5a-112">Save a Copy of a Package</span></span>](../../2014/integration-services/save-a-copy-of-a-package.md)  
  
  
