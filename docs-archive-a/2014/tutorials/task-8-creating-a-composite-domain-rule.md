---
title: 'Aufgabe 8: Erstellen einer Verbund Domänen Regel | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4766a1206eb09e98bb20d3712a63762126b682b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620687"
---
# <a name="task-8-creating-a-composite-domain-rule"></a><span data-ttu-id="d0f15-102">Aufgabe 8: Erstellen einer Verbunddomänenregel</span><span class="sxs-lookup"><span data-stu-id="d0f15-102">Task 8: Creating a Composite Domain Rule</span></span>
  <span data-ttu-id="d0f15-103">In dieser Aufgabe erstellen Sie eine Regel für die Verbund Domäne der **Adressvalidierung** .</span><span class="sxs-lookup"><span data-stu-id="d0f15-103">In this task, you create a rule for the **Address Validation** composite domain.</span></span> <span data-ttu-id="d0f15-104">Sie definieren eine Domänen übergreifende Regel: Wenn **Stadt** " **Los Angeles**" ist, muss der **Status** " **ca** " lauten, wobei " **City** " und " **State** " zwei Domänen</span><span class="sxs-lookup"><span data-stu-id="d0f15-104">You define a cross-domain rule: if **City** is **Los Angeles**, **State** must be **CA** where **City** and **State** are two domains.</span></span>  
  
1.  <span data-ttu-id="d0f15-105">Wechseln Sie im rechten Bereich zur Registerkarte für die **CD-Regeln** .</span><span class="sxs-lookup"><span data-stu-id="d0f15-105">In the right pane, switch to the **CD Rules** tab.</span></span>  
  
2.  <span data-ttu-id="d0f15-106">Klicken Sie auf der Symbolleiste auf **neue Domänen Regel hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="d0f15-106">Click **Add a new domain rule** from the toolbar.</span></span>  
  
3.  <span data-ttu-id="d0f15-107">Geben Sie **City-State Rule** für **Name** ein, und drücken **Sie Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="d0f15-107">Type **City-State Rule** for **Name** and press **ENTER**.</span></span>  
  
4.  <span data-ttu-id="d0f15-108">Wählen Sie im Bereich **Regel erstellen** in der Liste Domäne die Option **Stadt** aus, und wählen Sie Bedingungs **Wert ist gleich** aus, und geben Sie für den Wert den Wert **Los Angeles** ein.</span><span class="sxs-lookup"><span data-stu-id="d0f15-108">In the **Build a Rule** pane, select **City** in the domain list, and select condition **Value is equal to** and type **Los Angeles** for the value.</span></span>  
  
5.  <span data-ttu-id="d0f15-109">Wählen Sie im **Then** -Bereich **State** in der Liste Domäne aus, und wählen Sie **Wert ist gleich**aus, geben Sie **ca** als Wert ein, und drücken Sie die **Tab**-Taste.</span><span class="sxs-lookup"><span data-stu-id="d0f15-109">In the **Then** pane, select **State** in the domain list, and select **Value is equal to**, type **CA** for the value, and press **TAB**.</span></span>  
  
     <span data-ttu-id="d0f15-110">![Verbunddomänenregel](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Verbunddomänenregel")</span><span class="sxs-lookup"><span data-stu-id="d0f15-110">![Composite Domain Rule](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Composite Domain Rule")</span></span>  
  
6.  <span data-ttu-id="d0f15-111">Klicken Sie am unteren Rand der Seite auf die Schaltfläche **Schließen** , um zur Hauptseite des DQS-Clients zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d0f15-111">Click **Close** button at the bottom of the page to switch to the main page of DQS Client.</span></span> <span data-ttu-id="d0f15-112">In der nächsten Lektion veröffentlichen Sie die Wissensdatenbank.</span><span class="sxs-lookup"><span data-stu-id="d0f15-112">You will publish the knowledge base in the next lesson.</span></span> <span data-ttu-id="d0f15-113">Beachten Sie, dass die Wissensdatenbank gesperrt ist (Schlosssymbol).</span><span class="sxs-lookup"><span data-stu-id="d0f15-113">Notice that the knowledge base is in locked state (lock icon).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d0f15-114">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d0f15-114">Next Step</span></span>  
 [<span data-ttu-id="d0f15-115">Aufgabe 9: Konfigurieren eines Verweisdatendiensts</span><span class="sxs-lookup"><span data-stu-id="d0f15-115">Task 9: Configuring a Reference Data Service</span></span>](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
