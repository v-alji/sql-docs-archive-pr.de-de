---
title: Erstellen einer Entität (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 87ad67f7347da87c67afc11590df6775af4cf3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607873"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a><span data-ttu-id="4dd82-102">Erstellen einer Entität (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="4dd82-102">Create an Entity (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="4dd82-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]können Administratoren neue Entitäten erstellen, um Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4dd82-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create new entities to store data.</span></span> <span data-ttu-id="4dd82-104">Wenn Sie eine Entität erstellen, sollten Sie mindestens eine Stichprobenentnahme der Daten laden, die Sie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="4dd82-104">When you create an entity you should load at least a sampling of the data you want to store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4dd82-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4dd82-105">Prerequisites</span></span>  
 <span data-ttu-id="4dd82-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="4dd82-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4dd82-107">Sie müssen über die Berechtigung verfügen, auf die Funktionsbereiche **Systemverwaltung** und **Explorer** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4dd82-107">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="4dd82-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="4dd82-108">You must be a model administrator.</span></span> <span data-ttu-id="4dd82-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4dd82-109">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4dd82-110">Sie müssen über ein vorhandenes Modell verfügen, in dem die Entität erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4dd82-110">You must have an existing model to create the entity in.</span></span> <span data-ttu-id="4dd82-111">Weitere Informationen finden Sie unter [Erstellen eines Modells &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4dd82-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4dd82-112">Stellen Sie sicher, dass die Daten die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="4dd82-112">Ensure that your data meets the following requirements:</span></span>  
  
    -   <span data-ttu-id="4dd82-113">Die Daten sollten eine Kopfzeile haben.</span><span class="sxs-lookup"><span data-stu-id="4dd82-113">The data should have a header row.</span></span>  
  
    -   <span data-ttu-id="4dd82-114">Es ist hilfreich, wenn die Spalten **Name** und **Code** vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4dd82-114">It is helpful to have **Name** and **Code** columns.</span></span> <span data-ttu-id="4dd82-115">Der**Code** ist ein eindeutiger Bezeichner für jede Zeile.</span><span class="sxs-lookup"><span data-stu-id="4dd82-115">**Code** is a unique identifier for each row.</span></span>  
  
    -   <span data-ttu-id="4dd82-116">Außer der Kopfzeile sollte mindestens eine Zeile mit Daten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4dd82-116">You should have at least one row of data other than the header.</span></span> <span data-ttu-id="4dd82-117">Nicht in allen Spalten müssen Werte enthalten sein, aber die Daten sollten repräsentativ für die Daten sein, die in der Entität enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="4dd82-117">All columns do not need values, but the data should be representative of the data that will be in the entity.</span></span>  
  
    -   <span data-ttu-id="4dd82-118">Wenn Sie eine Spalte verwenden, die einen eindeutigen Bezeichner enthält (unter MDS als **Code**bezeichnet), sollten Sie sicherstellen, dass die Werte eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="4dd82-118">If you have a column that contains a unique identifier (known in MDS as **Code**), ensure that the values are unique.</span></span> <span data-ttu-id="4dd82-119">Falls keine Spalte Bezeichner enthält, können Sie diese beim Erstellen der Entität automatisch generieren lassen.</span><span class="sxs-lookup"><span data-stu-id="4dd82-119">If no column contains identifiers, you can have them generated automatically when you create the entity.</span></span>  
  
    -   <span data-ttu-id="4dd82-120">Stellen Sie sicher, dass keine Zellen Formeln enthalten.</span><span class="sxs-lookup"><span data-stu-id="4dd82-120">Ensure that no cells contain formulas.</span></span>  
  
    -   <span data-ttu-id="4dd82-121">Stellen Sie sicher, dass keine Zellen Zeitwerte enthalten.</span><span class="sxs-lookup"><span data-stu-id="4dd82-121">Ensure that no cells contain time values.</span></span> <span data-ttu-id="4dd82-122">Datumswerte können unter MDS gespeichert werden, aber für Zeitwerte ist dies nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="4dd82-122">Date values can be saved in MDS but time values cannot.</span></span>  
  
### <a name="to-create-an-entity-and-load-data"></a><span data-ttu-id="4dd82-123">So erstellen Sie eine Entität und laden Daten</span><span class="sxs-lookup"><span data-stu-id="4dd82-123">To create an entity and load data</span></span>  
  
