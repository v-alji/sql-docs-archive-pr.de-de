---
title: Vorlagen-Explorer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.wb.templates.f1
- sql12.swb.templates.explorer.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7ee1e6261c759580df3a836f9cc4b500a77ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619509"
---
# <a name="template-explorer"></a><span data-ttu-id="e27fa-102">Template Explorer</span><span class="sxs-lookup"><span data-stu-id="e27fa-102">Template Explorer</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e27fa-103">stellt eine Vielzahl von Vorlagen bereit.</span><span class="sxs-lookup"><span data-stu-id="e27fa-103">provides a variety of templates.</span></span> <span data-ttu-id="e27fa-104">Vorlagen sind Dateien mit Codevorlagen, die SQL-Skripts enthalten, mit deren Hilfe Sie Objekte in einer Datenbank erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e27fa-104">Templates are boilerplate files containing SQL scripts that help you create objects in a database.</span></span> <span data-ttu-id="e27fa-105">Beim ersten Öffnen des Vorlagen-Explorers wird eine Kopie der Vorlagen im Benutzerordner unter "c:\Users" unter "appdata\roaming\microsoft\sql Server Management studio\120\templates" abgelegt.</span><span class="sxs-lookup"><span data-stu-id="e27fa-105">The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span></span>  
  
 <span data-ttu-id="e27fa-106">Sie können die verfügbaren Vorlagen in Vorlagen-Explorer durchsuchen und dann eine Vorlage öffnen, um den Code in einem Fenster des Code-Editors zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="e27fa-106">You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window.</span></span> <span data-ttu-id="e27fa-107">Sie können auch benutzerdefinierte Vorlagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="e27fa-107">You can also create custom templates.</span></span>  
  
## <a name="benefits-of-templates"></a><span data-ttu-id="e27fa-108">Vorteile von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e27fa-108">Benefits of Templates</span></span>  
 <span data-ttu-id="e27fa-109">Vorlagen sind für Projektmappen, Projekte und verschiedene Arten von Code-Editoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e27fa-109">Templates are available for solutions, projects, and various types of code editors.</span></span> <span data-ttu-id="e27fa-110">Vorlagen dienen zum Erstellen von Objekten wie Datenbanken, Tabellen, Sichten, Indizes, gespeicherten Prozeduren, Trigger, Statistiken und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e27fa-110">Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions.</span></span> <span data-ttu-id="e27fa-111">Darüber hinaus sind Vorlagen vorhanden, mit denen Sie Ihren Server verwalten können, indem Sie erweiterte Eigenschaften, Verbindungsserver, Anmeldenamen, Rollen, Benutzer und Vorlagen für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="e27fa-111">In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e27fa-112">Die von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] bereitgestellten Vorlageskripts enthalten Parameter, die beim Anpassen von Code hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="e27fa-112">The template scripts provided with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contain parameters to help you customize the code.</span></span> <span data-ttu-id="e27fa-113">Verwenden Sie nach dem Öffnen einer Vorlage das Dialogfeld **Vorlagenparameter ersetzen** , um Werte in das Skript einzufügen.</span><span class="sxs-lookup"><span data-stu-id="e27fa-113">When you open a template, Use the **Replace Template Parameters** dialog box to insert values into the script.</span></span>  
  
 <span data-ttu-id="e27fa-114">Für regelmäßig auszuführende Aufgaben können Sie benutzerdefinierte Vorlagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="e27fa-114">Create custom templates for tasks you perform frequently.</span></span> <span data-ttu-id="e27fa-115">Sie können Ihre benutzerdefinierten Skripts in die vorhandenen Ordner einfügen oder eine neue Ordnerstruktur erstellen.</span><span class="sxs-lookup"><span data-stu-id="e27fa-115">Organize your custom scripts into the existing folders or create a new folder structure.</span></span>  
  
 <span data-ttu-id="e27fa-116">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor unterstützt darüber hinaus Codeausschnitte, die an einer bestimmten Stelle im Skript eingefügt werden können, indem Sie mit der rechten Maustaste an diese Stelle klicken.</span><span class="sxs-lookup"><span data-stu-id="e27fa-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e27fa-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e27fa-117">Related Tasks</span></span>  
 <span data-ttu-id="e27fa-118">Erste Schritte mit Vorlagen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e27fa-118">Use the following topics to get started with templates</span></span>  
  
|<span data-ttu-id="e27fa-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e27fa-119">**Description**</span></span>|<span data-ttu-id="e27fa-120">**Thema**</span><span class="sxs-lookup"><span data-stu-id="e27fa-120">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="e27fa-121">Beschreibt, wie der Code aus einer Vorlage in ein Code-Editorfenster integriert wird.</span><span class="sxs-lookup"><span data-stu-id="e27fa-121">Describes how to incorporate the code from a template into a code editor window.</span></span>|[<span data-ttu-id="e27fa-122">Öffnen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="e27fa-122">Open a Template</span></span>](open-a-template.md)|  
|<span data-ttu-id="e27fa-123">Beschreibt, wie Vorlagenparameterwerte nach dem Öffnen einer Vorlage in einem Code-Editor ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e27fa-123">Describes how to replace template parameter values after opening a template in a code editor.</span></span>|[<span data-ttu-id="e27fa-124">Vorlagenparameter ersetzen</span><span class="sxs-lookup"><span data-stu-id="e27fa-124">Replace Template Parameters</span></span>](replace-template-parameters.md)|  
  
  
