---
title: Tabellarische Modellierung (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44f358f0f36e84ad903a0a4fcb0203291019e7aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615609"
---
# <a name="tabular-modeling-ssas-tabular"></a><span data-ttu-id="f2e9c-102">Tabellarische Modellierung (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="f2e9c-102">Tabular Modeling (SSAS Tabular)</span></span>
  <span data-ttu-id="f2e9c-103">Tabellarische Modelle stellen in Analysis Services Datenbanken im Arbeitsspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-103">Tabular models are in-memory databases in Analysis Services.</span></span> <span data-ttu-id="f2e9c-104">Für die xVelocity-Engine für Datenanalyse im Arbeitsspeicher (VertiPaq) werden modernste Komprimierungsalgorithmen und ein Multithreaded-Abfrageprozessor verwendet, um Berichterstellungsclientanwendungen wie Microsoft Excel und Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] schnellen Zugriff auf Objekte und Daten tabellarischer Modelle zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-104">Using state-of-the-art compression algorithms and multi-threaded query processor, the xVelocity in-memory analytics engine (VertiPaq) delivers fast access to tabular model objects and data by reporting client applications such as Microsoft Excel and Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
 <span data-ttu-id="f2e9c-105">Tabellarische Modelle unterstützen den Datenzugriff in zwei Modi: im Modus mit Zwischenspeicherung und im DirectQuery-Modus.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-105">Tabular models support data access through two modes: Cached mode and DirectQuery mode.</span></span> <span data-ttu-id="f2e9c-106">Im Modus mit Zwischenspeicherung können Sie Daten aus mehreren Quellen einschließlich relationaler Datenbanken, Datenfeeds und einfacher Textdateien integrieren.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-106">In cached mode, you can integrate data from multiple sources including relational databases, data feeds, and flat text files.</span></span> <span data-ttu-id="f2e9c-107">Im DirectQuery-Modus können Sie das Modell im Arbeitsspeicher umgehen, sodass Clientanwendungen Daten direkt aus der (relationalen SQL Server-)Datenquelle abfragen können.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-107">In DirectQuery mode, you can bypass the in-memory model, allowing client applications to query data directly at the (SQL Server relational) source.</span></span>  
  
 <span data-ttu-id="f2e9c-108">Tabellarische Modelle werden in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] unter Verwendung neuer Projektvorlagen für tabellarische Modelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-108">Tabular models are authored in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using new tabular model project templates.</span></span> <span data-ttu-id="f2e9c-109">Sie können Daten aus mehreren Quellen importieren und das Modell erweitern, indem Sie Beziehungen, berechnete Spalten, Measures, KPIs und Hierarchien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-109">You can import data from multiple sources, and then enrich the model by adding relationships, calculated columns, measures, KPIs, and hierarchies.</span></span> <span data-ttu-id="f2e9c-110">Anschließend können die Modelle in einer Instanz von Analysis Services bereitgestellt werden, sodass Berichterstellungsclientanwendungen eine Verbindung mit den Modellen herstellen können.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-110">Models can then be deployed to an instance of Analysis Services where client reporting applications can connect to them.</span></span> <span data-ttu-id="f2e9c-111">Bereitgestellte Modelle können genauso wie mehrdimensionale Modelle in SQL Server Management Studio verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-111">Deployed models can be managed in SQL Server Management Studio just like multidimensional models.</span></span> <span data-ttu-id="f2e9c-112">Sie können partitioniert werden, um die Verarbeitung zu optimieren, und durch die Verwendung der rollenbasierten Sicherheit bis auf Zeilenebene gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="f2e9c-112">They can also be partitioned for optimized processing and secured to the row-level by using role based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2e9c-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f2e9c-113">In This Section</span></span>  
 [<span data-ttu-id="f2e9c-114">Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e9c-114">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
 [<span data-ttu-id="f2e9c-115">Tabellarische Modelldatenbanken &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="f2e9c-115">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-model-databases-ssas-tabular.md)  
  
 [<span data-ttu-id="f2e9c-116">Zugriff auf Daten im tabellarischen Modell</span><span class="sxs-lookup"><span data-stu-id="f2e9c-116">Tabular Model Data Access</span></span>](tabular-model-data-access.md)  
  
  
