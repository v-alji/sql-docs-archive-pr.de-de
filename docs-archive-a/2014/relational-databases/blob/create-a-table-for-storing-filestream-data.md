---
title: Erstellen einer Tabelle zum Speichern von FILESTREAM-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 484d7b58ce949df79dc7e17ee4dc7307b70c0154
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699782"
---
# <a name="create-a-table-for-storing-filestream-data"></a><span data-ttu-id="7d761-102">Erstellen einer Tabelle zum Speichern von FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="7d761-102">Create a Table for Storing FILESTREAM Data</span></span>
  <span data-ttu-id="7d761-103">In diesem Thema wird erläutert, wie Sie eine Tabelle zum Speichern von FILESTREAM-Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d761-103">This topic shows how to create a table for storing FILESTREAM data.</span></span>  
  
 <span data-ttu-id="7d761-104">Wenn die Datenbank eine FILESTREAM-Dateigruppe aufweist, können Sie Tabellen zum Speichern von FILESTREAM-Daten erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="7d761-104">When the database has a FILESTREAM filegroup, you can create or modify tables to store FILESTREAM data.</span></span> <span data-ttu-id="7d761-105">Um anzugeben, dass eine Spalte FILESTREAM-Daten enthält, erstellen Sie eine `varbinary(max)`-Spalte und fügen das FILESTREAM-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d761-105">To specify that a column contains FILESTREAM data, you create a `varbinary(max)` column and add the FILESTREAM attribute.</span></span>  
  
### <a name="to-create-a-table-to-store-filestream-data"></a><span data-ttu-id="7d761-106">So erstellen Sie eine Tabelle zum Speichern von FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="7d761-106">To create a table to store FILESTREAM data</span></span>  
  
1.  <span data-ttu-id="7d761-107">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf **Neue Abfrage** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7d761-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
2.  <span data-ttu-id="7d761-108">Kopieren Sie den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code aus dem folgenden Beispiel in den Abfrage-Editor.</span><span class="sxs-lookup"><span data-stu-id="7d761-108">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] code from the following example into the Query Editor.</span></span> <span data-ttu-id="7d761-109">Dieser [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code erstellt eine FILESTREAM-aktivierte Tabelle mit dem Namen Records.</span><span class="sxs-lookup"><span data-stu-id="7d761-109">This [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a FILESTREAM-enabled table called Records.</span></span>  
  
3.  <span data-ttu-id="7d761-110">Klicken Sie auf **Ausführen**, um die Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d761-110">To create the table, click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d761-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d761-111">Example</span></span>  
 <span data-ttu-id="7d761-112">Das folgende Codebeispiel zeigt, wie eine Tabelle mit der Bezeichnung `Records`erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7d761-112">The following code example shows how to create a table that is named `Records`.</span></span> <span data-ttu-id="7d761-113">Die `Id` -Spalte ist eine `ROWGUIDCOL` -Spalte, die zur Verwendung von FILESTREAM-Daten mit Win32-APIs erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7d761-113">The `Id` column is a `ROWGUIDCOL` column and is required to use FILESTREAM data with Win32 APIs.</span></span> <span data-ttu-id="7d761-114">Die `SerialNumber` -Spalte ist eine `UNIQUE INTEGER`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="7d761-114">The `SerialNumber` column is a `UNIQUE INTEGER`.</span></span> <span data-ttu-id="7d761-115">Die `Chart` -Spalte ist eine `FILESTREAM` -Spalte, die verwendet wird, um `Chart` im Dateisystem zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7d761-115">The `Chart` column is a `FILESTREAM` column and is used to store the `Chart` in the file system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d761-116">Dieses Beispiel bezieht sich auf die Datenbank „Archive“, die unter [Vorgehensweise: Erstellen einer FILESTREAM-aktivierten Datenbank](create-a-filestream-enabled-database.md)erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7d761-116">This example refers to the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_createtable)]  
  
## <a name="see-also"></a><span data-ttu-id="7d761-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d761-117">See Also</span></span>  
 <span data-ttu-id="7d761-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7d761-118">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 [<span data-ttu-id="7d761-119">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d761-119">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
