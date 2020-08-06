---
title: Optionen für Verlaufsattribute (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad005d6b8f80973abeb47dd881ef02b669d7b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621108"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="baa8e-102">Optionen für Verlaufsattribute (Assistent für langsam veränderliche Dimensionen)</span><span class="sxs-lookup"><span data-stu-id="baa8e-102">Historical Attribute Options (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="baa8e-103">Mithilfe des Dialogfelds **Optionen für Verlaufsattribute** können Sie Verlaufsattribute nach Anfangs- und Enddatum anzeigen oder sie in einer speziell zu diesem Zweck erstellten Spalte aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="baa8e-103">Use the **Historical Attributes Options** dialog box to show historical attributes by start and end dates, or to record historical attributes in a column specially created for this purpose.</span></span>  
  
 <span data-ttu-id="baa8e-104">Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="baa8e-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="baa8e-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="baa8e-105">Options</span></span>  
 <span data-ttu-id="baa8e-106">**Einzelne Spalte zum Anzeigen der aktuellen und abgelaufenen Datensätze verwenden**</span><span class="sxs-lookup"><span data-stu-id="baa8e-106">**Use a single column to show current and expired records**</span></span>  
 <span data-ttu-id="baa8e-107">Wenn Sie eine einzelne Spalte für zum Aufzeichnen des Status von Verlaufsattributen verwenden, sind folgende Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="baa8e-107">If you choose to use a single column to record the status of historical attributes, the following options are available:</span></span>  
  
|<span data-ttu-id="baa8e-108">Option</span><span class="sxs-lookup"><span data-stu-id="baa8e-108">Option</span></span>|<span data-ttu-id="baa8e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="baa8e-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="baa8e-110">**Spalte mit Indikator für aktuellen Datensatz**</span><span class="sxs-lookup"><span data-stu-id="baa8e-110">**Column to indicate current record**</span></span>|<span data-ttu-id="baa8e-111">Wählen Sie eine Spalte aus, in der der aktuelle Datensatz angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="baa8e-111">Select a column in which to indicate the current record.</span></span>|  
|<span data-ttu-id="baa8e-112">**Wert, wenn aktuell**</span><span class="sxs-lookup"><span data-stu-id="baa8e-112">**Value when current**</span></span>|<span data-ttu-id="baa8e-113">Verwenden Sie entweder **True** oder **Current** , um anzuzeigen, dass der Datensatz aktuell ist.</span><span class="sxs-lookup"><span data-stu-id="baa8e-113">Use either **True** or **Current** to show whether the record is current.</span></span>|  
|<span data-ttu-id="baa8e-114">**Wert, wenn abgelaufen**</span><span class="sxs-lookup"><span data-stu-id="baa8e-114">**Expiration value**</span></span>|<span data-ttu-id="baa8e-115">Verwenden Sie entweder **False** oder **Abgelaufen** , um anzuzeigen, dass der Datensatz ein abgelaufener Wert ist.</span><span class="sxs-lookup"><span data-stu-id="baa8e-115">Use either **False** or **Expired** to show whether the record is a historical value.</span></span>|  
  
 <span data-ttu-id="baa8e-116">**Start- und Enddatum zum Identifizieren aktueller und abgelaufener Datensätze verwenden**</span><span class="sxs-lookup"><span data-stu-id="baa8e-116">**Use start and end dates to identify current and expired records**</span></span>  
 <span data-ttu-id="baa8e-117">Die Dimensionstabelle für diese Option muss eine Datumsspalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="baa8e-117">The dimension table for this option must include a date column.</span></span> <span data-ttu-id="baa8e-118">Wenn Sie die Verlaufsattribute nach Start- und Enddatum anzeigen, sind folgende Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="baa8e-118">If you choose to show historical attributes by start and end dates, the following options are available:</span></span>  
  
|<span data-ttu-id="baa8e-119">Option</span><span class="sxs-lookup"><span data-stu-id="baa8e-119">Option</span></span>|<span data-ttu-id="baa8e-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="baa8e-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="baa8e-121">**Spalte mit Startdatum**</span><span class="sxs-lookup"><span data-stu-id="baa8e-121">**Start date column**</span></span>|<span data-ttu-id="baa8e-122">Wählen Sie die Spalte in der Dimensionstabelle aus, die das Startdatum enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="baa8e-122">Select the column in the dimension table to contain the start date.</span></span>|  
|<span data-ttu-id="baa8e-123">**Spalte mit Enddatum**</span><span class="sxs-lookup"><span data-stu-id="baa8e-123">**End date column**</span></span>|<span data-ttu-id="baa8e-124">Wählen Sie die Spalte in der Dimensionstabelle aus, die das Enddatum enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="baa8e-124">Select the column in the dimension table to contain the end date.</span></span>|  
|<span data-ttu-id="baa8e-125">**Variable zum Festlegen von Datumswerten**</span><span class="sxs-lookup"><span data-stu-id="baa8e-125">**Variable to set date values**</span></span>|<span data-ttu-id="baa8e-126">Wählen Sie eine Variable für die Datumswerte aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="baa8e-126">Select a date variable from the list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="baa8e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baa8e-127">See Also</span></span>  
 [<span data-ttu-id="baa8e-128">Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="baa8e-128">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
