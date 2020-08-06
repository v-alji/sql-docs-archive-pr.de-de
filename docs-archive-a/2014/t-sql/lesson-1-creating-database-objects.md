---
title: 'Lektion 1: Erstellen von Datenbankobjekten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
ms.assetid: 9fb8656b-0e4e-4ada-b404-4db4d3eea995
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 172fdbcaedc10f9c359befd48ed09ec825aea9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720683"
---
# <a name="lesson-1-creating-database-objects"></a><span data-ttu-id="fbebf-102">Lektion 1: Erstellen von Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="fbebf-102">Lesson 1: Creating Database Objects</span></span>
  <span data-ttu-id="fbebf-103">In dieser Lektion erfahren Sie, wie Sie eine Datenbank erstellen, eine Tabelle in der Datenbank erstellen und dann auf die Daten in der Tabelle zugreifen und diese ändern können.</span><span class="sxs-lookup"><span data-stu-id="fbebf-103">This lesson shows you how to create a database, create a table in the database, and then access and change the data in the table.</span></span> <span data-ttu-id="fbebf-104">Weil diese Lektion eine Einführung in die Verwendung von [!INCLUDE[tsql](../includes/tsql-md.md)]darstellt, werden viele der für diese Anweisungen verfügbaren Optionen nicht verwendet bzw. beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbebf-104">Because this lesson is an introduction to using [!INCLUDE[tsql](../includes/tsql-md.md)], it does not use or describe the many options that are available for these statements.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="fbebf-105">-Anweisungen können wie folgt geschrieben und an die [!INCLUDE[ssDE](../includes/ssde-md.md)] übertragen werden:</span><span class="sxs-lookup"><span data-stu-id="fbebf-105">statements can be written and submitted to the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="fbebf-106">Mithilfe von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbebf-106">By using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="fbebf-107">In diesem Lernprogramm wird vorausgesetzt, dass Sie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]verwenden. Sie können jedoch auch [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express verwenden, das als kostenloser Download im [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630)zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="fbebf-107">This tutorial assumes that you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], but you can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, which is available as a free download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630).</span></span>  
  
-   <span data-ttu-id="fbebf-108">Mithilfe des [Hilfsprogramms sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="fbebf-108">By using the [sqlcmd utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="fbebf-109">Durch Herstellen der Verbindung über eine von Ihnen erstellte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fbebf-109">By connecting from an application that you create.</span></span>  
  
 <span data-ttu-id="fbebf-110">Der Code wird in der [!INCLUDE[ssDE](../includes/ssde-md.md)] immer auf gleiche Weise und mit denselben Berechtigungen ausgeführt, unabhängig davon, wie Sie die Codeanweisungen übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fbebf-110">The code executes on the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the same way and with the same permissions, regardless of how you submit the code statements.</span></span>  
  
 <span data-ttu-id="fbebf-111">Damit Sie [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]ausführen können, öffnen Sie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] und stellen eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="fbebf-111">To run [!INCLUDE[tsql](../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fbebf-112">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fbebf-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="fbebf-113">Erstellen einer Datenbank &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebf-113">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
-   [<span data-ttu-id="fbebf-114">Erstellen einer Tabelle &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebf-114">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
-   [<span data-ttu-id="fbebf-115">Einfügen und Aktualisieren von Daten in einer Tabelle &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebf-115">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
-   [<span data-ttu-id="fbebf-116">Lesen der Daten in einer Tabelle &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebf-116">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
-   [<span data-ttu-id="fbebf-117">Zusammenfassung: Erstellen von Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="fbebf-117">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fbebf-118">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="fbebf-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fbebf-119">Erstellen einer Datenbank &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="fbebf-119">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
  
