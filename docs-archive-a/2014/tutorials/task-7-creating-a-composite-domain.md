---
title: 'Aufgabe 7: Erstellen einer Verbund Domäne | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42936d25e267bcad5ba8ae512750f9e12f041579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608133"
---
# <a name="task-7-creating-a-composite-domain"></a><span data-ttu-id="d36ab-102">Aufgabe 7: Erstellen einer Verbunddomäne</span><span class="sxs-lookup"><span data-stu-id="d36ab-102">Task 7: Creating a Composite Domain</span></span>
  <span data-ttu-id="d36ab-103">In dieser Aufgabe erstellen Sie eine Verbund Domäne, **Address Validation**(Adress **Zeile**, **Ort**, **Bundesland**und **ZIP** -Domänen).</span><span class="sxs-lookup"><span data-stu-id="d36ab-103">In this task, you create a composite domain, **Address Validation**, which comprises **Address Line**, **City**, **State**, and **Zip** domains.</span></span> <span data-ttu-id="d36ab-104">Mit einer Verbunddomäne können Sie eine domänenübergreifende Regel definieren, die mehrere Domänen an einer Regel beteiligt.</span><span class="sxs-lookup"><span data-stu-id="d36ab-104">A composite domain lets you define a cross-domain rule that involves multiple domains in a rule.</span></span> <span data-ttu-id="d36ab-105">Eine Verbunddomäne hat weitere Vorteile, beispielsweise die Möglichkeit, einen Feldwert für mehrere Domänen zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="d36ab-105">There are other advantages to a composite domain such as being able to parse a field value into multiple domains.</span></span>  <span data-ttu-id="d36ab-106">Beispielsweise kann ein Wert für ein Feld "Full Name" für separate Domänen "First Name", "Middle Name" und "Last Name" analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="d36ab-106">For example, a value for a Full Name field can be parsed into separate First Name, Middle Name, and Last Name domains.</span></span> <span data-ttu-id="d36ab-107">Im Rahmen dieses Lernprogramms definieren Sie nur eine domänenübergreifende Regel.</span><span class="sxs-lookup"><span data-stu-id="d36ab-107">In this tutorial, you only define a cross-domain rule.</span></span> <span data-ttu-id="d36ab-108">Weitere Informationen finden Sie unter [Verwalten einer Verbund Domäne](https://msdn.microsoft.com/library/hh510399.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d36ab-108">See [Managing a Composite Domain](https://msdn.microsoft.com/library/hh510399.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="d36ab-109">Klicken Sie im linken Bereich auf der Symbolleiste auf die Schaltfläche **Verbund Domäne erstellen** .</span><span class="sxs-lookup"><span data-stu-id="d36ab-109">In the left pane, click **Create a composite domain** button on the toolbar.</span></span>  
  
     <span data-ttu-id="d36ab-110">![Verbunddomäne erstellen (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Verbunddomäne erstellen (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="d36ab-110">![Create a Composite Domain Toolbar Button](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Create a Composite Domain Toolbar Button")</span></span>  
  
2.  <span data-ttu-id="d36ab-111">Geben Sie die **Adressvalidierung** für den **Verbund Domänen Namen**ein.</span><span class="sxs-lookup"><span data-stu-id="d36ab-111">Enter **Address Validation** for the **Composite Domain Name**.</span></span>  
  
     <span data-ttu-id="d36ab-112">![Beheben von Überprüfungsfehlern bei Verbunddomänen](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Beheben von Überprüfungsfehlern bei Verbunddomänen")</span><span class="sxs-lookup"><span data-stu-id="d36ab-112">![Address Validation Composite Domain](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Address Validation Composite Domain")</span></span>  
  
3.  <span data-ttu-id="d36ab-113">Wählen Sie in der Liste Domäne die Option **address line**, **City**, **State**und **ZIP** aus, und klicken Sie auf den **Pfeil nach rechts** , um Sie der Liste **Domänen in Verbund Domäne** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d36ab-113">From the domain list select **Address Line**, **City**, **State**, and **Zip** and click **right arrow** to add them to the **Domains in Composite Domain** list.</span></span>  
  
4.  <span data-ttu-id="d36ab-114">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d36ab-114">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d36ab-115">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d36ab-115">Next Step</span></span>  
 [<span data-ttu-id="d36ab-116">Aufgabe 8: Erstellen einer Verbunddomänenregel</span><span class="sxs-lookup"><span data-stu-id="d36ab-116">Task 8: Creating a Composite Domain Rule</span></span>](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
