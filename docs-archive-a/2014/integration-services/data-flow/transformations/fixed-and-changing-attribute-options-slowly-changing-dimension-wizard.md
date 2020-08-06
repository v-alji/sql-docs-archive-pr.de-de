---
title: Optionen für feste und veränderliche Attribute (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df654cd97b343179828ebd94dea40eacc90e003d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609978"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="8c3ef-102">Optionen für feste und veränderliche Attribute (Assistent für langsam veränderliche Dimensionen)</span><span class="sxs-lookup"><span data-stu-id="8c3ef-102">Fixed and Changing Attribute Options (Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="8c3ef-103">Geben Sie mithilfe des Dialogfelds **Optionen für feste und veränderliche Attribute** an, wie auf Änderungen bei festen und veränderlichen Attributen reagiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c3ef-103">Use the **Fixed and Changing Attribute Options** dialog box to specify how to respond to changes in fixed and changing attributes.</span></span>  
  
 <span data-ttu-id="8c3ef-104">Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ef-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8c3ef-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8c3ef-105">Options</span></span>  
 <span data-ttu-id="8c3ef-106">**Feste Attribute**</span><span class="sxs-lookup"><span data-stu-id="8c3ef-106">**Fixed attributes**</span></span>  
 <span data-ttu-id="8c3ef-107">Geben Sie für feste Attribute an, ob der Task fehlschlagen soll, wenn bei einem festen Attribut eine Änderung festgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8c3ef-107">For fixed attributes, indicate whether the task should fail if a change is detected in a fixed attribute.</span></span>  
  
 <span data-ttu-id="8c3ef-108">**Veränderliche Attribute**</span><span class="sxs-lookup"><span data-stu-id="8c3ef-108">**Changing attributes**</span></span>  
 <span data-ttu-id="8c3ef-109">Geben Sie für veränderliche Attribute an, ob der Task zusätzlich zu aktuellen Datensätzen veraltete oder abgelaufene Datensätze ändern soll, wenn bei einem veränderlichen Attribut eine Änderung erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8c3ef-109">For changing attributes, indicate whether the task should change outdated or expired records, in addition to current records, when a change is detected in a changing attribute.</span></span> <span data-ttu-id="8c3ef-110">Ein abgelaufener Datensatz ist ein Datensatz, der durch eine Änderung in einem Verlaufsattribut (eine Änderung vom Typ 2) durch einen neueren Datensatz ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="8c3ef-110">An expired record is a record that has been replaced with a newer record by a change in a historical attribute (a Type 2 change).</span></span> <span data-ttu-id="8c3ef-111">Das Auswählen dieser Option verursacht möglicherweise zusätzliche Verarbeitungsanforderungen für ein im relationalen Data Warehouse erstelltes mehrdimensionales Objekt.</span><span class="sxs-lookup"><span data-stu-id="8c3ef-111">Selecting this option may impose additional processing requirements on a multidimensional object constructed on the relational data warehouse.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3ef-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c3ef-112">See Also</span></span>  
 [<span data-ttu-id="8c3ef-113">Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="8c3ef-113">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
