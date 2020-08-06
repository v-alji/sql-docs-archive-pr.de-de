---
title: Große Konstanten werden im Kompatibilitätsmodus 90 oder höher als Typen mit hohen Werten typisiert. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 58acde8aaebdcac629463edcfb565eed13355ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609021"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a><span data-ttu-id="0a89c-102">Große Konstanten werden als Typen mit großen Werten im Kompatibilitätsmodus 90 oder höher eingegeben</span><span class="sxs-lookup"><span data-stu-id="0a89c-102">Large constants are typed as large-value types in 90 or later compatibility modes</span></span>
  <span data-ttu-id="0a89c-103">Der Upgrade Advisor hat vorhandene große Konstanten erkannt.</span><span class="sxs-lookup"><span data-stu-id="0a89c-103">Upgrade Advisor detected the presence of large constants.</span></span> <span data-ttu-id="0a89c-104">Zeichenfolgenkonstanten und binäre Konstanten, die größer als 8.000 Bytes sind, werden in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] als Datentyp für umfangreiche Objekte behandelt.</span><span class="sxs-lookup"><span data-stu-id="0a89c-104">Character string constants and binary constants that are more than 8,000 bytes in size are treated as large object data types in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="0a89c-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höheren Versionen werden große Zeichen-, Unicode- und binäre Konstanten als Typen mit großen Werten eingegeben.</span><span class="sxs-lookup"><span data-stu-id="0a89c-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, large character, Unicode, and binary constants, are typed as large-value types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0a89c-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="0a89c-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="0a89c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a89c-107">Description</span></span>  
 <span data-ttu-id="0a89c-108">Wenn Zeichenfolgenfunktionen wie CHARINDEX und PATINDEX mit Zeichenfolgen- oder binären Konstanten verwendet werden, die 8.000 Bytes übersteigen, gibt [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] den Fehler Nummer 8116 und [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höhere Versionen den Fehler Nummer 8152 zurück.</span><span class="sxs-lookup"><span data-stu-id="0a89c-108">When string functions, such as CHARINDEX and PATINDEX, are used with string or binary constants that exceed 8,000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] returns error number 8116, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions return error number 8152.</span></span>  
  
 <span data-ttu-id="0a89c-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] geben die Zeichenfolgenfunktionen den Fehler 8116 zurück, wenn sie mit den Datentypen `text`, `ntext` und `image` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a89c-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the string functions return error 8116 when they are used with the `text`, `ntext`, and `image` data types.</span></span>  
  
 <span data-ttu-id="0a89c-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höheren Versionen werden die großen Konstanten wie die Datentypen `varchar(max)`, `nvarchar(max)` und `varbinary(max)` behandelt.</span><span class="sxs-lookup"><span data-stu-id="0a89c-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, the large constants are treated as `varchar(max)`, `nvarchar(max)`, and `varbinary(max)` data types, respectively.</span></span> <span data-ttu-id="0a89c-111">Diese Datentypen sind mit Zeichenfolgenfunktionen kompatibel.</span><span class="sxs-lookup"><span data-stu-id="0a89c-111">These data types are compatible with string functions.</span></span>  
  
 <span data-ttu-id="0a89c-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] oder höheren Versionen gehen Zeichenfolgenfunktionen wie CHARINDEX und PATINDEX davon aus, dass die Zeichenfolge, die die zu findende Abfolge von Zeichen enthält, kleiner als 8.000 Bytes ist.</span><span class="sxs-lookup"><span data-stu-id="0a89c-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, string functions, such as CHARINDEX and PATINDEX, assume the string that contains the sequence of characters to be found is less than 8,000 bytes.</span></span> <span data-ttu-id="0a89c-113">Aus diesem Grund wird der Fehler 8152 für CHARINDEX und PATINDEX ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0a89c-113">This is why error 8152 is raised for CHARINDEX and PATINDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a89c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a89c-114">See Also</span></span>  
 <span data-ttu-id="0a89c-115">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="0a89c-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="0a89c-116">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="0a89c-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
