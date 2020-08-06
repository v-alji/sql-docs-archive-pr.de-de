---
title: Überprüfen von Daten (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f8e97ff6481996b2e16436e1f78478bd234fe6ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618079"
---
# <a name="validating-data-mds-add-in-for-excel"></a><span data-ttu-id="c9dae-102">Überprüfen von Daten (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="c9dae-102">Validating Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="c9dae-103">Beim Veröffentlichen von Daten werden in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]zwei Arten von Überprüfungen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="c9dae-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], when you publish data, two types of validation take place:</span></span>  
  
-   <span data-ttu-id="c9dae-104">Alle definierten Geschäftsregeln werden auf die Daten angewendet.</span><span class="sxs-lookup"><span data-stu-id="c9dae-104">Any defined business rules are applied to the data.</span></span>  
  
-   <span data-ttu-id="c9dae-105">Daten werden auf zulässige Attributwerte hin überprüft (z. B. die Anzahl der Zeichen oder der Typ der Daten).</span><span class="sxs-lookup"><span data-stu-id="c9dae-105">Data is checked against allowed attribute values (for example, number of characters or type of data).</span></span>  
  
 <span data-ttu-id="c9dae-106">Gültige Daten werden in jedem Fall im MDS-Repository veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c9dae-106">In each case, valid data is published to the MDS repository.</span></span> <span data-ttu-id="c9dae-107">Ungültige Daten werden hervorgehoben, und Details des Fehlers können in Statusspalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9dae-107">Data that is not valid is highlighted, and details of the error can be shown in status columns.</span></span>  
  
## <a name="when-validation-occurs"></a><span data-ttu-id="c9dae-108">Zeitpunkt der Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="c9dae-108">When Validation Occurs</span></span>  
 <span data-ttu-id="c9dae-109">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]wird die Überprüfung ausgeführt, wenn Sie neue oder geänderte Daten veröffentlichen oder wenn Sie Geschäftsregeln manuell anwenden.</span><span class="sxs-lookup"><span data-stu-id="c9dae-109">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], validation occurs when you publish new or changed data, or when you manually apply business rules.</span></span>  
  
 <span data-ttu-id="c9dae-110">Wenn für die Geschäftsregeln ein Fehler auftritt, werden die Daten trotzdem im MDS-Repository veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c9dae-110">When business rules fail, the data is still published to the MDS repository.</span></span> <span data-ttu-id="c9dae-111">Wenn die Überprüfung der Eingabe fehlschlägt, werden die Daten nicht im Repository veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c9dae-111">When input validation fails, the data is not published to the repository.</span></span>  
  
## <a name="validation-statuses"></a><span data-ttu-id="c9dae-112">Überprüfungsstatus</span><span class="sxs-lookup"><span data-stu-id="c9dae-112">Validation Statuses</span></span>  
 <span data-ttu-id="c9dae-113">Beim Veröffentlichen von Daten werden in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]sind die folgenden Überprüfungsstatus möglich.</span><span class="sxs-lookup"><span data-stu-id="c9dae-113">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following validation statuses are possible.</span></span>  
  
|<span data-ttu-id="c9dae-114">Status</span><span class="sxs-lookup"><span data-stu-id="c9dae-114">Status</span></span>|<span data-ttu-id="c9dae-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c9dae-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c9dae-116">Fehler</span><span class="sxs-lookup"><span data-stu-id="c9dae-116">Error</span></span>|<span data-ttu-id="c9dae-117">Für einen oder mehrere Werte in der Zeile ist bei der Überprüfung auf Grundlage der Geschäftsregeln, die von einem MDS-Administrator definiert wurden, ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c9dae-117">One or more values in the row failed validation against business rules defined by an MDS administrator.</span></span>|  
|<span data-ttu-id="c9dae-118">Nicht überprüft</span><span class="sxs-lookup"><span data-stu-id="c9dae-118">Not Validated</span></span>|<span data-ttu-id="c9dae-119">Werte in der Zeile wurden noch nicht auf Grundlage der Geschäftsregeln überprüft.</span><span class="sxs-lookup"><span data-stu-id="c9dae-119">Values in the row have not yet been validated against business rules.</span></span>|  
|<span data-ttu-id="c9dae-120">Erfolg</span><span class="sxs-lookup"><span data-stu-id="c9dae-120">Success</span></span>|<span data-ttu-id="c9dae-121">Alle Werte in der Zeile haben die Überprüfung auf Grundlage der Geschäftsregeln bestanden.</span><span class="sxs-lookup"><span data-stu-id="c9dae-121">All values in the row have passed validation against business rules.</span></span>|  
  
