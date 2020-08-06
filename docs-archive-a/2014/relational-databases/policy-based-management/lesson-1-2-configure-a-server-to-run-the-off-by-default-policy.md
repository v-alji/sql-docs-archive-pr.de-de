---
title: Konfigurieren eines Servers für das Ausführen der Richtlinie „Standardmäßig aus“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c0842a30b7d0bbcd1b01ee9e98ed1ed9a74f0f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609169"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a><span data-ttu-id="58efb-102">Konfigurieren eines Servers für das Ausführen der Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="58efb-102">Configure a Server to Run the Off By Default Policy</span></span>
  <span data-ttu-id="58efb-103">Nun verfügen Sie über eine Richtlinie mit dem Namen Standardmäßig aus.</span><span class="sxs-lookup"><span data-stu-id="58efb-103">Now you have a policy named Off By Default.</span></span> <span data-ttu-id="58efb-104">In dieser Aufgabe überprüfen Sie, ob Ihr Server die Anforderungen dieser Richtlinie einhält.</span><span class="sxs-lookup"><span data-stu-id="58efb-104">In this task, you will check to see whether your server complies with the requirements of this policy.</span></span>  
  
### <a name="to-run-the-off-by-default-policy"></a><span data-ttu-id="58efb-105">So führen Sie die Richtlinie 'Standardmäßig aus' aus</span><span class="sxs-lookup"><span data-stu-id="58efb-105">To run the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="58efb-106">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf Ihre Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], zeigen Sie auf **Richtlinien**, und klicken Sie anschließend auf **Auswerten**.</span><span class="sxs-lookup"><span data-stu-id="58efb-106">In Object Explorer, right-click your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], point to **Policies**, and then click **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="58efb-107">Im Dialogfeld **Richtlinien auswerten** können Sie Richtlinien aus einer anderen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder aus einer Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="58efb-107">In the **Evaluate Policies** dialog box you can select policies from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or from a file.</span></span> <span data-ttu-id="58efb-108">Für diesen Schritt belassen Sie als Einstellung für **Quelle** Ihre Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58efb-108">For this step, leave **Source** set to your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="58efb-109">Wählen Sie im Abschnitt **Richtlinien** die Richtlinie **Standardmäßig aus** aus.</span><span class="sxs-lookup"><span data-stu-id="58efb-109">In the **Policies** section, select the **Off By Default** policy.</span></span>  
  
4.  <span data-ttu-id="58efb-110">Um zu sehen, ob der Server diese Richtlinie einhält, klicken Sie auf **Auswerten**.</span><span class="sxs-lookup"><span data-stu-id="58efb-110">To see whether the server is in compliance with the policy, click **Evaluate**.</span></span>  
  
5.  <span data-ttu-id="58efb-111">Im Bereich **Ergebnisse** wird ein grüner Kreis mit einem Häkchen angezeigt, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Richtlinie einhält.</span><span class="sxs-lookup"><span data-stu-id="58efb-111">In the **Results** area, you will see a green circle with a check mark if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] complies with the policy.</span></span> <span data-ttu-id="58efb-112">Ein roter Kreis mit einem X wird angezeigt, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Richtlinie nicht einhält.</span><span class="sxs-lookup"><span data-stu-id="58efb-112">You will see a red circle with an X if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not comply with the policy.</span></span>  
  
6.  <span data-ttu-id="58efb-113">Im Bereich **Zieldetails** werden weitere Informationen in der Spalte **Meldung** angezeigt, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="58efb-113">In the **Target Details** area, you will see additional information in the **Message** column if an error occurs.</span></span> <span data-ttu-id="58efb-114">Klicken Sie in der Spalte **Meldung** auf **Anzeigen** , um einen Bericht anzuzeigen, der die Überprüfungsergebnisse für jede überprüfte Facet-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="58efb-114">In the **Message** column, click **View** to see a report that contains the results of the check for each facet property that was checked.</span></span>  
  
7.  <span data-ttu-id="58efb-115">Die Richtlinienbeschreibung wird unten auf der Seite angezeigt, und im Abschnitt **Zusätzliche Hilfe** wird der Link angezeigt, den Sie für die Richtlinie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="58efb-115">The policy description is displayed at the bottom of the page, and the **Additional help** section displays the hyperlink that you have configured for the policy.</span></span> <span data-ttu-id="58efb-116">Klicken Sie auf den Meldungslink, um die Webseite zu öffnen, die Sie beim Erstellen der Richtlinie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="58efb-116">Click the message hyperlink to open the Web page that you specified when you created the policy.</span></span>  
  
8.  <span data-ttu-id="58efb-117">Schließen Sie den Browser, und schließen Sie dann das Dialogfeld **Ergebnisse, Detailansicht** .</span><span class="sxs-lookup"><span data-stu-id="58efb-117">Close the browser, and then close the **Results Detailed View** dialog box.</span></span>  
  
9. <span data-ttu-id="58efb-118">Wenn der Server die Richtlinie nicht einhält und Sie Datenbank-E-Mail deaktivieren möchten, klicken Sie auf der Seite **Auswertungsergebnisse** auf **Anwenden** .</span><span class="sxs-lookup"><span data-stu-id="58efb-118">If the server is out of compliance and you want to disable Database Mail, click **Apply** in the **Evaluation Results** page.</span></span>  
  
10. <span data-ttu-id="58efb-119">Schließen Sie das Dialogfeld **Ergebnisse, Detailansicht** und das Dialogfeld **Richtlinien auswerten** .</span><span class="sxs-lookup"><span data-stu-id="58efb-119">Close both the **Results Detailed View** and the **Evaluate Policies** dialog boxes.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="58efb-120">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="58efb-120">Next Lesson</span></span>  
 [<span data-ttu-id="58efb-121">Lektion 2: Erstellen und Anwenden einer Richtlinie für Benennungsstandards</span><span class="sxs-lookup"><span data-stu-id="58efb-121">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
