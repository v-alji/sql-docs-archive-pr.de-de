---
title: SQL-Anweisung CREATE TABLE (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createtablesql.f1
ms.assetid: 0d6f6b3b-d023-4770-a8a9-65b2977c8d05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3fc2054711708a27691f2d7219c33749f11b977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619938"
---
# <a name="create-table-sql-statement-sql-server-import-and-export-wizard"></a><span data-ttu-id="9598a-102">SQL-Anweisung CREATE TABLE (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="9598a-102">Create Table SQL Statement (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="9598a-103">Verwenden Sie das Dialogfeld **SQL-Anweisung CREATE TABLE** , um die Anweisung anzuzeigen, die automatisch generiert wurde, oder um Sie für Ihre Zwecke zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9598a-103">Use the **Create Table SQL Statement** dialog box to view the statement that was generated automatically, or to modify it for your purposes.</span></span> <span data-ttu-id="9598a-104">Wenn Sie diese Anweisung ändern, müssen Sie möglicherweise auch entsprechende Änderungen an den Spaltenzuordnungen vornehmen und daher die bearbeitete SQL-Anweisung anschließend manuell warten.</span><span class="sxs-lookup"><span data-stu-id="9598a-104">If you modify this statement, you may also have to make associated changes to column mapping, and you will have to maintain the edited SQL statement manually thereafter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="9598a-105">generiert eine Standard-CREATE TABLE-Anweisung auf Grundlage der verbundenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="9598a-105">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="9598a-106">Diese Standard-CREATE TABLE-Anweisung enthält nicht das FILESTREAM-Attribut, selbst wenn die Quelltabelle eine Spalte mit der Erklärung des FILESTREAM-Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="9598a-106">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="9598a-107">Um eine [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Komponente mit dem FILESTREAM-Attribut auszuführen, implementieren Sie zunächst die FILESTREAM-Speicherung in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="9598a-107">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="9598a-108">Fügen Sie dann das FILESTREAM-Attribut der CREATE TABLE-Anweisung im Dialogfeld **Tabelle erstellen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="9598a-108">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="9598a-109">Weitere Informationen finden Sie unter [Blob-Daten &#40;Binary Large Object, SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9598a-109">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="9598a-110">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9598a-110">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="9598a-111">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9598a-111">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="9598a-112">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="9598a-112">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="9598a-113">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9598a-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="9598a-114">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="9598a-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="9598a-115">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9598a-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9598a-116">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9598a-116">Options</span></span>  
 <span data-ttu-id="9598a-117">**SQL-Anweisung**</span><span class="sxs-lookup"><span data-stu-id="9598a-117">**SQL statement**</span></span>  
 <span data-ttu-id="9598a-118">Zeigt die automatisch generierte SQL-Anweisung an, die hier auch bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9598a-118">Displays the auto-generated SQL statement and lets it be edited.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9598a-119">Wenn Sie einen Wagenrücklauf in die SQL-Anweisung einfügen möchten, drücken Sie STRG+EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="9598a-119">If you want to include a carriage return in the SQL statement, press CTRL+ENTER.</span></span> <span data-ttu-id="9598a-120">Wenn Sie nur die EINGABETASTE drücken, wird das Dialogfeld geschlossen.</span><span class="sxs-lookup"><span data-stu-id="9598a-120">If you press only ENTER, the dialog box closes.</span></span>  
  
 <span data-ttu-id="9598a-121">**Automatisch generieren**</span><span class="sxs-lookup"><span data-stu-id="9598a-121">**Autogenerate**</span></span>  
 <span data-ttu-id="9598a-122">Durch Klicken auf die Schaltfläche **Automatisch generieren** stellen Sie die Standard-SQL-Anweisung nach einer Änderung wieder her.</span><span class="sxs-lookup"><span data-stu-id="9598a-122">Restore the default SQL statement, if you have modified it, by clicking **Autogenerate**.</span></span>  
  
  
