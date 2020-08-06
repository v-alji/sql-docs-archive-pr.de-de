---
title: Speichern von Paketen (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.savedtspackage.f1
ms.assetid: 7bf8ac6a-5599-43ab-bf5c-e072c11b85a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d4e582558a1f86b18d935fcc6235ba5839faa031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619919"
---
# <a name="save-ssis-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="827ad-102">SSIS-Paket speichern (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="827ad-102">Save SSIS Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="827ad-103">Verwenden Sie die Seite **SSIS-Paket speichern** , um ein Integration Services-Paket () zu benennen, zu beschreiben und [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssIS](../../includes/ssis-md.md)] in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` Datenbank oder in einer Datei mit der Erweiterung. DTX zu speichern.</span><span class="sxs-lookup"><span data-stu-id="827ad-103">Use the **Save SSIS Package** page to name, describe, and save a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database or to a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="827ad-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] ist die Option zum Speichern des vom Assistenten erstellten Pakets nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="827ad-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="827ad-105">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="827ad-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="827ad-106">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="827ad-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="827ad-107">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="827ad-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="827ad-108">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="827ad-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="827ad-109">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="827ad-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="827ad-110">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="827ad-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="827ad-111">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="827ad-111">Static Options</span></span>  
 <span data-ttu-id="827ad-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="827ad-112">**Name**</span></span>  
 <span data-ttu-id="827ad-113">Geben Sie einen eindeutigen Namen für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="827ad-113">Provide a unique name for the package.</span></span>  
  
 <span data-ttu-id="827ad-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="827ad-114">**Description**</span></span>  
 <span data-ttu-id="827ad-115">Geben Sie eine Beschreibung für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="827ad-115">Provide a description for the package.</span></span> <span data-ttu-id="827ad-116">Die bewährte Methode ist hierbei, das Paket zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und leichter zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="827ad-116">As a best practice, describe the package in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="827ad-117">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="827ad-117">**Target**</span></span>  
 <span data-ttu-id="827ad-118">Zeigen Sie das Ziel an ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder Datei), das zuvor für die Zieldatei angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="827ad-118">View the target ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or file) that was previously specified for the destination file.</span></span>  
  
## <a name="target-dynamic-options"></a><span data-ttu-id="827ad-119">Dynamische Ziel Optionen</span><span class="sxs-lookup"><span data-stu-id="827ad-119">Target Dynamic Options</span></span>  
  
### <a name="target--sql-server"></a><span data-ttu-id="827ad-120">Ziel = SQL Server</span><span class="sxs-lookup"><span data-stu-id="827ad-120">Target = SQL Server</span></span>  
 <span data-ttu-id="827ad-121">**Servername**</span><span class="sxs-lookup"><span data-stu-id="827ad-121">**Server name**</span></span>  
 <span data-ttu-id="827ad-122">Wenn Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel ausgewählt haben, geben Sie den Namen des Zielservers ein, oder wählen Sie einen aus.</span><span class="sxs-lookup"><span data-stu-id="827ad-122">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, type or select the destination server name.</span></span>  
  
 <span data-ttu-id="827ad-123">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="827ad-123">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="827ad-124">Wenn Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel ausgewählt haben, gibt diese Option an, ob die Verbindung mit dem Server mithilfe der integrierten Windows-Authentifizierung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="827ad-124">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using Windows Integrated Authentication.</span></span> <span data-ttu-id="827ad-125">Dies ist die bevorzugte Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="827ad-125">This is the preferred authentication method.</span></span>  
  
 <span data-ttu-id="827ad-126">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="827ad-126">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="827ad-127">Wenn Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel ausgewählt haben, gibt diese Option an, ob die Verbindung mit dem Server mithilfe der SQL Server-Authentifizierung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="827ad-127">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="827ad-128">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="827ad-128">**User name**</span></span>  
 <span data-ttu-id="827ad-129">Wenn Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel ausgewählt und die SQL-Authentifizierung angegeben haben, geben Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="827ad-129">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="827ad-130">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="827ad-130">**Password**</span></span>  
 <span data-ttu-id="827ad-131">Wenn Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ziel ausgewählt und die SQL-Authentifizierung angegeben haben, geben Sie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="827ad-131">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] password.</span></span>  
  
### <a name="target--file-system"></a><span data-ttu-id="827ad-132">Ziel = Dateisystem</span><span class="sxs-lookup"><span data-stu-id="827ad-132">Target = File System</span></span>  
 <span data-ttu-id="827ad-133">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="827ad-133">**File name**</span></span>  
 <span data-ttu-id="827ad-134">Wenn Sie ein Dateiziel ausgewählt haben, geben Sie den Pfad für die Zieldatei ein, oder verwenden Sie die Schaltfläche **Durchsuchen** .</span><span class="sxs-lookup"><span data-stu-id="827ad-134">When you have selected a file destination, type the path for the destination file, or use the **Browse** button.</span></span>  
  
 <span data-ttu-id="827ad-135">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="827ad-135">**Browse**</span></span>  
 <span data-ttu-id="827ad-136">Wenn Sie ein Dateiziel ausgewählt haben, navigieren Sie zur Zieldatei, indem Sie das Dialogfeld **Paket speichern** verwenden.</span><span class="sxs-lookup"><span data-stu-id="827ad-136">When you have selected a file destination, browse to the destination file by using the **Save Package** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827ad-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="827ad-137">See Also</span></span>  
 [<span data-ttu-id="827ad-138">Speichern von Paketen</span><span class="sxs-lookup"><span data-stu-id="827ad-138">Save Packages</span></span>](../save-packages.md)  
  
  