## <a name="input-statuses"></a><span data-ttu-id="c9dae-122">Eingabestatus</span><span class="sxs-lookup"><span data-stu-id="c9dae-122">Input Statuses</span></span>  
 <span data-ttu-id="c9dae-123">Beim Veröffentlichen von Daten werden in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]sind die folgenden Eingabestatus möglich.</span><span class="sxs-lookup"><span data-stu-id="c9dae-123">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following input statuses are possible</span></span>  
  
|<span data-ttu-id="c9dae-124">Status</span><span class="sxs-lookup"><span data-stu-id="c9dae-124">Status</span></span>|<span data-ttu-id="c9dae-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c9dae-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c9dae-126">Fehler</span><span class="sxs-lookup"><span data-stu-id="c9dae-126">Error</span></span>|<span data-ttu-id="c9dae-127">Ein oder mehrere Werte in der Zeile erfüllen die Systemanforderungen nicht, z. B. Länge oder Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c9dae-127">One or more values in the row don't meet system requirements like length or data type.</span></span> <span data-ttu-id="c9dae-128">Der Wert wird im MDS-Repository nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c9dae-128">The value is not updated in the MDS repository.</span></span>|  
|<span data-ttu-id="c9dae-129">Neue Zeile</span><span class="sxs-lookup"><span data-stu-id="c9dae-129">New Row</span></span>|<span data-ttu-id="c9dae-130">Die Werte in der Zeile wurden noch nicht im MDS-Repository veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c9dae-130">The values in the row have not yet been published to the MDS repository.</span></span>|  
|<span data-ttu-id="c9dae-131">Nur Leseberechtigung</span><span class="sxs-lookup"><span data-stu-id="c9dae-131">Read Only</span></span>|<span data-ttu-id="c9dae-132">Der angemeldete Benutzer verfügt nur über die Leseberechtigung für einen oder mehrere Werte in der Zeile, und der Wert bzw. die Werte können nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9dae-132">The logged in user has Read-only permissions to one or more values in the row and the value(s) cannot be updated.</span></span>|  
|<span data-ttu-id="c9dae-133">Unverändert</span><span class="sxs-lookup"><span data-stu-id="c9dae-133">Unchanged</span></span>|<span data-ttu-id="c9dae-134">Kein Wert in der Zeile wurde im Arbeitsblatt geändert.</span><span class="sxs-lookup"><span data-stu-id="c9dae-134">No values in the row have been changed in the worksheet.</span></span> <span data-ttu-id="c9dae-135">Dies bedeutet nicht, dass sich die Werte im Repository nicht geändert haben. Klicken Sie zum Abrufen der aktuellen Daten im Blatt in der Gruppe **Verbinden und Laden** auf **Laden oder Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="c9dae-135">This does not mean the values in the repository have not changed; to get the latest data in the sheet, in the **Connect and Load** group, click **Load or Refresh**.</span></span><br /><br /> <span data-ttu-id="c9dae-136">Dies ist die Standardeinstellung für jede Zeile.</span><span class="sxs-lookup"><span data-stu-id="c9dae-136">This is the default setting for each row.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="c9dae-137">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c9dae-137">Related Tasks</span></span>  
  
|<span data-ttu-id="c9dae-138">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="c9dae-138">Task Description</span></span>|<span data-ttu-id="c9dae-139">Thema</span><span class="sxs-lookup"><span data-stu-id="c9dae-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="c9dae-140">Bestimmen Sie, welche Werte die definierten Geschäftsregeln nicht bestehen.</span><span class="sxs-lookup"><span data-stu-id="c9dae-140">Determine which values do not pass the defined business rules.</span></span>|[<span data-ttu-id="c9dae-141">Anwenden von Geschäftsregeln &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dae-141">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)|  
|<span data-ttu-id="c9dae-142">Zeigen Sie als Unterstützung beim Korrigieren von Überprüfungsfehlern alle Transaktionen an, die für ein Element ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c9dae-142">To help correct validation errors, view all transactions that have taken place for a member.</span></span>|[<span data-ttu-id="c9dae-143">Anzeigen aller Anmerkungen oder Transaktionen für ein Element &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dae-143">View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;</span></span>](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="c9dae-144">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="c9dae-144">Related Content</span></span>  
  
-   [<span data-ttu-id="c9dae-145">Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dae-145">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
