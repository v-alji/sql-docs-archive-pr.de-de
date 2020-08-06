---
title: Dialogfeld „Spaltenkonvertierungsdetails“ (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9207e76191060c56acad37db734827579a83aae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619944"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="4c8e4-102">Dialogfeld 'Spaltenkonvertierungsdetails' (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="4c8e4-102">Column Conversion Details Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="4c8e4-103">Im Dialogfeld **Spalten Konvertierungs Details** können Sie ausführliche Konvertierungs Informationen zu einer einzelnen Spalte überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-103">Use the **Column Conversion Details** dialog box to review detailed conversion information about an individual column.</span></span> <span data-ttu-id="4c8e4-104">Diese Konvertierungsinformationen enthalten den Datentyp der Spalte an Quelle und Ziel sowie die Konvertierung, die der Assistent ausführt.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-104">This conversion information contains the column's data type at the source and the destination, and the conversion that the wizard will perform.</span></span> <span data-ttu-id="4c8e4-105">Auf dieser Seite werden auch die Datentypzuordnungsdateien aufgelistet, anhand derer der Assistent die erforderlichen Datentypkonvertierungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-105">This page also lists the data type mapping files that the wizard uses to determine the data type conversions that are required.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="4c8e4-106">installiert diese Datentypzuordnungsdateien während des Setups.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-106">installs these data type mapping files during setup.</span></span>  
  
 <span data-ttu-id="4c8e4-107">**So öffnen Sie das Dialogfeld 'Spaltenkonvertierungsdetails'**</span><span class="sxs-lookup"><span data-stu-id="4c8e4-107">**To open the Column Conversion Details dialog box**</span></span>  
  
1.  <span data-ttu-id="4c8e4-108">Wählen Sie auf der Seite **Datentyp Probleme überprüfen** des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Import/Export-Assistenten in der Liste **Tabelle** eine Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-108">On the **Review Data Type Issues** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, in the **Table** list, select a table.</span></span>  
  
2.  <span data-ttu-id="4c8e4-109">Doppelklicken Sie in der Liste **Datentyp Zuordnung** auf die Zeile, die die Spalte enthält, für die Sie die Konvertierungs Details anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-109">In the **Data type mapping** list, double-click the row that contains the column for which you want to view conversion details.</span></span>  
  
 <span data-ttu-id="4c8e4-110">Weitere Informationen zum- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import/Export-Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4c8e4-110">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="4c8e4-111">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4c8e4-111">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="4c8e4-112">Mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-112">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="4c8e4-113">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="4c8e4-114">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="4c8e4-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="4c8e4-115">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4c8e4-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
