---
title: Datenbank-Engine – Programmierung der erweiterten gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], programming
- stored procedures [SQL Server], extended
- Database Engine [SQL Server], stored procedures
- macros [SQL Server]
- Extended Stored Procedure API [SQL Server]
ms.assetid: 158a6765-0542-4e84-b5ab-f173d946ef5e
author: rothja
ms.author: jroth
ms.openlocfilehash: fecb8f996ddfcaede83cdb330e9c82bffdce5819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622162"
---
# <a name="database-engine-extended-stored-procedure-programming"></a><span data-ttu-id="f1010-102">Datenbank-Engine – Programmierung der erweiterten gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="f1010-102">Database Engine Extended Stored Procedure Programming</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f1010-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="f1010-103">Use CLR Integration instead.</span></span> <span data-ttu-id="f1010-104">Weitere Informationen finden Sie unter [Common Language Runtime &#40;CLR&#41; Programmierkonzepte für die Integration](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="f1010-104">For more information, see [Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span></span>  
  
 <span data-ttu-id="f1010-105">Die [!INCLUDE[msCoName](../includes/msconame-md.md)] API für erweiterte gespeicherte Prozeduren bietet eine serverbasierte Anwendungsprogrammierschnittstelle (Application Programming Interface, API) zum Erweitern der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="f1010-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Extended Stored Procedure API provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="f1010-106">Die API besteht aus C- und C++-Funktionen und Makros, die zum Erstellen von Anwendungen in den folgenden Kategorien verwendet werden: erweiterte gespeicherte Prozeduren und Gateway-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f1010-106">The API consists of C and C++ functions and macros used to build applications in the following categories: extended stored procedures and gateway applications.</span></span>  
  
 <span data-ttu-id="f1010-107">Erweiterte gespeicherte Prozeduren ermöglichen es Ihnen, eigene externe Routinen in einer Programmiersprache, wie z. B. C, zu erstellen. Erweiterte gespeicherte Prozeduren werden für die Benutzer wie normale gespeicherte Prozeduren dargestellt und auch genauso ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1010-107">Extended stored procedures allow you to create your own external routines in a programming language such as C. The extended stored procedures appear to users as typical stored procedures and are executed in the same way.</span></span> <span data-ttu-id="f1010-108">Sie können Parameter an erweiterte gespeicherte Prozeduren übergeben, und die Prozeduren können Ergebnisse und Rückgabestatuswerte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f1010-108">Parameters can be passed to extended stored procedures, and they can return results and return status.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1010-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f1010-109">In This Section</span></span>  
 [<span data-ttu-id="f1010-110">Programmieren erweiterter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f1010-110">Programming Extended Stored Procedures</span></span>](extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)  
 <span data-ttu-id="f1010-111">Erklärt, wie erweiterte gespeicherte Prozeduren erstellt, verwaltet und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f1010-111">Explains how to create, manage, and use extended stored procedures.</span></span>  
  
 [<span data-ttu-id="f1010-112">Erweiterte gespeicherte Prozeduren – Programmierreferenz</span><span class="sxs-lookup"><span data-stu-id="f1010-112">Extended Stored Procedures Programmer's Reference</span></span>](extended-stored-procedures-reference/database-engine-extended-stored-procedures-reference.md)  
 <span data-ttu-id="f1010-113">Enthält Referenzthemen zur API für erweiterte gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="f1010-113">Contains reference topics for the Extended Stored Procedure API.</span></span>  
  
  
