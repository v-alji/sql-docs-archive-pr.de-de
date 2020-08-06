---
title: Abgeleitete Dimensionselemente (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.inferrdim.f1
ms.assetid: 809e395f-2e10-48ff-8860-56403f130628
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dda4345b91c69b134516baab2e5ba9b9990bd6af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621098"
---
# <a name="inferred-dimension-members-slowly-changing-dimension-wizard"></a><span data-ttu-id="a4843-102">Abgeleitete Dimensionselemente (Assistent für langsam veränderliche Dimensionen)</span><span class="sxs-lookup"><span data-stu-id="a4843-102">Inferred Dimension Members (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="a4843-103">Mithilfe des Dialogfelds **Abgeleitete Dimensionselemente** können Sie Optionen für das Verwenden von abgeleiteten Elementen angeben.</span><span class="sxs-lookup"><span data-stu-id="a4843-103">Use the **Inferred Dimension Members** dialog box to specify options for using inferred members.</span></span> <span data-ttu-id="a4843-104">Abgeleitete Elemente sind vorhanden, wenn eine Faktentabelle auf noch nicht geladene Dimensionselemente verweist.</span><span class="sxs-lookup"><span data-stu-id="a4843-104">Inferred members exist when a fact table references dimension members that are not yet loaded.</span></span> <span data-ttu-id="a4843-105">Wenn für das abgeleitete Element Daten geladen sind, können Sie den vorhandenen Datensatz aktualisieren, aber keinen neuen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4843-105">When data for the inferred member is loaded, you can update the existing record rather than create a new one.</span></span>  
  
 <span data-ttu-id="a4843-106">Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a4843-106">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4843-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a4843-107">Options</span></span>  
 <span data-ttu-id="a4843-108">**Unterstützung für abgeleitete Elemente aktivieren**</span><span class="sxs-lookup"><span data-stu-id="a4843-108">**Enable inferred member support**</span></span>  
 <span data-ttu-id="a4843-109">Wenn Sie abgeleitete Elemente aktivieren, müssen Sie eine der beiden folgenden Optionen auswählen.</span><span class="sxs-lookup"><span data-stu-id="a4843-109">If you choose to enable inferred members, you must select one of the two options that follow.</span></span>  
  
 <span data-ttu-id="a4843-110">**Alle Spalten mit einem Änderungstyp weisen den Wert NULL auf**</span><span class="sxs-lookup"><span data-stu-id="a4843-110">**All columns with a change type are null**</span></span>  
 <span data-ttu-id="a4843-111">Gibt an, dass in allen Spalten des neuen Datensatzes des abgeleiteten Elements, die einen Änderungstyp aufweisen, NULL-Werte eingetragen werden.</span><span class="sxs-lookup"><span data-stu-id="a4843-111">Specify whether to enter null values in all columns with a change type in the new inferred member record.</span></span>  
  
 <span data-ttu-id="a4843-112">**Mithilfe einer booleschen Spalte anzeigen, ob der aktuelle Datensatz ein abgeleitetes Element ist**</span><span class="sxs-lookup"><span data-stu-id="a4843-112">**Use a Boolean column to indicate whether the current record is an inferred member**</span></span>  
 <span data-ttu-id="a4843-113">Gibt an, dass eine vorhandene boolesche Spalte verwendet wird, um anzuzeigen, dass der aktuelle Datensatz ein abgeleitetes Element ist.</span><span class="sxs-lookup"><span data-stu-id="a4843-113">Specify whether to use an existing Boolean column to indicate whether the current record is an inferred member.</span></span>  
  
 <span data-ttu-id="a4843-114">**Indikator für abgeleitetes Element**</span><span class="sxs-lookup"><span data-stu-id="a4843-114">**Inferred member indicator**</span></span>  
 <span data-ttu-id="a4843-115">Wenn eine boolesche Spalte verwendet wird, um abgeleitete Elemente wie oben beschrieben anzuzeigen, wählen Sie die Spalte aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a4843-115">If you have chosen to use a Boolean column to indicate inferred members as described above, select the column from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4843-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4843-116">See Also</span></span>  
 [<span data-ttu-id="a4843-117">Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="a4843-117">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
