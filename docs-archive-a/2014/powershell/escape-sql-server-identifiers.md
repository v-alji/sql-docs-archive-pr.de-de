---
title: Escape-Bezeichner für SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8a73e945-daa6-4e5d-93da-10f000f1f3a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1821187632aeeea0b7a18bf9c4d51d933e947d43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618058"
---
# <a name="escape-sql-server-identifiers"></a><span data-ttu-id="0f52d-102">Escape-Bezeichner für SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f52d-102">Escape SQL Server Identifiers</span></span>
  <span data-ttu-id="0f52d-103">Sie können Zeichen, die zwar in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Begrenzungsbezeichnern zulässig sind, nicht jedoch in Windows PowerShell-Pfadnamen, oftmals mit dem Windows PowerShell-Escapezeichen (\`) umwandeln.</span><span class="sxs-lookup"><span data-stu-id="0f52d-103">You can often use the Windows PowerShell back-tick escape character (\`) to escape characters that are allowed in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delimited identifiers but not Windows PowerShell path names.</span></span> <span data-ttu-id="0f52d-104">Einige Zeichen können jedoch nicht mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="0f52d-104">Some characters, however, cannot be escaped.</span></span> <span data-ttu-id="0f52d-105">Zum Beispiel können Sie das Doppelpunktzeichen (:) in Windows PowerShell nicht mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="0f52d-105">For example, you cannot escape the colon character (:) in Windows PowerShell.</span></span> <span data-ttu-id="0f52d-106">Bezeichner mit diesem Zeichen müssen codiert werden.</span><span class="sxs-lookup"><span data-stu-id="0f52d-106">Identifiers with that character must be encoded.</span></span> <span data-ttu-id="0f52d-107">Codierung ist zuverlässiger als das Umwandeln mit Escapezeichen, da das Codieren für alle Zeichen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0f52d-107">Encoding is more reliable than escaping because encoding works for all characters.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0f52d-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0f52d-108">Before You Begin</span></span>  
 <span data-ttu-id="0f52d-109">Das Graviszeichen (\`) befindet sich i. d. R. oben rechts auf der Tastatur, links von der RÜCKTASTE.</span><span class="sxs-lookup"><span data-stu-id="0f52d-109">The back-tick character (\`) is usually on the key in the upper left of the keyboard, under the ESC key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0f52d-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0f52d-110">Examples</span></span>  
 <span data-ttu-id="0f52d-111">Dies ist ein Beispiel für das Umwandeln eines #-Zeichens mittels Escapezeichen:</span><span class="sxs-lookup"><span data-stu-id="0f52d-111">This is an example of escaping a # character:</span></span>  
  
```  
cd SQLSERVER:\SQL\MyComputer\MyInstance\MyDatabase\MySchema\`#MyTempTable  
```  
  
 <span data-ttu-id="0f52d-112">Dies ist ein Beispiel für das Maskieren der Klammer mit dem Escapezeichen beim Angeben von "(lokal)" als Computername:</span><span class="sxs-lookup"><span data-stu-id="0f52d-112">This is an example of escaping the parenthesis when specifying (local) as a computer name:</span></span>  
  
```  
Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f52d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f52d-113">See Also</span></span>  
 <span data-ttu-id="0f52d-114">[SQL Server Bezeichner in PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="0f52d-114">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="0f52d-115">[SQL Server PowerShell Anbieter](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="0f52d-115">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="0f52d-116">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f52d-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
