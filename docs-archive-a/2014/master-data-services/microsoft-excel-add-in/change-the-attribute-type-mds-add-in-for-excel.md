---
title: Ändern des Attributtyps (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a55ca53fcf6923957e2196840aea2fb5914e1746
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698390"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a><span data-ttu-id="ccf2b-102">Ändern des Attributtyps (MDS-Add-in für Excel)</span><span class="sxs-lookup"><span data-stu-id="ccf2b-102">Change the Attribute Type (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="ccf2b-103">Im [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]können Administratoren den Attributtyp ändern, wenn der Datentyp oder die Anzahl zulässiger Zeichen falsch ist.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can change the attribute type when the data type or number of allowed characters is incorrect.</span></span>  
  
 <span data-ttu-id="ccf2b-104">Wenn Sie den Attributtyp ändern möchten, um eine eingeschränkte Liste (domänenbasiertes Attribut) zu erstellen, finden Sie weitere Informationen unter [Erstellen eines domänenbasierten Attributs &#40;MDS-Add-In für Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ccf2b-104">If you want to change the attribute type to create a constrained list (domain-based attribute), see [Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccf2b-105">Sie können den Typ oder die Länge der Spalten **Name** oder **Code** nicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-105">You cannot update the type or length of the **Name** or **Code** columns.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ccf2b-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ccf2b-106">Prerequisites</span></span>  
 <span data-ttu-id="ccf2b-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="ccf2b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ccf2b-108">Sie müssen über die Berechtigung verfügen, auf die Funktionsbereiche **Systemverwaltung** und **Explorer** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="ccf2b-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-109">You must be a model administrator.</span></span> <span data-ttu-id="ccf2b-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ccf2b-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ccf2b-111">Modell, Entität und Attribut müssen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-111">There must be an existing model, entity, and attribute.</span></span>  
  
### <a name="to-change-the-attribute-type"></a><span data-ttu-id="ccf2b-112">So ändern Sie den Attributtyp</span><span class="sxs-lookup"><span data-stu-id="ccf2b-112">To change the attribute type</span></span>  
  
1.  <span data-ttu-id="ccf2b-113">Laden Sie in Excel die Entität, die die Spalte (Attribut) enthält, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-113">In Excel, load the entity that contains the column (attribute) you want to change.</span></span> <span data-ttu-id="ccf2b-114">Weitere Informationen finden Sie unter [Laden von Daten aus MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ccf2b-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="ccf2b-115">Klicken Sie in der Spalte, die Sie ändern möchten, auf eine beliebige Zelle.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-115">Click any cell in the column you want to change.</span></span>  
  
3.  <span data-ttu-id="ccf2b-116">Klicken Sie in der Gruppe **Modell erstellen** auf **Attributeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="ccf2b-117">Aktualisieren Sie im Dialogfeld **Attributeigenschaften** je nach Bedarf die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-117">In the **Attribute Properties** dialog box, update settings as needed.</span></span>  
  
5.  <span data-ttu-id="ccf2b-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-118">Click **OK**.</span></span>  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a><span data-ttu-id="ccf2b-119">Was geschieht, wenn Sie den Attributtyp ändern?</span><span class="sxs-lookup"><span data-stu-id="ccf2b-119">What happens when you change the attribute type?</span></span>  
 <span data-ttu-id="ccf2b-120">Wenn eine Abhängigkeit von dem Attribut besteht, wenn eine MDS-Geschäftsregel beispielsweise auf das Attribut verweist oder das Attribut in einer Abonnementsicht enthalten ist, und Sie den Datentyp eines Attributs ändern, verfährt MDS wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ccf2b-120">If there is any dependency on the attribute, such as the attribute is referenced by any MDS business rule or the attribute is included in a subscription view, and you change the data type of an attribute, MDS will:</span></span>  
  
-   <span data-ttu-id="ccf2b-121">Der Datentyp des Attributs wird geändert.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-121">Change the data type of the attribute.</span></span>  
  
-   <span data-ttu-id="ccf2b-122">Generieren Sie eine Kopie des Attributs mit dem Suffix "_old", das keinen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-122">Generate a copy of the attribute with the suffix "_old" that does not contain any value.</span></span> <span data-ttu-id="ccf2b-123">Dies wird als **veraltet** -Attribut bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-123">This is called a **deprecated** attribute.</span></span>  
  
 <span data-ttu-id="ccf2b-124">Alle vorhandenen Abhängigkeiten vom ursprünglichen Attribut verweisen jedoch auf das veraltete Attribut und nicht auf das geänderte.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-124">However, all the existing dependencies on the original attribute will point to the deprecated attribute, and not to the changed one.</span></span>  
  
 <span data-ttu-id="ccf2b-125">Dies impliziert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ccf2b-125">This implies that:</span></span>  
  
-   <span data-ttu-id="ccf2b-126">Da die Logik aufgrund des neuen Datentyps des Attributs u. U. nicht identisch ist, müssen Sie die Geschäftsregeln aktualisieren, sodass diese auf das geänderte Attribut verweisen.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-126">You must refresh the business rules to point to the changed attribute because the logic may not be the same given the new data type of the attribute.</span></span> <span data-ttu-id="ccf2b-127">Sie müssen jede betroffene Regel bearbeiten und dann die Ausdrücke ändern, um Verweise auf das veraltete Attribut (_old) zu entfernen, damit auf das aktualisierte Attribut verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-127">You will have to edit each affected rule, and then rework the expressions to point to remove references from the deprecated attribute (_old) to point to the updated attribute.</span></span>  
  
-   <span data-ttu-id="ccf2b-128">Sie müssen alle Abonnement Sichten unter der Auswahl Integration Management öffnen, die Zeile anzeigen auswählen, Sie zur Bearbeitung öffnen, indem Sie auf das Stift Symbol klicken und dann auf das Symbol Datenträger **Speichern** klicken, um die Sicht Definition zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-128">You must open any subscription views under the Integration Management selection, select the view row, open it for editing by clicking the pencil icon, and then click the **Save disk** icon to refresh the view definition.</span></span> <span data-ttu-id="ccf2b-129">Es sind keine weiteren Änderungen erforderlich, um die Sichtsyntax neu zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-129">No other change is needed to regenerate the view syntax.</span></span>  
  
-   <span data-ttu-id="ccf2b-130">Stagingtabellen, die das Attribut enthalten, wird eine Spalte für das veraltete Attribut hinzugefügt. Das bedeutet, dass der Stagingcode betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-130">Staging tables that include the attribute will have a deprecated attribute column added to them, which means that your staging code will be affected.</span></span> <span data-ttu-id="ccf2b-131">Um das veraltete Attribut zu entfernen, können Sie es löschen, nachdem Sie die Geschäftsregeln und Abonnementsichten aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-131">To get rid of the deprecated attribute, you can delete it after you have updated the business rules and subscription views.</span></span>  
  
 <span data-ttu-id="ccf2b-132">**Löschen des veralteten Attributs**</span><span class="sxs-lookup"><span data-stu-id="ccf2b-132">**Deleting the deprecated attribute**</span></span>  
  
 <span data-ttu-id="ccf2b-133">Bevor Sie ein veraltetes Attribut löschen, müssen Sie alle Verweise auf das Attribut entfernen, indem Sie die Geschäftsregeln korrigieren und die Abonnementsichten wie oben beschrieben neu generieren.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-133">Before you delete any deprecated attribute, you must remove any references to the attribute such as fixing the business rules and regenerating subscription views as described earlier.</span></span> <span data-ttu-id="ccf2b-134">Andernfalls wird beim Versuch, das veraltete Attribut zu löschen, auf der Webseite für die Systemverwaltung in einer Fehlermeldung darauf hingewiesen, dass das Attribut nicht gelöscht werden kann, da ein Objekt darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-134">Otherwise, you will get an error in the System Administration web page when you attempt to delete the deprecated attribute stating that the attribute cannot be deleted because it is referenced by an object.</span></span>  
  
 <span data-ttu-id="ccf2b-135">Informationen zum Löschen eines Attributs finden Sie unter [Löschen eines Attributs &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="ccf2b-135">To delete an attribute, see [Delete an Attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="ccf2b-136">Es ist aufwändig, Datentypen für MDS-Attribute zu ändern, die vorhandene Daten und zugehörige Entitäten aufweisen. Dies gilt insbesondere, wenn eine deklarierte Geschäftsregel oder Abonnementsicht von der Entität abhängt.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-136">It is cumbersome to change data types for MDS attributes that have existing data and related entities, especially if there is a business rule or subscription view declared which depends on the entity.</span></span> <span data-ttu-id="ccf2b-137">Als bewährte Methode wird empfohlen, mit einem Datentyp zu beginnen, der flexibel genug ist, um die erforderlichen Werte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-137">The best practice is to start with a data type that is flexible enough to hold the necessary values.</span></span> <span data-ttu-id="ccf2b-138">Zeichenfolgen können anfangs kurz sein, müssen aber im Laufe der Zeit u. U. erweitert werden, sodass immer der ungünstigste Fall berücksichtigt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-138">For example, strings may start small, but may need to be lengthened over time, so consider the worst case scenarios.</span></span> <span data-ttu-id="ccf2b-139">Die zusätzliche Länge von Textzeichenfolgen kann Probleme verursachen (da sich breite Textfelder in der grafischen Benutzeroberfläche beispielsweise nur schwer in den Bildschirm einpassen lassen). Daher sollten Sie zu lange Zeichenfolgen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ccf2b-139">Extra text string length can be burdensome (for example, wide GUI text boxes are hard to fit on the screen), so avoid too long string length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf2b-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccf2b-140">See Also</span></span>  
 <span data-ttu-id="ccf2b-141">[Attribute &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ccf2b-141">[Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span></span>  
 [<span data-ttu-id="ccf2b-142">Erstellen eines Modells &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="ccf2b-142">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
