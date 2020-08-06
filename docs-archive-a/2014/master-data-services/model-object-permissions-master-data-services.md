---
title: Berechtigungen für Modellobjekte (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], model objects
- models [Master Data Services], object permissions
ms.assetid: fab6335b-4cae-47de-ae7c-6c4743e0680f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4cc64d753b680cfabc3707a29c6d9de631708c20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621543"
---
# <a name="model-object-permissions-master-data-services"></a><span data-ttu-id="875b8-102">Berechtigungen für Modellobjekte (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="875b8-102">Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="875b8-103">Berechtigungen für Modellobjekte sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="875b8-103">Model object permissions are mandatory.</span></span> <span data-ttu-id="875b8-104">Sie bestimmen die Attribute, auf die ein Benutzer im Funktionsbereich **Explorer** der Benutzeroberfläche zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="875b8-104">They determine the attributes a user can access in the **Explorer** functional area of the UI.</span></span>  
  
 <span data-ttu-id="875b8-105">Wenn Sie z.B. der Entität „Product“ die Benutzerberechtigung **Aktualisieren** zuweisen, kann der Benutzer alle Attribute der Entität „Product“ aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="875b8-105">For example, if you assign a user **Update** permission to the Product entity, the user can update all of the attributes of the Product entity.</span></span> <span data-ttu-id="875b8-106">Wenn Sie einem einzelnen Attribut die Berechtigung **Aktualisieren** zuweisen, kann der Benutzer nur dieses Attribut aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="875b8-106">If you assign **Update** permission to a single attribute, the user can update that attribute only.</span></span>  
  
 <span data-ttu-id="875b8-107">Um die jedem Attributwert zugewiesene Sicherheit zu ermitteln, werden Modellobjektberechtigungen mit Hierarchieelementberechtigungen kombiniert, die die Elemente bestimmen, auf die ein Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="875b8-107">To determine security assigned on each individual attribute value, model object permissions are combined with hierarchy member permissions, which determine the members a user can access.</span></span>  
  
 <span data-ttu-id="875b8-108">Um einem Benutzer Zugriff auf einen anderen Funktionsbereich als **Explorer**zu geben, muss der Benutzer ein Modell Administrator sein, der auch das Zuweisen von Berechtigungen für Modell Objekte umfasst.</span><span class="sxs-lookup"><span data-stu-id="875b8-108">To give a user access to a functional area other than **Explorer**, the user must be a model administrator, which also involves assigning model object permissions.</span></span> <span data-ttu-id="875b8-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="875b8-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="875b8-110">Berechtigungen für Modell Objekte werden in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Benutzeroberfläche (User Interface, UI) im Funktionsbereich **Benutzer-und Gruppenberechtigungen** auf der Registerkarte **Modelle** zugewiesen. Auf dieser Registerkarte wird das Modell als Baumstruktur dargestellt.</span><span class="sxs-lookup"><span data-stu-id="875b8-110">Model object permissions are assigned in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), in the **User and Group Permissions** functional area on the **Models** tab. On this tab, the model is represented as a tree structure.</span></span> <span data-ttu-id="875b8-111">Wenn Sie einem Objekt in der Struktur eine Berechtigung zuweisen, wird diese Berechtigung von allen untergeordneten Objekten geerbt.</span><span class="sxs-lookup"><span data-stu-id="875b8-111">When you assign permission to an object in the tree, all objects below inherit that permission.</span></span> <span data-ttu-id="875b8-112">Sie können die Vererbung überschreiben, indem Sie einzelnen Objekten eine Berechtigung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="875b8-112">You can override that inheritance by assigning permission to individual objects.</span></span>  
  
 <span data-ttu-id="875b8-113">Sie können Modell Objekten die Berechtigung " **Lesen**", " **Aktualisieren**" oder " **verweigern** " zuweisen.</span><span class="sxs-lookup"><span data-stu-id="875b8-113">You can assign **Read-only**, **Update**, or **Deny** permission to model objects.</span></span> <span data-ttu-id="875b8-114">Wenn Sie auf der Registerkarte **Modelle** keine Berechtigungen zuweisen, kann der Benutzer keine Modelle oder Daten in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="875b8-114">If you do not assign any permissions on the **Models** tab, the user cannot view any models or data in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="875b8-115">Bewährte Methode</span><span class="sxs-lookup"><span data-stu-id="875b8-115">Best Practice</span></span>  
 <span data-ttu-id="875b8-116">Im Allgemeinen sollten Sie dem Modell Objekt die Berechtigung **Aktualisieren** zuweisen und dann untergeordneten Objekten die Berechtigung explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="875b8-116">In general, you should assign **Update** permission to the model object, and then explicitly assign permission to objects underneath.</span></span> <span data-ttu-id="875b8-117">Wenn Sie untergeordneten Objekten keine Berechtigung zuweisen, werden die Berechtigungen geerbt, und der Benutzer ist Administrator.</span><span class="sxs-lookup"><span data-stu-id="875b8-117">If you do not assign permission to objects underneath, the permissions are inherited and the user is an administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875b8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="875b8-118">See Also</span></span>  
 <span data-ttu-id="875b8-119">[Zuweisen von Berechtigungen für Modell Objekte &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="875b8-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="875b8-120">[Modell Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="875b8-120">[Model Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="875b8-121">[Berechtigungen für Funktionsbereiche &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="875b8-121">[Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="875b8-122">[Hierarchie Element Berechtigungen &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="875b8-122">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="875b8-123">Vorgehensweise: Festlegen von Berechtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="875b8-123">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
