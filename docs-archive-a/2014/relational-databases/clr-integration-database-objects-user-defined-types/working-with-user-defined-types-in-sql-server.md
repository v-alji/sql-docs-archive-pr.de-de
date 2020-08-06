---
title: Arbeiten mit benutzerdefinierten Typen in SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- user-defined types [CLR integration], queries
- UDTs [CLR integration], queries
- user-defined types [CLR integration], Transact-SQL
- UDTs [CLR integration], Transact-SQL
- queries [CLR integration]
ms.assetid: 807376fb-1f1a-4f2a-8cf8-a622c5858634
author: rothja
ms.author: jroth
ms.openlocfilehash: c9fed9ad4e73102eadd1374ff87d2a46d0ff4126
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698318"
---
# <a name="working-with-user-defined-types-in-sql-server"></a><span data-ttu-id="61d7a-102">Arbeiten mit benutzerdefinierten Typen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="61d7a-102">Working with User-Defined Types in SQL Server</span></span>
  <span data-ttu-id="61d7a-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Mithilfe der regulären Abfrage Syntax können Sie von der Sprache aus auf die Funktionalität des benutzerdefinierten Typs (User-Defined Type, UDT) zugreifen [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61d7a-103">You can access user-defined type (UDT) functionality in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[tsql](../../includes/tsql-md.md)] language by using regular query syntax.</span></span> <span data-ttu-id="61d7a-104">UDTs können für die Definition von Datenbankobjekten, als Variablen in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Batches, in Funktionen und gespeicherten Prozeduren und als Argumente in Funktionen und gespeicherten Prozeduren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61d7a-104">UDTs can be used in the definition of database objects, as variables in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, in functions and stored procedures, and as arguments in functions and stored procedures.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61d7a-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="61d7a-105">In This Section</span></span>  
 [<span data-ttu-id="61d7a-106">Definieren von UDT-Tabellen und -Spalten</span><span class="sxs-lookup"><span data-stu-id="61d7a-106">Defining UDT Tables and Columns</span></span>](working-with-user-defined-types-defining-udt-tables-and-columns.md)  
 <span data-ttu-id="61d7a-107">Beschreibt, wie [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet wird, um eine UDT-Spalte in einer Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61d7a-107">Describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a UDT column in a table.</span></span>  
  
 [<span data-ttu-id="61d7a-108">Bearbeiten von UDT-Daten</span><span class="sxs-lookup"><span data-stu-id="61d7a-108">Manipulating UDT Data</span></span>](working-with-user-defined-types-manipulating-udt-data.md)  
 <span data-ttu-id="61d7a-109">Beschreibt, wie [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet wird, um mit UDT-Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="61d7a-109">Describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to work with UDT data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d7a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61d7a-110">See Also</span></span>  
 [<span data-ttu-id="61d7a-111">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="61d7a-111">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
