---
title: Anzeigen oder Ändern von Modellierungsflags (Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d1169735-fb18-417b-b8d6-9a161e444020
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf0edd827321685a2d6a9041759328a7ac6e7cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717023"
---
# <a name="view-or-change-modeling-flags-data-mining"></a><span data-ttu-id="bc607-102">Anzeigen oder Ändern von Modellierungsflags (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="bc607-102">View or Change Modeling Flags (Data Mining)</span></span>
  <span data-ttu-id="bc607-103">Modellierungsflags sind Eigenschaften, die Sie für eine Miningstrukturspalte oder für Miningmodellspalten festlegen, um zu steuern, wie der Algorithmus die Daten während der Analyse verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bc607-103">Modeling flags are properties that you set on a mining structure column or mining model columns to control how the algorithm processes the data during analysis.</span></span>  
  
 <span data-ttu-id="bc607-104">Im Data Mining-Designer können Sie die Modellierungsflags, die einer Miningstruktur oder Miningspalte zugeordnet sind, betrachten und ändern, indem Sie die Eigenschaften der Struktur oder des Modells anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc607-104">In Data Mining Designer, you can view and modify the modeling flags associated with a mining structure or mining column by viewing the properties of the structure or model.</span></span> <span data-ttu-id="bc607-105">Sie können Modellierungsflags auch mit DMX, AMO oder XMLA festlegen.</span><span class="sxs-lookup"><span data-stu-id="bc607-105">You can also set modeling flags by using DMX, AMO, or XMLA.</span></span>  
  
 <span data-ttu-id="bc607-106">Diese Prozedur beschreibt, wie die Modellierungsflags im Designer geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bc607-106">This procedure describes how to change the modeling flags in the designer.</span></span>  
  
### <a name="view-or-change-the-modeling-flag-for-a-structure-column-or-model-column"></a><span data-ttu-id="bc607-107">Anzeigen oder Ändern des Modellierungsflags für eine Strukturspalte oder eine Modellspalte</span><span class="sxs-lookup"><span data-stu-id="bc607-107">View or change the modeling flag for a structure column or model column</span></span>  
  
1.  <span data-ttu-id="bc607-108">Öffnen Sie in SQL Server Design Studio den Projektmappen-Explorer, und doppelklicken Sie dann auf die Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="bc607-108">In SQL Server Design Studio, open Solution Explorer, and then double-click the mining structure.</span></span>  
  
2.  <span data-ttu-id="bc607-109">Zum Festlegen des NOT NULL-Modellierungsflags klicken Sie auf die Registerkarte **Mining Struktur** . Um die Regressor-oder MODEL_EXISTENCE_ONLY-Flags festzulegen, klicken Sie auf die Registerkarte **Mining Modell** .</span><span class="sxs-lookup"><span data-stu-id="bc607-109">To set the NOT NULL modeling flag, click the **Mining Structure** tab. To set the REGRESSOR or MODEL_EXISTENCE_ONLY flags, click the **Mining Model** tab.</span></span>  
  
3.  <span data-ttu-id="bc607-110">Klicken Sie mit der rechten Maustaste auf die Spalte, die Sie anzeigen oder ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="bc607-110">Right-click the column you want to view or change, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="bc607-111">Um ein neues Modellierungsflag hinzuzufügen, klicken Sie auf das Textfeld neben der Eigenschaft **ModelingFlags** , und aktivieren Sie das bzw. die Kontrollkästchen für die Modellierungsflags, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bc607-111">To add a new modeling flag, click the text box next to the **ModelingFlags** property, and select the check box or check boxes for the modeling flags you want to use.</span></span>  
  
     <span data-ttu-id="bc607-112">Modellierungsflags werden nur angezeigt, wenn sie für den Datentyp der Spalte geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="bc607-112">Modeling flags are displayed only if they are appropriate for the column data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc607-113">Nachdem ein Modellierungsflag geändert wurde, muss das Modell erneut verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="bc607-113">After you change a modeling flag, you must reprocess the model.</span></span>  
  
### <a name="get-the-modeling-flags-used-in-the-model"></a><span data-ttu-id="bc607-114">Abrufen der im Modell verwendeten Modellierungsflags</span><span class="sxs-lookup"><span data-stu-id="bc607-114">Get the modeling flags used in the model</span></span>  
  
-   <span data-ttu-id="bc607-115">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ein DMX-Abfragefenster, und geben Sie eine Anweisung ähnlich der folgenden ein:</span><span class="sxs-lookup"><span data-stu-id="bc607-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window, and type a query like the following:</span></span>  
  
    ```  
    SELECT COLUMN_NAME, CONTENT_TYPE, MODELING_FLAG  
    FROM $system.DMSCHEMA_MINING_COLUMNS  
    WHERE MODEL_NAME = 'Forecasting'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bc607-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc607-116">See Also</span></span>  
 <span data-ttu-id="bc607-117">[Mining Modell Tasks und Anleitungen](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="bc607-117">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="bc607-118">Modellierungsflags &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bc607-118">Modeling Flags &#40;Data Mining&#41;</span></span>](modeling-flags-data-mining.md)  
  
  
