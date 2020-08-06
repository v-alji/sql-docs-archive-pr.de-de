---
title: Neue Benutzerrolle (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newrole.f1
ms.assetid: 9f76a235-0b58-479c-8e5b-50588091b71c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 78201c5ebedd0cdb7f8108b9e6effcaa7fbe87b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700689"
---
# <a name="new-user-role-management-studio"></a><span data-ttu-id="79034-102">Neue Benutzerrolle (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="79034-102">New User Role (Management Studio)</span></span>
  <span data-ttu-id="79034-103">Verwenden Sie diese Seite, um eine Rollendefinition auf Elementebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="79034-103">Use this page to create an item-level role definition.</span></span> <span data-ttu-id="79034-104">Eine Rollendefinition auf Elementebene ist eine benannte Auflistung von Tasks, die Benutzer in Bezug auf Ordner, Berichte, Modelle, Ressourcen und freigegebene Datenquellen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="79034-104">An item-level role definition is a named collection of tasks that enumerate the tasks a user can perform in relation to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="79034-105">Ein Beispiel für eine Rollendefinition auf Elementebene ist die vordefinierte Rolle Browser, die Aktionen identifiziert, die der Endbenutzer eines Berichts zum Navigieren in Ordnern und zum Anzeigen von Berichten verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="79034-105">An example of an item-level role definition is the predefined Browser role that identifies the kinds of actions a report end user might require for navigating folders and viewing reports.</span></span>  
  
 <span data-ttu-id="79034-106">Es sollten nur wenige Rollendefinitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79034-106">Role definitions are intended to be few in number.</span></span> <span data-ttu-id="79034-107">In den meisten Anwendungen sind wenige Rollendefinitionen auch ausreichend.</span><span class="sxs-lookup"><span data-stu-id="79034-107">Most organizations only require a few role definitions.</span></span> <span data-ttu-id="79034-108">Wenn die vordefinierten Rollendefinitionen jedoch nicht ausreichend sind, können Sie diese bearbeiten oder neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="79034-108">However, if the predefined role definitions are insufficient, you can vary them or create new ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79034-109">Rollendefinitionen werden nur auf einem Berichtsserver verwendet, der im einheitlichen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="79034-109">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="79034-110">Ist der Berichtsserver für den integrierten SharePoint-Modus konfiguriert, ist diese Seite nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="79034-110">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="79034-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="79034-111">Options</span></span>  
 <span data-ttu-id="79034-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="79034-112">**Name**</span></span>  
 <span data-ttu-id="79034-113">Geben Sie den Namen der Rollendefinition ein.</span><span class="sxs-lookup"><span data-stu-id="79034-113">Type the name of the role definition.</span></span> <span data-ttu-id="79034-114">Ein Rollendefinitionsname muss innerhalb des Berichtsserver-Namespaces eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="79034-114">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="79034-115">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="79034-115">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="79034-116">Er kann auch Leerzeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="79034-116">It can also include spaces and some symbols.</span></span> <span data-ttu-id="79034-117">Folgende Zeichen können beim Angeben eines Namens nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="79034-117">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="79034-118">; ?</span><span class="sxs-lookup"><span data-stu-id="79034-118">; ?</span></span> <span data-ttu-id="79034-119">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="79034-119">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="79034-120">" /</span><span class="sxs-lookup"><span data-stu-id="79034-120">" /</span></span>  
  
 <span data-ttu-id="79034-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="79034-121">**Description**</span></span>  
 <span data-ttu-id="79034-122">Geben Sie eine Beschreibung ein, in der die Verwendung der Rolle erläutert wird, und die Art der Unterstützung durch die Rolle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="79034-122">Type a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="79034-123">**Aufgabe**</span><span class="sxs-lookup"><span data-stu-id="79034-123">**Task**</span></span>  
 <span data-ttu-id="79034-124">Wählen Sie die Tasks aus, die über diese Rolle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="79034-124">Select the tasks that can be performed through this role.</span></span> <span data-ttu-id="79034-125">Sie können keine neuen, von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]unterstützten Tasks erstellen oder solche vorhandenen Tasks ändern.</span><span class="sxs-lookup"><span data-stu-id="79034-125">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="79034-126">In einer Rollendefinition auf Elementebene können nur Tasks auf Elementebene verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79034-126">Only item-level tasks can be used in an item-level role definition.</span></span>  
  
 <span data-ttu-id="79034-127">**Taskbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="79034-127">**Task Description**</span></span>  
 <span data-ttu-id="79034-128">Zeigt eine Beschreibung des Tasks an, in der die durch den Task unterstützten Vorgänge bzw. Berechtigungen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="79034-128">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79034-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79034-129">See Also</span></span>  
 <span data-ttu-id="79034-130">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="79034-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="79034-131">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="79034-131">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
