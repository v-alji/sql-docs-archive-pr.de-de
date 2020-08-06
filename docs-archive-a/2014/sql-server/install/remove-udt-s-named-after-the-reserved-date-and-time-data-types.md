---
title: Entfernen Sie UDT-&#39;s, die nach den reservierten Datums-und Uhrzeit Datentypen benannt sind. Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620144"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a><span data-ttu-id="d9565-102">UDT-&#39;s entfernen, die nach den reservierten Datums-und Uhrzeit Datentypen benannt sind</span><span class="sxs-lookup"><span data-stu-id="d9565-102">Remove UDT&#39;s named after the reserved DATE and TIME data types</span></span>
  <span data-ttu-id="d9565-103">Der Upgrade Advisor hat einen benutzerdefinierten Typ (UDT, User-Defined Type) erkannt, der nach einem Ausdruck benannt ist, der entweder für den `date`-Datentyp oder den `time`-Datentyp reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="d9565-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `date` or the `time` data types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d9565-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="d9565-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d9565-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d9565-105">Description</span></span>  
 <span data-ttu-id="d9565-106">Die Ausdrücke, die für Datentypen verwendet werden, sollten nicht als Namen für die Common Language Runtime (CLR) oder Alias-UDTs genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="d9565-106">The terms used for data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d9565-107">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="d9565-107">Corrective Action</span></span>  
 <span data-ttu-id="d9565-108">Entfernen Sie den UDT, der nach dem Datentyp benannt ist, und erstellen Sie den UDT mit einem nicht reservierten Namen neu.</span><span class="sxs-lookup"><span data-stu-id="d9565-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
  
