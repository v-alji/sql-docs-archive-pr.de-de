---
title: Massen Import von LOB-Daten (Large Object) mithilfe des OPENROWSET-Massenrowsetanbieters (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- SINGLE_NCLOB option
- bulk rowset providers [SQL Server]
- bulk importing [SQL Server], data formats
- OPENROWSET function, bulk importing large data
- SINGLE_CLOB option
- data formats [SQL Server], large-object data
- large data, bulk imports
- SINGLE_BLOB option
ms.assetid: 171cdd5c-1e47-4bd7-b99a-4f0fd4e10526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0f43aa2fa5e7f7ef0b2c8f1f6e5e6ff28e02f9f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616996"
---
# <a name="bulk-import-large-object-data-by-using-the-openrowset-bulk-rowset-provider-sql-server"></a><span data-ttu-id="b91ac-102">Massenimport von LOB-Daten (Large Objects) mithilfe des OPENROWSET-Massenrowsetanbieters (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b91ac-102">Bulk Import Large-Object Data by using the OPENROWSET Bulk Rowset Provider (SQL Server)</span></span>
  <span data-ttu-id="b91ac-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET-Bulkrowsetanbieter ermöglicht den Massenimport einer Datendatei als LOB-Daten.</span><span class="sxs-lookup"><span data-stu-id="b91ac-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OPENROWSET Bulk Rowset Provider enables you to bulk import a data file as large-object data.</span></span>  
  
 <span data-ttu-id="b91ac-104">Vom OPENROWSET-Bulkrowsetanbieter unterstützte LOB-Datentypen: **varbinary(max)** oder **image**, **varchar(max)** oder **text**und **nvarchar(max)** oder **ntext**.</span><span class="sxs-lookup"><span data-stu-id="b91ac-104">The large-object data types supported by OPENROWSET Bulk Rowset Provider are **varbinary**(max) or **image**, **varchar**(max) or **text**, and **nvarchar**(max) or **ntext**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b91ac-105">Die Datentypen **image**, **text** und **ntext** sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="b91ac-105">The **image**, **text** and **ntext** data types are deprecated.</span></span>  
  
 <span data-ttu-id="b91ac-106">Die OPENROWSET BULK-Klausel unterstützt drei Optionen zum Importieren vom Inhalt einer Datendatei als einzeiliges, einspaltiges Rowset.</span><span class="sxs-lookup"><span data-stu-id="b91ac-106">The OPENROWSET BULK clause supports three options for importing the contents of a data file as a single-row, single-column rowset.</span></span> <span data-ttu-id="b91ac-107">Statt eine Formatdatei zu verwenden, können Sie eine dieser LOB-Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="b91ac-107">You can specify one of these large-object options instead of using a format file.</span></span> <span data-ttu-id="b91ac-108">Folgende Optionen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b91ac-108">These options are as follows:</span></span>  
  
 <span data-ttu-id="b91ac-109">SINGLE_BLOB</span><span class="sxs-lookup"><span data-stu-id="b91ac-109">SINGLE_BLOB</span></span>  
 <span data-ttu-id="b91ac-110">Liest die Inhalte von *data_file* als einzelne Zeile und gibt die Inhalte als einspaltiges Rowset des **varbinary(max)** -Datentyps zurück.</span><span class="sxs-lookup"><span data-stu-id="b91ac-110">Reads the contents of *data_file* as a single-row, returns the contents as a single-column rowset of type **varbinary(max)**.</span></span>  
  
 <span data-ttu-id="b91ac-111">SINGLE_CLOB</span><span class="sxs-lookup"><span data-stu-id="b91ac-111">SINGLE_CLOB</span></span>  
 <span data-ttu-id="b91ac-112">Liest die Inhalte der angegebenen Datendatei als Zeichen, und gibt die Inhalte als einzeiliges, einspaltiges Rowset im **varchar(max)** -Datentyp zurück, wobei die Sortierung der aktuellen Datenbank verwendet wird, z.B. Text oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word-Dokument.</span><span class="sxs-lookup"><span data-stu-id="b91ac-112">Reads the contents of the specified data file as characters, returns the contents as a single-row, single-column rowset of type **varchar(max)**, using the collation of the current database; such as a text or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Word document.</span></span>  
  
 <span data-ttu-id="b91ac-113">SINGLE_NCLOB</span><span class="sxs-lookup"><span data-stu-id="b91ac-113">SINGLE_NCLOB</span></span>  
 <span data-ttu-id="b91ac-114">Liest die Inhalte der angegebenen Datendatei als Unicode, und gibt die Inhalte als einzeiliges, einspaltiges Rowset im **nvarchar(max)** -Datentyp zurück, wobei die Sortierung der aktuellen Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b91ac-114">Reads the contents of the specified data file as Unicode, returns the contents as a single-row, single-column rowset of type **nvarchar(max)**, using the collation of the current database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91ac-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b91ac-115">See Also</span></span>  
 <span data-ttu-id="b91ac-116">[Importieren von Massendaten mithilfe von BULK INSERT oder OPENROWSET(BULK...) &#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b91ac-116">[Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md) </span></span>  
 <span data-ttu-id="b91ac-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b91ac-117">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b91ac-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b91ac-118">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="b91ac-119">[Beibehalten von NULL-Werten oder Verwenden von Standardwerten während des Massenimports &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b91ac-119">[Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md) </span></span>  
 <span data-ttu-id="b91ac-120">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b91ac-120">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="b91ac-121">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b91ac-121">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  
