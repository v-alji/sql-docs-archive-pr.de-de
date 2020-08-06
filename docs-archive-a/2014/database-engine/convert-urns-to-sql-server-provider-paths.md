---
title: Konvertieren von URNs in SQL Server-Anbieterpfade | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618266"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a><span data-ttu-id="8488e-102">Konvertieren von URNs in SQL Server-Anbieterpfade</span><span class="sxs-lookup"><span data-stu-id="8488e-102">Convert URNs to SQL Server Provider Paths</span></span>
  <span data-ttu-id="8488e-103">Das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object-Modell (SMO-Modell) erstellt einheitliche Ressourcennamen (Uniform Resource Names, URN) für seine Objekte.</span><span class="sxs-lookup"><span data-stu-id="8488e-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object model (SMO) builds Uniform Resource Names (URN) for its objects.</span></span> <span data-ttu-id="8488e-104">Jeder URN identifiziert eindeutig ein SMO-Objekt und kann mit dem `Convert-UrnToPath`-Cmdlet in einen SQL Server PowerShell-Anbieterpfad konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="8488e-104">Each URN uniquely identifies a SMO object, and can be converted to a SQL Server PowerShell provider path by using the `Convert-UrnToPath` cmdlet.</span></span>  
  
## <a name="converting-urns-to-paths"></a><span data-ttu-id="8488e-105">Konvertieren von URNs in Pfade</span><span class="sxs-lookup"><span data-stu-id="8488e-105">Converting URNs to Paths</span></span>  
 <span data-ttu-id="8488e-106">Jeder URN weist die gleichen Informationen wie einen Pfad zum Objekt auf, aber in einer anderen Form.</span><span class="sxs-lookup"><span data-stu-id="8488e-106">Each URN has the same information as a path to the object, but in a different form.</span></span> <span data-ttu-id="8488e-107">Dies ist beispielsweise der Pfad zu einer Tabelle:</span><span class="sxs-lookup"><span data-stu-id="8488e-107">For example, this is the path to a table:</span></span>  
  
 <span data-ttu-id="8488e-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span><span class="sxs-lookup"><span data-stu-id="8488e-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span></span>  
  
 <span data-ttu-id="8488e-109">Und dies ist die URN zum gleichen Objekt:</span><span class="sxs-lookup"><span data-stu-id="8488e-109">And this is the URN to the same object:</span></span>  
  
 <span data-ttu-id="8488e-110">Server [@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' und @Schema='Person']</span><span class="sxs-lookup"><span data-stu-id="8488e-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span></span>  
  
 <span data-ttu-id="8488e-111">Wenn Sie in einem PowerShell-Skript ein SMO-Objekt erstellt haben, können Sie auf die `Urn`-Eigenschaft verweisen, um den URN für das Objekt abzurufen. Anschließend können Sie das `Convert-UrnToPath`-Cmdlet verwenden, um die SMO-URN-Zeichenfolge in einen Windows PowerShell-Pfad zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="8488e-111">If you have created a SMO object in a PowerShell script, you can reference the `Urn` property to get the URN for the object, and then use the `Convert-UrnToPath` cmdlet to convert the SMO URN string to a Windows PowerShell path.</span></span> <span data-ttu-id="8488e-112">Sie können dann mithilfe des Anbieters zu anderen Positionen im Pfad navigieren.</span><span class="sxs-lookup"><span data-stu-id="8488e-112">You can then use the provider to navigate to different locations on the path.</span></span>  
  
 <span data-ttu-id="8488e-113">Wenn Knotennamen erweiterte Zeichen enthalten, die in Windows PowerShell-Pfadnamen nicht unterstützt werden, codiert `Convert-UrnToPath` sie in ihrer hexadezimalen Darstellung.</span><span class="sxs-lookup"><span data-stu-id="8488e-113">If node names contain extended characters that are not supported in Windows PowerShell path names, `Convert-UrnToPath` encodes them in their hexadecimal representation.</span></span> <span data-ttu-id="8488e-114">Zum Beispiel wird "Meine:Tabelle" als "Meine%3ATabelle" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8488e-114">For example "My:Table" is returned as "My%3ATable".</span></span>  
  
 <span data-ttu-id="8488e-115">Führen Sie Folgendes aus, um Beispiele für die Verwendung des Cmdlet in Windows PowerShell zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="8488e-115">For examples of using the cmdlet, in Windows PowerShell, run:</span></span>  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a><span data-ttu-id="8488e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8488e-116">See Also</span></span>  
 <span data-ttu-id="8488e-117">[Abfrage Ausdrücke und Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span><span class="sxs-lookup"><span data-stu-id="8488e-117">[Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span></span>  
 <span data-ttu-id="8488e-118">[SQL Server PowerShell Anbieter](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="8488e-118">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="8488e-119">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="8488e-119">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
