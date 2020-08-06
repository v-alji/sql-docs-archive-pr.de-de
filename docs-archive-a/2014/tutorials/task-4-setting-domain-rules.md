---
title: 'Aufgabe 4: Festlegen von Domänen Regeln | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3a7162ba-cf2f-481f-830d-bb6a02823827
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42bdbd0228fdd3515f68ce830581f445242768e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608941"
---
# <a name="task-4-setting-domain-rules"></a><span data-ttu-id="c55d8-102">Aufgabe 4: Festlegen von Domänenregeln</span><span class="sxs-lookup"><span data-stu-id="c55d8-102">Task 4: Setting Domain Rules</span></span>
  <span data-ttu-id="c55d8-103">In dieser Aufgabe erstellen Sie eine Regel für die **Kontakt-e-Mail-** Domäne, um zu prüfen, ob die e-Mail-Adresse mit \*\* \@ Adventure-Works.com\*\*endet.</span><span class="sxs-lookup"><span data-stu-id="c55d8-103">In this task, you create a rule for the **Contact Email** domain to verify if the email address ends with **\@adventure-works.com**.</span></span> <span data-ttu-id="c55d8-104">Weitere Informationen zu dieser Seite finden Sie im Thema [Erstellen einer Domänen Regel](https://msdn.microsoft.com/library/hh510397.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c55d8-104">See [Creating a Domain Rule](https://msdn.microsoft.com/library/hh510397.aspx) topic for more details on the page.</span></span>  
  
1.  <span data-ttu-id="c55d8-105">Klicken Sie in der **Domänen Liste**auf **Contact Email** .</span><span class="sxs-lookup"><span data-stu-id="c55d8-105">Click **Contact Email** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="c55d8-106">Wechseln Sie im rechten Bereich zur Registerkarte **Domänen Regeln** .</span><span class="sxs-lookup"><span data-stu-id="c55d8-106">Switch to the **Domain Rules** tab in the right pane.</span></span>  
  
     <span data-ttu-id="c55d8-107">![Neue Domänenregel hinzufügen (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Neue Domänenregel hinzufügen (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="c55d8-107">![Add a New Domain Rule Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Add a New Domain Rule Toolbar Button")</span></span>  
  
3.  <span data-ttu-id="c55d8-108">Klicken Sie im rechten Bereich auf der Symbolleiste auf die Schaltfläche **neue Domänen Regel hinzufügen** (siehe Abbildung), um eine Regel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c55d8-108">In the right pane, click **Add a new domain rule** button on the toolbar (see the image) to add a rule.</span></span>  
  
4.  <span data-ttu-id="c55d8-109">Geben Sie als **Regelname** **e-Mail-Überprüfung** ein, und drücken **Sie**</span><span class="sxs-lookup"><span data-stu-id="c55d8-109">Type **Email Validation** for the **rule name** and press **ENTER**.</span></span> <span data-ttu-id="c55d8-110">Das Kontrollkästchen **aktiv** sollte standardmäßig aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c55d8-110">The **Active** check box should be checked by default.</span></span> <span data-ttu-id="c55d8-111">Dieses Steuerelement ermöglicht Ihnen, eine Regel temporär zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c55d8-111">This control allows you to deactivate a rule temporarily.</span></span>  
  
5.  <span data-ttu-id="c55d8-112">Klicken Sie im Bereich **Regel erstellen** auf **Pfeil nach unten**, und wählen Sie **Wert endet mit**aus.</span><span class="sxs-lookup"><span data-stu-id="c55d8-112">In the **Build a Rule** pane, click **down arrow**, and select **Value ends with**.</span></span>  
  
6.  <span data-ttu-id="c55d8-113">Geben Sie \*\* \@ Adventure-Works.com\*\* in das Textfeld ein, und drücken Sie **Tab**.</span><span class="sxs-lookup"><span data-stu-id="c55d8-113">Type **\@adventure-works.com** in the text box and press **TAB**.</span></span> <span data-ttu-id="c55d8-114">Sie können weitere Bedingungen hinzufügen, indem Sie im Bereich **Regel erstellen** **auf der Symbolleiste der ausgewählten Klausel auf neue Bedingung hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="c55d8-114">You can add more conditions by clicking **Add a new condition to the selected clause** toolbar button in the **Build a Rule** pane.</span></span>  
  
     <span data-ttu-id="c55d8-115">![E-Mail-Überprüfungsregel](../../2014/tutorials/media/et-settingdomainrules-02.jpg "E-Mail-Überprüfungsregel")</span><span class="sxs-lookup"><span data-stu-id="c55d8-115">![Email Validation Rule](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Email Validation Rule")</span></span>  
  
7.  <span data-ttu-id="c55d8-116">Klicken Sie auf der Symbolleiste im rechten Bereich auf die Schaltfläche **ausgewählte Domänen Regel für Testdaten ausführen** , um die Regel mit Beispiel Daten zu testen.</span><span class="sxs-lookup"><span data-stu-id="c55d8-116">Click **Run the selected domain rule on test data** button on the toolbar in the right pane to test the rule against sample data.</span></span>  
  
     <span data-ttu-id="c55d8-117">![Ausgewählte Domänenregel für Testdaten ausführen (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Ausgewählte Domänenregel für Testdaten ausführen (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="c55d8-117">![Run the Domain Rule on Test Data Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Run the Domain Rule on Test Data Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="c55d8-118">Klicken Sie im Dialogfeld **Test Domänen Regel** auf der Symbolleiste auf **einen neuen Test Begriff für die Domänen Regel hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="c55d8-118">In the **Test Domain Rule** dialog box, click **Adds a new testing term for the domain rule** button on the toolbar.</span></span>  
  
     <span data-ttu-id="c55d8-119">![Domänenregel testen (Dialogfeld)](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Domänenregel testen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="c55d8-119">![Test Domain Rule Dialog Box](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Test Domain Rule Dialog Box")</span></span>  
  
9. <span data-ttu-id="c55d8-120">Geben Sie **frank7 \@ Adventure-Works.com** (einen gültigen Wert) in der Spalte **Kontakt-e-Mail** ein.</span><span class="sxs-lookup"><span data-stu-id="c55d8-120">Type **frank7\@adventure-works.com** (a valid value) in the **Contact Email** column.</span></span>  
  
10. <span data-ttu-id="c55d8-121">Wiederholen Sie die vorherigen beiden Schritte, um **Joe2 \@ Adventure-work.com** hinzuzufügen (ein ungültiger Wert ohne ' ').</span><span class="sxs-lookup"><span data-stu-id="c55d8-121">Repeat previous two steps to add **joe2\@adventure-work.com** (an invalid value with no 's').</span></span>  
  
11. <span data-ttu-id="c55d8-122">Klicken Sie auf der Symbolleiste auf die letzte Schaltfläche (**Testen Sie die Domänen Regel nach allen Begriffen**), um die Eingabedaten für die Regel zu testen.</span><span class="sxs-lookup"><span data-stu-id="c55d8-122">Click the last button (**Test the domain rule on all the terms**) on the toolbar to test the input data against the rule.</span></span>  
  
     <span data-ttu-id="c55d8-123">![Testet die Domänenregeln für alle Begriffe (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Testet die Domänenregeln für alle Begriffe (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="c55d8-123">![Test the Domain Rule on All Terms Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Test the Domain Rule on All Terms Toolbar Button")</span></span>  
  
12. <span data-ttu-id="c55d8-124">Beachten Sie, dass der erste Eintrag als gültiges Element und der zweite als ungültiges Element angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c55d8-124">Notice that the first entry is shown as a valid item and the second one as an invalid item.</span></span>  
  
     <span data-ttu-id="c55d8-125">![Ergebnisse des Domänenregeltests](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Ergebnisse des Domänenregeltests")</span><span class="sxs-lookup"><span data-stu-id="c55d8-125">![Test Domain Rule Results](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Test Domain Rule Results")</span></span>  
  
13. <span data-ttu-id="c55d8-126">Klicken Sie auf **Schließen** , um das Dialogfeld **Domänen Regel testen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c55d8-126">Click **Close** to close the **Test Domain Rule** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c55d8-127">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c55d8-127">Next Step</span></span>  
 [<span data-ttu-id="c55d8-128">Aufgabe 5: Festlegen begriffsbasierter Beziehungen</span><span class="sxs-lookup"><span data-stu-id="c55d8-128">Task 5: Setting Term Based Relationships</span></span>](../../2014/tutorials/task-5-setting-term-based-relationships.md)  
  
  
