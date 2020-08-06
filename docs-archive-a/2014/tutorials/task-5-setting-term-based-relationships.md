---
title: 'Aufgabe 5: Festlegen von Begriffs basierten Beziehungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6569d512-637d-4f7b-82e1-1e8582278b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1589ec5843053baa6c42a0b9b0dec019c887da9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720404"
---
# <a name="task-5-setting-term-based-relationships"></a><span data-ttu-id="e69c1-102">Aufgabe 5: Festlegen begriffsbasierter Beziehungen</span><span class="sxs-lookup"><span data-stu-id="e69c1-102">Task 5: Setting Term Based Relationships</span></span>
  <span data-ttu-id="e69c1-103">In dieser Aufgabe definieren Sie einige Begriffs basierte Beziehungen für Werte für die Domäne **Supplier Name** .</span><span class="sxs-lookup"><span data-stu-id="e69c1-103">In this task, you define a few term-based relations for values for the **Supplier Name** domain.</span></span> <span data-ttu-id="e69c1-104">Eine Begriffs basierte Beziehung ermöglicht es Ihnen, eine Korrektur an einem Begriff vorzunehmen, der Teil eines Werts in einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="e69c1-104">A term-based relation enables you to make a correction to a term that is part of a value in a domain.</span></span> <span data-ttu-id="e69c1-105">Mehrere Werte, die abgesehen von der Schreibweise eines gemeinsamen Teils identisch sind, werden als identische Synonyme angesehen.</span><span class="sxs-lookup"><span data-stu-id="e69c1-105">It enables multiple values that are identical except for the spelling of a common part of them to be considered identical synonyms.</span></span> <span data-ttu-id="e69c1-106">Beispielsweise kann **Inc.** in **integriert**werden.</span><span class="sxs-lookup"><span data-stu-id="e69c1-106">For example, **Inc.** can be corrected to **Incorporated**.</span></span> <span data-ttu-id="e69c1-107">DQS verwendet diese Beziehungen bei der Wissensermittlung, Bereinigung oder beim Abgleich.</span><span class="sxs-lookup"><span data-stu-id="e69c1-107">DQS uses these relations in the knowledge discovery, cleansing, or matching processes.</span></span> <span data-ttu-id="e69c1-108">Weitere Informationen finden Sie unter [Erstellen von Begriffs basierten Beziehungen](https://msdn.microsoft.com/library/hh510404.aspx) .</span><span class="sxs-lookup"><span data-stu-id="e69c1-108">See [Create Term-based Relations](https://msdn.microsoft.com/library/hh510404.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="e69c1-109">Wählen Sie in der **Liste Domäne**den **Namen Lieferanten Name** aus.</span><span class="sxs-lookup"><span data-stu-id="e69c1-109">Select **Supplier Name** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="e69c1-110">Wechseln Sie im rechten Bereich zur Registerkarte **Begriffs basierte Beziehungen** .</span><span class="sxs-lookup"><span data-stu-id="e69c1-110">Switch to the **Term-Based Relationships** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="e69c1-111">Klicken Sie auf der Symbolleiste auf neue Beziehungs Schaltfläche **Hinzufügen** , um der Tabelle eine Beziehung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e69c1-111">Click **Add new relation** button on the toolbar to add a relation to the table.</span></span>  
  
4.  <span data-ttu-id="e69c1-112">Geben Sie **Co.** für das Feld **Wert** und **Unternehmen** für das Feld **korrigieren in** ein.</span><span class="sxs-lookup"><span data-stu-id="e69c1-112">Type **Co.** for the **Value** field and **Company** for the **Correct To** field.</span></span>  
  
5.  <span data-ttu-id="e69c1-113">Wiederholen Sie die beiden vorherigen Schritten für folgende Werte:</span><span class="sxs-lookup"><span data-stu-id="e69c1-113">Repeat the previous two steps for the following values:</span></span>  
  
    |<span data-ttu-id="e69c1-114">Wert</span><span class="sxs-lookup"><span data-stu-id="e69c1-114">Value</span></span>|<span data-ttu-id="e69c1-115">Korrigieren in</span><span class="sxs-lookup"><span data-stu-id="e69c1-115">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="e69c1-116">Corp.</span><span class="sxs-lookup"><span data-stu-id="e69c1-116">Corp.</span></span>|<span data-ttu-id="e69c1-117">Corporation</span><span class="sxs-lookup"><span data-stu-id="e69c1-117">Corporation</span></span>|  
    |<span data-ttu-id="e69c1-118">Inc.</span><span class="sxs-lookup"><span data-stu-id="e69c1-118">Inc.</span></span>|<span data-ttu-id="e69c1-119">Incorporated</span><span class="sxs-lookup"><span data-stu-id="e69c1-119">Incorporated</span></span>|  
  
     <span data-ttu-id="e69c1-120">![Begriffsbasierte Beziehungen](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Begriffsbasierte Beziehungen")</span><span class="sxs-lookup"><span data-stu-id="e69c1-120">![Term Based Relations](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Term Based Relations")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e69c1-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e69c1-121">Next Step</span></span>  
 [<span data-ttu-id="e69c1-122">Aufgabe 6: Festlegen von Synonymen</span><span class="sxs-lookup"><span data-stu-id="e69c1-122">Task 6: Setting Synonyms</span></span>](../../2014/tutorials/task-6-setting-synonyms.md)  
  
  
