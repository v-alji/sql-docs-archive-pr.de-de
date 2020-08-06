---
title: Entfernen einer Spalte aus einer SQL Server-Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: rothja
ms.author: jroth
ms.openlocfilehash: 8f40c466910aae7e0d349cd4a65ab265282bc8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619082"
---
# <a name="removing-a-column-from-a-sql-server-table"></a><span data-ttu-id="0efaa-102">Entfernen einer Spalte aus einer SQL Server-Tabelle</span><span class="sxs-lookup"><span data-stu-id="0efaa-102">Removing a Column from a SQL Server Table</span></span>
  <span data-ttu-id="0efaa-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter stellt die **ITableDefinition::D ropcolumn** -Funktion zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0efaa-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropColumn** function.</span></span> <span data-ttu-id="0efaa-104">Mit dieser Funktion können Consumer eine Spalte aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle entfernen.</span><span class="sxs-lookup"><span data-stu-id="0efaa-104">This allows consumers to remove a column from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="0efaa-105">Consumer geben den Tabellennamen als Unicode-Zeichenfolge im *pwszName*-Element der *uName*-Vereinigung des *pTableID*-Parameters an.</span><span class="sxs-lookup"><span data-stu-id="0efaa-105">Consumers specify the table name as a Unicode character string in the *pwszName*member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="0efaa-106">Das *eKind*-Element von *pTableID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="0efaa-106">The *eKind*member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="0efaa-107">Der Consumer gibt einen Spaltennamen im *pwszName*-Element der *uName*-Vereinigung des *pColumnID*-Parameters an.</span><span class="sxs-lookup"><span data-stu-id="0efaa-107">The consumer indicates a column name in the *pwszName*member of the *uName* union in the *pColumnID* parameter.</span></span> <span data-ttu-id="0efaa-108">Der Spaltenname ist eine Unicode-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0efaa-108">The column name is a Unicode character string.</span></span> <span data-ttu-id="0efaa-109">Das *eKind*-Element von *pColumnID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="0efaa-109">The *eKind* member of *pColumnID* must be DBKIND_NAME.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0efaa-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0efaa-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="0efaa-111">Code</span><span class="sxs-lookup"><span data-stu-id="0efaa-111">Code</span></span>  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a><span data-ttu-id="0efaa-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0efaa-112">See Also</span></span>  
 [<span data-ttu-id="0efaa-113">Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="0efaa-113">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
