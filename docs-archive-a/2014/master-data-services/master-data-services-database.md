---
title: Master Data Services-Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e4bae180dfb7c9051d5445a689c44978ef73bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619173"
---
# <a name="master-data-services-database"></a><span data-ttu-id="da2db-102">Master Data Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="da2db-102">Master Data Services Database</span></span>
  <span data-ttu-id="da2db-103">Die Datenbank enthält alle Informationen für das [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -System.</span><span class="sxs-lookup"><span data-stu-id="da2db-103">The database contains all of the information for the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span> <span data-ttu-id="da2db-104">Sie ist wesentlich für eine [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="da2db-104">It is central to a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span> <span data-ttu-id="da2db-105">Die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="da2db-105">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database:</span></span>  
  
-   <span data-ttu-id="da2db-106">Speichert die vom [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -System benötigten Einstellungen, Datenbankobjekte und Daten.</span><span class="sxs-lookup"><span data-stu-id="da2db-106">Stores the settings, database objects, and data required by the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span>  
  
-   <span data-ttu-id="da2db-107">Enthält Stagingtabellen zur Verarbeitung von Daten aus Quellsystemen.</span><span class="sxs-lookup"><span data-stu-id="da2db-107">Contains staging tables that are used to process data from source systems.</span></span>  
  
-   <span data-ttu-id="da2db-108">Stellt ein Schema und die Datenbankobjekte zum Speichern von Masterdaten aus Quellsystemen bereit.</span><span class="sxs-lookup"><span data-stu-id="da2db-108">Provides a schema and database objects to store master data from source systems.</span></span>  
  
-   <span data-ttu-id="da2db-109">Unterstützt die Versionsfunktionalität, einschließlich der Überprüfung von Geschäftsregeln und E-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="da2db-109">Supports versioning functionality, including business rule validation and e-mail notifications.</span></span>  
  
-   <span data-ttu-id="da2db-110">Stellt Sichten für Abonnementssysteme bereit, die Daten aus der Datenbank abrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="da2db-110">Provides views for subscribing systems that need to retrieve data from the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da2db-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="da2db-111">In This Section</span></span>  
  
-   [<span data-ttu-id="da2db-112">Stagingtabelle für Blattelemente &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da2db-112">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](leaf-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="da2db-113">Konsolidierte Elementstagingtabelle &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da2db-113">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="da2db-114">Stagingtabelle für Beziehungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da2db-114">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="da2db-115">Fehler des Stagingprozesses &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da2db-115">Staging Process Errors &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="da2db-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da2db-116">See Also</span></span>  
 <span data-ttu-id="da2db-117">[Erstellen einer Master Data Services Datenbank](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="da2db-117">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 <span data-ttu-id="da2db-118">[Datenbankobjekt-Sicherheits &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="da2db-118">[Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span></span>  
 [<span data-ttu-id="da2db-119">Datenbankanmeldenamen, -benutzer und -rollen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da2db-119">Database Logins, Users, and Roles &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
