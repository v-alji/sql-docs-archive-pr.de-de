---
title: Zugreifen auf benutzerdefinierte Typen in ADO.net | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: a94e333ad743ed07dff6b973ebfe227312a1cab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620445"
---
# <a name="accessing-user-defined-types-in-adonet"></a><span data-ttu-id="b0a2c-102">Zugreifen auf benutzerdefinierte Typen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b0a2c-102">Accessing User-Defined Types in ADO.NET</span></span>
  <span data-ttu-id="b0a2c-103">Benutzerdefinierte Typen (User-Defined Types, UDTs) werden mit einer beliebigen Sprache geschrieben, die von der [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework Common Language Runtime (CLR) unterstützt wird, die überprüfbaren Code erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-103">User-defined types (UDTs) are written using any of the languages supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="b0a2c-104">Dazu gehören [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# und [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-104">This includes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span></span> <span data-ttu-id="b0a2c-105">UDTs ermöglichen das Speichern von Objekten und benutzerdefinierten Datenstrukturen in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-105">UDTs allow objects and custom data structures to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="b0a2c-106">Die Daten werden als öffentliche Elemente einer .NET Framework-Klasse oder -Struktur verfügbar gemacht. Das Verhalten wird durch die Methoden der Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-106">The data is exposed as public members of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span> <span data-ttu-id="b0a2c-107">Ein UDT kann als Spaltendefinition einer Tabelle, als Variable in einem [!INCLUDE[tsql](../../includes/tsql-md.md)]-Batch oder als Argument einer [!INCLUDE[tsql](../../includes/tsql-md.md)]-Funktion oder gespeicherten Prozedur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-107">A UDT can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
 <span data-ttu-id="b0a2c-108">In ADO.NET macht der `System.Data.SqlClient`-Anbieter UDTs wie folgt verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b0a2c-108">In ADO.NET, the `System.Data.SqlClient` provider exposes UDTs in the following ways:</span></span>  
  
-   <span data-ttu-id="b0a2c-109">Über `System.Data.SqlClient.SqlDataReader` als Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-109">Through the `System.Data.SqlClient.SqlDataReader` as an object.</span></span>  
  
-   <span data-ttu-id="b0a2c-110">Über `SqlDataReader` als Rohbytes.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-110">Through the `SqlDataReader` as raw bytes.</span></span>  
  
-   <span data-ttu-id="b0a2c-111">Als Parameter eines `System.Data.SqlClient.SqlParameter`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-111">As a parameter of a `System.Data.SqlClient.SqlParameter` object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0a2c-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b0a2c-112">In This Section</span></span>  
 [<span data-ttu-id="b0a2c-113">Abrufen von UDT-Daten</span><span class="sxs-lookup"><span data-stu-id="b0a2c-113">Retrieving UDT Data</span></span>](accessing-user-defined-types-retrieving-udt-data.md)  
 <span data-ttu-id="b0a2c-114">Beschreibt, wie UDT-Daten abgerufen und Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-114">Describes how to retrieve UDT data and how to specify parameters.</span></span>  
  
 [<span data-ttu-id="b0a2c-115">Aktualisieren von UDT-Spalten mit DataAdapters</span><span class="sxs-lookup"><span data-stu-id="b0a2c-115">Updating UDT Columns with DataAdapters</span></span>](accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 <span data-ttu-id="b0a2c-116">Beschreibt, wie mit UDTs in `DataSets` gearbeitet wird und wie UDT-Daten mit `DataAdapters` aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b0a2c-116">Describes how to work with UDTs in `DataSets` and how to update UDT data using `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a2c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0a2c-117">See Also</span></span>  
 [<span data-ttu-id="b0a2c-118">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="b0a2c-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
