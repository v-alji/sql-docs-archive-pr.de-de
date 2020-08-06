---
title: 'Lernprogramm: SQL Server Management Studio | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.tutorialstart.ssms.f1
helpviewer_keywords:
- projects [SQL Server Management Studio], tutorials
- templates [SQL Server], SQL Server Management Studio
- source controls [SQL Server Management Studio], tutorials
- Help [SQL Server], SQL Server Management Studio
- tutorials [SQL Server Management Studio]
- Transact-SQL tutorials
- solutions [SQL Server Management Studio], tutorials
- SQL Server Management Studio [SQL Server], tutorials
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d2bade70-07cf-4d94-b5d2-88aecb538ed1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8206fea828d6169975dc1d026a22e18e682f71e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621811"
---
# <a name="tutorial-sql-server-management-studio"></a><span data-ttu-id="d9b20-102">Tutorial: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9b20-102">Tutorial: SQL Server Management Studio</span></span>
  <span data-ttu-id="d9b20-103">Das [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Lernprogramm bietet eine Einführung in die integrierte Umgebung zum Verwalten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="d9b20-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutorial introduces you to the integrated environment for managing your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d9b20-104">verfügt über eine grafische Oberfläche zum Konfigurieren, Überwachen und Verwalten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="d9b20-104">presents a graphical interface for configuring, monitoring, and administering instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d9b20-105">Darüber hinaus vermittelt Ihnen das Lernprogramm, wie Sie die von Ihren Anwendungen, z. B. Datenbanken und Data Warehouses, verwendeten Datenebenenkomponenten bereitstellen, überwachen und aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d9b20-105">It also allows you to deploy, monitor, and upgrade the data-tier components used by your applications, such as databases and data warehouses.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d9b20-106">stellt auch Editoren für die [!INCLUDE[tsql](../../includes/tsql-md.md)]-, MDX-, DMX- und XML-Sprache bereit, um Skripts zu bearbeiten und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="d9b20-106">also provides [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML language editors for editing and debugging scripts.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="d9b20-107">Lernziele</span><span class="sxs-lookup"><span data-stu-id="d9b20-107">What You Will Learn</span></span>  
 <span data-ttu-id="d9b20-108">Mit diesem Lernprogramm können Sie die Präsentation von Informationen in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] erlernen und herausfinden, wie Sie die Funktionen effektiv verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9b20-108">This tutorial will help you understand the presentation of information in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to take advantage of the features.</span></span> <span data-ttu-id="d9b20-109">Beachten Sie, dass dieses Lernprogramm für die vollständige Installation von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] gilt, die in allen Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], außer [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d9b20-109">Note that this tutorial applies to the complete installation of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] that is included with all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="d9b20-110">Die Funktionalität zu grundlegenden Installationen von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] und [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]-Installationen, die im Lieferumfang von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] enthalten sind, unterscheidet sich etwas von den in diesem Lernprogramm behandelten Informationen.</span><span class="sxs-lookup"><span data-stu-id="d9b20-110">Functionality for basic installations of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] installations that ship with [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] is slightly different than what is presented in this tutorial.</span></span>  
  
 <span data-ttu-id="d9b20-111">Am besten machen Sie sich mit [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] vertraut, indem Sie einige praktischen Aufgaben durchführen.</span><span class="sxs-lookup"><span data-stu-id="d9b20-111">The best way to get acquainted with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is through hands-on practice.</span></span> <span data-ttu-id="d9b20-112">In diesem Lernprogramm erfahren Sie, wie Sie die Komponenten von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] verwalten und wie Sie die Funktionen finden, die Sie regelmäßig verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9b20-112">This tutorial will teach you how to manage the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to find the features that you use regularly.</span></span>  
  
 <span data-ttu-id="d9b20-113">Dieses Lernprogramm ist in drei Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="d9b20-113">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="d9b20-114">Lektion 1: Grundlegendes zur Navigation in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9b20-114">Lesson 1: Basic Navigation in SQL Server Management Studio</span></span>](lesson-1-basic-navigation-in-sql-server-management-studio.md)  
 <span data-ttu-id="d9b20-115">In dieser Lektion erfahren Sie, wie Sie die Komponenten von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]verwenden, wie das Umgebungslayout neu konfiguriert wird und wie Sie das Standardlayout wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b20-115">In this lesson you will learn how to use the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], how to reconfigure the environment layout, and how to restore the default layout.</span></span>  
  
 [<span data-ttu-id="d9b20-116">Lektion 2: Schreiben von Transact-SQL-Code</span><span class="sxs-lookup"><span data-stu-id="d9b20-116">Lesson 2: Writing Transact-SQL</span></span>](lesson-2-writing-transact-sql.md)  
 <span data-ttu-id="d9b20-117">In dieser Lektion erfahren Sie, wie der Abfrage-Editor geöffnet wird, wie Code verwaltet wird und wie weitere, neue Funktionen des Abfrage-Editors verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b20-117">In this lesson, you will learn how to open Query Editor, how to manage code, and how to use the other new features of Query Editor.</span></span>  
  
 [<span data-ttu-id="d9b20-118">Lektion 3: Verwenden von Vorlagen, Lösungen und Skriptprojekten</span><span class="sxs-lookup"><span data-stu-id="d9b20-118">Lesson 3: Working with Templates, Solutions, and Script Projects</span></span>](lesson-3-working-with-templates-solutions-and-script-projects.md)  
 <span data-ttu-id="d9b20-119">In dieser Lektion erfahren Sie, wie Sie Vorlagen verwenden und Skripts in Lösungen und Projekten organisieren.</span><span class="sxs-lookup"><span data-stu-id="d9b20-119">In this lesson you will learn how to use templates, and organize scripts into solutions and projects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9b20-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d9b20-120">Requirements</span></span>  
 <span data-ttu-id="d9b20-121">Dieses Lernprogramm richtet sich an erfahrene Datenbankadministratoren und -entwickler, die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]noch nicht kennen, aber mit Datenbankkonzepten und der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Programmiersprache vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="d9b20-121">This tutorial is intended for experienced database administrators and database developers who are not familiar with [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], but who are who are familiar with database concepts and the [!INCLUDE[tsql](../../includes/tsql-md.md)] language.</span></span>  
  
 <span data-ttu-id="d9b20-122">Auf Ihrem System müssen zum Verwenden dieses Lernprogramms folgende Anwendungen installiert sein:</span><span class="sxs-lookup"><span data-stu-id="d9b20-122">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="d9b20-123">oder eine höhere Version mit den [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbanken.</span><span class="sxs-lookup"><span data-stu-id="d9b20-123">or a later version with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample databases.</span></span> <span data-ttu-id="d9b20-124">Aus Sicherheitsgründen werden die Beispieldatenbanken standardmäßig nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="d9b20-124">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="d9b20-125">Informationen zur Installation der Beispieldatenbanken finden Sie unter [Installieren der SQL Server-Beispiele und -Beispieldatenbanken](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="d9b20-125">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
-   <span data-ttu-id="d9b20-126">Internet Explorer 9,0 oder höher</span><span class="sxs-lookup"><span data-stu-id="d9b20-126">Internet Explorer 9.0 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b20-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9b20-127">See Also</span></span>  
 [<span data-ttu-id="d9b20-128">Lernprogramme zur Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="d9b20-128">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
