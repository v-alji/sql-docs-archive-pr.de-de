---
title: Definieren von UDT-Tabellen und-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], columns
- UDTs [CLR integration], columns
- columns [CLR integration]
- user-defined types [CLR integration], tables
- tables [CLR integration]
- UDTs [CLR integration], tables
- UDTs [CLR integration], indexes
- user-defined types [CLR integration], indexes
- indexes [CLR integration]
ms.assetid: aea495f4-ce26-4952-b019-38f012625f3f
author: rothja
ms.author: jroth
ms.openlocfilehash: aa9596629ed8b4877b1793fa0c56956c52989499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630670"
---
# <a name="defining-udt-tables-and-columns"></a><span data-ttu-id="ac769-102">Definieren von UDT-Tabellen und -Spalten</span><span class="sxs-lookup"><span data-stu-id="ac769-102">Defining UDT Tables and Columns</span></span>
  <span data-ttu-id="ac769-103">Nachdem die Assembly, die die UDT-Definition (User-Defined Type, benutzerdefinierter Typ) enthält, in einer-Datenbank registriert wurde [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , kann Sie in einer Spaltendefinition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac769-103">Once the assembly containing the user-defined type (UDT) definition has been registered in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, it can be used in a column definition.</span></span>  
  
## <a name="creating-tables-with-udts"></a><span data-ttu-id="ac769-104">Erstellen von Tabellen mit UDTs</span><span class="sxs-lookup"><span data-stu-id="ac769-104">Creating Tables with UDTs</span></span>  
 <span data-ttu-id="ac769-105">Es gibt keine spezielle Syntax für das Erstellen einer UDT-Spalte in einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ac769-105">There is no special syntax for creating a UDT column in a table.</span></span> <span data-ttu-id="ac769-106">Sie können den Namen des UDT in einer Spaltendefinition verwenden, als wäre er einer der systeminternen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="ac769-106">You can use the name of the UDT in a column definition as though it were one of the intrinsic [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="ac769-107">Die folgende CREATE TABLE- [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisung erstellt eine Tabelle mit dem Namen " **Points**" mit einer Spalte mit dem Namen " **ID",** die als `int` Identitäts Spalte und \ den Primärschlüssel für die Tabelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ac769-107">The following CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates a table named **Points**, with a column named **ID,** which is defined as an `int` identity column and \ the primary key for the table.</span></span> <span data-ttu-id="ac769-108">Die zweite Spalte hat den Namen **PointValue**und den Datentyp **Point**.</span><span class="sxs-lookup"><span data-stu-id="ac769-108">The second column is named **PointValue**, with a data type of **Point**.</span></span> <span data-ttu-id="ac769-109">Der in diesem Beispiel verwendete Schema Name lautet **dbo**.</span><span class="sxs-lookup"><span data-stu-id="ac769-109">The schema name used in this example is **dbo**.</span></span> <span data-ttu-id="ac769-110">Beachten Sie, dass Sie über die erforderlichen Berechtigungen verfügen müssen, um einen Schemanamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ac769-110">Note that you must have the necessary permissions to specify a schema name.</span></span> <span data-ttu-id="ac769-111">Wenn Sie den Schemanamen nicht angeben, wird das Standardschema für den Datenbankbenutzer verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac769-111">If you omit the schema name, the default schema for the database user is used.</span></span>  
  
```  
CREATE TABLE dbo.Points   
(ID int IDENTITY(1,1) PRIMARY KEY, PointValue Point)  
```  
  
## <a name="creating-indexes-on-udt-columns"></a><span data-ttu-id="ac769-112">Erstellen von Indizes für UDT-Spalten</span><span class="sxs-lookup"><span data-stu-id="ac769-112">Creating Indexes on UDT Columns</span></span>  
 <span data-ttu-id="ac769-113">Es gibt zwei Optionen für das Indizieren einer UDT-Spalte:</span><span class="sxs-lookup"><span data-stu-id="ac769-113">There are two options for indexing a UDT column:</span></span>  
  
-   <span data-ttu-id="ac769-114">Indizieren Sie den vollständigen Wert.</span><span class="sxs-lookup"><span data-stu-id="ac769-114">Index the full value.</span></span> <span data-ttu-id="ac769-115">In diesem Fall, wenn der UDT binär sortiert ist, können Sie einen Index über die gesamte UDT-Spalte mithilfe der CREATE INDEX-[!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac769-115">In this case, if the UDT is binary ordered, you can create an index over the entire UDT column by using the CREATE INDEX [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="ac769-116">Indizieren Sie UDT-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="ac769-116">Index UDT expressions.</span></span> <span data-ttu-id="ac769-117">Sie können Indizes auf persistenten berechneten Spalten über UDT-Ausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac769-117">You can create indexes on persisted computed columns over UDT expressions.</span></span> <span data-ttu-id="ac769-118">Der UDT-Ausdruck kann ein Feld, eine Methode oder eine Eigenschaft eines UDT sein.</span><span class="sxs-lookup"><span data-stu-id="ac769-118">The UDT expression can be a field, method, or property of a UDT.</span></span> <span data-ttu-id="ac769-119">Der Ausdruck muss deterministisch sein und darf keinen Datenzugriff ausführen.</span><span class="sxs-lookup"><span data-stu-id="ac769-119">The expression must be deterministic and must not perform data access.</span></span>  
  
 <span data-ttu-id="ac769-120">Weitere Informationen finden Sie unter [benutzerdefinierte CLR-Typen](clr-user-defined-types.md) und [Create Index &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac769-120">For more information, see [CLR User-Defined Types](clr-user-defined-types.md) and [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac769-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac769-121">See Also</span></span>  
 [<span data-ttu-id="ac769-122">Arbeiten mit benutzerdefinierten Typen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac769-122">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
