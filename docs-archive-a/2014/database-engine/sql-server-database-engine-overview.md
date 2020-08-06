---
title: Datenbank-Engine von SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server]
- SQL Server Database Engine
ms.assetid: 65e2f424-1386-45a6-8912-bd053f434073
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a6c243115e940f7af085c0068d2ca5c277aa5162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608814"
---
# <a name="sql-server-database-engine"></a><span data-ttu-id="bad4b-102">SQL Server-Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="bad4b-102">SQL Server Database Engine</span></span>
  <span data-ttu-id="bad4b-103">[!INCLUDE[ssDE](../includes/ssde-md.md)] ist der Kerndienst zum Speichern, Verarbeiten und Sichern von Daten.</span><span class="sxs-lookup"><span data-stu-id="bad4b-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="bad4b-104">[!INCLUDE[ssDE](../includes/ssde-md.md)] ermöglicht einen gesteuerten Zugriff und eine schnelle Transaktionsverarbeitung, um auch den Anforderungen der anspruchsvollsten Datenverarbeitungsanwendungen in Ihrem Unternehmen gerecht zu werden.</span><span class="sxs-lookup"><span data-stu-id="bad4b-104">The [!INCLUDE[ssDE](../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications within your enterprise.</span></span>

 <span data-ttu-id="bad4b-105">Verwenden Sie [!INCLUDE[ssDE](../includes/ssde-md.md)] , um relationale Datenbanken für OLTP- (Online Transactional Processing, Onlinetransaktionsverarbeitung) oder OLAP-Daten (Online Analytical Processing, Analytische Onlineverarbeitung) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bad4b-105">Use the [!INCLUDE[ssDE](../includes/ssde-md.md)] to create relational databases for online transaction processing or online analytical processing data.</span></span> <span data-ttu-id="bad4b-106">Dazu gehört das Erstellen von Tabellen zur Datenspeicherung und von Datenbankobjekten, wie z. B. Indizes, Sichten und gespeicherte Prozeduren, zum Anzeigen, Verwalten und Sichern von Daten.</span><span class="sxs-lookup"><span data-stu-id="bad4b-106">This includes creating tables for storing data, and database objects such as indexes, views, and stored procedures for viewing, managing, and securing data.</span></span> <span data-ttu-id="bad4b-107">Verwenden Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , um die Datenbankobjekte zu verwalten, und [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] , um Serverereignisse aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bad4b-107">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the database objects, and [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to capture server events.</span></span>

 <span data-ttu-id="bad4b-108">**Inhalt nach Bereich Durchsuchen** ![kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [Neues (Datenbank-Engine)](whats-new-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="bad4b-108">**Browse Content by Area** ![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [What's New (Database Engine)](whats-new-in-sql-server-2016.md)</span></span>

 <span data-ttu-id="bad4b-109">![Kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [SQL Server Datenbank-Engine Abwärtskompatibilität](sql-server-database-engine-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="bad4b-109">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Database Engine Backward Compatibility](sql-server-database-engine-backward-compatibility.md)</span></span>

 <span data-ttu-id="bad4b-110">![Kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [SQL Server-Verwaltungstools Abwärtskompatibilität](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="bad4b-110">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Management Tools Backward Compatibility](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span></span>

 <span data-ttu-id="bad4b-111">![Kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [Datenbankfunktionen und Aufgaben](../../2014/database-engine/database-engine-features-and-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="bad4b-111">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Database Features and Tasks](../../2014/database-engine/database-engine-features-and-tasks.md)</span></span>

 <span data-ttu-id="bad4b-112">![Kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [Technische Referenz](../../2014/database-engine/technical-reference-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="bad4b-112">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Technical Reference](../../2014/database-engine/technical-reference-database-engine.md)</span></span>

 <span data-ttu-id="bad4b-113">![Kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [Transact-SQL-Referenz](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="bad4b-113">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Transact-SQL Reference](/sql/t-sql/language-reference)</span></span>

 <span data-ttu-id="bad4b-114">![Kleines Datei Ordnersymbol](../../2014/integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") [XQuery-Referenz](/sql/xquery/xquery-language-reference-sql-server)</span><span class="sxs-lookup"><span data-stu-id="bad4b-114">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [XQuery Reference](/sql/xquery/xquery-language-reference-sql-server)</span></span>

## <a name="see-also"></a><span data-ttu-id="bad4b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bad4b-115">See Also</span></span>
 [<span data-ttu-id="bad4b-116">SQL Server-Ressourcencenter</span><span class="sxs-lookup"><span data-stu-id="bad4b-116">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=219676)


