---
title: Standardfeldsatz für Power View Berichte konfigurieren (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66fbbacd0cc2efd7d379bcc8e68149551476869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696153"
---
# <a name="configure-default-field-set-for-power-view-reports-ssas-tabular"></a><span data-ttu-id="605dc-102">Konfigurieren eines Standardfeldsatzes für Power View-Berichte (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="605dc-102">Configure Default Field Set for Power View Reports (SSAS Tabular)</span></span>
  <span data-ttu-id="605dc-103">Ein Standardfeldsatz ist eine vordefinierte Liste von Spalten und Measures, die einem [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] -Berichtszeichenbereich automatisch hinzugefügt werden, wenn Sie in der Berichtsfeldliste die Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="605dc-103">A default field set is a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span> <span data-ttu-id="605dc-104">Ersteller tabellarischer Modelle können ein Standardfeld generieren, das für die Berichtsautoren, die das Modell für ihre Berichte verwenden, auf die Eliminierung redundanter Schritte abzielt.</span><span class="sxs-lookup"><span data-stu-id="605dc-104">Tabular model authors can create a default field set to eliminate redundant steps for report authors who use the model for their reports.</span></span> <span data-ttu-id="605dc-105">Wenn Sie beispielsweise wissen, dass die meisten Berichtsautoren, die Kundenkontaktdaten verwenden, immer einen Kontaktnamen, eine primäre Telefonnummer, eine E-Mail-Adresse und einen Unternehmensnamen benötigen, können Sie diese Spalten im Voraus auswählen, sodass sie dem Berichtszeichenbereich immer hinzugefügt werden, sobald der Autor auf die Kundenkontakttabelle klickt.</span><span class="sxs-lookup"><span data-stu-id="605dc-105">For example, if you know that most report authors who work with customer contact information always want to see a contact name, a primary phone number, an email address, and a company name, you can pre-select those columns so that they are always added to the report canvas when the author clicks the Customer Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="605dc-106">Ein Standardfeldsatz gilt nur für ein tabellarisches Modell, das in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]als Datenmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="605dc-106">A default field set applies only to a tabular model used as a data model in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="605dc-107">Standardfeldsätze werden in Excel-Pivotberichten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="605dc-107">Default field sets are not supported in Excel pivot reports.</span></span>  
  
## <a name="creating-a-default-field-set"></a><span data-ttu-id="605dc-108">Erstellen eines Standardfeldsatzes</span><span class="sxs-lookup"><span data-stu-id="605dc-108">Creating a Default Field Set</span></span>  
 <span data-ttu-id="605dc-109">Sie können bestimmen, welche Felder ggf. standardmäßig eingefügt werden, wenn eine bestimmte Tabelle in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="605dc-109">You can determine which fields, if any, are included by default whenever a specific table is selected in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="605dc-110">Sie können auch die Reihenfolge bestimmen, in der die Felder in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="605dc-110">You can also determine the order in which fields appear in the list.</span></span> <span data-ttu-id="605dc-111">Sie können einen Standardfeldsatz angeben, indem Sie Berichtseigenschaften im tabellarischen Modellprojekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="605dc-111">To specify a default field set, you set report properties in the tabular model project.</span></span>  
  
#### <a name="to-add-a-default-field-set"></a><span data-ttu-id="605dc-112">So fügen Sie einen Standardfeldsatz hinzu</span><span class="sxs-lookup"><span data-stu-id="605dc-112">To add a default field set</span></span>  
  
1.  <span data-ttu-id="605dc-113">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf die Tabelle (Registerkarte), für die Sie eine Standardfeldliste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="605dc-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the table (tab) for which you are configuring a default field list.</span></span>  
  
2.  <span data-ttu-id="605dc-114">Klicken Sie im **Eigenschaftenfenster** in der Eigenschaft **Standardfeldsatz** auf **Zum Bearbeiten klicken**.</span><span class="sxs-lookup"><span data-stu-id="605dc-114">In the **Properties** window, in the **Default Field Set** property, click **Click to edit**.</span></span>  
  
3.  <span data-ttu-id="605dc-115">Wählen Sie im Standardfeldsatz ein oder mehrere Felder aus.</span><span class="sxs-lookup"><span data-stu-id="605dc-115">In the Default Field Set dialog, select one or more fields.</span></span> <span data-ttu-id="605dc-116">Sie können jedes beliebige Feld, einschließlich Measures, in der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="605dc-116">You can choose any field in the table, including measures.</span></span> <span data-ttu-id="605dc-117">Halten Sie die UMSCHALTTASTE gedrückt, um mehrere aufeinander folgende Felder auszuwählen, bzw. die STRG-TASTE, um einzelne Felder auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="605dc-117">Hold down the Shift key to select a range, or the Ctrl key to select individual fields.</span></span>  
  
4.  <span data-ttu-id="605dc-118">Klicken Sie auf **Hinzufügen** , um die Felder dem Standardfeldsatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="605dc-118">Click **Add** to add them to the default field set.</span></span>  
  
5.  <span data-ttu-id="605dc-119">Mithilfe der NACH-OBEN-TASTE und der NACH-UNTEN-TASTE können Sie die Reihenfolge in der Feldliste festlegen.</span><span class="sxs-lookup"><span data-stu-id="605dc-119">Use the Up and Down buttons to specify an order to the field list.</span></span> <span data-ttu-id="605dc-120">Felder werden dem Bericht in der Reihenfolge hinzugefügt, in der sie im Feldsatz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="605dc-120">Fields will be added to the report in the order defined for the field set.</span></span>  
  
6.  <span data-ttu-id="605dc-121">Wiederholen Sie diese Schritte für weitere Tabellen in der Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="605dc-121">Repeat these steps for other tables in your workbook.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="605dc-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="605dc-122">Next Step</span></span>  
 <span data-ttu-id="605dc-123">Nach dem Erstellen eines Standardfeldsatzes können Sie die Benutzerfreundlichkeit des Berichtsentwurfs weiter beeinflussen, indem Sie Standardbezeichnungen, Standardbilder, Standardgruppenverhalten oder die Anordnung von Zeilen mit gleichem Wert gruppiert in einer Zeile oder einzeln angeben.</span><span class="sxs-lookup"><span data-stu-id="605dc-123">After you create a default field set, you can further influence the report design experience by specifying default labels, default images, default group behavior, or whether rows that contain the same value are grouped together in one row or listed individually.</span></span> <span data-ttu-id="605dc-124">Weitere Informationen finden Sie unter [Konfigurieren von Tabellenverhaltenseigenschaften für Power View-Berichte &#40;SSAS – tabellarisch&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span><span class="sxs-lookup"><span data-stu-id="605dc-124">For more information, see [Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span></span>  
  
  
