---
title: Flatfileziel konfigurieren (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619940"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="029e8-102">Flatfileziel konfigurieren (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="029e8-102">Configure Flat File Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="029e8-103">Verwenden Sie die Seite **Flatfileziel konfigurieren** , um Formatierungsoptionen für die Zielflatfile anzugeben und die Vorschau der Ergebnisse anzuzeigen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="029e8-103">Use the **Configure Flat File Destination** page to specify formatting options for the destination flat file, and to preview results before continuing.</span></span>  
  
 <span data-ttu-id="029e8-104">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="029e8-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="029e8-105">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="029e8-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="029e8-106">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="029e8-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="029e8-107">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="029e8-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="029e8-108">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="029e8-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="029e8-109">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="029e8-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="029e8-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="029e8-110">Options</span></span>  
 <span data-ttu-id="029e8-111">**Quellflatfile**</span><span class="sxs-lookup"><span data-stu-id="029e8-111">**Source flat file**</span></span>  
 <span data-ttu-id="029e8-112">Der Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="029e8-112">The name of the destination file.</span></span>  
  
 <span data-ttu-id="029e8-113">**Zeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="029e8-113">**Row delimiter**</span></span>  
 <span data-ttu-id="029e8-114">Wählen Sie ein Trennzeichen für Zeilen aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="029e8-114">Select from the list of delimiters for rows.</span></span>  
  
|<span data-ttu-id="029e8-115">Wert</span><span class="sxs-lookup"><span data-stu-id="029e8-115">Value</span></span>|<span data-ttu-id="029e8-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="029e8-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="029e8-117">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="029e8-117">**{CR}{LF}**</span></span>|<span data-ttu-id="029e8-118">Als Trennzeichen für Zeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="029e8-118">The row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="029e8-119">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="029e8-119">**{CR}**</span></span>|<span data-ttu-id="029e8-120">Als Trennzeichen für Zeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="029e8-120">The row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="029e8-121">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="029e8-121">**{LF}**</span></span>|<span data-ttu-id="029e8-122">Als Trennzeichen für Zeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="029e8-122">The row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="029e8-123">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="029e8-123">**Semicolon {;}**</span></span>|<span data-ttu-id="029e8-124">Als Trennzeichen für Zeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="029e8-124">The row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="029e8-125">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="029e8-125">**Colon {:}**</span></span>|<span data-ttu-id="029e8-126">Als Trennzeichen für Zeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="029e8-126">The row is delimited by a colon.</span></span>|  
|<span data-ttu-id="029e8-127">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="029e8-127">**Comma {,}**</span></span>|<span data-ttu-id="029e8-128">Als Trennzeichen für Zeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="029e8-128">The row is delimited by a comma.</span></span>|  
|<span data-ttu-id="029e8-129">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="029e8-129">**Tab {t}**</span></span>|<span data-ttu-id="029e8-130">Als Trennzeichen für Zeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="029e8-130">The row is delimited by a tab.</span></span>|  
|<span data-ttu-id="029e8-131">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="029e8-131">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="029e8-132">Als Trennzeichen für Zeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="029e8-132">The row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="029e8-133">**Spaltentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="029e8-133">**Column delimiter**</span></span>  
 <span data-ttu-id="029e8-134">Wählen Sie ein Trennzeichen für Spalten aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="029e8-134">Select from the list of delimiters for columns.</span></span>  
  
|<span data-ttu-id="029e8-135">Wert</span><span class="sxs-lookup"><span data-stu-id="029e8-135">Value</span></span>|<span data-ttu-id="029e8-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="029e8-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="029e8-137">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="029e8-137">**{CR}{LF}**</span></span>|<span data-ttu-id="029e8-138">Die Spalten werden durch eine Kombination aus Wagen Rücklauf-Zeilenvorschub getrennt.</span><span class="sxs-lookup"><span data-stu-id="029e8-138">The columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="029e8-139">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="029e8-139">**{CR}**</span></span>|<span data-ttu-id="029e8-140">Als Trennzeichen für Spalten dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="029e8-140">The columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="029e8-141">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="029e8-141">**{LF}**</span></span>|<span data-ttu-id="029e8-142">Als Trennzeichen für Spalten dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="029e8-142">The columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="029e8-143">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="029e8-143">**Semicolon {;}**</span></span>|<span data-ttu-id="029e8-144">Als Trennzeichen für Spalten dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="029e8-144">The columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="029e8-145">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="029e8-145">**Colon {:}**</span></span>|<span data-ttu-id="029e8-146">Als Trennzeichen für Spalten dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="029e8-146">The columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="029e8-147">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="029e8-147">**Comma {,}**</span></span>|<span data-ttu-id="029e8-148">Als Trennzeichen für Spalten dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="029e8-148">The columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="029e8-149">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="029e8-149">**Tab {t}**</span></span>|<span data-ttu-id="029e8-150">Als Trennzeichen für Spalten dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="029e8-150">The columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="029e8-151">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="029e8-151">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="029e8-152">Als Trennzeichen für Spalten dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="029e8-152">The columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="029e8-153">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="029e8-153">**Preview**</span></span>  
 <span data-ttu-id="029e8-154">Zeigen Sie im Dialogfeld **Vorschau Daten** die Ergebnisse der ausgewählten Formatierungsoptionen für die Zielflatfile an.</span><span class="sxs-lookup"><span data-stu-id="029e8-154">View in the **Preview Data** dialog box the results of the selected formatting options for the destination flat file.</span></span>  
  
 <span data-ttu-id="029e8-155">**Transformation bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="029e8-155">**Edit transform**</span></span>  
 <span data-ttu-id="029e8-156">Zeilen löschen, Zeilen anfügen und Spalten in der Zieldatei konfigurieren, indem Sie das Dialogfeld **Spalten** Zuordnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="029e8-156">Delete rows, append rows, and configure columns in the destination file by using the **Column Mappings** dialog box.</span></span>  
  
  
