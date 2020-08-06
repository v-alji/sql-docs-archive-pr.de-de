---
title: Datenbank erstellen (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createdatabase.f1
ms.assetid: 56a8a79f-086c-4bdc-8888-0045bb4b0cbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 617b3fe10a17ae2d8659b51e85cdb3fed4470506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619936"
---
# <a name="create-database-sql-server-import-and-export-wizard"></a><span data-ttu-id="343ee-102">Datenbank erstellen (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="343ee-102">Create Database (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="343ee-103">Verwenden Sie die Seite **Datenbank erstellen** , um eine neue Datenbank für eine Zieldatei zu definieren.</span><span class="sxs-lookup"><span data-stu-id="343ee-103">Use the **Create Database** page to define a new database for a destination file.</span></span>  
  
 <span data-ttu-id="343ee-104">Diese Seite stellt eine Teilmenge der verfügbaren Optionen zum Erstellen einer neuen Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="343ee-104">This page offers a subset of the available options for creating a new database.</span></span> <span data-ttu-id="343ee-105">Verwenden Sie, um alle Optionen anzuzeigen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="343ee-105">To view all the options, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="343ee-106">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="343ee-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="343ee-107">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="343ee-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="343ee-108">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="343ee-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="343ee-109">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="343ee-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="343ee-110">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="343ee-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="343ee-111">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="343ee-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="343ee-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="343ee-112">Options</span></span>  
 <span data-ttu-id="343ee-113">**Name**</span><span class="sxs-lookup"><span data-stu-id="343ee-113">**Name**</span></span>  
 <span data-ttu-id="343ee-114">Geben Sie einen eindeutigen Namen für die SQL Server-Zieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="343ee-114">Provide a unique name for the destination SQL Server database.</span></span> <span data-ttu-id="343ee-115">Beachten Sie beim Benennen dieser Datenbank die entsprechenden Konventionen von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="343ee-115">Make sure that you follow SQL Server conventions when you name this database.</span></span>  
  
 <span data-ttu-id="343ee-116">**Datendateiname**</span><span class="sxs-lookup"><span data-stu-id="343ee-116">**Data file name**</span></span>  
 <span data-ttu-id="343ee-117">Zeigen Sie den Namen der Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="343ee-117">View the name of the data file.</span></span> <span data-ttu-id="343ee-118">Dieser wird aus dem zu einem früheren Zeitpunkt angegebenen Datenbanknamen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="343ee-118">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="343ee-119">**Protokoll Dateiname**</span><span class="sxs-lookup"><span data-stu-id="343ee-119">**Log file name**</span></span>  
 <span data-ttu-id="343ee-120">Zeigen Sie den Namen der Protokolldatei an.</span><span class="sxs-lookup"><span data-stu-id="343ee-120">View the name of the log file.</span></span> <span data-ttu-id="343ee-121">Dieser wird aus dem zu einem früheren Zeitpunkt angegebenen Datenbanknamen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="343ee-121">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="343ee-122">**Anfangsgröße (Datendatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-122">**Initial size (data file)**</span></span>  
 <span data-ttu-id="343ee-123">Geben Sie die Anzahl der Megabytes für die Anfangsgröße der Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="343ee-123">Specify the number of megabytes for the initial size of the data file.</span></span>  
  
 <span data-ttu-id="343ee-124">**Keine Vergrößerung zulässig (Datendatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-124">**No growth allowed (data file)**</span></span>  
 <span data-ttu-id="343ee-125">Geben Sie an, ob die Datendatei die Größe der angegebenen Anfangsgröße übersteigen kann.</span><span class="sxs-lookup"><span data-stu-id="343ee-125">Indicate whether the data file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="343ee-126">**Vergrößerung nach Prozent (Datendatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-126">**Grow by percentage (data file)**</span></span>  
 <span data-ttu-id="343ee-127">Geben Sie einen Prozentsatz an, um den die Datendatei wachsen kann.</span><span class="sxs-lookup"><span data-stu-id="343ee-127">Specify a percentage by which the data file can grow.</span></span>  
  
 <span data-ttu-id="343ee-128">**Vergrößerung nach Größe (Datendatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-128">**Grow by size (data file)**</span></span>  
 <span data-ttu-id="343ee-129">Geben Sie die Anzahl der Megabytes an, um die die Datendatei wachsen kann.</span><span class="sxs-lookup"><span data-stu-id="343ee-129">Specify a number of megabytes by which the data file can grow.</span></span>  
  
 <span data-ttu-id="343ee-130">**Anfangsgröße (Protokolldatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-130">**Initial size (log file)**</span></span>  
 <span data-ttu-id="343ee-131">Geben Sie die Anzahl der Megabytes für die Anfangsgröße der Protokolldatei an.</span><span class="sxs-lookup"><span data-stu-id="343ee-131">Specify the number of megabytes for the initial size of the log file.</span></span>  
  
 <span data-ttu-id="343ee-132">**Keine Vergrößerung zulässig (Protokolldatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-132">**No growth allowed (log file)**</span></span>  
 <span data-ttu-id="343ee-133">Geben Sie an, ob die Protokolldatei die Größe der angegebenen Anfangsgröße übersteigen kann.</span><span class="sxs-lookup"><span data-stu-id="343ee-133">Indicate whether the log file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="343ee-134">**Vergrößerung nach Prozent (Protokolldatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-134">**Grow by percentage (log file)**</span></span>  
 <span data-ttu-id="343ee-135">Geben Sie einen Prozentsatz an, um den die Protokolldatei wachsen kann.</span><span class="sxs-lookup"><span data-stu-id="343ee-135">Specify a percentage by which the log file can grow.</span></span>  
  
 <span data-ttu-id="343ee-136">**Vergrößerung nach Größe (Protokolldatei)**</span><span class="sxs-lookup"><span data-stu-id="343ee-136">**Grow by size (log file)**</span></span>  
 <span data-ttu-id="343ee-137">Geben Sie die Anzahl der Megabytes an, um die die Protokolldatei wachsen kann.</span><span class="sxs-lookup"><span data-stu-id="343ee-137">Specify a number of megabytes by which the log file can grow.</span></span>  
  
  
