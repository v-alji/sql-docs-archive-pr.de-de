---
title: Verteilte Ad-hoc-Abfragen (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- OPENROWSET function, ad hoc distributed queries option
- Ad Hoc Distributed Queries option
- ad hoc distributed queries
- 7415 (Database Engine Error)
- OPENDATASOURCE function, ad hoc distributed queries option
- ad hoc access
ms.assetid: 5b982015-e196-44c3-83b8-275fb9d769b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d07b3c038597916cdaf026e24e90aab9d6b61616
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607985"
---
# <a name="ad-hoc-distributed-queries-server-configuration-option"></a><span data-ttu-id="99640-102">Ad Hoc Distributed Queries (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="99640-102">ad hoc distributed queries Server Configuration Option</span></span>
  <span data-ttu-id="99640-103">Standardmäßig ist es in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht zulässig, dass für verteilte Ad-hoc-Abfragen OPENROWSET und OPENDATASOURCE verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99640-103">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc distributed queries using OPENROWSET and OPENDATASOURCE.</span></span> <span data-ttu-id="99640-104">Wird diese Option auf 1 festgelegt, ist in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] der Ad-hoc-Zugriff zulässig.</span><span class="sxs-lookup"><span data-stu-id="99640-104">When this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows ad hoc access.</span></span> <span data-ttu-id="99640-105">Wenn diese Option nicht festgelegt oder auf 0 festgelegt wird, ist in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kein Ad-hoc-Zugriff zulässig.</span><span class="sxs-lookup"><span data-stu-id="99640-105">When this option is not set or is set to 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc access.</span></span>  
  
 <span data-ttu-id="99640-106">Verteilte Ad-hoc-Abfragen verwenden die OPENROWSET- und OPENDATASOURCE-Funktionen, um eine Verbindung mit Remotedatenquellen herzustellen, die OLE DB verwenden.</span><span class="sxs-lookup"><span data-stu-id="99640-106">Ad hoc distributed queries use the OPENROWSET and OPENDATASOURCE functions to connect to remote data sources that use OLE DB.</span></span> <span data-ttu-id="99640-107">OPENROWSET und OPENDATASOURCE sollten nur für Verweise auf OLE DB-Datenquellen verwendet werden, auf die selten zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="99640-107">OPENROWSET and OPENDATASOURCE should be used only to reference OLE DB data sources that are accessed infrequently.</span></span> <span data-ttu-id="99640-108">Definieren Sie einen Verbindungsserver für Datenquellen, auf die mehr als nur wenige Male zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="99640-108">For any data sources that will be accessed more than several times, define a linked server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="99640-109">Das Aktivieren der Verwendung von Ad-hoc-Namen bedeutet, dass jede authentifizierte Anmeldung an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf den Anbieter zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="99640-109">Enabling the use of ad hoc names means that any authenticated login to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can access the provider.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="99640-110">-Administratoren sollten diese Funktion für Anbieter aktivieren, auf die von jeder lokalen Anmeldung sicher zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="99640-110">administrators should enable this feature for providers that are safe to be accessed by any local login.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99640-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="99640-111">Remarks</span></span>  
 <span data-ttu-id="99640-112">Der Versuch, eine Ad-hoc-Verbindung ohne die Option **Ad Hoc Distributed Queries** herzustellen, verursacht den folgenden Fehler: Meldung 7415, Ebene 16, Status 1, Zeile 1</span><span class="sxs-lookup"><span data-stu-id="99640-112">Attempting to make an ad hoc connection with **Ad Hoc Distributed Queries** not enabled results in error: Msg 7415, Level 16, State 1, Line 1</span></span>  
  
 <span data-ttu-id="99640-113">Der Ad-hoc-Zugriff auf den OLE DB-Anbieter 'Microsoft.ACE.OLEDB.12.0' wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="99640-113">Ad hoc access to OLE DB provider 'Microsoft.ACE.OLEDB.12.0' has been denied.</span></span> <span data-ttu-id="99640-114">Sie müssen auf diesen Anbieter über einen Verbindungsserver zugreifen.</span><span class="sxs-lookup"><span data-stu-id="99640-114">You must access this provider through a linked server.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="99640-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="99640-115">Examples</span></span>  
 <span data-ttu-id="99640-116">Im folgenden Beispiel werden 'Ad Hoc Distributed Queries' aktiviert und anschließend ein Server mit dem Namen `Seattle1` mithilfe der `OPENROWSET` -Funktion abgefragt.</span><span class="sxs-lookup"><span data-stu-id="99640-116">The following example enables ad hoc distributed queries and then queries a server named `Seattle1` using the `OPENROWSET` function.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
sp_configure 'Ad Hoc Distributed Queries', 1;  
RECONFIGURE;  
GO  
  
SELECT a.*  
FROM OPENROWSET('SQLNCLI', 'Server=Seattle1;Trusted_Connection=yes;',  
     'SELECT GroupName, Name, DepartmentID  
      FROM AdventureWorks2012.HumanResources.Department  
      ORDER BY GroupName, Name') AS a;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="99640-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99640-117">See Also</span></span>  
 <span data-ttu-id="99640-118">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="99640-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="99640-119">[Verbindungsserver &#40;Datenbank-Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="99640-119">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="99640-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99640-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="99640-121">[OPENDATASOURCE (Transact-SQL)](/sql/t-sql/functions/opendatasource-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99640-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span></span>  
 [<span data-ttu-id="99640-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="99640-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)  
  
  
