---
title: Kopie des Pakets speichern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.savecopyas.f1
helpviewer_keywords:
- Save Copy of Package dialog box
ms.assetid: 7b44c0d7-d8fa-4491-8836-0899f621d3a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f0a685d8b38299e1ba1d03c4ec8c1052cc957dbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722906"
---
# <a name="save-copy-of-package"></a><span data-ttu-id="580c8-102">Kopie des Pakets speichern</span><span class="sxs-lookup"><span data-stu-id="580c8-102">Save Copy of Package</span></span>
  <span data-ttu-id="580c8-103">Verwenden Sie das in **verfügbare Dialogfeld** Kopie des Pakets speichern [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], um eine Kopie eines [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakets aus [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] an einem anderen Speicherort zu speichern und dabei optional die Schutzebene des Pakets zu ändern.</span><span class="sxs-lookup"><span data-stu-id="580c8-103">Use the **Save Copy of Package** dialog box, available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], to save a copy of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to a different location and, optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="580c8-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="580c8-104">Options</span></span>  
 <span data-ttu-id="580c8-105">**Paketspeicherort**</span><span class="sxs-lookup"><span data-stu-id="580c8-105">**Package location**</span></span>  
 <span data-ttu-id="580c8-106">Wählen Sie den Typ des Speicherortes aus, an dem das Paket gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="580c8-106">Select the type of storage location in which to save the package copy.</span></span> <span data-ttu-id="580c8-107">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="580c8-107">The following options are available:</span></span>  
  
 <span data-ttu-id="580c8-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="580c8-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="580c8-109">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="580c8-109">**File System**</span></span>  
  
 <span data-ttu-id="580c8-110">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="580c8-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="580c8-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="580c8-111">**Server**</span></span>  
 <span data-ttu-id="580c8-112">Geben Sie einen Servernamen ein, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="580c8-112">Type a server name or select a server from the list.</span></span> <span data-ttu-id="580c8-113">Diese Option ist nur verfügbar, wenn der Speicherort **SQL Server** oder **SSIS-Paketspeicher**ist.</span><span class="sxs-lookup"><span data-stu-id="580c8-113">This option is available only if the storage location is **SQL Server** or **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="580c8-114">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="580c8-114">**Authentication**</span></span>  
 <span data-ttu-id="580c8-115">Wählen Sie die Windows-Authentifizierung oder die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="580c8-115">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="580c8-116">Diese Option ist nur verfügbar, wenn der Speicherort [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ist.</span><span class="sxs-lookup"><span data-stu-id="580c8-116">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="580c8-117">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="580c8-117">Whenever possible use Windows Authentication.</span></span>  
  
 <span data-ttu-id="580c8-118">**Authentifizierungstyp**</span><span class="sxs-lookup"><span data-stu-id="580c8-118">**Authentication type**</span></span>  
 <span data-ttu-id="580c8-119">Wählen Sie einen Authentifizierungstyp aus.</span><span class="sxs-lookup"><span data-stu-id="580c8-119">Select an authentication type.</span></span>  
  
 <span data-ttu-id="580c8-120">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="580c8-120">**User name**</span></span>  
 <span data-ttu-id="580c8-121">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, stellen Sie einen Benutzernamen bereit.</span><span class="sxs-lookup"><span data-stu-id="580c8-121">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="580c8-122">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="580c8-122">**Password**</span></span>  
 <span data-ttu-id="580c8-123">Geben Sie ein Kennwort an, falls Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="580c8-123">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="580c8-124">**Paketpfad**</span><span class="sxs-lookup"><span data-stu-id="580c8-124">**Package path**</span></span>  
 <span data-ttu-id="580c8-125">Geben Sie den Paketpfad ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , und suchen Sie den Ordner, in dem das Paket gespeichert</span><span class="sxs-lookup"><span data-stu-id="580c8-125">Type the package path, or click the browse **(...)** button and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="580c8-126">**Schutzebene**</span><span class="sxs-lookup"><span data-stu-id="580c8-126">**Protection level**</span></span>  
 <span data-ttu-id="580c8-127">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , und aktualisieren Sie im Dialogfeld **Paket Schutz Ebene** die Schutz Ebene.</span><span class="sxs-lookup"><span data-stu-id="580c8-127">Click the browse **(...)** button and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="580c8-128">Weitere Informationen finden Sie unter [Dialogfeld „Paket- und Projektschutzebene“](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="580c8-128">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580c8-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="580c8-129">See Also</span></span>  
 <span data-ttu-id="580c8-130">[Referenz zur Benutzeroberfläche des Dialog Felds Paket importieren](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="580c8-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="580c8-131">[Referenz zur Benutzeroberfläche des Dialog Felds Paket exportieren](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="580c8-131">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="580c8-132">[Pakete speichern](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="580c8-132">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="580c8-133">Importieren und Exportieren von Paketen &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="580c8-133">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
