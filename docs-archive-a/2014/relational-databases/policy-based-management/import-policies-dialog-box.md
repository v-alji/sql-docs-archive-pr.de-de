---
title: Dialogfeld „Richtlinien importieren“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609183"
---
# <a name="import-policies-dialog-box"></a><span data-ttu-id="cb129-102">Dialogfeld 'Richtlinien importieren'</span><span class="sxs-lookup"><span data-stu-id="cb129-102">Import Policies Dialog Box</span></span>
  <span data-ttu-id="cb129-103">Mithilfe dieses Dialogfelds können Sie ein oder mehrere Richtlinien (und deren referenzierte Bedingung), die als XML-Dateien gespeichert sind, in die aktuelle [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Instanz importieren.</span><span class="sxs-lookup"><span data-stu-id="cb129-103">Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb129-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="cb129-104">Options</span></span>  
 <span data-ttu-id="cb129-105">**Zu importierende Dateien**</span><span class="sxs-lookup"><span data-stu-id="cb129-105">**Files to import**</span></span>  
 <span data-ttu-id="cb129-106">Um eine Richtlinie aus einer XML-Datei zu importieren, geben Sie den Pfad und den Namen der Datei ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="cb129-106">To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.</span></span>  
  
 <span data-ttu-id="cb129-107">**Duplikate mit importierten Elementen ersetzen**</span><span class="sxs-lookup"><span data-stu-id="cb129-107">**Replace duplicates with items imported**</span></span>  
 <span data-ttu-id="cb129-108">Wählen Sie diese Option aus, um eine vorhandene Richtlinie oder Bedingung mit demselben Namen zu überschreiben, wenn diese bereits in dieser [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cb129-108">Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance.</span></span> <span data-ttu-id="cb129-109">Eine Bedingung mit einer abhängigen Richtlinie kann nur überschrieben werden, wenn die abhängige Richtlinie ebenfalls überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="cb129-109">A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten.</span></span> <span data-ttu-id="cb129-110">Wenn diese Option nicht aktiviert ist, verursacht eine vorhandene Bedingung, die denselben Bedingungsausdruck verwendet, keinen Fehler.</span><span class="sxs-lookup"><span data-stu-id="cb129-110">If this option is not selected, an existing condition that is using the same condition expression will not cause an error.</span></span>  
  
 <span data-ttu-id="cb129-111">**Richtlinienstatus**</span><span class="sxs-lookup"><span data-stu-id="cb129-111">**Policy state**</span></span>  
 <span data-ttu-id="cb129-112">Wählen Sie für die importierte Richtlinie den gewünschten Status aus:</span><span class="sxs-lookup"><span data-stu-id="cb129-112">Select the state that you want for the imported policy:</span></span>  
  
-   <span data-ttu-id="cb129-113">**Richtlinienstatus beim Import beibehalten**</span><span class="sxs-lookup"><span data-stu-id="cb129-113">**Preserve policy state on import**</span></span>  
  
-   <span data-ttu-id="cb129-114">**Alle Richtlinien beim Import aktivieren**</span><span class="sxs-lookup"><span data-stu-id="cb129-114">**Enable all policies on import**</span></span>  
  
-   <span data-ttu-id="cb129-115">**Alle Richtlinien beim Import deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="cb129-115">**Disable all policies on import**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb129-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb129-116">See Also</span></span>  
 <span data-ttu-id="cb129-117">[Verwalten von Servern mit der richtlinienbasierten Verwaltung](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="cb129-117">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 <span data-ttu-id="cb129-118">[Importieren einer Richtlinie der richtlinienbasierten Verwaltung](import-a-policy-based-management-policy.md) </span><span class="sxs-lookup"><span data-stu-id="cb129-118">[Import a Policy-Based Management Policy](import-a-policy-based-management-policy.md) </span></span>  
 [<span data-ttu-id="cb129-119">Exportieren einer Richtlinie der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="cb129-119">Export a Policy-Based Management Policy</span></span>](export-a-policy-based-management-policy.md)  
  
  
