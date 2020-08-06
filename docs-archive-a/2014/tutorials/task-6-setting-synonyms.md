---
title: 'Aufgabe 6: Festlegen von Synonymen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b7d35ee9-d1c9-41d9-bbc5-0ca7db93e54d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bde0c0ec7f230ba2325aa01328b191fd8fd67fa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608149"
---
# <a name="task-6-setting-synonyms"></a><span data-ttu-id="ef863-102">Aufgabe 6: Festlegen von Synonymen</span><span class="sxs-lookup"><span data-stu-id="ef863-102">Task 6: Setting Synonyms</span></span>
  <span data-ttu-id="ef863-103">In dieser Aufgabe legen Sie zwei Domänen Werte ( **USA** und **USA**) der Domäne **Country** als Synonyme fest, wobei **USA** als führender Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ef863-103">In this task, you set two domain values, **USA** and **United States**, of the **Country** domain as synonyms with **United States** as the leading value.</span></span> <span data-ttu-id="ef863-104">Da die Option **führende Werte verwenden** beim Erstellen der Domäne **Country** ausgewählt wurde, werden alle **US** -Werte für die Domäne **Country** als **USA** ausgegeben (da USA der führende Wert ist).</span><span class="sxs-lookup"><span data-stu-id="ef863-104">Since the **Use Leading Values** option was selected when creating the **Country** domain, any **USA** values for the **Country** domain will be output as **United States** (as United States is the leading value).</span></span> <span data-ttu-id="ef863-105">Weitere Informationen finden Sie unter [Ändern von Domänen Werten](https://msdn.microsoft.com/library/hh510408.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ef863-105">See [Change Domain Values](https://msdn.microsoft.com/library/hh510408.aspx) for more details.</span></span>

1.  <span data-ttu-id="ef863-106">Wählen Sie **Land** aus der Liste der Domänen aus.</span><span class="sxs-lookup"><span data-stu-id="ef863-106">Select **Country** from the list of domains.</span></span>

2.  <span data-ttu-id="ef863-107">Wechseln Sie zur Registerkarte **Domänen Werte** .</span><span class="sxs-lookup"><span data-stu-id="ef863-107">Switch to the **Domain Values** tab.</span></span>

3.  <span data-ttu-id="ef863-108">Klicken Sie auf der Symbolleiste auf **neue Domänen Wert hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="ef863-108">Click **Add new domain value** button on the toolbar.</span></span>

4.  <span data-ttu-id="ef863-109">Geben Sie **USA** als Wert ein, und drücken **Sie die Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="ef863-109">Type **USA** for the value and press **ENTER**.</span></span>

5.  <span data-ttu-id="ef863-110">Wählen Sie **USA** und **USA** mit STRG oder Umschalttaste aus, klicken Sie mit der rechten Maustaste auf die ausgewählten Elemente, und klicken Sie dann auf **als Synonyme festlegen**.</span><span class="sxs-lookup"><span data-stu-id="ef863-110">Multiselect **United States** and **USA** using CTRL or SHIFT keys, right-click the selected items, and then click **Set as Synonyms**.</span></span> <span data-ttu-id="ef863-111">DQS gruppiert diese Werte und legt einen der Werte als führenden Wert fest, durch den die anderen Werte ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ef863-111">DQS groups these values and designate one of the values as the leading value that the other values are replaced with.</span></span>

     <span data-ttu-id="ef863-112">![Als Synonyme festlegen (Menü)](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Als Synonyme festlegen (Menü)")</span><span class="sxs-lookup"><span data-stu-id="ef863-112">![Set as Synonyms Menu](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Set as Synonyms Menu")</span></span>

6.  <span data-ttu-id="ef863-113">Beachten Sie, dass **USA** als führender Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ef863-113">Notice that **United States** is set as the leading value.</span></span> <span data-ttu-id="ef863-114">Wenn Sie möchten, dass "USA" der führende Wert ist, können Sie mit der rechten Maustaste auf "USA" klicken und **als führende Option festlegen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ef863-114">If you want USA to be the leading value, you can right-click on USA and select **Set as Leading** option.</span></span> <span data-ttu-id="ef863-115">In diesem Tutorial verwenden wir **USA** als führenden Wert.</span><span class="sxs-lookup"><span data-stu-id="ef863-115">For this tutorial, we use **United States** as the leading value.</span></span>

     <span data-ttu-id="ef863-116">![Vereinigte Staaten und USA als Synonyme](../../2014/tutorials/media/et-settingsynonyms-02.jpg "Vereinigte Staaten und USA als Synonyme")</span><span class="sxs-lookup"><span data-stu-id="ef863-116">![United States and USA as Synonyms](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States and USA as Synonyms")</span></span>

## <a name="next-step"></a><span data-ttu-id="ef863-117">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ef863-117">Next Step</span></span>
 [<span data-ttu-id="ef863-118">Aufgabe 7: Erstellen einer Verbunddomäne</span><span class="sxs-lookup"><span data-stu-id="ef863-118">Task 7: Creating a Composite Domain</span></span>](../../2014/tutorials/task-7-creating-a-composite-domain.md)


