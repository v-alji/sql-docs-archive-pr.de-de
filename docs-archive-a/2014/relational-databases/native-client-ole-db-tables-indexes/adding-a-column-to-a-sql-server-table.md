---
title: Hinzufügen einer Spalte zu einer SQL Server-Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 97aa2656ccde662a34e1dd80fd662b22f601d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723762"
---
# <a name="adding-a-column-to-a-sql-server-table"></a><span data-ttu-id="a9c28-102">Hinzufügen einer Spalte zu einer SQL Server-Tabelle</span><span class="sxs-lookup"><span data-stu-id="a9c28-102">Adding a Column to a SQL Server Table</span></span>
  <span data-ttu-id="a9c28-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter stellt die **ITableDefinition:: AddColumn** -Funktion zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a9c28-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::AddColumn** function.</span></span> <span data-ttu-id="a9c28-104">Mit dieser Funktion können Consumer einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle eine Spalte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a9c28-104">This allows consumers to add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="a9c28-105">Wenn Sie einer Tabelle eine Spalte hinzufügen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird der Consumer des Native Client OLE DB-Anbieters wie folgt eingeschränkt:</span><span class="sxs-lookup"><span data-stu-id="a9c28-105">When you add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is constrained as follows:</span></span>  
  
-   <span data-ttu-id="a9c28-106">Wenn DBPROP_COL_AUTOINCREMENT VARIANT_TRUE ist, muss DBPROP_COL_NULLABLE VARIANT_FALSE sein.</span><span class="sxs-lookup"><span data-stu-id="a9c28-106">If DBPROP_COL_AUTOINCREMENT is VARIANT_TRUE, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="a9c28-107">Wenn die Spalte mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp**-Datentyp definiert wird, muss DBPROP_COL_NULLABLE auf VARIANT_FALSE festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="a9c28-107">If the column is defined by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** data type, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="a9c28-108">Für alle anderen Spaltendefinitionen muss DBPROP_COL_NULLABLE  VARIANT_TRUE sein.</span><span class="sxs-lookup"><span data-stu-id="a9c28-108">For any other column definition, DBPROP_COL_NULLABLE must be VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="a9c28-109">Consumer geben den Tabellennamen als Unicode-Zeichenfolge in das *pwszName*-Element der *uName*-Vereinigung des *pTableID*-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="a9c28-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="a9c28-110">Das *eKind*-Element von *pTableID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="a9c28-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="a9c28-111">Der neue Spaltenname wird als Unicode-Zeichenfolge im *pwszName*-Element der *uName*-Vereinigung des *dbcid*-Elements des DBCOLUMNDESC-Parameters *pColumnDesc* angegeben.</span><span class="sxs-lookup"><span data-stu-id="a9c28-111">The new column name is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *dbcid* member of the DBCOLUMNDESC parameter *pColumnDesc*.</span></span> <span data-ttu-id="a9c28-112">Das *eKind*-Element muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="a9c28-112">The *eKind* member must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c28-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9c28-113">See Also</span></span>  
 <span data-ttu-id="a9c28-114">[Tabellen und Indizes](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a9c28-114">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 [<span data-ttu-id="a9c28-115">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a9c28-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
