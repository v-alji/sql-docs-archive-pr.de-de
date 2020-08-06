---
title: Referenz zur Benutzeroberfläche des Dialog Felds "Paket importieren" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.importpackage.f1
helpviewer_keywords:
- Import Package dialog box
ms.assetid: 0e5fb127-c7ff-4dfa-b90e-d9bcf0ce763b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff20bf8eb221778465a26944280d53b6aab07601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618194"
---
# <a name="import-package-dialog-box-ui-reference"></a><span data-ttu-id="259cd-102">Referenz zur Benutzeroberfläche für Dialogfeld "Paket importieren"</span><span class="sxs-lookup"><span data-stu-id="259cd-102">Import Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="259cd-103">Verwenden Sie das in **verfügbare Dialogfeld** Paket importieren [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], um ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket zu importieren und die Schutzebene des Pakets festzulegen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="259cd-103">Use the **Import Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to import a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and to set or modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="259cd-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="259cd-104">Options</span></span>  
 <span data-ttu-id="259cd-105">**Paketspeicherort**</span><span class="sxs-lookup"><span data-stu-id="259cd-105">**Package location**</span></span>  
 <span data-ttu-id="259cd-106">Wählen Sie den Typ des Speicherortes, an den das Paket importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="259cd-106">Select the type of storage location to import the package to.</span></span> <span data-ttu-id="259cd-107">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="259cd-107">The following options are available:</span></span>  
  
 <span data-ttu-id="259cd-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="259cd-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="259cd-109">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="259cd-109">**File System**</span></span>  
  
 <span data-ttu-id="259cd-110">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="259cd-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="259cd-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="259cd-111">**Server**</span></span>  
 <span data-ttu-id="259cd-112">Geben Sie einen Servernamen ein, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="259cd-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="259cd-113">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="259cd-113">**Authentication**</span></span>  
 <span data-ttu-id="259cd-114">Wählen Sie die Windows-Authentifizierung oder die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="259cd-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="259cd-115">Diese Option ist nur verfügbar, wenn der Speicherort [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ist.</span><span class="sxs-lookup"><span data-stu-id="259cd-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="259cd-116">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="259cd-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="259cd-117">**Authentifizierungstyp**</span><span class="sxs-lookup"><span data-stu-id="259cd-117">**Authentication type**</span></span>  
 <span data-ttu-id="259cd-118">Wählen Sie einen Authentifizierungstyp aus.</span><span class="sxs-lookup"><span data-stu-id="259cd-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="259cd-119">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="259cd-119">**User name**</span></span>  
 <span data-ttu-id="259cd-120">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, stellen Sie einen Benutzernamen bereit.</span><span class="sxs-lookup"><span data-stu-id="259cd-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="259cd-121">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="259cd-121">**Password**</span></span>  
 <span data-ttu-id="259cd-122">Geben Sie ein Kennwort an, falls Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="259cd-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="259cd-123">**Paketpfad**</span><span class="sxs-lookup"><span data-stu-id="259cd-123">**Package path**</span></span>  
 <span data-ttu-id="259cd-124">Geben Sie den Paketpfad ein, oder klicken Sie auf die Schaltfläche „Durchsuchen“ **(…)** , und suchen Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="259cd-124">Type the package path, or click the browse button **(...)** and locate the package.</span></span>  
  
 <span data-ttu-id="259cd-125">**Paketname**</span><span class="sxs-lookup"><span data-stu-id="259cd-125">**Package name**</span></span>  
 <span data-ttu-id="259cd-126">Sie können das Paket auch umbenennen.</span><span class="sxs-lookup"><span data-stu-id="259cd-126">Optionally, rename the package.</span></span> <span data-ttu-id="259cd-127">Der Standardname ist der Name des zu importierenden Pakets.</span><span class="sxs-lookup"><span data-stu-id="259cd-127">The default name is the name of the package to import.</span></span>  
  
 <span data-ttu-id="259cd-128">**Schutzebene**</span><span class="sxs-lookup"><span data-stu-id="259cd-128">**Protection level**</span></span>  
 <span data-ttu-id="259cd-129">Klicken Sie auf die Schaltfläche „Durchsuchen“ **(…)** , und aktualisieren Sie im Dialogfeld **Paketschutzebene** die Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="259cd-129">Click the browse button **(...)** and, in the **Package Protection Level** dialog box, update the protection level.</span></span> <span data-ttu-id="259cd-130">Weitere Informationen finden Sie unter [Dialogfeld „Paket- und Projektschutzebene“](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="259cd-130">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259cd-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="259cd-131">See Also</span></span>  
 <span data-ttu-id="259cd-132">[Kopie des Pakets speichern](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="259cd-132">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="259cd-133">[Referenz zur Benutzeroberfläche des Dialog Felds Paket exportieren](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="259cd-133">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="259cd-134">[Pakete speichern](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="259cd-134">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="259cd-135">Importieren und Exportieren von Paketen &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="259cd-135">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
