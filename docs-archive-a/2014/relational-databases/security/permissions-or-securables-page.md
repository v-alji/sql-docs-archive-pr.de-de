---
title: Seite „Berechtigungen“ oder „Sicherungsfähige Elemente“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.permissions.f1
- sql12.swb.SecurableAndEffectPermissions.f1
- sql12.swb.availabilitygroupproperties.permission.f1
- sql12.swb.common.columnperm.f1
- sql12.swb.SecurableAndEffectivePermission.f1
ms.assetid: b3bf077a-bec2-4161-ac0c-460586199906
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 80417c720258833850f07eb67f83f5c47f487ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697713"
---
# <a name="permissions-or-securables-page"></a><span data-ttu-id="4ab97-102">Seite 'Berechtigungen' oder 'Sicherungsfähige Elemente'</span><span class="sxs-lookup"><span data-stu-id="4ab97-102">Permissions or Securables Page</span></span>
  <span data-ttu-id="4ab97-103">Auf der Seite **Berechtigungen** oder **Sicherungsfähige Elemente** können die Berechtigungen für sicherungsfähige Elemente angezeigt oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-103">Use the **Permissions** page or the **Securables** page to view or set the permissions for securables.</span></span> <span data-ttu-id="4ab97-104">Diese Seite kann von vielen Orten aus geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-104">This page can be opened from many locations.</span></span> <span data-ttu-id="4ab97-105">Der Inhalt der Seite kann sich geringfügig ändern, je nachdem, wie die Seite geöffnet wird und was sie enthält.</span><span class="sxs-lookup"><span data-stu-id="4ab97-105">The contents of the page can change slightly, depending on how the page is opened and what it contains.</span></span> <span data-ttu-id="4ab97-106">Das obere Raster der Seite ist u. U. aufgefüllt, wenn die Seite geöffnet wird, oder es ist leer.</span><span class="sxs-lookup"><span data-stu-id="4ab97-106">The top grid of the page might be populated when the page opens, or it might be empty.</span></span> <span data-ttu-id="4ab97-107">Klicken Sie auf **Suchen**, um dem oberen Raster Elemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ab97-107">To add items to the upper grid, click **Search**.</span></span> <span data-ttu-id="4ab97-108">Wählen Sie im oberen Raster ein Element aus, und legen Sie dann auf der Registerkarte **Explizit** die entsprechenden Berechtigungen fest. Verwenden Sie zum Anzeigen von aggregierten Berechtigungen die Registerkarte **Effektiv** .</span><span class="sxs-lookup"><span data-stu-id="4ab97-108">In the upper grid, select an item, and then set the appropriate permissions on the **Explicit** tab. To view aggregated permissions, use the **Effective** tab.</span></span>  
  
 <span data-ttu-id="4ab97-109">Weitere Informationen zu möglichen Kombinationen aus sicherungsfähigen Elementen und Prinzipalen finden Sie bei den Links zur spezifischen Syntax für sicherungsfähige Elemente im Thema [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ab97-109">To understand the possible combinations of securables and principals, see the securable-specific syntax links in the topic [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="4ab97-110">Weitere Informationen finden Sie unter [Securables](securables.md).</span><span class="sxs-lookup"><span data-stu-id="4ab97-110">For more information, see [Securables](securables.md).</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="4ab97-111">Seitenheader</span><span class="sxs-lookup"><span data-stu-id="4ab97-111">Page Header</span></span>  
 <span data-ttu-id="4ab97-112">Der Header der Seite **Berechtigungen** oder **Sicherungsfähige Elemente** variiert je nach sicherungsfähigem Element oder Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="4ab97-112">The header of the **Permissions** or **Securables** page varies depending on the securable or principal.</span></span> <span data-ttu-id="4ab97-113">Er zeigt für das Element relevante Informationen an, z. B. den Namen.</span><span class="sxs-lookup"><span data-stu-id="4ab97-113">It displays information relevant to the item, such as its name.</span></span>  
  
## <a name="upper-grid"></a><span data-ttu-id="4ab97-114">Oberes Raster</span><span class="sxs-lookup"><span data-stu-id="4ab97-114">Upper Grid</span></span>  
 <span data-ttu-id="4ab97-115">Das obere Raster enthält ein oder mehrere Elemente, für die Berechtigungen festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="4ab97-115">The upper grid contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="4ab97-116">Das Dialogfeld enthält die Schaltfläche **Suchen** , über die Sie Objekte oder Prinzipale auswählen können, die Sie dem oberen Raster hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="4ab97-116">This dialog box provides the **Search** button for selecting objects or principals to add to the upper grid.</span></span> <span data-ttu-id="4ab97-117">Der Name des Rasters enthält u. U. **Sicherungsfähige Elemente** oder einen oder mehrere Typen an sicherungsfähigen Elementen oder Prinzipalen.</span><span class="sxs-lookup"><span data-stu-id="4ab97-117">The name of the grid might display **Securables** or one or more types of securables or principals.</span></span> <span data-ttu-id="4ab97-118">Die im oberen Raster angezeigten Spalten variieren je nach Prinzipal oder sicherungsfähigem Element.</span><span class="sxs-lookup"><span data-stu-id="4ab97-118">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="4ab97-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="4ab97-119">**Name**</span></span>  
 <span data-ttu-id="4ab97-120">Die Namen der Prinzipale oder sicherungsfähigen Elemente, die dem Raster hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-120">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="4ab97-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4ab97-121">**Type**</span></span>  
 <span data-ttu-id="4ab97-122">Beschreibt den Typ jedes Elements.</span><span class="sxs-lookup"><span data-stu-id="4ab97-122">Describes the type of each item.</span></span>  
  
## <a name="explicit-tab"></a><span data-ttu-id="4ab97-123">Registerkarte 'Explizit'</span><span class="sxs-lookup"><span data-stu-id="4ab97-123">Explicit Tab</span></span>  
 <span data-ttu-id="4ab97-124">Die Registerkarte **Explizit** enthält die möglichen Berechtigungen für die im oberen Raster ausgewählten sicherungsfähigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="4ab97-124">The **Explicit** tab lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="4ab97-125">Um die Berechtigungen zu konfigurieren, aktivieren oder deaktivieren Sie die Kontrollkästchen **Erteilen** (oder **Zulassen**), **Mit Erteilung**und **Verweigern** .</span><span class="sxs-lookup"><span data-stu-id="4ab97-125">To configure the permissions, select or clear the **Grant** (or **Allow**), **With Grant**, and **Deny** check boxes.</span></span> <span data-ttu-id="4ab97-126">Für einige explizite Berechtigungen sind nicht alle Optionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ab97-126">All options are not available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="4ab97-127">**Berechtigungen**</span><span class="sxs-lookup"><span data-stu-id="4ab97-127">**Permissions**</span></span>  
 <span data-ttu-id="4ab97-128">Der Name der Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="4ab97-128">The name of the permission.</span></span>  
  
 <span data-ttu-id="4ab97-129">**Grantor**</span><span class="sxs-lookup"><span data-stu-id="4ab97-129">**Grantor**</span></span>  
 <span data-ttu-id="4ab97-130">Der Prinzipal, der die Berechtigung erteilt.</span><span class="sxs-lookup"><span data-stu-id="4ab97-130">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="4ab97-131">**Erteilen**</span><span class="sxs-lookup"><span data-stu-id="4ab97-131">**Grant**</span></span>  
 <span data-ttu-id="4ab97-132">Aktivieren Sie diese Option, um der Anmeldung diese Berechtigung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="4ab97-132">Select to grant this permission to the login.</span></span> <span data-ttu-id="4ab97-133">Deaktivieren Sie diese Option, um diese Berechtigung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="4ab97-133">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="4ab97-134">**Mit Erteilung**</span><span class="sxs-lookup"><span data-stu-id="4ab97-134">**With Grant**</span></span>  
 <span data-ttu-id="4ab97-135">Zeigt den Status der WITH GRANT-Option für die angezeigte Berechtigung an.</span><span class="sxs-lookup"><span data-stu-id="4ab97-135">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="4ab97-136">Dieses Feld ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="4ab97-136">This box is read-only.</span></span> <span data-ttu-id="4ab97-137">Verwenden Sie die [GRANT](/sql/t-sql/statements/grant-transact-sql) -Anweisung, um diese Berechtigung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-137">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="4ab97-138">**Deny**</span><span class="sxs-lookup"><span data-stu-id="4ab97-138">**Deny**</span></span>  
 <span data-ttu-id="4ab97-139">Aktivieren Sie diese Option, um der Anmeldung diese Berechtigung zu verweigern.</span><span class="sxs-lookup"><span data-stu-id="4ab97-139">Select to deny this permission to the login.</span></span> <span data-ttu-id="4ab97-140">Deaktivieren Sie diese Option, um diese Berechtigung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="4ab97-140">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="4ab97-141">**Spaltenberechtigungen**</span><span class="sxs-lookup"><span data-stu-id="4ab97-141">**Column Permissions**</span></span>  
 <span data-ttu-id="4ab97-142">Bei Objekten, die Spalten enthalten (z.B. Tabellen, Sichten oder Tabellenwertfunktionen), wird mit der Schaltfläche **Spaltenberechtigungen** das Dialogfeld **Spaltenberechtigungen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4ab97-142">For objects that contain columns (such as tables, views, or table-valued functions), the **Column Permissions** button opens the **Column Permissions** dialog box.</span></span> <span data-ttu-id="4ab97-143">In diesem Dialogfeld können Sie für einzelne Spalten einer Tabelle oder Sicht die Berechtigungen **Erteilen**, **Zulassen**oder **Verweigern** festlegen.</span><span class="sxs-lookup"><span data-stu-id="4ab97-143">In this dialog box, you can set **Grant**, **Allow**, or **Deny** permissions on individual columns of a table or view.</span></span> <span data-ttu-id="4ab97-144">Diese Option ist nicht für alle Objekttypen bzw. Berechtigungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ab97-144">This option is not available for all object types or permissions.</span></span>  
  
## <a name="effective-tab"></a><span data-ttu-id="4ab97-145">Registerkarte 'Effektiv'</span><span class="sxs-lookup"><span data-stu-id="4ab97-145">Effective Tab</span></span>  
 <span data-ttu-id="4ab97-146">Die Berechtigungen, die ein Prinzipal einem sicherungsfähigen Element zuordnet, stammen möglicherweise aus Berechtigungen, die für mehrere unterschiedliche Prinzipale festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-146">The permissions that a principal has related to a securable may come from permissions that are set for several different principals.</span></span> <span data-ttu-id="4ab97-147">Einer Anmeldung könnten beispielsweise einzeln oder als Gruppenmitglied Berechtigungen erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-147">For example, a login might be granted permissions individually and also as a member of a group.</span></span> <span data-ttu-id="4ab97-148">Die Registerkarte **Effektiv** zeigt das Ergebnis einer Kombination aus expliziten Berechtigungen und den Berechtigungen, die aus Gruppen- oder Rollenmitgliedschaften empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="4ab97-148">The **Effective** tab shows the result of combining explicit permissions and the permissions that are received from group or role memberships.</span></span> <span data-ttu-id="4ab97-149">Erteilen-Berechtigungen sind aggregiert.</span><span class="sxs-lookup"><span data-stu-id="4ab97-149">Grant permissions are aggregated.</span></span> <span data-ttu-id="4ab97-150">Eine Verweigern-Berechtigung überschreibt alle Erteilen-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="4ab97-150">A deny permission overrides all grant permissions.</span></span>  
  
 <span data-ttu-id="4ab97-151">**Berechtigungen**</span><span class="sxs-lookup"><span data-stu-id="4ab97-151">**Permissions**</span></span>  
 <span data-ttu-id="4ab97-152">Der Name der Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="4ab97-152">The name of the permission.</span></span>  
  
 <span data-ttu-id="4ab97-153">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4ab97-153">**Column**</span></span>  
 <span data-ttu-id="4ab97-154">Die Namen der Spalten, auf die sich die Berechtigung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="4ab97-154">The names of columns that are affected by the permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab97-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ab97-155">See Also</span></span>  
 <span data-ttu-id="4ab97-156">[Rollen auf Datenbankebene](authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="4ab97-156">[Database-Level Roles](authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="4ab97-157">Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="4ab97-157">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
