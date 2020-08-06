---
title: Datenvorschau (Dialogfeld) (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.previewdata.f1
ms.assetid: 423ac26a-ba02-4fdf-88b4-07995fe4a97e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 17debc001d8ba7826fe845c006e944e5a3dc87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619927"
---
# <a name="preview-data-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="926f2-102">Datenvorschau (Dialogfeld) (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="926f2-102">Preview Data Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="926f2-103">Verwenden Sie das Dialogfeld **Daten Vorschau** , um die Abfrage anzuzeigen, die vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Import/Export-Assistenten an die Datenquelle gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="926f2-103">Use the **Preview Data** dialog box to see the query that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard will send to the data source.</span></span> <span data-ttu-id="926f2-104">In diesem Dialogfeld können Sie auch bis zu 200 Zeilen der Beispieldaten in der Vorschau anzeigen.</span><span class="sxs-lookup"><span data-stu-id="926f2-104">You can also use this dialog box to preview up to 200 rows of sample data.</span></span>  
  
 <span data-ttu-id="926f2-105">Weitere Informationen zum- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import/Export-Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="926f2-105">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="926f2-106">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="926f2-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="926f2-107">Mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="926f2-107">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="926f2-108">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="926f2-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="926f2-109">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="926f2-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="926f2-110">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="926f2-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
 <span data-ttu-id="926f2-111">**So öffnen Sie das Dialogfeld "Datenvorschau"**</span><span class="sxs-lookup"><span data-stu-id="926f2-111">**To open the Preview Data dialog box**</span></span>  
  
-   <span data-ttu-id="926f2-112">Klicken Sie auf der Seite **Quell Tabellen und-Sichten auswählen** des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Import/Export-Assistenten auf **Vorschau**.</span><span class="sxs-lookup"><span data-stu-id="926f2-112">On the **Select Source Tables and Views** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, click **Preview**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="926f2-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="926f2-113">Options</span></span>  
 <span data-ttu-id="926f2-114">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="926f2-114">**Source**</span></span>  
 <span data-ttu-id="926f2-115">Zeigt die Abfrage an, die der Assistent an die Datenquelle sendet.</span><span class="sxs-lookup"><span data-stu-id="926f2-115">Displays the query that the wizard will send to the data source.</span></span>  
  
 <span data-ttu-id="926f2-116">**Beispieldatenraster**</span><span class="sxs-lookup"><span data-stu-id="926f2-116">**Sample data grid**</span></span>  
 <span data-ttu-id="926f2-117">Zeigt bis zu 200 Zeilen der Beispieldaten an, die von der Abfrage zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="926f2-117">Displays up to 200 rows of sample data that the query returned.</span></span>  
  
  
