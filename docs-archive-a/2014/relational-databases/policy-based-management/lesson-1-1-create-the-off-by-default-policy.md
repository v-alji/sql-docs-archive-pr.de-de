---
title: Erstellen der Richtlinie „Standardmäßig aus“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 98fde3c5-297c-4d95-981e-95700bbf5ccd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16d0893c155627a41149263b5ce7b21a4a217b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609170"
---
# <a name="create-the-off-by-default-policy"></a><span data-ttu-id="deaac-102">Erstellen der Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="deaac-102">Create the Off By Default Policy</span></span>
  <span data-ttu-id="deaac-103">In dieser Aufgabe erstellen Sie eine Bedingung mit dem Namen Mail aus, die auf dem Oberflächenkonfigurationsfacet basiert.</span><span class="sxs-lookup"><span data-stu-id="deaac-103">This task creates a condition named Mail Off that is based on the Surface Area Configuration facet.</span></span> <span data-ttu-id="deaac-104">Anschließend erstellen Sie eine Richtlinie mit dem Namen Standardmäßig aus.</span><span class="sxs-lookup"><span data-stu-id="deaac-104">Then, it creates a policy named Off By Default.</span></span>  
  
### <a name="to-create-the-mail-off-condition"></a><span data-ttu-id="deaac-105">So erstellen Sie die Bedingung 'Mail aus'</span><span class="sxs-lookup"><span data-stu-id="deaac-105">To create the Mail Off condition</span></span>  
  
1.  <span data-ttu-id="deaac-106">Erweitern Sie im Objekt-Explorer **Verwaltung**, erweitern Sie **Richtlinienverwaltung**, erweitern Sie **Facets**, klicken Sie mit der rechten Maustaste auf **Oberflächenkonfiguration**und anschließend auf **Neue Bedingung**.</span><span class="sxs-lookup"><span data-stu-id="deaac-106">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Facets**, right-click **Surface Area Configuration**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="deaac-107">Geben Sie im Dialogfeld **Neue Bedingung erstellen** im Feld **Name** den Namen **Mail aus**ein.</span><span class="sxs-lookup"><span data-stu-id="deaac-107">In the **Create New Condition** dialog box, in the **Name** box, type **Mail Off**.</span></span>  
  
3.  <span data-ttu-id="deaac-108">Bestätigen Sie im Feld **Facet** , dass das Facet **Oberflächenkonfiguration** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="deaac-108">In the **Facet** box, confirm that **Surface Area Configuration** facet is selected.</span></span>  
  
4.  <span data-ttu-id="deaac-109">Wählen Sie im Bereich **Ausdruck** im **Feld Feld** die \*\* \@ Option databasemailaktivierte\*\*aus, wählen Sie im Feld **Operator** die Option aus **=** , und wählen Sie im Feld **Wert** **false**aus.</span><span class="sxs-lookup"><span data-stu-id="deaac-109">In the **Expression** area, in the **Field** box, select **\@DatabaseMailEnabled**, in the **Operator** box select **=**, and in the **Value** select **False**.</span></span>  
  
5.  <span data-ttu-id="deaac-110">Geben Sie auf der Seite **Beschreibung** eine Beschreibung der Bedingung ein, und klicken Sie dann auf **OK** , um die Bedingung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="deaac-110">On the **Description** page, type a description of the condition, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-off-by-default-policy"></a><span data-ttu-id="deaac-111">So erstellen Sie die Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="deaac-111">To create the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="deaac-112">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf **Oberflächenkonfiguration**und anschließend auf **Neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="deaac-112">In Object Explorer, right-click **Surface Area Configuration**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="deaac-113">Geben Sie im Dialogfeld **Neue Richtlinie erstellen** im Feld **Name** den Namen **Standardmäßig aus**ein.</span><span class="sxs-lookup"><span data-stu-id="deaac-113">In the **Create New Policy** dialog box, in the **Name** box, type **Off By Default**.</span></span>  
  
3.  <span data-ttu-id="deaac-114">Lassen Sie das Kontrollkästchen **Aktiviert** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="deaac-114">Leave the **Enabled** checkbox unchecked.</span></span> <span data-ttu-id="deaac-115">Das Kontrollkästchen **Aktiviert** gilt für automatisierte Richtlinien, und diese Richtlinie wird bei Bedarf ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="deaac-115">The **Enabled** checkbox applies to automated policies, and this policy will be executed on demand.</span></span>  
  
4.  <span data-ttu-id="deaac-116">Führen Sie im Kontrollkästchen **Bedingung überprüfen** einen Bildlauf nach unten zum Bereich **Oberflächenkonfiguration** durch, und wählen Sie dann **Mail aus** als die zu überprüfende Bedingung aus.</span><span class="sxs-lookup"><span data-stu-id="deaac-116">In the **Check condition** checkbox, scroll down to the **Surface Area Configuration** area, and then select **Mail Off** as the condition to check.</span></span>  
  
5.  <span data-ttu-id="deaac-117">Das Feld **Für Ziele** ist leer, da dies eine serverbezogene Richtlinie ist.</span><span class="sxs-lookup"><span data-stu-id="deaac-117">The **Against targets** box will be blank because this is a server-scoped policy.</span></span>  
  
6.  <span data-ttu-id="deaac-118">Wählen Sie im Feld **Auswertungsmodus** den Modus **Bedarfsgesteuert** aus.</span><span class="sxs-lookup"><span data-stu-id="deaac-118">In the **Evaluation Mode** checkbox, select **On demand** as the evaluation mode.</span></span>  
  
7.  <span data-ttu-id="deaac-119">Wählen Sie im Feld **Serverbeschränkung** die Option **Keine**aus.</span><span class="sxs-lookup"><span data-stu-id="deaac-119">In the **Server restriction** checkbox, select **None**.</span></span>  
  
8.  <span data-ttu-id="deaac-120">Geben Sie auf der Seite **Beschreibung** eine Beschreibung der Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="deaac-120">On the **Description** page, type a description of the policy.</span></span>  
  
9. <span data-ttu-id="deaac-121">Sie können im Bereich **Zusätzlicher Hilfelink** einen Link zu einer Webseite für Ihre Richtlinien bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="deaac-121">You can provide a hyperlink to a Web page for your policies in the **Additional help hyperlink** area.</span></span> <span data-ttu-id="deaac-122">Geben Sie im Feld **Anzuzeigender Text** den Text ein, der für den Link angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="deaac-122">In the **Text to display** box, type the text that will appear for the hyperlink.</span></span>  
  
10. <span data-ttu-id="deaac-123">Geben Sie in das Feld **Adresse** einen Link zu einer Hilfeseite ein, z. B. die Startseite der IT-Abteilung Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="deaac-123">In the **Address** box, type a hyperlink to a Help page, such as the home page for the IT department of your company.</span></span>  
  
11. <span data-ttu-id="deaac-124">Um diese Webseite zur Bestätigung der Adresse zu öffnen, klicken Sie auf **Link testen**.</span><span class="sxs-lookup"><span data-stu-id="deaac-124">To confirm the address by opening the Web page, click **Test Link**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="deaac-125">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="deaac-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="deaac-126">Konfigurieren eines Servers für das Ausführen der Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="deaac-126">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
  
