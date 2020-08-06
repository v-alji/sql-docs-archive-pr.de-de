---
title: Referenz zur Benutzeroberfläche des Dialog Felds "Paket exportieren" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727078"
---
# <a name="export-package-dialog-box-ui-reference"></a><span data-ttu-id="9066a-102">Referenz zur Benutzeroberfläche des Dialogfelds Paket exportieren</span><span class="sxs-lookup"><span data-stu-id="9066a-102">Export Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="9066a-103">Verwenden Sie das in **verfügbare Dialogfeld** Paket exportieren [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], um ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket an einen anderen Speicherort zu exportieren und optional die Schutzebene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9066a-103">Use the **Export Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to export a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package to a different location and optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9066a-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9066a-104">Options</span></span>  
 <span data-ttu-id="9066a-105">**Paketspeicherort**</span><span class="sxs-lookup"><span data-stu-id="9066a-105">**Package location**</span></span>  
 <span data-ttu-id="9066a-106">Wählen Sie den Speichertyp aus, in den das Paket exportiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9066a-106">Select the type of storage to export the package to.</span></span> <span data-ttu-id="9066a-107">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9066a-107">The following options are available:</span></span>  
  
 <span data-ttu-id="9066a-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9066a-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="9066a-109">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="9066a-109">**File System**</span></span>  
  
 <span data-ttu-id="9066a-110">**SSIS-Paketspeicher**</span><span class="sxs-lookup"><span data-stu-id="9066a-110">**SSIS Package Storage**</span></span>  
  
 <span data-ttu-id="9066a-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="9066a-111">**Server**</span></span>  
 <span data-ttu-id="9066a-112">Geben Sie einen Servernamen ein, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="9066a-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="9066a-113">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="9066a-113">**Authentication**</span></span>  
 <span data-ttu-id="9066a-114">Wählen Sie die Windows-Authentifizierung oder die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="9066a-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="9066a-115">Diese Option ist nur verfügbar, wenn der Speicherort [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ist.</span><span class="sxs-lookup"><span data-stu-id="9066a-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9066a-116">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9066a-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="9066a-117">**Authentifizierungstyp**</span><span class="sxs-lookup"><span data-stu-id="9066a-117">**Authentication type**</span></span>  
 <span data-ttu-id="9066a-118">Wählen Sie einen Authentifizierungstyp aus.</span><span class="sxs-lookup"><span data-stu-id="9066a-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="9066a-119">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="9066a-119">**User name**</span></span>  
 <span data-ttu-id="9066a-120">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, stellen Sie einen Benutzernamen bereit.</span><span class="sxs-lookup"><span data-stu-id="9066a-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="9066a-121">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="9066a-121">**Password**</span></span>  
 <span data-ttu-id="9066a-122">Geben Sie ein Kennwort an, falls Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9066a-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="9066a-123">**Paketpfad**</span><span class="sxs-lookup"><span data-stu-id="9066a-123">**Package path**</span></span>  
 <span data-ttu-id="9066a-124">Geben Sie den Paketpfad ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um nach dem Ordner zu suchen, in dem das Paket gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9066a-124">Type the package path, or click the browse button **(...)** and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="9066a-125">**Schutzebene**</span><span class="sxs-lookup"><span data-stu-id="9066a-125">**Protection level**</span></span>  
 <span data-ttu-id="9066a-126">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , und aktualisieren Sie im Dialogfeld **Paketschutzebene** die Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="9066a-126">Click the browse button **(...)** and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="9066a-127">Weitere Informationen finden Sie unter [Dialogfeld „Paket- und Projektschutzebene“](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="9066a-127">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9066a-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9066a-128">See Also</span></span>  
 <span data-ttu-id="9066a-129">[Kopie des Pakets speichern](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="9066a-129">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="9066a-130">[Referenz zur Benutzeroberfläche des Dialog Felds Paket importieren](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9066a-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="9066a-131">[Pakete speichern](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="9066a-131">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="9066a-132">Importieren und Exportieren von Paketen &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="9066a-132">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
