---
title: Hinzufügen mehrerer Bedingungen zu einer Geschäftsregel (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], multiple conditions
ms.assetid: 5f0f6958-6cf2-444b-bdcd-05b887637a0b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c62b8dfa4f459958d12bd384b85aa74bef382b21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619894"
---
# <a name="add-multiple-conditions-to-a-business-rule-master-data-services"></a><span data-ttu-id="4ddba-102">Hinzufügen mehrerer Bedingungen zu einer Geschäftsregel (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4ddba-102">Add Multiple Conditions to a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="4ddba-103">Sie können einer Geschäftsregel in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]mehrere **AND** - oder **OR** -Bedingungen hinzufügen, um eine komplexere Regel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ddba-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add multiple **AND** or **OR** conditions to a business rule when you want a more complex rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ddba-104">Wenn Sie eine Geschäftsregel erstellen, die den **OR** -Operator verwendet, sollten Sie eine separate Regel für jede Bedingungsanweisung erstellen, die unabhängig ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4ddba-104">If you create a business rule that uses the **OR** operator, consider creating a separate rule for each conditional statement that can be evaluated independently.</span></span> <span data-ttu-id="4ddba-105">Sie können dann Regeln nach Bedarf ausschließen und so mehr Flexibilität und eine einfachere Problembehandlung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ddba-105">You can then exclude rules as needed, providing more flexibility and easier troubleshooting.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ddba-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4ddba-106">Prerequisites</span></span>  
 <span data-ttu-id="4ddba-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="4ddba-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4ddba-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ddba-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4ddba-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="4ddba-109">You must be a model administrator.</span></span> <span data-ttu-id="4ddba-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ddba-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4ddba-111">Eine Geschäftsregel muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4ddba-111">A business rule must exist.</span></span> <span data-ttu-id="4ddba-112">Weitere Informationen finden Sie unter [Erstellen und Veröffentlichen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ddba-112">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-add-multiple-conditions-to-a-business-rule"></a><span data-ttu-id="4ddba-113">So fügen Sie einer Geschäftsregel mehrere Bedingungen hinzu</span><span class="sxs-lookup"><span data-stu-id="4ddba-113">To add multiple conditions to a business rule</span></span>  
  
1.  <span data-ttu-id="4ddba-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="4ddba-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4ddba-115">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="4ddba-115">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="4ddba-116">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="4ddba-116">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4ddba-117">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="4ddba-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="4ddba-118">Wählen Sie in der Liste **Elementtyp** einen Typ des Members aus.</span><span class="sxs-lookup"><span data-stu-id="4ddba-118">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="4ddba-119">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="4ddba-119">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="4ddba-120">Klicken Sie auf die Zeile für die Geschäftsregel, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4ddba-120">Click the row for the business rule you want to edit.</span></span>  
  
8.  <span data-ttu-id="4ddba-121">Klicken Sie auf **Ausgewählte Geschäftsregel bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4ddba-121">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="4ddba-122">Erweitern Sie im Bereich **Komponenten** den Knoten **logische Operatoren** .</span><span class="sxs-lookup"><span data-stu-id="4ddba-122">In the **Components** pane, expand the **Logical Operators** node.</span></span>  
  
10. <span data-ttu-id="4ddba-123">Klicken Sie auf **and** oder **or** , und ziehen Sie es **auf die Bezeichnung** **und** .</span><span class="sxs-lookup"><span data-stu-id="4ddba-123">Click **AND** or **OR** and drag it to the **IF** pane's **AND** label.</span></span>  
  
11. <span data-ttu-id="4ddba-124">Erweitern Sie im Bereich **Komponenten** den Knoten **Bedingungen** .</span><span class="sxs-lookup"><span data-stu-id="4ddba-124">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
12. <span data-ttu-id="4ddba-125">Klicken Sie auf eine Bedingung, und ziehen Sie Sie in den Bereich **if** , in die Bezeichnung **und** oder **oder** aus Schritt 10.</span><span class="sxs-lookup"><span data-stu-id="4ddba-125">Click a condition and drag it to **IF** pane, to the **AND** or **OR** label from step 10.</span></span>  
  
13. <span data-ttu-id="4ddba-126">Klicken Sie im Bereich **Attribute** auf ein Attribut, und ziehen Sie es im Bereich **Bedingung bearbeiten** auf die Bezeichnung **Attribut auswählen** .</span><span class="sxs-lookup"><span data-stu-id="4ddba-126">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
14. <span data-ttu-id="4ddba-127">Vervollständigen Sie im Bereich **Bedingung bearbeiten** alle erforderlichen Felder.</span><span class="sxs-lookup"><span data-stu-id="4ddba-127">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
15. <span data-ttu-id="4ddba-128">Klicken Sie im Bereich **Bedingung bearbeiten** auf **Element speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ddba-128">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
16. <span data-ttu-id="4ddba-129">Wenn Sie weitere Bedingungen hinzufügen möchten, ziehen Sie aus dem **Komponenten** Bereich **und** oder **oder** in beliebige **und** oder **oder** im **if** -Bereich.</span><span class="sxs-lookup"><span data-stu-id="4ddba-129">Optionally, to add more conditions, from the **Components** pane, drag **AND** or **OR** to any **AND** or **OR** in the **IF** pane.</span></span> <span data-ttu-id="4ddba-130">Führen Sie dann die Schritte 13 bis 15 aus.</span><span class="sxs-lookup"><span data-stu-id="4ddba-130">Then follow steps 13-15.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="4ddba-131">Um eine Bedingung zu löschen, klicken Sie auf den Namen der Bedingung, und klicken Sie im Bereich **Bedingung bearbeiten** auf **Element löschen**.</span><span class="sxs-lookup"><span data-stu-id="4ddba-131">To delete a condition, click the name of the condition and in the **Edit Condition** pane, click **Delete item**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ddba-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ddba-132">See Also</span></span>  
 <span data-ttu-id="4ddba-133">[Master Data Services von Geschäftsregeln &#40;&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ddba-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 <span data-ttu-id="4ddba-134">[Ändern Sie den Namen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ddba-134">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="4ddba-135">Konfigurieren von Geschäftsregeln für das Senden von Benachrichtigungen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="4ddba-135">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
