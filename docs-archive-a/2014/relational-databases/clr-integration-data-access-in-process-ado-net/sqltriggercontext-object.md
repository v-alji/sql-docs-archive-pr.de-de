---
title: SqlTriggerContext-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlTriggerContext object
- triggers [CLR integration]
- context [CLR integration]
ms.assetid: 472a2d0b-64ae-4877-8f11-a5620aa698b7
author: rothja
ms.author: jroth
ms.openlocfilehash: f7eae3d290a70bedee0ed9badf9e6d0503caa2bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725990"
---
# <a name="sqltriggercontext-object"></a><span data-ttu-id="a117e-102">SqlTriggerContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="a117e-102">SqlTriggerContext Object</span></span>
  <span data-ttu-id="a117e-103">Die `SqlTriggerContext`-Klasse stellt Kontextinformationen über den Trigger zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a117e-103">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="a117e-104">Diese Kontextinformationen umfassen den Typ der Aktion, die den Trigger ausgelöst hat, die bei einem UPDATE-Vorgang aktualisierten Spalten und im Falle eines DDL-Triggers (Data Definition Language) eine XML-`EventData`-Struktur, die den auslösenden Vorgang beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a117e-104">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a data definition language (DDL) trigger, an XML `EventData` structure that describes the triggering operation.</span></span> <span data-ttu-id="a117e-105">Weitere Informationen und Beispiele zur Verwendung der- `SqlTriggerContext` Klasse finden Sie unter [CLR-Trigger](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="a117e-105">For more information and examples of how to use the `SqlTriggerContext` class, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
 <span data-ttu-id="a117e-106">Weitere Informationen finden Sie in der Referenz zu der `Microsoft.SqlServer.Server.SqlTriggerContext`-Klasse und in der .NET Framework SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a117e-106">For more information, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the .NET Framework SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a117e-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a117e-107">See Also</span></span>  
 <span data-ttu-id="a117e-108">[CLR-Trigger](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="a117e-108">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="a117e-109">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a117e-109">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
