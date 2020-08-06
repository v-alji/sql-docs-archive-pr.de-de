---
title: Verwenden von DiffGrams zum Ändern von Daten in SQLXML 4,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- data deletions [SQLXML]
- updating data [SQLXML]
- DiffGrams [SQLXML]
- modifying data [SQLXML]
- .NET Framework [SQLXML], DiffGrams
- XML [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- data modifications [SQLXML]
- record insertion [SQLXML]
- SQLXML, DiffGrams
- deleting data
- record updates [SQLXML]
- record deletions [SQLXML]
ms.assetid: 48b8a8f9-f3af-404f-8c84-f4c3703364d9
author: rothja
ms.author: jroth
ms.openlocfilehash: cc2e24304679a7648f18148eb45f33b9bf719a9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618587"
---
# <a name="using-diffgrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="a8031-102">Verwenden von DiffGrams zum Ändern von Daten in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="a8031-102">Using DiffGrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="a8031-103">Das DiffGram-Format wird in der **DataSet** -Komponente des [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a8031-103">The DiffGram format is introduced in the **DataSet** component of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="a8031-104">Innerhalb von .NET Framework können Sie DiffGrams erstellen und sie zum Ändern der Daten in Tabellen einer Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8031-104">Within the .NET Framework, you can create DiffGrams and use them to modify data in tables in a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8031-105">Dieser Abschnitt enthält eine kurze Einführung in DiffGrams sowie Anwendungsbeispiele.</span><span class="sxs-lookup"><span data-stu-id="a8031-105">This section provides a brief introduction to DiffGrams and examples of how to use them.</span></span> <span data-ttu-id="a8031-106">Es wird vorausgesetzt, dass Sie mit DiffGrams in .NET Framework vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="a8031-106">It is assumed that you are familiar with DiffGrams in the .NET Framework.</span></span> <span data-ttu-id="a8031-107">In dieser Dokumentation liegt der Schwerpunkt auf DiffGram-Problemen, die für SQLXML spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="a8031-107">In this documentation, the primary focus is on DiffGram issues that are specific to SQLXML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8031-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a8031-108">In This Section</span></span>  
 [<span data-ttu-id="a8031-109">Einführung in DiffGrams für SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="a8031-109">Introduction to DiffGrams in SQLXML 4.0</span></span>](introduction-to-diffgrams-in-sqlxml-4-0.md)  
 <span data-ttu-id="a8031-110">Stellt grundlegende Informationen über DiffGrams bereit.</span><span class="sxs-lookup"><span data-stu-id="a8031-110">Provides basic information about Diffgrams.</span></span>  
  
 [<span data-ttu-id="a8031-111">DiffGram-Beispiele &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a8031-111">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
 <span data-ttu-id="a8031-112">Bietet Beispiele für die Verwendung von DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="a8031-112">Provides examples of using Diffgrams.</span></span>  
  
 [<span data-ttu-id="a8031-113">Ausführen eines DiffGram-&#40;mithilfe von ADO SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a8031-113">Executing a DiffGram by Using ADO &#40;SQLXML 4.0&#41;</span></span>](executing-a-diffgram-by-using-ado-sqlxml-4-0.md)  
 <span data-ttu-id="a8031-114">Stellt ein Beispiel für die Ausführung eines DiffGrams mit ActiveX Data Objects (ADO) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a8031-114">Provides an example of executing a Diffgram with ActiveX Data Objects (ADO).</span></span>  
  
 [<span data-ttu-id="a8031-115">Ausführen eines DiffGram-Objekts mit verwalteten SQLXML-Klassen</span><span class="sxs-lookup"><span data-stu-id="a8031-115">Executing a DiffGram by Using SQLXML Managed Classes</span></span>](../net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="a8031-116">Stellt ein Beispiel für das Ausführen eines DiffGrams mit verwalteten SQLXML-Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="a8031-116">Provides an example of executing a Diffgram with SQLXML Managed Classes.</span></span>  
  
  
