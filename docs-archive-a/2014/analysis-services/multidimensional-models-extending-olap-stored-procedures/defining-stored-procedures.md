---
title: Definieren von gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services]
- OLAP [Analysis Services], stored procedures
- external routines [Analysis Services]
- stored procedures [Analysis Services], about stored procedures
ms.assetid: f9c57d91-f60f-4f0e-8f7f-d87f4ba97b7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc1f028f822d2289ee79702feb2494487040977c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700425"
---
# <a name="defining-stored-procedures"></a><span data-ttu-id="1af07-102">Definieren von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-102">Defining Stored Procedures</span></span>
  <span data-ttu-id="1af07-103">Sie können gespeicherte Prozeduren verwenden, um externe Routinen von aufzurufen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1af07-103">You can use stored procedures to call external routines from [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="1af07-104">Sie können den Aufruf von externen Routinen über eine gespeicherte Prozedur in jeder beliebigen CLR-Sprache (Common Language Runtime) schreiben, z. B. C, C++, C#, Visual Basic oder Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="1af07-104">You can write an external routines called by a stored procedure in any common language runtime (CLR) language, such as C, C++, C#, Visual Basic, or Visual Basic .NET.</span></span> <span data-ttu-id="1af07-105">Eine gespeicherte Prozedur kann einmal erstellt werden und dann in zahlreichen Kontexten aufgerufen werden, z. B. von anderen gespeicherten Prozeduren, berechneten Measures oder Clientanwendungen.</span><span class="sxs-lookup"><span data-stu-id="1af07-105">A stored procedure can be created once and called from many contexts, such as other stored procedures, calculated measures, or client applications.</span></span> <span data-ttu-id="1af07-106">Gespeicherte Prozeduren vereinfachen die Entwicklung und Implementierung von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbanken, da gemeinsamer Code nur einmal entwickelt werden muss und an einem einzelnen Ort gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1af07-106">Stored procedures simplify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="1af07-107">Mit gespeicherten Prozeduren kann Anwendungen Geschäftsfunktionalität hinzugefügt werden, die von der systemeigenen Funktionalität von MDX nicht bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1af07-107">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="1af07-108">Dieser Abschnitt enthält die Informationen, die zum Verständnis, Entwurf und zur Implementierung von gespeicherten Prozeduren erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1af07-108">This section provides the information necessary to understand, design, and implement stored procedures.</span></span>  
  
|<span data-ttu-id="1af07-109">Thema</span><span class="sxs-lookup"><span data-stu-id="1af07-109">Topic</span></span>|<span data-ttu-id="1af07-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1af07-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1af07-111">Entwerfen von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-111">Designing Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/designing-stored-procedures.md)|<span data-ttu-id="1af07-112">Beschreibt das Entwerfen von Assemblys zum Verwenden mit [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1af07-112">Describes how to design assemblies for use with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1af07-113">Erstellen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-113">Creating Stored Procedures</span></span>](creating-stored-procedures.md)|<span data-ttu-id="1af07-114">Beschreibt das Erstellen von Assemblys für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1af07-114">Describes how to create assemblies for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1af07-115">Aufrufen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-115">Calling Stored Procedures</span></span>](calling-stored-procedures.md)|<span data-ttu-id="1af07-116">Stellt Informationen zum Verwenden von Assemblys in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereit.</span><span class="sxs-lookup"><span data-stu-id="1af07-116">Provides information on how to use assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1af07-117">Zugreifen auf den Abfragekontext in gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-117">Accessing Query Context in Stored Procedures</span></span>](accessing-query-context-in-stored-procedures.md)|<span data-ttu-id="1af07-118">Beschreibt das Zugreifen auf Informationen zum Gültigkeitsbereich und Kontext mit Assemblys.</span><span class="sxs-lookup"><span data-stu-id="1af07-118">Describes how to access scope and context information with assemblies.</span></span>|  
|[<span data-ttu-id="1af07-119">Festlegen der Sicherheit für gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-119">Setting Security for Stored Procedures</span></span>](setting-security-for-stored-procedures.md)|<span data-ttu-id="1af07-120">Beschreibt das Konfigurieren der Sicherheit für Assemblys in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1af07-120">Describes how to configure security for assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1af07-121">Debuggen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1af07-121">Debugging Stored Procedures</span></span>](debugging-stored-procedures.md)|<span data-ttu-id="1af07-122">Beschreibt das Debuggen von Assemblys in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1af07-122">Describes how to debug assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1af07-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1af07-123">See Also</span></span>  
 [<span data-ttu-id="1af07-124">Verwaltung von mehrdimensionalen Modellassemblys</span><span class="sxs-lookup"><span data-stu-id="1af07-124">Multidimensional Model Assemblies Management</span></span>](../multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
