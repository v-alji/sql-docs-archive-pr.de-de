---
title: Erstellen, Löschen oder Ändern einer Rolle (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- deleting roles
- removing roles
- roles [Reporting Services], definitions
- modifying roles
- roles [Reporting Services], deleting
- roles [Reporting Services], modifying
ms.assetid: 3d1d56e6-a283-44a7-8417-36cb4d2c74d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 543bddda88e41af39d3200df4728716d46b3ae8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721061"
---
# <a name="create-delete-or-modify-a-role-management-studio"></a><span data-ttu-id="3242d-102">Erstellen, Löschen oder Ändern einer Rolle (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3242d-102">Create, Delete, or Modify a Role (Management Studio)</span></span>
  <span data-ttu-id="3242d-103">Reporting Services stellt vordefinierte Rollen, die eine Zugriffsebene für einen Berichtsserver definieren, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3242d-103">Reporting Services provides predefined roles that define a level of access to a report server.</span></span> <span data-ttu-id="3242d-104">Jeder Benutzer bzw. jede Benutzergruppe, die auf den Berichtsserver zugreifen möchte, benötigt hierfür eine Rolle, mit der die ausführbaren Aufgaben beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3242d-104">Each user or group who requires access to report server does so through a role that describes the tasks that can be performed.</span></span> <span data-ttu-id="3242d-105">Rollen werden für den gesamten Berichtsserver definiert.</span><span class="sxs-lookup"><span data-stu-id="3242d-105">Roles are defined for the report server as a whole.</span></span> <span data-ttu-id="3242d-106">Sie können eine Rollendefinition nicht für bestimmte Bereiche des Berichtsservers abändern oder angeben, dass eine Rolle je nach Zusammenhängen unterschiedlich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3242d-106">You cannot vary a role definition for specific parts of the report server, or specify that a role be used differently depending on the circumstances.</span></span>  
  
 <span data-ttu-id="3242d-107">Verwenden Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], um Rollen zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3242d-107">To create, modify, or delete roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="3242d-108">Sie können nur Rollen löschen, die nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3242d-108">You can only delete roles that are not used.</span></span>  
  
 <span data-ttu-id="3242d-109">Sie können die Zuweisungen von Benutzern und Gruppen zu von Ihnen erstellten Rollen mit dem Berichts-Manager vornehmen:</span><span class="sxs-lookup"><span data-stu-id="3242d-109">To assign users and groups to the roles that you create, use Report Manager.</span></span> <span data-ttu-id="3242d-110">Weitere Informationen finden Sie unter [Gewähren von Benutzer Zugriff auf einen Berichts Server &#40;Berichts-Manager&#41;](grant-user-access-to-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="3242d-110">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3242d-111">Wenn ein Berichtsserver für die Ausführung im integrierten SharePoint-Modus konfiguriert wird und Sie eine Verbindung zur SharePoint-Website hergestellt haben, in die der Berichtsserver integriert ist, können Sie die Berechtigungsebenen zur Steuerung des Zugriffs auf Inhalt und Vorgänge des Berichtsservers anzeigen lassen und ändern.</span><span class="sxs-lookup"><span data-stu-id="3242d-111">If the report server is configured for SharePoint integrated mode, and you connected to the SharePoint site that the report server is integrated with, you can view and modify the permission levels that control access to report server content and operations.</span></span>  
  
### <a name="to-create-a-role-definition"></a><span data-ttu-id="3242d-112">So erstellen Sie eine Rollendefinition</span><span class="sxs-lookup"><span data-stu-id="3242d-112">To create a role definition</span></span>  
  
1.  <span data-ttu-id="3242d-113">Erweitern Sie im Objekt-Explorer einen Berichtsserverknoten.</span><span class="sxs-lookup"><span data-stu-id="3242d-113">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="3242d-114">Erweitern Sie den Ordner Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="3242d-114">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="3242d-115">Falls Sie eine Rollendefinition auf Elementebene erstellen, klicken Sie mit der rechten Maustaste auf **Rollen**, und zeigen Sie anschließend auf **Neue Rolle**.</span><span class="sxs-lookup"><span data-stu-id="3242d-115">If you are creating an item-level role definition, right-click **Roles**, and point to **New Role**.</span></span>  
  
     <span data-ttu-id="3242d-116">Falls Sie eine Rollendefinition auf Systemebene erstellen, können Sie mit der rechten Maustaste auf **Systemrollen**klicken und anschließend auf **Neue Systemrolle**zeigen.</span><span class="sxs-lookup"><span data-stu-id="3242d-116">Or, if you are creating a system-level role definition, right-click **System Roles**, and point to **New System Role**.</span></span>  
  
4.  <span data-ttu-id="3242d-117">Geben Sie einen eindeutigen Namen für die Rolle ein.</span><span class="sxs-lookup"><span data-stu-id="3242d-117">Type a unique name for the role.</span></span> <span data-ttu-id="3242d-118">Der Name muss mindestens ein Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3242d-118">A name must contain at least one character.</span></span> <span data-ttu-id="3242d-119">Er kann auch Leerzeichen und Sonderzeichen enthalten, er darf jedoch folgende Zeichen nicht enthalten: ; ?</span><span class="sxs-lookup"><span data-stu-id="3242d-119">It can also include spaces and certain symbols, but not the characters ; ?</span></span> <span data-ttu-id="3242d-120">: \@ & = +, $/\* \< > | "oder/.</span><span class="sxs-lookup"><span data-stu-id="3242d-120">: \@ & = + , $ / \* \< > | " or /.</span></span>  
  
5.  <span data-ttu-id="3242d-121">Geben Sie optional eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="3242d-121">Optionally type a description.</span></span> <span data-ttu-id="3242d-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] wird diese Beschreibung nur auf dieser Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3242d-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] this description is visible only on this page.</span></span> <span data-ttu-id="3242d-123">Benutzer, die dieses Element im Berichts-Manager anzeigen, können diese Beschreibung in diesem Tool anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3242d-123">Users who view this item through Report Manager can see this description in that tool.</span></span>  
  
6.  <span data-ttu-id="3242d-124">Wählen Sie die Aufgaben aus, die Mitglieder dieser Rolle ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3242d-124">Select the tasks that members of this role can perform.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-or-modify-a-role-definition"></a><span data-ttu-id="3242d-125">So löschen oder ändern Sie eine Rollendefinition</span><span class="sxs-lookup"><span data-stu-id="3242d-125">To delete or modify a role definition</span></span>  
  
1.  <span data-ttu-id="3242d-126">Erweitern Sie im Objekt-Explorer einen Berichtsserverknoten.</span><span class="sxs-lookup"><span data-stu-id="3242d-126">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="3242d-127">Erweitern Sie den Ordner Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="3242d-127">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="3242d-128">Erweitern Sie den Ordner Rollen, um eine Rollendefinition auf Elementebene zu löschen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3242d-128">To delete or modify an item-level role definition, expand the Roles folder.</span></span> <span data-ttu-id="3242d-129">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3242d-129">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="3242d-130">Klicken Sie zum Löschen einer Rollendefinition mit der rechten Maustaste auf das Element, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3242d-130">To delete a role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="3242d-131">Das Dialogfeld **Objekt löschen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3242d-131">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="3242d-132">Klicken Sie zum Ändern einer Rollendefinition mit der rechten Maustaste auf das Element, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3242d-132">To modify a role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="3242d-133">Die Seite Allgemein im Dialogfeld **Benutzerrolleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3242d-133">The General page of the **User Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="3242d-134">Wählen Sie die Aufgaben aus, die Mitglieder dieser Rolle ausführen können, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3242d-134">Select the tasks that members of this role can perform, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="3242d-135">Erweitern Sie den Ordner **Systemrollen** , um eine Rollendefinition auf Systemebene zu löschen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3242d-135">To delete or modify a system-level role definition, expand the **System Roles** folder.</span></span> <span data-ttu-id="3242d-136">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3242d-136">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="3242d-137">Klicken Sie zum Löschen einer Systemrollendefinition auf Systemebene mit der rechten Maustaste auf das Element, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3242d-137">To delete a system role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="3242d-138">Das Dialogfeld **Objekt löschen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3242d-138">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="3242d-139">Klicken Sie zum Ändern einer Systemrollendefinition auf Systemebene mit der rechten Maustaste auf das Element, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3242d-139">To modify a system role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="3242d-140">Die Seite Allgemein im Dialogfeld **Systemrolleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3242d-140">The General page of the **System Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="3242d-141">Wählen Sie die Aufgaben aus, die Mitglieder dieser Rolle ausführen können, und klicken Sie dann auf **OK** , um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="3242d-141">Select the tasks that members of this role can perform, and click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3242d-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3242d-142">See Also</span></span>  
 <span data-ttu-id="3242d-143">[Herstellen einer Verbindung mit einem Berichts Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="3242d-143">[Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="3242d-144">(Create-and-manage-role-assignments.MD)</span><span class="sxs-lookup"><span data-stu-id="3242d-144">(create-and-manage-role-assignments.md)</span></span>   
 [<span data-ttu-id="3242d-145">Reporting Services in SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="3242d-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span></span>](../tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
  
