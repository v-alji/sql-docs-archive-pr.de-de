---
title: Verwalten von CLR-Integrationsassemblys Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 191ccd73ca42ef4c26291e6de88f5f2b0cf565ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720023"
---
# <a name="managing-clr-integration-assemblies"></a><span data-ttu-id="d6dce-102">Verwalten von CLR-Integrationsassemblys</span><span class="sxs-lookup"><span data-stu-id="d6dce-102">Managing CLR Integration Assemblies</span></span>
  <span data-ttu-id="d6dce-103">Verwalteter Code wird kompiliert und dann in Einheiten bereitgestellt, die Assembly genannt werden.</span><span class="sxs-lookup"><span data-stu-id="d6dce-103">Managed code is compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="d6dce-104">Eine Assembly wird als DLL oder ausführbare Datei (EXE) gepackt.</span><span class="sxs-lookup"><span data-stu-id="d6dce-104">An assembly is packaged as a DLL or executable (.exe) file.</span></span> <span data-ttu-id="d6dce-105">Während eine ausführbare Datei auch alleine ausgeführt werden kann, muss eine DLL in einer vorhandenen Anwendung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="d6dce-105">While an executable file can run on its own, a DLL must be hosted in an existing application.</span></span> <span data-ttu-id="d6dce-106">Verwaltete DLL-Assemblys können in geladen und von gehostet werden [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6dce-106">Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d6dce-107">Datenbank, die die Create Assembly-Anweisung verwendet, bevor Sie in den Prozess geladen und verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6dce-107">database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used.</span></span> <span data-ttu-id="d6dce-108">Assemblys können auch von einer neueren Version aus mithilfe der ALTER ASSEMBLY-Anweisung aktualisiert oder aus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mithilfe der DROP ASSEMBLY-Anweisung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d6dce-108">Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.</span></span>  
  
 <span data-ttu-id="d6dce-109">Assemblyinformationen werden in der Tabelle `sys.assembly_files` in der Datenbank gespeichert, in der die Assembly installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6dce-109">Assembly information is stored in the `sys.assembly_files` table in the database where the assembly has been installed.</span></span> <span data-ttu-id="d6dce-110">Die Tabelle `sys.assembly_files` enthält die folgenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="d6dce-110">The `sys.assembly_files` table contains the following columns.</span></span>  
  
|<span data-ttu-id="d6dce-111">Spalte</span><span class="sxs-lookup"><span data-stu-id="d6dce-111">Column</span></span>|<span data-ttu-id="d6dce-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d6dce-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d6dce-113">assembly_id</span><span class="sxs-lookup"><span data-stu-id="d6dce-113">assembly_id</span></span>|<span data-ttu-id="d6dce-114">Der für die Assembly definierte Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="d6dce-114">The identifier defined for the assembly.</span></span> <span data-ttu-id="d6dce-115">Diese Nummer wird allen Objekten mit Bezug auf dieselbe Assembly zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d6dce-115">This number is assigned to all objects relating to the same assembly.</span></span>|  
|<span data-ttu-id="d6dce-116">name</span><span class="sxs-lookup"><span data-stu-id="d6dce-116">name</span></span>|<span data-ttu-id="d6dce-117">Der Name des Objekts.</span><span class="sxs-lookup"><span data-stu-id="d6dce-117">The name of the object.</span></span>|  
|<span data-ttu-id="d6dce-118">file_id</span><span class="sxs-lookup"><span data-stu-id="d6dce-118">file_id</span></span>|<span data-ttu-id="d6dce-119">Eine Nummer, die die einzelnen Objekte identifiziert, wobei das erste Objekt, das einer angegebenen `assembly_id` zugeordnet ist, den Wert 1 erhält.</span><span class="sxs-lookup"><span data-stu-id="d6dce-119">A number identifying each object, with the first object associated with a given `assembly_id` being given the value of 1.</span></span> <span data-ttu-id="d6dce-120">Wenn mehrere Objekte derselben `assembly_id` zugeordnet werden, wird jeder nachfolgende `file_id`-Wert um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="d6dce-120">If multiple objects are associated with the same `assembly_id`, then each subsequent `file_id` value is incremented by 1.</span></span>|  
|<span data-ttu-id="d6dce-121">Inhalt</span><span class="sxs-lookup"><span data-stu-id="d6dce-121">content</span></span>|<span data-ttu-id="d6dce-122">Die Hexadezimaldarstellung der Assembly oder Datei.</span><span class="sxs-lookup"><span data-stu-id="d6dce-122">The hexadecimal representation of the assembly or file.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="d6dce-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d6dce-123">In This Section</span></span>  
 [<span data-ttu-id="d6dce-124">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="d6dce-124">Creating an Assembly</span></span>](creating-an-assembly.md)  
 <span data-ttu-id="d6dce-125">Erläutert das Erstellen der Assemblys SAFE, EXTERNAL_ACCESS und UNSAFE CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6dce-125">Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d6dce-126">Ändern einer Assembly</span><span class="sxs-lookup"><span data-stu-id="d6dce-126">Altering an Assembly</span></span>](altering-an-assembly.md)  
 <span data-ttu-id="d6dce-127">Beschreibt das Aktualisieren von CLR-Assemblys in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6dce-127">Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d6dce-128">Löschen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="d6dce-128">Dropping an Assembly</span></span>](dropping-an-assembly.md)  
 <span data-ttu-id="d6dce-129">Erläutert das Löschen von CLR-Assemblys aus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6dce-129">Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6dce-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6dce-130">See Also</span></span>  
 <span data-ttu-id="d6dce-131">[Sicherheit der CLR-Integration](../security/clr-integration-security.md) </span><span class="sxs-lookup"><span data-stu-id="d6dce-131">[CLR Integration Security](../security/clr-integration-security.md) </span></span>  
 [<span data-ttu-id="d6dce-132">CLR-Integration und Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="d6dce-132">CLR Integration Code Access Security</span></span>](../security/clr-integration-code-access-security.md)  
  
  