1.  <span data-ttu-id="4dd82-124">Öffnen oder erstellen Sie ein Excel-Arbeitsblatt, das die zu ladenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="4dd82-124">Open or create an Excel worksheet that contains data you want to load.</span></span>  
  
2.  <span data-ttu-id="4dd82-125">Wählen Sie die Zellen aus, die Sie in die neue Entität laden möchten.</span><span class="sxs-lookup"><span data-stu-id="4dd82-125">Select the cells you want to load into the new entity.</span></span>  
  
3.  <span data-ttu-id="4dd82-126">Klicken Sie auf der Registerkarte **Masterdaten** in der Gruppe **Modell erstellen** auf **Entität erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4dd82-126">On the **Master Data** tab, in the **Build Model** group, click **Create Entity**.</span></span>  
  
4.  <span data-ttu-id="4dd82-127">Stellen Sie eine Verbindung mit einem MDS-Repository her, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4dd82-127">If you are prompted to connect to an MDS repository, connect.</span></span>  
  
5.  <span data-ttu-id="4dd82-128">Lassen Sie den Standardbereich im Dialogfeld **Entität erstellen** unverändert, oder passen Sie ihn an die zu ladenden Daten an.</span><span class="sxs-lookup"><span data-stu-id="4dd82-128">In the **Create Entity** dialog box, leave the default range or change it to apply to the data you want to load.</span></span>  
  
6.  <span data-ttu-id="4dd82-129">Deaktivieren Sie nicht das Kontrollkästchen **Meine Daten besitzen Kopfzeilen** .</span><span class="sxs-lookup"><span data-stu-id="4dd82-129">Do not clear the **My data has headers** check box.</span></span>  
  
7.  <span data-ttu-id="4dd82-130">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="4dd82-130">From the **Model** list, select a model.</span></span>  
  
8.  <span data-ttu-id="4dd82-131">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="4dd82-131">From the **Version** list, select a version.</span></span>  
  
9. <span data-ttu-id="4dd82-132">Geben Sie im Feld **Neuer Entitätsname** einen Namen für die Entität ein.</span><span class="sxs-lookup"><span data-stu-id="4dd82-132">In the **New entity name** box, type a name for the entity.</span></span>  
  
10. <span data-ttu-id="4dd82-133">Wählen Sie in der Liste **Code** die Spalte aus, die eindeutige Bezeichner enthält, oder lassen Sie die Codes automatisch generieren.</span><span class="sxs-lookup"><span data-stu-id="4dd82-133">From the **Code** list, select the column that contains unique identifiers or have codes generated automatically.</span></span>  
  
11. <span data-ttu-id="4dd82-134">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dd82-134">Optional.</span></span> <span data-ttu-id="4dd82-135">Wählen Sie in der Liste **Name** eine Spalte aus, die Namen für jedes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="4dd82-135">From the **Name** list, select a column that contains names for each member.</span></span>  
  
12. <span data-ttu-id="4dd82-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dd82-136">Click **OK**.</span></span> <span data-ttu-id="4dd82-137">Nachdem die Entität erfolgreich erstellt wurde, wird eine neue Kopfzeile angezeigt, die Zellen werden hervorgehoben, und der Blattname wird an den Entitätsnamen angepasst.</span><span class="sxs-lookup"><span data-stu-id="4dd82-137">When the entity has been created successfully, a new header row is displayed, the cells are highlighted, and the sheet name is updated to match the entity name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4dd82-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4dd82-138">Next Steps</span></span>  
  
-   <span data-ttu-id="4dd82-139">Um Fehler anzuzeigen, die in der Gruppe **Veröffentlichen und Überprüfen** aufgetreten sind, klicken Sie auf **Status anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="4dd82-139">To view errors that occurred, in the **Publish and Validate** group, click **Show Status**.</span></span> <span data-ttu-id="4dd82-140">Die Spalten ValidationStatus und InputStatus werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dd82-140">ValidationStatus and InputStatus columns are displayed.</span></span> <span data-ttu-id="4dd82-141">Weitere Informationen finden Sie unter [Überprüfen von Daten &#40;MDS-Add-In für Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4dd82-141">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
-   <span data-ttu-id="4dd82-142">Bestätigen Sie, dass die Attribute mit dem gewünschten Datentyp erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4dd82-142">Confirm that the attributes were created as the data type you expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd82-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4dd82-143">See Also</span></span>  
 [<span data-ttu-id="4dd82-144">Erstellen eines domänenbasierten Attributs &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd82-144">Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;</span></span>](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  
