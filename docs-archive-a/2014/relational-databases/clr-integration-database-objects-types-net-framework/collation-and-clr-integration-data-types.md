---
title: Collations-und CLR-Integrations Datentypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data types [CLR integration]
- parameter collation [CLR integration]
- collations [CLR integration]
ms.assetid: 6ebaed8e-2e2b-4f6d-bf4b-bc25452de441
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a5b0367487aeb80355b8c5c976818e1b6c1ac04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725966"
---
# <a name="collation-and-clr-integration-data-types"></a><span data-ttu-id="42274-102">Sortierung und Datentypen für die CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="42274-102">Collation and CLR Integration Data Types</span></span>
  <span data-ttu-id="42274-103">In [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] werden Sortierungen vom `CompareInfo`-Objekt gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="42274-103">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], the `CompareInfo` object handles collations.</span></span> <span data-ttu-id="42274-104">Die Zeichenfolgen-APIs (Application Programming Interface, API) von [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] verwenden die `CompareInfo`-Eigenschaft zusammen mit dem `CultureInfo`-Objekt des aktuellen Threads, um Zeichenfolgenvergleiche durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="42274-104">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] string application programming interfaces (APIs) use the `CompareInfo` property associated with the `CultureInfo` object of the current thread to perform string comparisons.</span></span> <span data-ttu-id="42274-105">Die Standardeinstellung des- `CultureInfo` Objekts basiert auf der Windows-Gebiets Schema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Einstellung für den Computer, auf dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42274-105">The default setting of the `CultureInfo` object is based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows locale setting for the computer on which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="42274-106">Dies bestimmt die Standardvergleichssemantik bei Vergleichen von `CultureInfo`-Werten, wenn `System.String` nicht explizit angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="42274-106">This determines the default comparison semantics, if no explicit `CultureInfo` is specified, for comparisons of `System.String` values.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="42274-107">ändert die `CompareInfo`-Eigenschaft nicht explizit in die Datenbank- oder Serversortierung.</span><span class="sxs-lookup"><span data-stu-id="42274-107">does not explicitly change the `CompareInfo` property to the database or server collation.</span></span> <span data-ttu-id="42274-108">Falls erforderlich, müssen Benutzer die entsprechende `CompareInfo`-Eigenschaft in ihren Routinen festlegen.</span><span class="sxs-lookup"><span data-stu-id="42274-108">If required, users must set the appropriate `CompareInfo` property in their routines.</span></span>  
  
## <a name="parameter-collation"></a><span data-ttu-id="42274-109">Parametersortierung</span><span class="sxs-lookup"><span data-stu-id="42274-109">Parameter Collation</span></span>  
 <span data-ttu-id="42274-110">Wenn Sie eine CLR-Routine (Common Language Runtime) erstellen, und ein an die Routine gebundener Parameter einer CLR-Methode den Typ `SQLString` aufweist, erstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Instanz des Parameters mit der Standardsortierung der Datenbank, die die aufrufende Routine enthält.</span><span class="sxs-lookup"><span data-stu-id="42274-110">When you create a common language runtime (CLR) routine, and a parameter of a CLR method bound to the routine is of type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an instance of the parameter with the default collation of the database containing the calling routine.</span></span> <span data-ttu-id="42274-111">Wenn ein Parameter nicht vom Typ `SqlType` ist (beispielsweise `String`, nicht `SQLString`), werden die Sortierungsinformationen der Datenbank nicht mit dem Parameter verknüpft.</span><span class="sxs-lookup"><span data-stu-id="42274-111">If a parameter is not a `SqlType` (for example, `String` rather than `SQLString`), the collation information from the database is not associated with the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42274-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42274-112">See Also</span></span>  
 [<span data-ttu-id="42274-113">SQL Server-Datentypen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="42274-113">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
