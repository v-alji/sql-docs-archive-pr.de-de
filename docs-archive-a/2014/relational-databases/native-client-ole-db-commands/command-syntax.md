---
title: Befehlssyntax | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
author: rothja
ms.author: jroth
ms.openlocfilehash: da5ddb75a5c6fc10db031707b7d97ead71363e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725589"
---
# <a name="command-syntax"></a><span data-ttu-id="e3f54-102">Befehlsyntax</span><span class="sxs-lookup"><span data-stu-id="e3f54-102">Command Syntax</span></span>
  <span data-ttu-id="e3f54-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter erkennt die vom DBGUID_SQL-Makro angegebene Befehlssyntax.</span><span class="sxs-lookup"><span data-stu-id="e3f54-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes command syntax specified by the DBGUID_SQL macro.</span></span> <span data-ttu-id="e3f54-104">Für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter gibt der Spezifizierer an, dass ein Amalgam von ODBC SQL, ISO und eine [!INCLUDE[tsql](../../includes/tsql-md.md)] gültige Syntax ist.</span><span class="sxs-lookup"><span data-stu-id="e3f54-104">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the specifier indicates that an amalgam of ODBC SQL, ISO, and [!INCLUDE[tsql](../../includes/tsql-md.md)] is valid syntax.</span></span> <span data-ttu-id="e3f54-105">Die folgende SQL-Anweisung beispielsweise verwendet eine ODBC SQL-Escapesequenz, um die LCASE-Zeichenfolgenfunktion anzugeben:</span><span class="sxs-lookup"><span data-stu-id="e3f54-105">For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 <span data-ttu-id="e3f54-106">LCASE gibt eine Zeichenfolge zurück und konvertiert alle Großbuchstaben in ihre kleingeschriebenen Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="e3f54-106">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents.</span></span> <span data-ttu-id="e3f54-107">Die ISO-Zeichenfolgenfunktion LOWER führt denselben Vorgang durch, daher ist die folgende SQL-Anweisung eine ISO-Entsprechung der oben aufgeführten ODBC-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="e3f54-107">The ISO string function LOWER performs the same operation, so the following SQL statement is a ISO equivalent to the ODBC statement presented above:</span></span>  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 <span data-ttu-id="e3f54-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verarbeitet beide Formen der Anweisung erfolgreich, wenn er als Text für einen Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e3f54-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider processes either form of the statement successfully when specified as text for a command.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="e3f54-109">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e3f54-109">Stored Procedures</span></span>  
 <span data-ttu-id="e3f54-110">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Verwenden Sie die ODBC-Escapesequenz im Befehls Text, wenn Sie eine gespeicherte Prozedur mit einem Native Client OLE DB Provider-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="e3f54-110">When executing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider command, use the ODBC CALL escape sequence in the command text.</span></span> <span data-ttu-id="e3f54-111">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verwendet dann den Remote Prozedur aufrufsmechanismus von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , um die Befehls Verarbeitung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="e3f54-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider then uses the remote procedure call mechanism of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize command processing.</span></span> <span data-ttu-id="e3f54-112">Zum Beispiel ist die folgende ODBC SQL-Anweisung bevorzugter Befehlstext über das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Formular:</span><span class="sxs-lookup"><span data-stu-id="e3f54-112">For example, the following ODBC SQL statement is preferred command text over the [!INCLUDE[tsql](../../includes/tsql-md.md)] form:</span></span>  
  
-   <span data-ttu-id="e3f54-113">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="e3f54-113">ODBC SQL</span></span>  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   <span data-ttu-id="e3f54-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3f54-114">Transact-SQL</span></span>  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e3f54-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3f54-115">See Also</span></span>  
 [<span data-ttu-id="e3f54-116">Befehle</span><span class="sxs-lookup"><span data-stu-id="e3f54-116">Commands</span></span>](commands.md)  
  
  
