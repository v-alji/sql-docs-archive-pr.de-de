---
title: Referenz zur Benutzeroberfläche des Dialogfelds „Spaltentypen vorschlagen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.suggestdatatypes.f1
ms.assetid: 8d5652e0-cf57-483f-828b-10f00c08418b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbca2a3186a58b1148eb9627825fdfddf334339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724861"
---
# <a name="suggest-column-types-dialog-box-ui-reference"></a><span data-ttu-id="4ca01-102">Referenz zur Benutzeroberfläche des Dialogfelds Spaltentypen vorschlagen</span><span class="sxs-lookup"><span data-stu-id="4ca01-102">Suggest Column Types Dialog Box UI Reference</span></span>
  <span data-ttu-id="4ca01-103">Identifizieren Sie mithilfe des Dialogfelds **Spaltentypen vorschlagen** den Datentyp und die -länge von Spalten im Verbindungs-Manager für Flatfiles basierend auf einer Stichprobe für den Dateiinhalt.</span><span class="sxs-lookup"><span data-stu-id="4ca01-103">Use the **Suggest Column Types** dialog box to identify the data type and length of columns in a Flat File Connection Manager based on a sampling of the file content.</span></span>  
  
 <span data-ttu-id="4ca01-104">Weitere Informationen zu den von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]verwendeten Datentypen, finden Sie unter [Integration Services-Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4ca01-104">To learn more about the data types used by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4ca01-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4ca01-105">Options</span></span>  
 <span data-ttu-id="4ca01-106">**Anzahl von Zeilen**</span><span class="sxs-lookup"><span data-stu-id="4ca01-106">**Number of rows**</span></span>  
 <span data-ttu-id="4ca01-107">Geben Sie die Anzahl der Zeilen im vom Algorithmus verwendeten Beispiel an, oder wählen Sie die Anzahl aus.</span><span class="sxs-lookup"><span data-stu-id="4ca01-107">Type or select the number of rows in the sample that the algorithm uses.</span></span>  
  
 <span data-ttu-id="4ca01-108">**Den kleinsten integer-Datentyp vorschlagen**</span><span class="sxs-lookup"><span data-stu-id="4ca01-108">**Suggest the smallest integer data type**</span></span>  
 <span data-ttu-id="4ca01-109">Deaktivieren Sie dieses Kontrollkästchen, um die Analyse auszulassen.</span><span class="sxs-lookup"><span data-stu-id="4ca01-109">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="4ca01-110">Wenn dieses Kontrollkästchen aktiviert ist, bestimmt es den kleinsten integer-Datentyp für Spalten, die numerische Daten vom integer-Typ enthalten.</span><span class="sxs-lookup"><span data-stu-id="4ca01-110">If selected, determines the smallest possible integer data type for columns that contain integral numeric data.</span></span>  
  
 <span data-ttu-id="4ca01-111">**Den kleinsten Real-Datentyp vorschlagen**</span><span class="sxs-lookup"><span data-stu-id="4ca01-111">**Suggest the smallest real data type**</span></span>  
 <span data-ttu-id="4ca01-112">Deaktivieren Sie dieses Kontrollkästchen, um die Analyse auszulassen.</span><span class="sxs-lookup"><span data-stu-id="4ca01-112">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="4ca01-113">Wenn dieses Kontrollkästchen aktiviert ist, bestimmt es, ob Spalten mit numerischen Daten vom real-Typ den kleineren real-Datentyp, DT_R4, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4ca01-113">If selected, determines whether columns that contain real numeric data can use the smaller real data type, DT_R4.</span></span>  
  
 <span data-ttu-id="4ca01-114">**Boolesche Spalten mithilfe der folgenden Werte identifizieren**</span><span class="sxs-lookup"><span data-stu-id="4ca01-114">**Identify Boolean columns using the following values**</span></span>  
 <span data-ttu-id="4ca01-115">Geben Sie die beiden Werte ein, die Sie als die booleschen Werte für true und false verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4ca01-115">Type the two values that you want to use as the Boolean values true and false.</span></span> <span data-ttu-id="4ca01-116">Die Werte müssen durch ein Komma getrennt sein. Der erste Wert repräsentiert True.</span><span class="sxs-lookup"><span data-stu-id="4ca01-116">The values must be separated by a comma, and the first value represents True.</span></span>  
  
 <span data-ttu-id="4ca01-117">**Auffüllung zu Zeichenfolgenspalten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="4ca01-117">**Pad string columns**</span></span>  
 <span data-ttu-id="4ca01-118">Aktivieren Sie dieses Kontrollkästchen, um die Zeichenfolgenauffüllung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4ca01-118">Select this check box to enable string padding.</span></span>  
  
 <span data-ttu-id="4ca01-119">**Prozentsatz der Auffüllung**</span><span class="sxs-lookup"><span data-stu-id="4ca01-119">**Percent padding**</span></span>  
 <span data-ttu-id="4ca01-120">Geben Sie den Prozentsatz der Spaltenlänge ein, um den die Länge von Spalten für Zeichendatentypen vergrößert werden soll, oder wählen Sie den Wert aus.</span><span class="sxs-lookup"><span data-stu-id="4ca01-120">Type or select the percentage of the column lengths by which to increase the length of columns for character data types.</span></span> <span data-ttu-id="4ca01-121">Der Prozentsatz muss als ganze Zahl angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4ca01-121">The percentage must be an integer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca01-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ca01-122">See Also</span></span>  
 <span data-ttu-id="4ca01-123">[Fehler- und Meldungsreferenz von Integration Services](../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4ca01-123">[Integration Services Error and Message Reference](../integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="4ca01-124">Verbindungs-Manager für Flatfiles</span><span class="sxs-lookup"><span data-stu-id="4ca01-124">Flat File Connection Manager</span></span>](file-connection-manager.md)  
  
  
