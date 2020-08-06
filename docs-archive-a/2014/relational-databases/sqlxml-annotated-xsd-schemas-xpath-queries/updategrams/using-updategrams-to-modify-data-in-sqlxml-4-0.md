---
title: Verwenden von Updategrams zum Ändern von Daten in SQLXML 4,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- data insertions [SQLXML]
- data deletions [SQLXML]
- updating data [SQLXML]
- modifying data [SQLXML]
- OPENXML function
- updategrams [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- modifying databases
- data modifications [SQLXML]
- deleting data
- inserting data
ms.assetid: b8b3b892-cb73-41d0-b945-bce148d81d9b
author: rothja
ms.author: jroth
ms.openlocfilehash: a4a2397668ed08df91377cc35dea22fd52788580
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619731"
---
# <a name="using-updategrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="b8866-102">Verwenden von Updategrams zum Ändern von Daten in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="b8866-102">Using Updategrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="b8866-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Mithilfe eines Update grams oder der OPENXML-Funktion können Sie eine Datenbank in aus einem vorhandenen XML-Dokument ändern (einfügen, aktualisieren oder löschen) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8866-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="b8866-104">Dieser Abschnitt enthält Informationen über Updategrams und Beispiele für ihre Verwendung.</span><span class="sxs-lookup"><span data-stu-id="b8866-104">This section provides information about updategrams and examples of their usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8866-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b8866-105">In This Section</span></span>  
 [<span data-ttu-id="b8866-106">Einführung in Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-106">Introduction to Updategrams &#40;SQLXML 4.0&#41;</span></span>](introduction-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-107">Stellt grundlegende Informationen und Beispiele für Updategrams bereit.</span><span class="sxs-lookup"><span data-stu-id="b8866-107">Provides basic information and examples of updategrams.</span></span>  
  
 [<span data-ttu-id="b8866-108">Angeben eines Schemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-108">Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;</span></span>](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-109">Erklärt anhand von Beispielen die Zuordnungsschemas mit Anmerkungen in Updategrams.</span><span class="sxs-lookup"><span data-stu-id="b8866-109">Explains and provides examples of annotated mapping schemas in updategrams.</span></span>  
  
 [<span data-ttu-id="b8866-110">NULL-Behandlung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-110">NULL Handling &#40;SQLXML 4.0&#41;</span></span>](null-handling-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-111">Beschreibt das Angeben von NULL für Element- und Attributwerte.</span><span class="sxs-lookup"><span data-stu-id="b8866-111">Describes how to specify NULL for element and attribute values.</span></span>  
  
 [<span data-ttu-id="b8866-112">Einfügen von Daten mit XML-Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-112">Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](inserting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-113">Beschreibt anhand von Beispielen das Verwenden von Updategrams zum Einfügen von Daten.</span><span class="sxs-lookup"><span data-stu-id="b8866-113">Describes and provides examples of using updategrams to insert data.</span></span>  
  
 [<span data-ttu-id="b8866-114">Löschen von Daten mit XML-Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-114">Deleting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](deleting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-115">Beschreibt anhand von Beispielen das Verwenden von Updategrams zum Löschen von Daten.</span><span class="sxs-lookup"><span data-stu-id="b8866-115">Describes and provides examples of using updategrams to delete data.</span></span>  
  
 [<span data-ttu-id="b8866-116">Aktualisieren von Daten mit XML-Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-116">Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](updating-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-117">Beschreibt anhand von Beispielen das Verwenden von Updategrams zum Ändern vorhandener Daten.</span><span class="sxs-lookup"><span data-stu-id="b8866-117">Describes and provides examples of using updategrams to modify existing data.</span></span>  
  
 [<span data-ttu-id="b8866-118">Übergeben von Parametern an Updategrams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-118">Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;</span></span>](passing-parameters-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-119">Beschreibt anhand von Beispielen das Weitergeben von Parametern an Updategrams.</span><span class="sxs-lookup"><span data-stu-id="b8866-119">Describes and provides examples of passing parameters to updategrams.</span></span>  
  
 [<span data-ttu-id="b8866-120">Behandeln von Parallelitäts Problemen in der Datenbank in Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-120">Handling Database Concurrency Issues in Updategrams &#40;SQLXML 4.0&#41;</span></span>](handling-database-concurrency-issues-in-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-121">Beschreibt die verschiedenen Ebenen des möglichen Schutzes für das Behandeln von Parallelitätsproblemen in Updategrams und stellt Beispiele bereit.</span><span class="sxs-lookup"><span data-stu-id="b8866-121">Describes the various levels of protection possible for handling concurrency issues in updategrams, and provides examples.</span></span>  
  
 [<span data-ttu-id="b8866-122">Updategram-Beispielanwendungen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-122">Updategram Sample Applications &#40;SQLXML 4.0&#41;</span></span>](../../../database-engine/dev-guide/updategram-sample-applications-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-123">Stellt Beispielanwendungen bereit, die Updategrams verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8866-123">Provides sample applications that use updategrams.</span></span>  
  
 [<span data-ttu-id="b8866-124">Richtlinien und Einschränkungen von XML-Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b8866-124">Guidelines and Limitations of XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="b8866-125">Listet einige wichtige Aspekte für das Arbeiten mit Updategrams auf.</span><span class="sxs-lookup"><span data-stu-id="b8866-125">Lists some things to remember when working with updategrams.</span></span>  
  
  
