---
title: Neue Systemrolle (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700694"
---
# <a name="new-system-role-management-studio"></a><span data-ttu-id="ce931-102">Neue Systemrolle (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ce931-102">New System Role (Management Studio)</span></span>
  <span data-ttu-id="ce931-103">Verwenden Sie diese Seite, um eine Rollendefinition auf Systemebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce931-103">Use this page to create a system-level role definition.</span></span> <span data-ttu-id="ce931-104">Eine Systemrollendefinition gibt eine Gruppe von Aufgaben auf Systemebene an, die für den gesamten Berichtsserver gültig sind.</span><span class="sxs-lookup"><span data-stu-id="ce931-104">A system role definition specifies a set of system-level tasks that apply to a report server as whole.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce931-105">Rollendefinitionen werden nur auf einem Berichtsserver verwendet, der im einheitlichen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce931-105">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="ce931-106">Ist der Berichtsserver für den integrierten SharePoint-Modus konfiguriert, ist diese Seite nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ce931-106">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ce931-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ce931-107">Options</span></span>  
 <span data-ttu-id="ce931-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="ce931-108">**Name**</span></span>  
 <span data-ttu-id="ce931-109">Geben Sie den Namen der Rollendefinition ein.</span><span class="sxs-lookup"><span data-stu-id="ce931-109">Type the name of the role definition.</span></span> <span data-ttu-id="ce931-110">Ein Rollendefinitionsname muss innerhalb des Berichtsserver-Namespaces eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ce931-110">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="ce931-111">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce931-111">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="ce931-112">Er kann auch Leerzeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce931-112">It can also include spaces and some symbols.</span></span> <span data-ttu-id="ce931-113">Folgende Zeichen können beim Angeben eines Namens nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ce931-113">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="ce931-114">; ?</span><span class="sxs-lookup"><span data-stu-id="ce931-114">; ?</span></span> <span data-ttu-id="ce931-115">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="ce931-115">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="ce931-116">" /</span><span class="sxs-lookup"><span data-stu-id="ce931-116">" /</span></span>  
  
 <span data-ttu-id="ce931-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ce931-117">**Description**</span></span>  
 <span data-ttu-id="ce931-118">Stellen Sie eine Beschreibung bereit, in der die Verwendung der Rolle erläutert wird, und die Art der Unterstützung durch die Rolle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="ce931-118">Provide a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="ce931-119">**Aufgabe**</span><span class="sxs-lookup"><span data-stu-id="ce931-119">**Task**</span></span>  
 <span data-ttu-id="ce931-120">Wählen Sie die Tasks auf Systemebene aus, die über diese Rolle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="ce931-120">Select the system-level tasks that can be performed through this role.</span></span> <span data-ttu-id="ce931-121">Sie können keine neuen, von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]unterstützten Tasks erstellen oder solche vorhandenen Tasks ändern.</span><span class="sxs-lookup"><span data-stu-id="ce931-121">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="ce931-122">Außerdem können Sie keine Tasks auf Elementebene für eine Systemrollendefinition auswählen.</span><span class="sxs-lookup"><span data-stu-id="ce931-122">You cannot choose item-level tasks for a system role definition.</span></span>  
  
 <span data-ttu-id="ce931-123">**Taskbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="ce931-123">**Task Description**</span></span>  
 <span data-ttu-id="ce931-124">Zeigt eine Beschreibung des Tasks an, in der die durch den Task unterstützten Vorgänge bzw. Berechtigungen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ce931-124">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce931-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce931-125">See Also</span></span>  
 <span data-ttu-id="ce931-126">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="ce931-126">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="ce931-127">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="ce931-127">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
