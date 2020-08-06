---
title: 'Tutorial: auswerten bewährter Methoden mithilfe der Richtlinien basierten Verwaltung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- best practices analyzer
- Policy-Based Management, best practices policies
- Best Practices [Database Engine]
- Policy-Based Management, evaluating policies
- BPA
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: c7867f9b-7acc-4fae-bde1-63808c403ebc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 42e6b505c71abecce7b56b5cb2544b4e9f4e8f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717044"
---
# <a name="tutorial-evaluating-best-practices-by-using-policy-based-management"></a><span data-ttu-id="2eb00-102">Tutorial: Auswerten von Best Practices mithilfe der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="2eb00-102">Tutorial: Evaluating Best Practices by Using Policy-Based Management</span></span>
  <span data-ttu-id="2eb00-103">Willkommen beim Lernprogramm "Auswerten von Best Practices mithilfe der richtlinienbasierten Verwaltung".</span><span class="sxs-lookup"><span data-stu-id="2eb00-103">Welcome to the Evaluating Best Practices by Using Policy-Based Management tutorial.</span></span> <span data-ttu-id="2eb00-104">Dieses Lernprogramm richtet sich an Benutzer, die zwar mit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], jedoch nicht mit der richtlinienbasierten Verwaltung vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="2eb00-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but new to Policy-Based Management.</span></span> <span data-ttu-id="2eb00-105">Die richtlinienbasierte Verwaltung ist ein System zum Definieren von Richtlinien, die zum Durchsetzen von Standards zur Websiteverwaltung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2eb00-105">Policy-Based Management is a system for defining policies that can be used enforce site administration standards.</span></span> <span data-ttu-id="2eb00-106">Die richtlinienbasierte Verwaltung umfasst eine Reihe von Best Practices-Richtlinien, die Sie verwenden können, um eine Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] zu analysieren und zu bestimmen, ob die Instanz Richtlinien und Empfehlungen für Best Practices erfüllt.</span><span class="sxs-lookup"><span data-stu-id="2eb00-106">Policy-Based Management includes a set of best practices policies that you can use to analyze an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to determine whether the instance meets best practices guidelines and recommendations.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="2eb00-107">Lernziele</span><span class="sxs-lookup"><span data-stu-id="2eb00-107">What You Will Learn</span></span>  
 <span data-ttu-id="2eb00-108">In diesem Lernprogramm erfahren Sie, wie Best Practices-Richtlinien für das [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] bedarfsgesteuert (bzw. "ad hoc") auf der Basis eines Zeitplans auswerten.</span><span class="sxs-lookup"><span data-stu-id="2eb00-108">In this tutorial, you will learn how to evaluate best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on an on-demand (or "ad hoc") basis, or on a scheduled basis.</span></span>  
  
 <span data-ttu-id="2eb00-109">Dieses Lernprogramm ist in zwei Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="2eb00-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="2eb00-110">Lektion 1: Bedarfsgesteuertes Auswerten von Best Practices</span><span class="sxs-lookup"><span data-stu-id="2eb00-110">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
 <span data-ttu-id="2eb00-111">In dieser Lektion führen Sie die bedarfsgesteuerte Auswertung der Richtlinien gegen mindestens eine Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] aus.</span><span class="sxs-lookup"><span data-stu-id="2eb00-111">In this lesson, you perform an on-demand evaluation of the policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="2eb00-112">Lektion 2: Auswerten von Best Practices-Richtlinien auf Basis eines Zeitplans</span><span class="sxs-lookup"><span data-stu-id="2eb00-112">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
 <span data-ttu-id="2eb00-113">In dieser Lektion konfigurieren Sie Best Practices-Richtlinien für die zeitgesteuerte Ausführung.</span><span class="sxs-lookup"><span data-stu-id="2eb00-113">In this lesson, you configure best practices policies to run on a scheduled basis.</span></span> <span data-ttu-id="2eb00-114">Die Lektion zeigt, wie Sie geplante Richtlinien für eine einzelne Instanz konfigurieren und geplante Richtlinien von einem zentralen Ort aus für mehrere Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2eb00-114">The lesson shows how to configure scheduled policies on a single instance, and how to deploy scheduled policies from a central location to multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eb00-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2eb00-115">Requirements</span></span>  
 <span data-ttu-id="2eb00-116">Für diese Lektion benötigen Sie grundlegende Datenbankkenntnisse und grundlegende Kenntnisse von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb00-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="2eb00-117">Damit Sie dieses Lernprogramm verwenden können, muss auf dem Server [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installiert sein.</span><span class="sxs-lookup"><span data-stu-id="2eb00-117">To use this tutorial, the server must have [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="2eb00-118">Lernprogramm starten</span><span class="sxs-lookup"><span data-stu-id="2eb00-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="2eb00-119">Lektion 1: Bedarfsgesteuertes Auswerten von Best Practices</span><span class="sxs-lookup"><span data-stu-id="2eb00-119">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="2eb00-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2eb00-120">See Also</span></span>  
 [<span data-ttu-id="2eb00-121">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="2eb00-121">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
