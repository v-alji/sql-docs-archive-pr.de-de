---
title: Veröffentlichungsdatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608550"
---
# <a name="publication-database"></a><span data-ttu-id="4e5b5-102">Veröffentlichungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="4e5b5-102">Publication Database</span></span>
  <span data-ttu-id="4e5b5-103">Bei der Veröffentlichungsdatenbank handelt es sich um die Datenbank auf dem Verleger, die als Quelle der zu replizierenden Daten und Datenbankobjekte fungiert.</span><span class="sxs-lookup"><span data-stu-id="4e5b5-103">The publication database is the database on the Publisher that is the source of data and database objects to be replicated.</span></span> <span data-ttu-id="4e5b5-104">Die in einer Replikation verwendeten Veröffentlichungsdatenbanken müssen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4e5b5-104">Each publication database used in replication must be enabled.</span></span> <span data-ttu-id="4e5b5-105">Die Datenbank wird aktiviert, wenn ein Mitglied der festen Serverrolle **sysadmin** Folgendes ausführt:</span><span class="sxs-lookup"><span data-stu-id="4e5b5-105">The database is enabled when a member of the **sysadmin** fixed server role:</span></span>  
  
-   <span data-ttu-id="4e5b5-106">Erstellt eine Veröffentlichung auf der betreffenden Datenbank mithilfe des Assistenten für neue Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="4e5b5-106">Creates a publication on that database using the New Publication Wizard.</span></span>  
  
-   <span data-ttu-id="4e5b5-107">Wählt die Datenbank im Dialogfeld **Verlegereigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="4e5b5-107">Selects the database in the **Publisher Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="4e5b5-108">Führt **sp_replicationdboption** aus und legt für die Option **publish** (bei Momentaufnahme- oder Transaktionsveröffentlichungen) oder die Option **merge publish** (bei Mergeveröffentlichungen) **True**fest.</span><span class="sxs-lookup"><span data-stu-id="4e5b5-108">Executes **sp_replicationdboption** and sets the option **publish** (for snapshot or transactional publications) or **merge publish** (for merge publications) to **True**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e5b5-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4e5b5-109">Options</span></span>  
 <span data-ttu-id="4e5b5-110">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="4e5b5-110">**Databases**</span></span>  
 <span data-ttu-id="4e5b5-111">Wählen Sie den Namen der Datenbank aus, die die Daten und Datenbankobjekte enthält, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4e5b5-111">Select the name of the database that contains the data and database objects that you want to publish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5b5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e5b5-112">See Also</span></span>  
 <span data-ttu-id="4e5b5-113">[Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="4e5b5-113">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="4e5b5-114">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="4e5b5-114">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="4e5b5-115">[Anzeigen und Ändern der Verteiler- und Verlegereigenschaften](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4e5b5-115">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="4e5b5-116">sp_replicationdboption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e5b5-116">sp_replicationdboption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
