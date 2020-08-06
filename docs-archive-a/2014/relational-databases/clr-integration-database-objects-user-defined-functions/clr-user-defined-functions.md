---
title: Benutzerdefinierte CLR-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
author: rothja
ms.author: jroth
ms.openlocfilehash: ba7a4a983ec0cb36ef0fd79df44491f7f23f7648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620449"
---
# <a name="clr-user-defined-functions"></a><span data-ttu-id="31769-102">CLR-benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="31769-102">CLR User-Defined Functions</span></span>
  <span data-ttu-id="31769-103">Benutzerdefinierte Funktionen sind Routinen, die Parameter annehmen, Berechnungen oder andere Aktionen ausführen und Ergebnisse zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="31769-103">User-defined functions are routines that can take parameters, perform calculations or other actions, and return a result.</span></span> <span data-ttu-id="31769-104">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] können Sie benutzerdefinierte Funktionen in jeder beliebigen [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-Programmiersprache schreiben, beispielsweise in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="31769-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can write user-defined functions in any [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework programming language, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="31769-105">Es sind zwei Arten von Funktionen verfügbar: Skalarfunktionen, die einen einzigen Wert zurückgeben, und Tabellenwertfunktionen, die einen Satz Zeilen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="31769-105">There are two types of functions: scalar, which returns a single value, and table-valued, which returns a set of rows.</span></span>  
  
 <span data-ttu-id="31769-106">In der folgenden Tabelle sind die Themen dieses Abschnitts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="31769-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="31769-107">CLR-Skalarwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="31769-107">CLR Scalar-Valued Functions</span></span>](clr-scalar-valued-functions.md)  
 <span data-ttu-id="31769-108">Beschreibt Implementierungsanforderungen und führt Beispiele für Skalarwertfunktionen an.</span><span class="sxs-lookup"><span data-stu-id="31769-108">Covers implementation requirements and examples of scalar-valued functions.</span></span>  
  
 [<span data-ttu-id="31769-109">CLR-Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="31769-109">CLR Table-Valued Functions</span></span>](clr-table-valued-functions.md)  
 <span data-ttu-id="31769-110">Erörtert, wie Tabellenwertfunktionen (Table-Valued Functions, TVFs) implementiert und verwendet werden, und beschreibt die Unterschiede zwischen [!INCLUDE[tsql](../../includes/tsql-md.md)]- und CLR-TVFs.</span><span class="sxs-lookup"><span data-stu-id="31769-110">Discusses how to implement and use table-valued functions (TVFs), as well as differences between [!INCLUDE[tsql](../../includes/tsql-md.md)] and common language runtime (CLR) TVFs.</span></span>  
  
 [<span data-ttu-id="31769-111">Benutzerdefinierte CLR-Aggregate</span><span class="sxs-lookup"><span data-stu-id="31769-111">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
 <span data-ttu-id="31769-112">Beschreibt die Implementierung und Verwendung von benutzerdefinierten Aggregaten.</span><span class="sxs-lookup"><span data-stu-id="31769-112">Describes how to implement and use user-defined aggregates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31769-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31769-113">See Also</span></span>  
 [<span data-ttu-id="31769-114">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="31769-114">User-Defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)  
  
  
