---
title: Anpassen (Seite Befehle) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.vs.customizecom.f1
ms.assetid: c8965f2c-51d9-437d-a6f3-8ac2075ede6b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684fb9a6266fafae00b9881eb64a3642e6c98c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717209"
---
# <a name="customize-commands-page"></a><span data-ttu-id="63eae-102">Anpassen (Seite Befehle)</span><span class="sxs-lookup"><span data-stu-id="63eae-102">Customize (Commands Page)</span></span>
  <span data-ttu-id="63eae-103">Mithilfe dieses Dialogfelds können Sie Befehle zu Symbolleisten und Menüs hinzufügen und die Bilder für auf Symbolleisten verwendeten Schaltflächen sowie für Menübefehle ändern.</span><span class="sxs-lookup"><span data-stu-id="63eae-103">This dialog box enables you to add and remove commands on toolbars and menus as well as change the images used for toolbar buttons or menu commands.</span></span> <span data-ttu-id="63eae-104">Sie können auf die Seite **Befehle** zugreifen, indem Sie im Menü **Extras** auf **Anpassen** klicken und anschließend auf **Befehle**klicken.</span><span class="sxs-lookup"><span data-stu-id="63eae-104">You can access the **Commands** page by clicking **Customize** on the **Tools** menu and then clicking **Commands**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="63eae-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="63eae-105">UI element list</span></span>  
 <span data-ttu-id="63eae-106">**Kategorien**</span><span class="sxs-lookup"><span data-stu-id="63eae-106">**Categories**</span></span>  
 <span data-ttu-id="63eae-107">Gibt die Gruppe an Befehlen an, die im Listenfeld **Befehle** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="63eae-107">Specifies the set of commands that are displayed in the **Commands** list box.</span></span> <span data-ttu-id="63eae-108">Die Befehlskategorien basieren auf Menütiteln, die durch die aktuell von der Umgebung unterstützten Tools und Designer zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="63eae-108">The categories of commands are based on menu titles provided by the tools and designers that the environment is currently supporting.</span></span> <span data-ttu-id="63eae-109">Die Titelliste ist dynamisch, und die Reihenfolge der Kategorien und der Menütitel ändert sich. Dies hängt von den Tools sowie vom Designer sowie von ggf. daran vorgenommenen Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="63eae-109">This list of titles is dynamic so that the order of categories and the menu titles change, depending on the tools and the designer, as well as any customizations made to them.</span></span> <span data-ttu-id="63eae-110">Deshalb können zwei Menüs in unterschiedlichen Designern denselben Namen besitzen. Ein Name kann also zweimal vorkommen und verschiedene Befehlsgruppen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="63eae-110">Therefore, it is possible for two menus from different designers to have the same name, so the same title can appear twice but offer different command sets.</span></span>  
  
 <span data-ttu-id="63eae-111">**Befehle**</span><span class="sxs-lookup"><span data-stu-id="63eae-111">**Commands**</span></span>  
 <span data-ttu-id="63eae-112">Zeigt die Befehle und die für Befehle verwendeten Bilder auf der Grundlage der von Ihnen ausgewählten Kategorien an.</span><span class="sxs-lookup"><span data-stu-id="63eae-112">Displays the commands and command images based on the category you selected.</span></span> <span data-ttu-id="63eae-113">Sie können einen Befehl auf eine anzupassende Symbolleiste ziehen.</span><span class="sxs-lookup"><span data-stu-id="63eae-113">You can drag a command onto the toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="63eae-114">**Auswahl ändern**</span><span class="sxs-lookup"><span data-stu-id="63eae-114">**Modify Selection**</span></span>  
 <span data-ttu-id="63eae-115">Zeigt eine Befehlsliste an, mit der Sie die Anzeige der Schaltflächen auf der Symbolleiste anpassen können.</span><span class="sxs-lookup"><span data-stu-id="63eae-115">Displays a list of commands you can use to customize the display of the button on the toolbar.</span></span> <span data-ttu-id="63eae-116">Sie können beispielsweise das verwendete Bild oder die Tastenkombination ändern und angeben, ob anstelle eines Bilds ein Text für den Befehl angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="63eae-116">For example, you can change the image or accelerator keys, as well as specify whether to display text instead of an image for the command.</span></span> <span data-ttu-id="63eae-117">Diese Schaltfläche ist verfügbar, nachdem Sie eine Befehlsschaltfläche auf einer Symbolleiste ausgewählt haben, die Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="63eae-117">This button is available after you select a command button on a toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="63eae-118">**Befehle neu anordnen**</span><span class="sxs-lookup"><span data-stu-id="63eae-118">**Rearrange Commands**</span></span>  
 <span data-ttu-id="63eae-119">Zeigt das Dialogfeld **Befehle neu anordnen** an, mit dem Sie Befehle in Menüs oder Symbolleisten umbenennen, in eine neue Reihenfolge bringen oder daraus entfernen können. Darüber hinaus können Sie hiermit die für Schaltfläche und Befehle verwendeten Bilder ändern.</span><span class="sxs-lookup"><span data-stu-id="63eae-119">Displays the **Rearrange Commands** dialog box, which allows you to rename, reorder, add, and remove commands on menus and toolbars as well as change button and command images.</span></span>  
  
 <span data-ttu-id="63eae-120">**Tastatur**</span><span class="sxs-lookup"><span data-stu-id="63eae-120">**Keyboard**</span></span>  
 <span data-ttu-id="63eae-121">Zeigt die Seite **Tastatur** des Dialogfelds **Optionen** an, in dem Sie Tastenkombinationen für Befehle angeben können.</span><span class="sxs-lookup"><span data-stu-id="63eae-121">Displays the **Keyboard** page of the **Options** dialog box so you can specify shortcut key combinations for commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63eae-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63eae-122">See Also</span></span>  
 [<span data-ttu-id="63eae-123">Anpassen von Menüs und Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="63eae-123">Customize Menus and Shortcut Keys</span></span>](../customize-menus-and-shortcut-keys.md)  
