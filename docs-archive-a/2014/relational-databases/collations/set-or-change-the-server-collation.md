---
title: Festlegen oder Ändern der Serversortierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- server collations [SQL Server]
- collations [SQL Server], server
ms.assetid: 3242deef-6f5f-4051-a121-36b3b4da851d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7be051c8cf63a272f2bf42fb54b1c45ed4160
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622692"
---
# <a name="set-or-change-the-server-collation"></a><span data-ttu-id="93ec7-102">Festlegen oder Ändern der Serversortierung</span><span class="sxs-lookup"><span data-stu-id="93ec7-102">Set or Change the Server Collation</span></span>
  <span data-ttu-id="93ec7-103">Die Serversortierung fungiert als Standardsortierung für alle Systemdatenbanken, die zusammen mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]installiert werden, sowie für alle neu erstellten Benutzerdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="93ec7-103">The server collation acts as the default collation for all system databases that are installed with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and also any newly created user databases.</span></span> <span data-ttu-id="93ec7-104">Die Serversortierung wird bei der Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angegeben.</span><span class="sxs-lookup"><span data-stu-id="93ec7-104">The server collation is specified during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="93ec7-105">Weitere Informationen finden Sie unter [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="93ec7-105">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
## <a name="changing-the-server-collation"></a><span data-ttu-id="93ec7-106">Ändern der Serversortierung</span><span class="sxs-lookup"><span data-stu-id="93ec7-106">Changing the Server Collation</span></span>  
 <span data-ttu-id="93ec7-107">Das Ändern der Standardsortierung für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann ein komplexer Vorgang sein, der die folgenden Schritte umfasst:</span><span class="sxs-lookup"><span data-stu-id="93ec7-107">Changing the default collation for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be a complex operation and involves the following steps:</span></span>  
  
-   <span data-ttu-id="93ec7-108">Sicherstellen, dass Ihnen alle Informationen oder Skripts zur Verfügung stehen, die zum erneuten Erstellen der Benutzerdatenbanken und aller darin enthaltenen Objekte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="93ec7-108">Make sure you have all the information or scripts needed to re-create your user databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="93ec7-109">Exportieren aller Daten mithilfe eines Tools wie z. B. dem [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="93ec7-109">Export all your data using a tool such as the [bcp Utility](../../tools/bcp-utility.md).</span></span> <span data-ttu-id="93ec7-110">Weitere Informationen finden Sie unter [Massenimport und -export von Daten &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="93ec7-110">For more information, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="93ec7-111">Löschen aller Benutzerdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="93ec7-111">Drop all the user databases.</span></span>  
  
-   <span data-ttu-id="93ec7-112">Neuerstellen der Masterdatenbank unter Angabe der neuen Sortierung in der SQLCOLLATION-Eigenschaft des **setup** -Befehls.</span><span class="sxs-lookup"><span data-stu-id="93ec7-112">Rebuild the master database specifying the new collation in the SQLCOLLATION property of the **setup** command.</span></span> <span data-ttu-id="93ec7-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="93ec7-113">For example:</span></span>  
  
    ```  
    Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName   
    /SQLSYSADMINACCOUNTS=accounts /[ SAPWD= StrongPassword ]   
    /SQLCOLLATION=CollationName  
    ```  
  
     <span data-ttu-id="93ec7-114">Weitere Informationen finden Sie unter [Neuerstellen von Systemdatenbanken](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="93ec7-114">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="93ec7-115">Erstellen aller Datenbanken und aller darin enthaltenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="93ec7-115">Create all the databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="93ec7-116">Importieren aller Daten.</span><span class="sxs-lookup"><span data-stu-id="93ec7-116">Import all your data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93ec7-117">Anstatt die Standardsortierung einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu ändern, können Sie eine Standardsortierung für alle neu zu erstellenden Datenbanken angeben.</span><span class="sxs-lookup"><span data-stu-id="93ec7-117">Instead of changing the default collation of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can specify a default collation for each new database you create.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ec7-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93ec7-118">See Also</span></span>  
 <span data-ttu-id="93ec7-119">[Sortierung und Unicode-Unterstützung](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="93ec7-119">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="93ec7-120">[Festlegen oder Ändern der Datenbanksortierung](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="93ec7-120">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 <span data-ttu-id="93ec7-121">[Festlegen oder Ändern der Spaltensortierung](set-or-change-the-column-collation.md) </span><span class="sxs-lookup"><span data-stu-id="93ec7-121">[Set or Change the Column Collation](set-or-change-the-column-collation.md) </span></span>  
 [<span data-ttu-id="93ec7-122">Neuerstellen von Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="93ec7-122">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
