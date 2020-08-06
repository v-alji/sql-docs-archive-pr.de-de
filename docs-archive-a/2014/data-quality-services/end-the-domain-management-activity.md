---
title: Beenden der Domänen Verwaltungs Aktivität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ab6505ad-3090-453b-bb01-58435e7fa7c0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c776674a369bfae8c7da6fa0deabfbd932029570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700256"
---
# <a name="end-the-domain-management-activity"></a><span data-ttu-id="35a40-102">Beenden der Domänenverwaltungsaktivität</span><span class="sxs-lookup"><span data-stu-id="35a40-102">End the Domain Management Activity</span></span>
  <span data-ttu-id="35a40-103">In diesem Thema wird beschrieben wie die Domänenverwaltungsaktivität in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) abgeschlossen, geschlossen oder abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="35a40-103">This topic describes how to complete, close, or cancel the domain management activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="35a40-104">Die Domänenverwaltung wird nicht von einem Assistenten durchgeführt. Daher können die unten beschriebenen Steuerelemente auf allen Seiten der Domänenverwaltungsaktivität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35a40-104">Domain management is not performed by a wizard, so the controls described below can used from any of the pages of the domain management activity.</span></span>  
  
## <a name="end-domain-management"></a><span data-ttu-id="35a40-105">Beenden der Domänenverwaltung</span><span class="sxs-lookup"><span data-stu-id="35a40-105">End Domain Management</span></span>  
 <span data-ttu-id="35a40-106">**Fertig stellen**</span><span class="sxs-lookup"><span data-stu-id="35a40-106">**Finish**</span></span>  
 <span data-ttu-id="35a40-107">Klicken Sie auf diese Schaltfläche, um die Domänenverwaltung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="35a40-107">Click to complete domain management.</span></span> <span data-ttu-id="35a40-108">Ein Popupfenster mit den folgenden Optionen wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="35a40-108">A popup will be displayed enabling you to do the following:</span></span>  
  
-   <span data-ttu-id="35a40-109">**Ja – Wissensdatenbank veröffentlichen und beenden**: Die Wissensdatenbank wird veröffentlicht und kann vom aktuellen Benutzer oder von anderen Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35a40-109">**Yes - Publish the knowledge base and exit**: The knowledge base will be published for the current user or others to use.</span></span> <span data-ttu-id="35a40-110">Die Wissensdatenbank wird nicht gesperrt, der Status der Wissensdatenbank (in der Wissensdatenbanktabelle) wird auf leer festgelegt, und die Aktivitäten für die Domänenverwaltung sowie die Wissensermittlung sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35a40-110">The knowledge base will not be locked, the state of the knowledge base (in the knowledge base table) will be set to empty, and both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="35a40-111">Sie kehren zur Seite „Wissensdatenbank öffnen“ zurück.</span><span class="sxs-lookup"><span data-stu-id="35a40-111">You will be returned to the Open Knowledge Base screen.</span></span>  
  
-   <span data-ttu-id="35a40-112">**Nein, die Arbeit in der Wissensdatenbank speichern und beenden**: Ihre Arbeit wird gespeichert, die Wissensdatenbank bleibt gesperrt, und der Status der Wissensdatenbank wird auf in Arbeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="35a40-112">**No - Save the work on the knowledge base and exit**: Your work will be saved, the knowledge base will remained locked, and the state of the knowledge base will be set to In work.</span></span> <span data-ttu-id="35a40-113">Sowohl die Domänenverwaltungs- als auch die Wissensermittlungsaktivitäten sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35a40-113">Both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="35a40-114">Sie kehren zur Startseite zurück.</span><span class="sxs-lookup"><span data-stu-id="35a40-114">You will be returned to the home page.</span></span>  
  
-   <span data-ttu-id="35a40-115">**Abbrechen-auf dem aktuellen Bildschirm bleiben**: das Popup Fenster wird geschlossen, und Sie werden zum Bildschirm "Domänen Verwaltung" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="35a40-115">**Cancel - Stay on the current screen**: The popup will be closed and you will be returned to the Domain Management screen.</span></span>  
  
 <span data-ttu-id="35a40-116">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="35a40-116">**Cancel**</span></span>  
 <span data-ttu-id="35a40-117">Klicken Sie auf diese Schaltfläche, um die Domänenverwaltungsaktivität abzubrechen, ohne die Arbeit zu speichern, und zur DQS-Startseite zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="35a40-117">Click to terminate the Domain Management activity, losing your work, and return to the DQS home page.</span></span>  
  
 <span data-ttu-id="35a40-118">**Close**</span><span class="sxs-lookup"><span data-stu-id="35a40-118">**Close**</span></span>  
 <span data-ttu-id="35a40-119">Klicken Sie auf diese Schaltfläche, um die Arbeit zu speichern, und kehren Sie zur DQS-Startseite zurück.</span><span class="sxs-lookup"><span data-stu-id="35a40-119">Click to save your work, and return to the DQS home page.</span></span> <span data-ttu-id="35a40-120">Die Wissensdatenbank wird gesperrt, und der Status der Wissensdatenbank wird in der Wissensdatenbanktabelle auf der Seite **Wissensdatenbank öffnen** als **Domänenverwaltung**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="35a40-120">The knowledge base will be locked, and the state of the knowledge base in the knowledge base table in the **Open Knowledge Base** screen will be **Domain Management**.</span></span> <span data-ttu-id="35a40-121">Nachdem Sie auf **Schließen**geklickt haben, um die Wissensermittlung durchzuführen, müssen Sie auf **Domänenverwaltung** klicken, auf **Fertig stellen**klicken und anschließend **Ja** (um die Wissensdatenbank zu veröffentlichen) oder **Nein** (um die Arbeit in der Wissensdatenbank zu speichern und zu beenden) auswählen.</span><span class="sxs-lookup"><span data-stu-id="35a40-121">After clicking **Close**, to perform the Knowledge Discovery activity, you would have to return to the **Domain Management** screen, click **Finish**, and then click either **Yes** to publish the knowledge base or **No** to save the work on the knowledge base and exit.</span></span>  <span data-ttu-id="35a40-122">Weitere Informationen zum Öffnen einer gesperrter Wissensdatenbank finden Sie unter [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="35a40-122">For more information on opening a locked knowledge base, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
  
