---
title: Rollen und Berechtigungen (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], about security
- security [Analysis Services - multidimensional data], about security
ms.assetid: bb885447-868b-4686-853c-8241f63d4370
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6595d931b2c2760e5fd3013ff6bec88f85106d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727222"
---
# <a name="roles-and-permissions-analysis-services"></a><span data-ttu-id="02805-102">Rollen und Berechtigungen (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="02805-102">Roles and Permissions (Analysis Services)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="02805-103">bietet ein rollenbasiertes Autorisierungsmodell, mit dem der Zugriff auf Vorgänge, Objekte und Daten erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="02805-103">provides a role-based authorization model that grants access to operations, objects, and data.</span></span> <span data-ttu-id="02805-104">Alle Benutzer, die auf eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz oder -Datenbank zugreifen, müssen den Vorgang im Kontext einer Rolle ausführen.</span><span class="sxs-lookup"><span data-stu-id="02805-104">All users who access an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance or database must do so within the context of a role.</span></span>  
  
 <span data-ttu-id="02805-105">Der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Systemadministrator ist dafür verantwortlich, Mitgliedschaften für die **Serveradministratorrolle** zu gewähren, die uneingeschränkten Zugriff auf Servervorgänge bietet.</span><span class="sxs-lookup"><span data-stu-id="02805-105">As an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] system administrator, you are in charge of granting membership to the **server administrator role** that conveys unrestricted access to operations on the server.</span></span> <span data-ttu-id="02805-106">Diese Rolle verfügt über feste Berechtigungen und kann nicht angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="02805-106">This role has fixed permissions and cannot be customized.</span></span> <span data-ttu-id="02805-107">Standardmäßig sind Mitglieder der lokalen Administratorgruppe automatisch Analysis Services-Systemadministratoren.</span><span class="sxs-lookup"><span data-stu-id="02805-107">By default, members of the local Administrators group are automatically Analysis Services system administrators.</span></span>  
  
 <span data-ttu-id="02805-108">Benutzer, die keine Administratoren sind, und Daten abrufen oder verarbeiten, erhalten Zugriff über **Datenbankrollen**.</span><span class="sxs-lookup"><span data-stu-id="02805-108">Non-administrative users who query or process data are granted access through **database roles**.</span></span> <span data-ttu-id="02805-109">Als Systemadministrator oder Datenbankadministrator können Sie die Rollen erstellen, mit denen die verschiedenen Zugriffsebenen innerhalb einer bestimmten Datenbank beschrieben werden, und jedem Benutzer, der Zugriff benötigt, eine Mitgliedschaft zuweisen.</span><span class="sxs-lookup"><span data-stu-id="02805-109">Both system administrators and database administrators can create the roles that describe different levels of access within a given database, and then assign membership to every user who requires access.</span></span> <span data-ttu-id="02805-110">Jede Rolle besitzt einen benutzerdefinierten Satz von Berechtigungen, mit denen Benutzer in einer bestimmten Datenbank auf Objekte und Vorgänge zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="02805-110">Each role has a customized set of permissions for accessing objects and operations within a particular database.</span></span> <span data-ttu-id="02805-111">Sie können Berechtigungen auf folgenden Ebenen zuweisen: Datenbank, innere Objekte wie Cubes und Dimensionen (aber keine Perspektiven) sowie Zeilen.</span><span class="sxs-lookup"><span data-stu-id="02805-111">You can assign permissions at these levels: database, interior objects such as cubes and dimensions (but not perspectives), and rows.</span></span>  
  
 <span data-ttu-id="02805-112">Üblicherweise erfolgt das Erstellen von Rollen und Zuweisen von Mitgliedschaften voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="02805-112">It is common practice to create roles and assign membership as separate operations.</span></span> <span data-ttu-id="02805-113">Der Modellentwickler fügt Rollen häufig in der Entwurfsphase hinzu.</span><span class="sxs-lookup"><span data-stu-id="02805-113">Often, the model designer adds roles during the design phase.</span></span> <span data-ttu-id="02805-114">Auf diese Weise werden alle Rollendefinitionen in den Projektdateien widergespiegelt, durch die das Modell definiert wird.</span><span class="sxs-lookup"><span data-stu-id="02805-114">This way, all role definitions are reflected in the project files that define the model.</span></span> <span data-ttu-id="02805-115">Rollenmitgliedschaften werden in der Regel später eingerichtet, wenn die Datenbank in die Produktionsumgebung eingebunden wird. Dafür sind normalerweise Datenbankadministratoren zuständig, die Skripts erstellen, die entwickelt, getestet und als unabhängiger Vorgang ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="02805-115">Role membership is typically rolled out later as the database moves into production, usually by database administrators who create scripts that can be developed, tested, and run as an independent operation.</span></span>  
  
 <span data-ttu-id="02805-116">Die gesamte Autorisierung basiert auf einer gültigen Windows-Benutzeridentität.</span><span class="sxs-lookup"><span data-stu-id="02805-116">All authorization is predicated on a valid Windows user identity.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="02805-117">wird ausschließlich die Windows-Authentifizierung zum Authentifizieren von Benutzeridentitäten verwendet.</span><span class="sxs-lookup"><span data-stu-id="02805-117">uses Windows authentication exclusively to authenticate user identities.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="02805-118">stellt keine proprietäre Authentifizierungsmethode bereit. Weitere Informationen finden Sie unter [Von Analysis Services unterstützte Authentifizierungsmethoden](../instances/authentication-methodologies-supported-by-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="02805-118">provides no proprietary authentication method.See [Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="02805-119">Berechtigungen sind additiv für jeden Windows-Benutzer/jede Windows-Gruppe, über alle Rollen in der Datenbank hinweg.</span><span class="sxs-lookup"><span data-stu-id="02805-119">Permissions are additive for each Windows user or group, across all roles in the database.</span></span> <span data-ttu-id="02805-120">Wenn eine Rolle dem Benutzer oder der Gruppe das Ausführen bestimmter Tasks oder das Anzeigen bestimmter Daten untersagt, eine andere Rolle dem Benutzer oder der Gruppe diese Berechtigung allerdings erteilt, dann ist der Benutzer oder die Gruppe berechtigt, den Task auszuführen bzw. die Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="02805-120">If one role denies a user or group permission to perform certain tasks or view certain data, but another role grants this permission to that user or group, the user or group will have permission to perform the task or view the data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02805-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="02805-121">In this section</span></span>  
  
-   [<span data-ttu-id="02805-122">Autorisieren des Zugriffs auf Objekte und Vorgänge &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-122">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](authorizing-access-to-objects-and-operations-analysis-services.md)  
  
-   [<span data-ttu-id="02805-123">Erteilen von Datenbankberechtigungen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-123">Grant database permissions &#40;Analysis Services&#41;</span></span>](grant-database-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="02805-124">Erteilen von Cube- oder Modellberechtigungen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-124">Grant cube or model permissions &#40;Analysis Services&#41;</span></span>](grant-cube-or-model-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="02805-125">Erteilen von Verarbeitungsberechtigungen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-125">Grant process permissions &#40;Analysis Services&#41;</span></span>](grant-process-permissions-analysis-services.md)  
  
-   [<span data-ttu-id="02805-126">Erteilen von Berechtigungen zum Lesen von Definitionen für Objektmetadaten &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-126">Grant read definition permissions on object metadata &#40;Analysis Services&#41;</span></span>](grant-read-definition-permissions-on-object-metadata-analysis-services.md)  
  
-   [<span data-ttu-id="02805-127">Erteilen von Berechtigungen für ein Datenquellenobjekt &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-127">Grant permissions on a data source object &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-data-source-object-analysis-services.md)  
  
-   [<span data-ttu-id="02805-128">Erteilen von Berechtigungen für Data Mining-Strukturen und -Modelle &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-128">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](grant-permissions-on-data-mining-structures-and-models-analysis-services.md)  
  
-   [<span data-ttu-id="02805-129">Gewähren von Berechtigungen in einer Dimension &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-129">Grant permissions on a dimension &#40;Analysis Services&#41;</span></span>](grant-permissions-on-a-dimension-analysis-services.md)  
  
-   [<span data-ttu-id="02805-130">Erteilen von benutzerdefiniertem Zugriff auf Dimensionsdaten &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-130">Grant custom access to dimension data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-dimension-data-analysis-services.md)  
  
-   [<span data-ttu-id="02805-131">Erteilen von benutzerdefiniertem Zugriff auf Zellendaten &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-131">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="02805-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02805-132">See Also</span></span>  
 [<span data-ttu-id="02805-133">Erstellen und Verwalten von Rollen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="02805-133">Create and Manage Roles &#40;SSAS Tabular&#41;</span></span>](../tabular-models/roles-ssas-tabular.md)  
  
  
