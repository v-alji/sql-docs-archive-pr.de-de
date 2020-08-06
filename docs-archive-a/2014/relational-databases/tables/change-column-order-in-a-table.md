---
title: Ändern der Spaltenreihenfolge einer Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
author: stevestein
ms.author: sstein
ms.openlocfilehash: d162f9dc793ceb9ea423d94922f7358f1729712e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617881"
---
# <a name="change-column-order-in-a-table"></a><span data-ttu-id="c1493-102">Ändern der Spaltenreihenfolge einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="c1493-102">Change Column Order in a Table</span></span>
  <span data-ttu-id="c1493-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] die Reihenfolge der Spalten im Tabellen-Designer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="c1493-103">You can change the order of columns in Table Designer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c1493-104">Das Ändern der Spaltenreihenfolge in einer Tabelle kann sich auf den Code und die Anwendungen auswirken, die von einer bestimmten Spaltenreihenfolge abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="c1493-104">Changing the column order of a table may affect code and applications that depend on the specific order of columns.</span></span> <span data-ttu-id="c1493-105">Dies schließt Abfragen, Sichten, gespeicherte Prozeduren, benutzerdefinierte Funktionen und Clientanwendungen ein.</span><span class="sxs-lookup"><span data-stu-id="c1493-105">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="c1493-106">Bedenken Sie sorgfältig die Konsequenzen, bevor Sie Änderungen an der Spaltenreihenfolge vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c1493-106">Carefully consider any changes you want to make to column order before making it.</span></span> <span data-ttu-id="c1493-107">Best Practice ist, in der Anwendung oder auf der Abfrageebene die Reihenfolge anzugeben, in der die Spalten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c1493-107">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="c1493-108">Sie sollten sich nicht darauf verlassen, dass bei Verwendung von SELECT \* alle Spalten in der Reihenfolge, in der sie in der Tabelle definiert worden sind, zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c1493-108">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="c1493-109">Geben Sie die Spalten in Abfragen und Anwendungen immer namentlich in der Reihenfolge an, in der sie angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c1493-109">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
 <span data-ttu-id="c1493-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c1493-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1493-111">**So ändern Sie die Spaltenreihenfolge mit:**</span><span class="sxs-lookup"><span data-stu-id="c1493-111">**To change the column order, using:**</span></span>  
  
     [<span data-ttu-id="c1493-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1493-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1493-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1493-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1493-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1493-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-column-order"></a><span data-ttu-id="c1493-115">So ändern Sie die Spaltenreihenfolge</span><span class="sxs-lookup"><span data-stu-id="c1493-115">To change the column order</span></span>  
  
1.  <span data-ttu-id="c1493-116">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle mit Spalten, die Sie neu anordnen möchten, und klicken Sie auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="c1493-116">In **Object Explorer**, right-click the table with columns you want to reorder and click **Design**.</span></span>  
  
2.  <span data-ttu-id="c1493-117">Markieren Sie das Feld links neben dem Namen der Spalte, deren Reihenfolge Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c1493-117">Select the box to the left of the column name that you want to reorder.</span></span>  
  
3.  <span data-ttu-id="c1493-118">Ziehen Sie die Spalte an eine andere Position innerhalb der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c1493-118">Drag the column to another location within the table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1493-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1493-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="c1493-120">**So ändern Sie die Spaltenreihenfolge**</span><span class="sxs-lookup"><span data-stu-id="c1493-120">**To change the column order**</span></span>  
  
 <span data-ttu-id="c1493-121">Diese Aufgabe kann nicht mit Transact-SQL-Anweisungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c1493-121">This task cannot be performed using Transact-SQL statements.</span></span>  
  
###  <a name="TsqlExample"></a>  
