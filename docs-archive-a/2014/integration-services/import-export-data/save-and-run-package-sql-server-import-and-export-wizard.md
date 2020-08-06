---
title: Paket speichern und ausführen (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.saveschedule.f1
ms.assetid: b582c462-3d7a-4a4c-a2a2-2c79fedab75a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a23f69bf66ca3355f1e1c62cc42d51e4aea3da5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619923"
---
# <a name="save-and-execute-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="984e5-102">Paket speichern und ausführen (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="984e5-102">Save and Execute Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="984e5-103">Verwenden Sie das Dialogfeld **Paket speichern und ausführen** , um das Paket sofort auszuführen, es zur späteren Ausführung zu speichern oder beides.</span><span class="sxs-lookup"><span data-stu-id="984e5-103">Use the **Save and Execute Package** dialog box to run the package immediately, save it to run later, or both.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-104"> Wenn Sie ein Paket vor dem Abschluss der Ausführung beenden, wird das Paket nicht gespeichert, auch wenn Sie das Kontrollkästchen **Speichern** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="984e5-104">If you stop a package before it finishes running, the package is not saved, even if you selected the **Save** check box.</span></span>  
  
 <span data-ttu-id="984e5-105">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="984e5-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="984e5-106">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="984e5-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="984e5-107">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="984e5-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="984e5-108">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="984e5-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="984e5-109">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="984e5-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="984e5-110">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="984e5-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="984e5-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="984e5-111">Options</span></span>  
 <span data-ttu-id="984e5-112">**Sofort ausführen**</span><span class="sxs-lookup"><span data-stu-id="984e5-112">**Execute immediately**</span></span>  
 <span data-ttu-id="984e5-113">Wählen Sie diese Option aus, um das Paket sofort auszuführen.</span><span class="sxs-lookup"><span data-stu-id="984e5-113">Select this option to run the package immediately.</span></span>  
  
 <span data-ttu-id="984e5-114">**SSIS-Paket speichern**</span><span class="sxs-lookup"><span data-stu-id="984e5-114">**Save SSIS Package**</span></span>  
 <span data-ttu-id="984e5-115">Speichern Sie das Paket zur späteren Ausführung, mit der Option, es sofort auszuführen.</span><span class="sxs-lookup"><span data-stu-id="984e5-115">Save the package to run later, with the option to run it immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] ist die Option zum Speichern des vom Assistenten erstellten Pakets nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="984e5-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="984e5-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="984e5-117">**SQL Server**</span></span>  
 <span data-ttu-id="984e5-118">Wählen Sie diese Option aus, um das Paket in der Datenbank zu speichern [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` .</span><span class="sxs-lookup"><span data-stu-id="984e5-118">Select this option to save the package to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-119">Diese Option ist nur verfügbar, wenn Sie die Option **SSIS-Paket speichern** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="984e5-119">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="984e5-120">**Dateisystem**</span><span class="sxs-lookup"><span data-stu-id="984e5-120">**File system**</span></span>  
 <span data-ttu-id="984e5-121">Wählen Sie diese Option aus, um das Paket als Datei mit der Erweiterung \*.dtsx zu speichern.</span><span class="sxs-lookup"><span data-stu-id="984e5-121">Select this option to save the package as a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-122">Diese Option ist nur verfügbar, wenn Sie die Option **SSIS-Paket speichern** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="984e5-122">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="984e5-123">**Paketschutzebene**</span><span class="sxs-lookup"><span data-stu-id="984e5-123">**Package protection level**</span></span>  
 <span data-ttu-id="984e5-124">Wählen Sie eine Schutzebene aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="984e5-124">Select a protection level from the list.</span></span>  
  
 <span data-ttu-id="984e5-125">Die Schutzebene bestimmt die Methode, das Kennwort oder den Benutzerschlüssel und den Bereich des Paketschutzes.</span><span class="sxs-lookup"><span data-stu-id="984e5-125">The protection level determines the protection method, the password or user key, and the scope of package protection.</span></span> <span data-ttu-id="984e5-126">Der Schutz kann alle Daten oder nur vertrauliche Daten einschließen.</span><span class="sxs-lookup"><span data-stu-id="984e5-126">Protection can include all data or sensitive data only.</span></span> <span data-ttu-id="984e5-127">Informationen zu den Anforderungen und Optionen für die Paket Sicherheit finden Sie unter [Access Control für sensible Daten in Paketen](../security/access-control-for-sensitive-data-in-packages.md) und [Sicherheitsübersicht &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="984e5-127">To understand the requirements and options for package security, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [Security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-128">Diese Option ist nur verfügbar, wenn Sie die Option **SSIS-Paket speichern** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="984e5-128">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="984e5-129">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="984e5-129">**Password**</span></span>  
 <span data-ttu-id="984e5-130">Geben Sie ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="984e5-130">Type a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-131">Diese Option ist nur verfügbar, wenn Sie die Option **Paket Schutz Ebene** auf entweder vertrauliche **Daten mit Kennwort verschlüsseln** oder **alle Daten mit einem Kennwort verschlüsseln**festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="984e5-131">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
 <span data-ttu-id="984e5-132">**Kennwort erneut eingeben**</span><span class="sxs-lookup"><span data-stu-id="984e5-132">**Retype password**</span></span>  
 <span data-ttu-id="984e5-133">Geben Sie das Kennwort erneut ein.</span><span class="sxs-lookup"><span data-stu-id="984e5-133">Type the password again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="984e5-134">Diese Option ist nur verfügbar, wenn Sie die Option **Paket Schutz Ebene** auf entweder vertrauliche **Daten mit Kennwort verschlüsseln** oder **alle Daten mit einem Kennwort verschlüsseln**festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="984e5-134">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="984e5-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="984e5-135">See Also</span></span>  
 <span data-ttu-id="984e5-136">[Ausführung von Projekten und Paketen](../packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="984e5-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="984e5-137">Speichern von Paketen</span><span class="sxs-lookup"><span data-stu-id="984e5-137">Save Packages</span></span>](../save-packages.md)  
  
  
