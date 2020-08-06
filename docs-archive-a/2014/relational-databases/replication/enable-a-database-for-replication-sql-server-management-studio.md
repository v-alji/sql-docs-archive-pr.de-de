---
title: Aktivieren einer Datenbank für die Replikation (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609110"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a><span data-ttu-id="07eed-102">Aktivieren einer Datenbank für die Replikation (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="07eed-102">Enable a Database for Replication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="07eed-103">Eine Datenbank wird implizit für die Replikation aktiviert, wenn ein Mitglied der festen Serverrolle **sysadmin** mit dem Assistenten für neue Veröffentlichung eine Veröffentlichung erstellt.</span><span class="sxs-lookup"><span data-stu-id="07eed-103">A database is implicitly enabled for replication when a member of the **sysadmin** fixed server role creates a publication with the New Publication Wizard.</span></span> <span data-ttu-id="07eed-104">Ein Mitglied der festen Serverrolle **sysadmin** kann eine Datenbank auch explizit für die Replikation aktivieren, sodass ein Mitglied der festen Datenbankrolle **db_owner** eine oder mehrere Veröffentlichungen in der Datenbank erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="07eed-104">A member of the **sysadmin** fixed server role can also enable a database for replication explicitly, so that a member of the **db_owner** fixed database role can create one or more publications in that database.</span></span> <span data-ttu-id="07eed-105">Verwenden Sie zum expliziten Aktivieren einer Datenbank die Seite **Veröffentlichungsdatenbanken** im Dialogfeld **Verlegereigenschaften - \<Publisher>** .</span><span class="sxs-lookup"><span data-stu-id="07eed-105">To enable a database explicitly, use the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box.</span></span> <span data-ttu-id="07eed-106">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="07eed-106">For more information about accessing this dialog box, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
### <a name="to-enable-a-database-for-replication"></a><span data-ttu-id="07eed-107">So aktivieren Sie eine Datenbank für die Replikation</span><span class="sxs-lookup"><span data-stu-id="07eed-107">To enable a database for replication</span></span>  
  
1.  <span data-ttu-id="07eed-108">Aktivieren Sie auf der Seite **Veröffentlichungsdatenbanken** im Dialogfeld **Verlegereigenschaften - \<Publisher>** das Kontrollkästchen **Transaktionsreplikation** und/oder **Mergereplikation** für jede Datenbank, die Sie replizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="07eed-108">On the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box, select the **Transactional** and/or **Merge** check box for each database you want to replicate.</span></span> <span data-ttu-id="07eed-109">Aktivieren Sie **Transaktionsreplikation** , um die Datenbank für die Momentaufnahmereplikation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="07eed-109">Select **Transactional** to enable the database for snapshot replication.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
