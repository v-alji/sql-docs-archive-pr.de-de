---
title: Referenz zur Benutzeroberfläche des Dialog Felds Paket Rollen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.packageroles.f1
helpviewer_keywords:
- Package Roles dialog box
ms.assetid: 63f13416-c0aa-4480-a336-ef1e6e31a860
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 389b29ddee5674af7ecd106f4f82d61bbb3a0f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718556"
---
# <a name="package-roles-dialog-box-ui-reference"></a><span data-ttu-id="a4296-102">Referenz zur Benutzeroberfläche des Dialogfelds Paketrollen</span><span class="sxs-lookup"><span data-stu-id="a4296-102">Package Roles Dialog Box UI Reference</span></span>
  <span data-ttu-id="a4296-103">Verwenden Sie das Dialogfeld **Paketrollen** , das in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]verfügbar ist, um die Rollen auf Datenbankebene anzugeben, die Lesezugriff auf das Paket besitzen, sowie die Rollen auf Datenbankebene, die Schreibzugriff auf das Paket besitzen.</span><span class="sxs-lookup"><span data-stu-id="a4296-103">Use the **Package Roles** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to specify the database-level roles that have read access to the package and the database-level roles that have write access to the package.</span></span> <span data-ttu-id="a4296-104">Rollen auf Datenbankebene gelten nur für Pakete, die in der -Datenbank [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a4296-104">Database-level roles apply only to packages that are stored in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span></span>  
  
 <span data-ttu-id="a4296-105">Weitere Informationen zu den Rollen auf Datenbankebene von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] und ihren Berechtigungen finden Sie unter [Integration Services-Rollen &#40;SSIS-Dienst&#41;](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="a4296-105">To learn more about the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] database-level roles and their permissions, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>  
  
 <span data-ttu-id="a4296-106">Die im Dialogfeld aufgeführten Rollen sind die aktuellen Rollen der **msdb** -Systemdatenbank.</span><span class="sxs-lookup"><span data-stu-id="a4296-106">The roles listed in the dialog box are the current database roles of the **msdb** system database.</span></span> <span data-ttu-id="a4296-107">Wenn keine Rollen ausgewählt sind, gelten die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Standardrollen.</span><span class="sxs-lookup"><span data-stu-id="a4296-107">If no roles are selected, the default [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] roles apply.</span></span> <span data-ttu-id="a4296-108">Standardmäßig enthält die Leserolle **db_ssisadmin**, **db_ssisoperator**und den Benutzer, der das Paket erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="a4296-108">By default, the reader role includes **db_ssisadmin**, **db_ssisoperator**, and the user who created the package.</span></span> <span data-ttu-id="a4296-109">Ein Benutzer, der Mitglied einer dieser Rollen ist oder die Pakete erstellt hat, kann Pakete aufzählen, anzeigen, exportieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="a4296-109">A user who is a member of one of these roles or created the packages can enumerate, view, export, and run packages.</span></span> <span data-ttu-id="a4296-110">Standardmäßig schließt die Schreibrolle **db_ssisadmin** und den Benutzer ein, der das Paket erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="a4296-110">By default, the writer role includes **db_ssisadmin** and the user who created the package.</span></span> <span data-ttu-id="a4296-111">Ein Benutzer, der Mitglied dieser Rolle ist, und der Benutzer, der die Pakete erstellt hat, kann Pakete importieren, löschen und ändern.</span><span class="sxs-lookup"><span data-stu-id="a4296-111">A user who is a member of this role and the user who created the packages can import, delete, and change packages.</span></span>  
  
 <span data-ttu-id="a4296-112">Die **ownersid** -Spalte in der **sysssispackages** -Tabelle enthält die eindeutige Sicherheits-ID des Benutzers, der das Paket erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="a4296-112">The **ownersid** column in the **sysssispackages** table lists the unique security identifier of the user who created the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4296-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a4296-113">Options</span></span>  
 <span data-ttu-id="a4296-114">**Paketname**</span><span class="sxs-lookup"><span data-stu-id="a4296-114">**Package Name**</span></span>  
 <span data-ttu-id="a4296-115">Gibt den Namen des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="a4296-115">Specify the name of the package.</span></span>  
  
 <span data-ttu-id="a4296-116">**Leser-Rolle**</span><span class="sxs-lookup"><span data-stu-id="a4296-116">**Reader Role**</span></span>  
 <span data-ttu-id="a4296-117">Auswählen einer Rolle in der Liste.</span><span class="sxs-lookup"><span data-stu-id="a4296-117">Select a role in the list.</span></span>  
  
 <span data-ttu-id="a4296-118">**Schreibrolle**</span><span class="sxs-lookup"><span data-stu-id="a4296-118">**Writer Role**</span></span>  
 <span data-ttu-id="a4296-119">Auswählen einer Rolle in der Liste</span><span class="sxs-lookup"><span data-stu-id="a4296-119">Select a role in the list</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4296-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4296-120">See Also</span></span>  
 <span data-ttu-id="a4296-121">[Rollen auf Datenbankebene](../relational-databases/security/authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="a4296-121">[Database-Level Roles](../relational-databases/security/authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="a4296-122">Sicherheitsübersicht &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a4296-122">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
