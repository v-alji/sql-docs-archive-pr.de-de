---
title: Löschen eines SQL Server-Index | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: add3ba14-10b1-4723-b7c0-3e83689e9fdd
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267cc92645ff8b28757ad2d266e58917fcb4b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619084"
---
# <a name="dropping-a-sql-server-index"></a><span data-ttu-id="06732-102">Löschen eines SQL Server-Index</span><span class="sxs-lookup"><span data-stu-id="06732-102">Dropping a SQL Server Index</span></span>
  <span data-ttu-id="06732-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die **IIndexDefinition::D ropindex** -Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06732-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::DropIndex** function.</span></span> <span data-ttu-id="06732-104">Mit dieser Funktion können Consumer einen Index aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle entfernen.</span><span class="sxs-lookup"><span data-stu-id="06732-104">This allows consumers to remove an index from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="06732-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht einige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Primary Key-und UNIQUE-Einschränkungen als Indizes verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06732-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PRIMARY KEY and UNIQUE constraints as indexes.</span></span> <span data-ttu-id="06732-106">Der Tabellenbesitzer, der Datenbankbesitzer sowie bestimmte Inhaber von Administrationsfunktionen können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabellen bearbeiten und Einschränkungen löschen.</span><span class="sxs-lookup"><span data-stu-id="06732-106">The table owner, database owner, and some administrative role members can modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, dropping a constraint.</span></span> <span data-ttu-id="06732-107">Standardmäßig kann nur der Tabellenbesitzer einen vorhandenen Index löschen.</span><span class="sxs-lookup"><span data-stu-id="06732-107">By default, only the table owner can drop an existing index.</span></span> <span data-ttu-id="06732-108">Aus diesem Grund hängt es nicht nur von den Zugriffsrechten des Anwendungsbenutzers, sondern auch von der Art des angegebenen Indexes ab, ob **DropIndex** erfolgreich verläuft oder fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="06732-108">Therefore, **DropIndex** success or failure depends not only on the application user's access rights but also on the type of index indicated.</span></span>  
  
 <span data-ttu-id="06732-109">Consumer geben den Tabellennamen als Unicode-Zeichenfolge in das *pwszName*-Element der *uName*-Vereinigung des *pTableID*-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="06732-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="06732-110">Das *eKind*-Element von *pTableID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="06732-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="06732-111">Consumer geben den Indexnamen als Unicode-Zeichenfolge in das *pwszName*-Element der *uName*-Vereinigung des *pIndexID*-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="06732-111">Consumers specify the index name as a Unicode character string in the *pwszName* member of the *uName* union in the *pIndexID* parameter.</span></span> <span data-ttu-id="06732-112">Das *eKind*-Element von *pIndexID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="06732-112">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span> <span data-ttu-id="06732-113">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt das OLE DB Feature zum Löschen aller Indizes einer Tabelle nicht, wenn *pIndexID* NULL ist.</span><span class="sxs-lookup"><span data-stu-id="06732-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support the OLE DB feature of dropping all indexes on a table when *pIndexID* is null.</span></span> <span data-ttu-id="06732-114">Wenn *pIndexID* NULL ist, wird E_INVALIDARG zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06732-114">If *pIndexID* is null, E_INVALIDARG is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06732-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06732-115">See Also</span></span>  
 <span data-ttu-id="06732-116">[Tabellen und Indizes](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="06732-116">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 <span data-ttu-id="06732-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06732-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="06732-118">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06732-118">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
