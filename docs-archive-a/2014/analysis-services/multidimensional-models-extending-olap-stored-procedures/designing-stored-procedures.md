---
title: Entwerfen gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b33873d6bdf28f7f702bcf186d681f57d6024d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700430"
---
# <a name="designing-stored-procedures"></a><span data-ttu-id="abc85-102">Entwerfen von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="abc85-102">Designing Stored Procedures</span></span>
  <span data-ttu-id="abc85-103">In gespeicherten Prozeduren ist sowohl das administrative Objektmodell "Analysis Management Objects" (AMO) als auch das clientorientierte Objektmodell "[!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional)" (ADO MD) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="abc85-103">Both the administrative object model Analysis Management Objects (AMO) and the client oriented object model [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) are available in stored procedures.</span></span>  
  
 <span data-ttu-id="abc85-104">Gespeicherte Prozeduren müssen sich in ihrem Gültigkeitsbereich (entweder der Server oder die Datenbank) befinden, um auf der aufzurufenden MDX-Ebene (Multidimensional Expressions) sichtbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="abc85-104">Stored procedures must be in scope (either the server or the database) to be visible at the Multidimensional Expressions (MDX) level to be called.</span></span> <span data-ttu-id="abc85-105">Nachdem eine gespeicherte Prozedur aufgerufen wurde, ist ihr Gültigkeitsbereich jedoch nicht auf Aktionen unter dem übergeordneten Element begrenzt.</span><span class="sxs-lookup"><span data-stu-id="abc85-105">However, once a stored procedure is invoked, its scope is not limited to actions under its parent.</span></span> <span data-ttu-id="abc85-106">Eine gespeicherte Prozedur kann überall auf dem Server Änderungen vornehmen. Dabei müssen lediglich die Sicherheitseinschränkungen des Benutzerprozesses, der sie aufruft, oder die Einschränkungen der Transaktion beachtet werden, in der sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="abc85-106">A stored procedure may make changes or modifications anywhere on the server, subject only to the security limitations of the user process that invokes it or to the limitations of the transaction in which it is operating.</span></span>  
  
 <span data-ttu-id="abc85-107">Serverbereichsprozeduren sind in allen Kontexten auf dem Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="abc85-107">Server scope procedures are available in all contexts on the server.</span></span> <span data-ttu-id="abc85-108">Gespeicherte Datenbankbereichsprozeduren sind nur im Datenbankkontext der Datenbank sichtbar, in der sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="abc85-108">Database scope stored procedures are visible only in the database context of the database in which they are defined.</span></span>  
  
 <span data-ttu-id="abc85-109">Wie jede andere MDX-Funktion muss eine gespeicherte Prozedur aufgelöst werden, bevor eine MDX-Sitzung fortgesetzt werden kann. Während ihrer Ausführung sperren gespeicherte Prozeduren MDX-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="abc85-109">As with any MDX function, stored procedure must be resolved before an MDX session can continue; stored procedures lock MDX sessions while executing.</span></span> <span data-ttu-id="abc85-110">Sofern nicht spezielle Gründe für das Anhalten einer MDX-Sitzung bei wartenden Benutzerinteraktionen vorliegen, wird von Benutzerinteraktionen (z. B. Dialogfeldern) abgeraten.</span><span class="sxs-lookup"><span data-stu-id="abc85-110">Unless a specific reason exists to halt an MDX session pending user interaction, then user interactions (such as dialog boxes) are discouraged.</span></span>  
  
## <a name="dependent-assemblies"></a><span data-ttu-id="abc85-111">Abhängige Assemblys</span><span class="sxs-lookup"><span data-stu-id="abc85-111">Dependent Assemblies</span></span>  
 <span data-ttu-id="abc85-112">Alle abhängigen Assemblys müssen in eine Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] geladen werden, um von der Common Language Runtime (CLR) gefunden zu werden.</span><span class="sxs-lookup"><span data-stu-id="abc85-112">All dependent assemblies must be loaded into an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to be found by the common language runtime (CLR).</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="abc85-113">speichert die abhängigen Assemblys im gleichen Ordner wie die Hauptassembly, damit alle Verweise auf Funktionen in den Assemblys von der CLR automatisch aufgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="abc85-113">stores the dependent assemblies in the same folder as the main assembly, so the CLR automatically resolves all function references to functions in those assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc85-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abc85-114">See Also</span></span>  
 <span data-ttu-id="abc85-115">[Verwaltung von mehrdimensionalen Modellen](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="abc85-115">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="abc85-116">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="abc85-116">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
