---
title: Quelltabellen und -sichten auswählen (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.selectsourcetablesandviews.f1
ms.assetid: f60e1a19-2ea6-403c-89ab-3e60ac533ea0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e18f9f34db7965033d4e1e62964060a26404a45e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619918"
---
# <a name="select-source-tables-and-views-sql-server-import-and-export-wizard"></a><span data-ttu-id="9c4f1-102">Quelltabellen und -sichten auswählen (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="9c4f1-102">Select Source Tables and Views (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="9c4f1-103">Verwenden Sie die Seite **Quell Tabellen und-Sichten auswählen** , um die Tabellen und Sichten anzugeben, die aus der Datenquelle in das Ziel kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-103">Use the **Select Source Tables and Views** page to specify the tables and views to be copied from the data source to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c4f1-104">Sie müssen nicht alle Spalten in einer Tabelle kopieren, wenn Sie die Option zum Kopieren von Tabellen auswählen.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="9c4f1-105">Nachdem Sie eine Ziel Tabelle ausgewählt haben, klicken Sie auf Zuordnungen bearbeiten, um das Dialogfeld **Spalten** Zuordnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-105">After selecting a destination table, click Edit Mappings to display the **Column Mappings** dialog box.</span></span> <span data-ttu-id="9c4f1-106">Wählen Sie in der Spalte **\<ignore>** **Ziel** im Dialogfeld **Spalten** Zuordnungen die Spalten aus, die Sie überspringen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-106">Select **\<ignore>** in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="9c4f1-107">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9c4f1-107">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="9c4f1-108">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9c4f1-108">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="9c4f1-109">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-109">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="9c4f1-110">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-110">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="9c4f1-111">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-111">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="9c4f1-112">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="9c4f1-112">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c4f1-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9c4f1-113">Options</span></span>  
  
### <a name="tables-and-views-list"></a><span data-ttu-id="9c4f1-114">Liste 'Tabellen und Sichten'</span><span class="sxs-lookup"><span data-stu-id="9c4f1-114">Tables and views List</span></span>  
 <span data-ttu-id="9c4f1-115">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="9c4f1-115">**Source**</span></span>  
 <span data-ttu-id="9c4f1-116">Wählen Sie mithilfe der Kontrollkästchen aus der Liste der verfügbaren Tabellen und Sichten die in das Ziel zu kopierenden Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-116">Using the check boxes, select from the list of available tables and views to copy to the destination.</span></span> <span data-ttu-id="9c4f1-117">Wenn Sie eine Quelltabelle oder -sicht auswählen und keine weitere Aktion ausführen, werden das Schema und die Daten aus der Quelle ohne Änderungen kopiert.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-117">If you select a source table or view and perform no other action, the schema and data from the source are copied without changes.</span></span>  
  
 <span data-ttu-id="9c4f1-118">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="9c4f1-118">**Destination**</span></span>  
 <span data-ttu-id="9c4f1-119">Wählen Sie aus der Liste für jede Quelltabelle eine Zieltabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-119">Select a destination table from the list for each source table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c4f1-120">Wenn Sie zu diesem Zeitpunkt den Assistenten anhalten, um eine Zieltabelle in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] oder eines anderen Tools zu erstellen, ist die neue Tabelle in der Liste verfügbarer Zieltabellen nicht sofort sichtbar.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-120">If you pause at this point in the wizard to create a destination table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or another tool, the new table is not immediately visible in the list of available destination tables.</span></span> <span data-ttu-id="9c4f1-121">Um die Liste der Ziel Tabellen zu aktualisieren, führen Sie zwei Seiten auf die Seite **Ziel auswählen** zurück, wählen Sie die Zieldatenbank erneut aus, und führen Sie dann erneut die Option **Quell Tabellen und-Sichten auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-121">To refresh the list of destination tables, step back two pages to the **Choose a Destination** page, re-select the destination database, then step forward again to the **Select Source Tables and Views**.</span></span>  
  
### <a name="other-options"></a><span data-ttu-id="9c4f1-122">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="9c4f1-122">Other Options</span></span>  
 <span data-ttu-id="9c4f1-123">**Zuordnungen bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="9c4f1-123">**Edit mappings**</span></span>  
 <span data-ttu-id="9c4f1-124">Im Dialogfeld **Spalten** Zuordnungen können Sie Ziel Spalten angeben, um die Quelldaten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-124">Use the **Column Mappings** dialog box to specify destination columns to receive the source data.</span></span> <span data-ttu-id="9c4f1-125">Sie können nur eine Teilmenge von Spalten kopieren, indem Sie \<ignore> in der Spalte **Ziel** des Dialog Felds **Spalten** Zuordnungen für Spalten auswählen, die Sie überspringen möchten.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-125">You can copy only a subset of columns by selecting \<ignore> in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="9c4f1-126">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="9c4f1-126">**Preview**</span></span>  
 <span data-ttu-id="9c4f1-127">Stellen Sie im Dialogfeld **Vorschau Daten** eine Vorschau der Quelldaten zur Überprüfung vor dem Importieren oder exportieren vor.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-127">Preview source data in the **Preview Data** dialog box to verify it before performing the import or export.</span></span> <span data-ttu-id="9c4f1-128">Im Dialogfeld **Vorschau Daten** werden bis zu 200 Daten Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-128">The **Preview Data** dialog box displays up to 200 rows of data.</span></span>  
  
 <span data-ttu-id="9c4f1-129">Nach der Vorschau der Daten können Sie die Optionen ändern, die Sie für die Datenquelle und das Ziel ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-129">After previewing the data, you might want to change the options that you have selected for the data source and destination.</span></span> <span data-ttu-id="9c4f1-130">Um diese Änderungen vorzunehmen, klicken Sie auf der Seite **Quelltabellen und -sichten auswählen** auf **Zurück** , um zu vorherigen Seiten zurückzukehren, auf denen Sie Ihre Auswahlen ändern können.</span><span class="sxs-lookup"><span data-stu-id="9c4f1-130">To make these changes, on the **Select Source Tables and Views** page, click **Back** to return to previous pages where you can change your selections.</span></span>  
  
  
