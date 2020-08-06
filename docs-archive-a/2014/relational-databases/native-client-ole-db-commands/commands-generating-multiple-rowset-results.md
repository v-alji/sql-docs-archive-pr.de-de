---
title: Befehle, die mehrere Rowsetergebnisse erzeugen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695593"
---
# <a name="commands-generating-multiple-rowset-results"></a><span data-ttu-id="a09ba-102">Mehrere Rowsetergebnisse generierende Befehle</span><span class="sxs-lookup"><span data-stu-id="a09ba-102">Commands Generating Multiple-Rowset Results</span></span>
  <span data-ttu-id="a09ba-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter kann mehrere Rowsets von-Anweisungen zurückgeben [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a09ba-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can return multiple rowsets from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a09ba-104">-Anweisungen geben unter folgenden Bedingungen mehrere Rowsetergebnisse zurück:</span><span class="sxs-lookup"><span data-stu-id="a09ba-104">statements return multiple-rowset results under the following conditions:</span></span>  
  
-   <span data-ttu-id="a09ba-105">SQL-Anweisungen im Batchmodus werden als einzelner Befehl gesendet.</span><span class="sxs-lookup"><span data-stu-id="a09ba-105">Batched SQL statements are submitted as a single command.</span></span>  
  
-   <span data-ttu-id="a09ba-106">Gespeicherte Prozeduren implementieren einen Batch SQL-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a09ba-106">Stored procedures implement a batch of SQL statements.</span></span>  
  
## <a name="batches"></a><span data-ttu-id="a09ba-107">Batches</span><span class="sxs-lookup"><span data-stu-id="a09ba-107">Batches</span></span>  
 <span data-ttu-id="a09ba-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter erkennt das Semikolon als Batch Trennzeichen für SQL-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="a09ba-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes the semicolon character as a batch delimiter for SQL statements:</span></span>  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 <span data-ttu-id="a09ba-109">Mehrere SQL-Anweisungen in einem Batch zu senden ist effizienter, als jede SQL-Anweisung einzeln auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a09ba-109">Sending multiple SQL statements in one batch is more efficient than executing each SQL statement separately.</span></span> <span data-ttu-id="a09ba-110">Durch Senden eines Batches werden die Netzwerkroundtrips vom Client auf den Server reduziert.</span><span class="sxs-lookup"><span data-stu-id="a09ba-110">Sending one batch reduces the network round trips from the client to the server.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="a09ba-111">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a09ba-111">Stored Procedures</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a09ba-112">gibt ein Resultset für jede Anweisung in einer gespeicherten Prozedur zurück, sodass die meisten gespeicherten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozeduren mehrere Resultsets zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a09ba-112">returns a result set for each statement in a stored procedure, so most [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return multiple result sets.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a09ba-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a09ba-113">In This Section</span></span>  
  
-   [<span data-ttu-id="a09ba-114">Verwenden von 'IMultipleResults' zur Verarbeitung mehrerer Resultsets</span><span class="sxs-lookup"><span data-stu-id="a09ba-114">Using IMultipleResults to Process Multiple Result Sets</span></span>](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="a09ba-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a09ba-115">See Also</span></span>  
 [<span data-ttu-id="a09ba-116">Befehle</span><span class="sxs-lookup"><span data-stu-id="a09ba-116">Commands</span></span>](commands.md)  
  
  
