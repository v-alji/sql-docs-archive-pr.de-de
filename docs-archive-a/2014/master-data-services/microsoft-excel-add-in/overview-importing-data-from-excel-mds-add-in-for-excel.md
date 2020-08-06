---
title: Veröffentlichen von Daten (MDS-Add-in für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ab37a353469d1902394a3e2cd8060d9be82abb40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720215"
---
# <a name="publishing-data-mds-add-in-for-excel"></a><span data-ttu-id="aaea7-102">Veröffentlichen von Daten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="aaea7-102">Publishing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="aaea7-103">Veröffentlichen Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]im MDS-Repository Daten, wenn Sie diese für andere Benutzer freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="aaea7-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you want to share it with other users.</span></span> <span data-ttu-id="aaea7-104">Sobald die Daten veröffentlicht werden, stehen sie anderen Benutzern des Add-Ins zum Herunterladen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="aaea7-104">As soon as data is published, it is available for other users of the Add-in to download.</span></span>  
  
 <span data-ttu-id="aaea7-105">Wenn Sie Daten veröffentlichen, werden alle Daten, die Sie hinzugefügt oder aktualisiert haben, im MDS-Repository veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="aaea7-105">When you publish data, any data you've added or updated is published to the MDS repository.</span></span> <span data-ttu-id="aaea7-106">Gelöschte Daten werden nicht veröffentlicht. Sie müssen Daten separat löschen.</span><span class="sxs-lookup"><span data-stu-id="aaea7-106">Data you've deleted is not published-you must delete data separately.</span></span> <span data-ttu-id="aaea7-107">Weitere Informationen finden Sie unter [Löschen einer Zeile &#40;MDS-Add-In für Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="aaea7-107">For more information, see [Delete a Row &#40;MDS Add-in for Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aaea7-108">Die Veröffentlichung kann nicht zum Erstellen einer neuen Entität verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aaea7-108">Publishing cannot be used to create a new entity.</span></span> <span data-ttu-id="aaea7-109">Weitere Informationen zum Erstellen von Entitäten finden Sie unter [Erstellen einer Entität &#40;MDS-Add-In für Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="aaea7-109">For more information about creating entities, see [Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span></span>  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a><span data-ttu-id="aaea7-110">Wenn mehrere Benutzer gleichzeitig veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="aaea7-110">When Multiple Users Publish at the Same Time</span></span>  
 <span data-ttu-id="aaea7-111">Mehrere Benutzer können Updates zu den gleichen Daten veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="aaea7-111">Multiple users can publish updates to the same data.</span></span> <span data-ttu-id="aaea7-112">Sobald jeder Benutzer veröffentlicht hat, wird das Update in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aaea7-112">As each user publishes, the update is saved to the database.</span></span> <span data-ttu-id="aaea7-113">Dies bedeutet, dass ein Benutzer, der nicht mit den zuletzt aktualisierten Daten gearbeitet hat, immer noch den Wert ändern kann, wenn er oder sie veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="aaea7-113">This means that a user who was not working with the most recently-updated data can still change the value when he or she publishes.</span></span>  
  
 <span data-ttu-id="aaea7-114">Nur die Updates, die Sie vornehmen, werden in der Datenbank veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="aaea7-114">Only the updates you make are published to the database.</span></span> <span data-ttu-id="aaea7-115">Alle veraltete Daten im Arbeitsblatt werden nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="aaea7-115">Any out-of-date data in the worksheet is not published.</span></span>  
  
## <a name="transactions-and-annotations"></a><span data-ttu-id="aaea7-116">Transaktionen und Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="aaea7-116">Transactions and Annotations</span></span>  
 <span data-ttu-id="aaea7-117">Jede veröffentlichte Änderung wird als Transaktion gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aaea7-117">Each published change is saved as a transaction.</span></span> <span data-ttu-id="aaea7-118">Wenn Sie möchten, können Sie einer Transaktion Anmerkungen (Kommentare) hinzufügen, um zu erklären, warum Sie die Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="aaea7-118">If you choose, you can add annotations (comments) to a transaction, to explain why you made the change.</span></span>  
  
-   <span data-ttu-id="aaea7-119">Sie können keine Löschungen kommentieren, obwohl Löschungen als Transaktionen gespeichert werden, die von einem Administrator umgekehrt werden können.</span><span class="sxs-lookup"><span data-stu-id="aaea7-119">You cannot annotate deletions, although deletions are saved as transactions that can be reversed by an administrator.</span></span>  
  
-   <span data-ttu-id="aaea7-120">Wenn Sie den **Codewert** für ein Element ändern, wird er nicht als Transaktion aufgezeichnet, und alle vorherigen Transaktionen für den Member sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aaea7-120">If you change the **Code** value for a member, it is not recorded as a transaction, and all previous transactions for the member are unavailable.</span></span>  
  
-   <span data-ttu-id="aaea7-121">Sie können Transaktionen anzeigen, die von anderen Benutzern an einem Element vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="aaea7-121">You can view transactions made to a member by other users.</span></span> <span data-ttu-id="aaea7-122">Sie können auch alle Transaktionen anzeigen, die Sie an einem Element vorgenommen haben, auch wenn Sie nicht mehr über die Berechtigung für bestimmte Attribute verfügen.</span><span class="sxs-lookup"><span data-stu-id="aaea7-122">You can also view all transactions you've made to a member, even if you no longer have permission to specific attributes.</span></span>  
  
 <span data-ttu-id="aaea7-123">Sie können alle an einem Element vorgenommenen Transaktionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="aaea7-123">You can view all transactions made to a member.</span></span> <span data-ttu-id="aaea7-124">Weitere Informationen finden Sie unter [Anzeigen aller Anmerkungen oder Transaktionen für ein Element &#40;MDS-Add-In für Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="aaea7-124">For more information, see [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aaea7-125">Wenn Sie eine Anmerkung von mehr als 500 Zeichen eingeben, wird die Anmerkung automatisch abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="aaea7-125">If you enter an annotation of more than 500 characters, the annotation is automatically truncated.</span></span>  
  
## <a name="business-rule-and-other-validation"></a><span data-ttu-id="aaea7-126">Geschäftsregel und andere Überprüfung</span><span class="sxs-lookup"><span data-stu-id="aaea7-126">Business Rule and Other Validation</span></span>  
 <span data-ttu-id="aaea7-127">Wenn Sie Daten veröffentlichen, wird eine Überprüfung ausgeführt, um sicherzustellen, dass die Daten richtig sind, bevor sie dem MDS-Repository hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aaea7-127">When you publish data, validation is performed to ensure data is accurate before it's added to the MDS repository.</span></span> <span data-ttu-id="aaea7-128">Wenn die Daten die angegebenen Kriterien nicht erfüllen, werden sie nicht im Repository veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="aaea7-128">If the data does not meet specified criteria, it will not be published to the repository.</span></span> <span data-ttu-id="aaea7-129">Weitere Informationen finden Sie unter [Überprüfen von Daten &#40;MDS-Add-In für Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="aaea7-129">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="aaea7-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="aaea7-130">Related Tasks</span></span>  
  
|<span data-ttu-id="aaea7-131">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="aaea7-131">Task Description</span></span>|<span data-ttu-id="aaea7-132">Thema</span><span class="sxs-lookup"><span data-stu-id="aaea7-132">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="aaea7-133">Veröffentlichen Sie Daten vom aktiven Arbeitsblatt zurück zum MDS-Repository.</span><span class="sxs-lookup"><span data-stu-id="aaea7-133">Publish data from the active worksheet back to the MDS repository.</span></span>|[<span data-ttu-id="aaea7-134">Daten aus Excel in MDS &#40;MDS-Add-in für Excel veröffentlichen&#41;</span><span class="sxs-lookup"><span data-stu-id="aaea7-134">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|<span data-ttu-id="aaea7-135">Löschen Sie eine Zeile aus dem MDS-Repository und vom Arbeitsblatt zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="aaea7-135">Delete a row from the MDS repository and from the worksheet at the same time.</span></span>|[<span data-ttu-id="aaea7-136">Löschen einer Zeile &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="aaea7-136">Delete a Row &#40;MDS Add-in for Excel&#41;</span></span>](delete-a-row-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="aaea7-137">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="aaea7-137">Related Content</span></span>  
  
-   [<span data-ttu-id="aaea7-138">Aktualisieren von Daten &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="aaea7-138">Refreshing Data &#40;MDS Add-in for Excel&#41;</span></span>](refreshing-data-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="aaea7-139">Master Data Services-Add-In für Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="aaea7-139">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
