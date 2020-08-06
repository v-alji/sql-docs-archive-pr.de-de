---
title: Entfernen Sie UDT-&#39;s, die nach dem reservierten ordpath-Datentyp benannt sind. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 474e910a-6abb-4e28-acc2-055338c011d4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0528d19de17781d863e3a42fdef7db558fe5d190
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726482"
---
# <a name="remove-udt39s-named-after-the-reserved-ordpath-data-type"></a><span data-ttu-id="969d6-102">UDT-&#39;s entfernen, die nach dem reservierten ordpath-Datentyp benannt sind</span><span class="sxs-lookup"><span data-stu-id="969d6-102">Remove UDT&#39;s named after the reserved ORDPATH data type</span></span>
  <span data-ttu-id="969d6-103">Upgrade Advisor hat einen benutzerdefinierten Typ (UDT, User-Defined Type) erkannt, der nach einem Ausdruck benannt ist, der für den `ORDPATH`-Datentyp reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="969d6-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for the `ORDPATH` data type.</span></span>  
  
## <a name="component"></a><span data-ttu-id="969d6-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="969d6-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="969d6-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="969d6-105">Description</span></span>  
 <span data-ttu-id="969d6-106">Die Ausdrücke, die für integrierte Datentypen verwendet werden, sollten nicht als Namen für die Common Language Runtime (CLR) oder Alias-UDTs genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="969d6-106">The terms used for built-in data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="969d6-107">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="969d6-107">Corrective Action</span></span>  
 <span data-ttu-id="969d6-108">Entfernen Sie den UDT, der nach dem Datentyp benannt ist, und erstellen Sie den UDT mit einem nicht reservierten Namen neu.</span><span class="sxs-lookup"><span data-stu-id="969d6-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="969d6-109">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="969d6-109">External Resources</span></span>  
 [<span data-ttu-id="969d6-110">Erstellen eines benutzerdefinierten Typs</span><span class="sxs-lookup"><span data-stu-id="969d6-110">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
  
