---
title: Festlegen der Textfeldausrichtung (Berichts-Generator und SSRS) |- Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 64bd53f4-2f31-4732-8c2e-64c7b54b6972
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d509f1df29203fa5def79b61b74ae9db8f40d204
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608282"
---
# <a name="set-text-box-orientation-report-builder-and-ssrs"></a><span data-ttu-id="9bfd6-102">Festlegen der Textfeldausrichtung (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="9bfd6-102">Set Text Box Orientation (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9bfd6-103">Ein Textfeld kann in verschiedene Richtungen ausgerichtet werden: horizontal, vertikal (der Text wird von unten nach oben gelesen) oder um 270 Grad gedreht (Text wird von unten nach oben gelesen).</span><span class="sxs-lookup"><span data-stu-id="9bfd6-103">A text box can be oriented in different directions: horizontally, vertically (text reading from top to bottom), or rotated by 270 degrees (text reading from bottom to top).</span></span> <span data-ttu-id="9bfd6-104">Da die Ausrichtung für das Textfeld und nicht den Text selbst festgelegt wird, gilt sie für den gesamten Text im Textfeld.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-104">Because orientation is set on the text box not the text, the orientation applies to all the text in the text box.</span></span> <span data-ttu-id="9bfd6-105">Sie können keine anderen Ausrichtungen für Teile des Texts angeben.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-105">You cannot specify different orientations for parts of the text.</span></span> <span data-ttu-id="9bfd6-106">Passen Sie die Spaltenbreite und die Zeilenhöhe manuell an, damit der gedrehte Text vollständig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-106">Size the column width and the row height manually to accommodate the rotated text.</span></span>  
  
 <span data-ttu-id="9bfd6-107">Die "Write Mode"-Eigenschaft, mit der Sie die Textausrichtung angeben, ist im Dialogfeld " **Text Feldeigenschaften** " nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-107">The WritingMode property, which you use to specify text orientation, is not available in the **Text Box Properties** dialog box.</span></span> <span data-ttu-id="9bfd6-108">Zum Festlegen der Eigenschaft müssen Sie das Eigenschaftenfenster öffnen und die Eigenschaft dort festlegen.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-108">You need to open the Properties pane and set the property there.</span></span> <span data-ttu-id="9bfd6-109">Die verfügbaren Werte für die Eigenschaft "beschreitingmode" sind **Horizontal** (Text Lesevorgang von links nach rechts), **vertikal** (Text wird von oben nach unten gelesen), **Rotate270** (Text wird von unten nach oben gelesen).</span><span class="sxs-lookup"><span data-stu-id="9bfd6-109">The available values for the WritingMode property are **Horizontal** (text reading left to right), **Vertical** (text reading top to bottom), **Rotate270** (text reading bottom to top).</span></span> <span data-ttu-id="9bfd6-110">Sie müssen die Spaltenbreite und die Zeilenhöhe manuell anpassen, damit der Text vollständig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-110">You must manually size the column width and the row height to accommodate the text.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-text-orientation"></a><span data-ttu-id="9bfd6-111">So legen Sie die Textausrichtung fest</span><span class="sxs-lookup"><span data-stu-id="9bfd6-111">To set text orientation</span></span>  
  
1.  <span data-ttu-id="9bfd6-112">Erstellen Sie einen neuen Bericht, oder öffnen Sie einen vorhandenen Bericht.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-112">Create a new report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="9bfd6-113">Wenn der Eigenschaftenbereich nicht geöffnet ist, klicken Sie auf die Registerkarte **Ansicht** , und aktivieren Sie das Kontrollkästchen **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="9bfd6-113">If the Properties pane is not open, click the **View** tab and select the **Properties** check box.</span></span>  
  
3.  <span data-ttu-id="9bfd6-114">Klicken Sie auf das Textfeld, für das die Textausrichtung geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-114">Click the text box for which you want to change text orientation.</span></span>  
  
4.  <span data-ttu-id="9bfd6-115">Suchen Sie im Eigenschaften Bereich nach der Eigenschaft "beschreitingmode", und wählen Sie in der Dropdown Liste die Textausrichtung aus, die auf das Textfeld angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-115">Locate the WritingMode property in the Properties pane and in the drop-down list select the text orientation to apply to the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bfd6-116">Wenn die Eigenschaften im Eigenschaftenbereich in Kategorien angeordnet sind, befindet sich WritingMode in der Kategorie **Lokalisierung** .</span><span class="sxs-lookup"><span data-stu-id="9bfd6-116">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span>  
  
5.  <span data-ttu-id="9bfd6-117">Wählen Sie im Listenfeld **Horizontal**, **Vertical**oder **Rotate270**aus.</span><span class="sxs-lookup"><span data-stu-id="9bfd6-117">In the list box, select **Horizontal**, **Vertical**, or **Rotate270**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfd6-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9bfd6-118">See Also</span></span>  
 <span data-ttu-id="9bfd6-119">[Text Felder &#40;Berichts-Generator und SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9bfd6-119">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9bfd6-120">Tutorial: Formatieren von Text (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="9bfd6-120">Tutorial: Format Text &#40;Report Builder&#41;</span></span>](../tutorial-format-text-report-builder.md)  
  
  
