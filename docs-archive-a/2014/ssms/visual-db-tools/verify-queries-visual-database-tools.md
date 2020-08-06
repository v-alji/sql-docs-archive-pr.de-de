---
title: Überprüfen von Abfragen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:100644
helpviewer_keywords:
- verifying queries
- queries [SQL Server], verifying
- checking queries
ms.assetid: 1382c0c0-46dc-45f9-ab38-9bba1d347eea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7bf24de9bdc0e8b7b7ceb33bb881812b180ce112
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618962"
---
# <a name="verify-queries-visual-database-tools"></a><span data-ttu-id="b3f04-102">Überprüfen von Abfragen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b3f04-102">Verify Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="b3f04-103">Um Probleme zu vermeiden, können Sie die erstellte Abfrage auf richtige Syntax überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b3f04-103">To avoid problems, you can check the query you have built to ensure its syntax is correct.</span></span> <span data-ttu-id="b3f04-104">Diese Option ist insbesondere dann nützlich, wenn Sie Anweisungen im [SQL-Bereich](visual-database-tools.md)eingeben.</span><span class="sxs-lookup"><span data-stu-id="b3f04-104">This option is especially useful when you enter statements in the [SQL pane](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="b3f04-105">Einige Hinweise, die beim Überprüfen von Abfragen bedacht werden sollten:</span><span class="sxs-lookup"><span data-stu-id="b3f04-105">Some notes to keep in mind about verifying queries:</span></span>  
  
-   <span data-ttu-id="b3f04-106">Eine Anweisung kann gültig und daher problemlos überprüfbar sein, auch wenn sie sich im **Diagrammbereich** und **Kriterienbereich**nicht darstellen lässt.</span><span class="sxs-lookup"><span data-stu-id="b3f04-106">A statement can be valid, and therefore be verified successfully, even if it cannot be represented in the **Diagram Pane** and **Criteria Pane**.</span></span>  
  
-   <span data-ttu-id="b3f04-107">Bei einer SQL-Überprüfung werden einige, aber möglicherweise nicht alle SQL-Fehler erkannt.</span><span class="sxs-lookup"><span data-stu-id="b3f04-107">SQL Verification can detect some, but not all SQL errors.</span></span> <span data-ttu-id="b3f04-108">Wenn eine Abfrage einen bei der SQL-Überprüfung nicht erkannten Fehler enthält, erkennt die Datenbank den Fehler beim Ausführen der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b3f04-108">If a query contains an error not detected during SQL verification, the database will detect the error when you run the query.</span></span>  
  
-   <span data-ttu-id="b3f04-109">Abfragen, die Parameter enthalten, können nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b3f04-109">Queries that contain parameters cannot be verified.</span></span>  
  
### <a name="to-verify-an-sql-statement"></a><span data-ttu-id="b3f04-110">So überprüfen Sie eine SQL-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b3f04-110">To verify an SQL statement</span></span>  
  
-   <span data-ttu-id="b3f04-111">Klicken Sie mit der rechten Maustaste in den **SQL-Bereich**, und wählen Sie im Kontextmenü den Befehl **SQL-Syntax überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b3f04-111">Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f04-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3f04-112">See Also</span></span>  
 <span data-ttu-id="b3f04-113">[Ausführen von Abfragen &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b3f04-113">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b3f04-114">Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b3f04-114">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
