---
title: Löschen von Daten- oder Protokolldateien aus einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- deleting files
- removing files
- removing data
- data deletions [SQL Server]
- file deletion [SQL Server]
- deleting data
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f7bd170e085e9bc94b00446545850e905efaa34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725877"
---
# <a name="delete-data-or-log-files-from-a-database"></a><span data-ttu-id="7df52-102">Löschen von Daten- oder Protokolldateien aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="7df52-102">Delete Data or Log Files from a Database</span></span>
  <span data-ttu-id="7df52-103">In diesem Thema wird beschrieben, wie Daten- oder Protokolldateien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7df52-103">This topic describes how to delete data or log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7df52-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7df52-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7df52-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7df52-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="7df52-106">Eine Datei muss leer sein, bevor sie gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="7df52-106">A file must be empty before it can be deleted.</span></span> <span data-ttu-id="7df52-107">Weitere Informationen finden Sie unter [Verkleinern einer Datei](shrink-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="7df52-107">For more information, see [Shrink a File](shrink-a-file.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7df52-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7df52-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7df52-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7df52-109">Permissions</span></span>  
 <span data-ttu-id="7df52-110">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7df52-110">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7df52-111">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7df52-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="7df52-112">So löschen Sie Daten- oder Protokolldateien aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="7df52-112">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="7df52-113">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="7df52-113">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7df52-114">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die Datenbank, aus der Sie die Datei löschen möchten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7df52-114">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7df52-115">Wählen Sie die Seite **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="7df52-115">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="7df52-116">Wählen Sie im Raster **Datenbankdateien** die zu löschende Datei aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="7df52-116">In the **Database files** grid, select the file to delete and then click **Remove**.</span></span>  
  
5.  <span data-ttu-id="7df52-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7df52-117">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7df52-118">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7df52-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="7df52-119">So löschen Sie Daten- oder Protokolldateien aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="7df52-119">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="7df52-120">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="7df52-120">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7df52-121">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7df52-121">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7df52-122">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7df52-122">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7df52-123">In diesem Beispiel wird die Datei `test1dat4`entfernt.</span><span class="sxs-lookup"><span data-stu-id="7df52-123">This example removes the file `test1dat4`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase4)]  
  
 <span data-ttu-id="7df52-124">Weitere Beispiele finden Sie unter [ALTER DATABASE-Optionen Datei und Dateigruppe &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="7df52-124">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df52-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7df52-125">See Also</span></span>  
 <span data-ttu-id="7df52-126">[Verkleinern einer Datenbank](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="7df52-126">[Shrink a Database](shrink-a-database.md) </span></span>  
 [<span data-ttu-id="7df52-127">Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="7df52-127">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
