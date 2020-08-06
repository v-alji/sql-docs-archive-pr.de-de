---
title: Parameterinfo (IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e5e7496753006808f75378182db0d3cb606d4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621458"
---
# <a name="parameter-info-intellisense"></a><span data-ttu-id="9cac8-102">Parameterinfo (IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="9cac8-102">Parameter Info (IntelliSense)</span></span>
  <span data-ttu-id="9cac8-103">Die Option [!INCLUDE[msCoName](../../includes/msconame-md.md)] Parameter Info **von** IntelliSense öffnet eine Parameterliste, die Informationen über die Anzahl, Namen und Typen der Parameter enthält, die für eine Funktion oder gespeicherte Prozedur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9cac8-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Parameter Info** option opens a parameters list that provides information about the number, names, and types of the parameters that are required by a function or stored procedure.</span></span> <span data-ttu-id="9cac8-104">Der fett formatierte Parameter gibt den nächsten Parameter an, der beim Eingeben einer Funktion oder gespeicherten Prozedur erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9cac8-104">The parameter in bold indicates the next parameter that is required as you type a function or stored procedure.</span></span>  
  
 <span data-ttu-id="9cac8-105">Die Parameterliste wird auch für geschachtelte Funktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cac8-105">The parameter list is also displayed for nested functions.</span></span> <span data-ttu-id="9cac8-106">Wenn Sie eine Funktion als Parameter für eine andere Funktion eingeben, werden in der Parameterliste die Parameter für die innere Funktion angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cac8-106">If you type a function as a parameter to another function, the parameter list displays the parameters for the inner function.</span></span> <span data-ttu-id="9cac8-107">Wenn die Parameterliste der inneren Funktion vollständig ist, werden in der Parameterliste anschließend die Parameter der äußeren Funktion angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cac8-107">Then, when the inner function parameter list is complete, the parameter list reverts to displaying the outer function parameters.</span></span>  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a><span data-ttu-id="9cac8-108">So zeigen Sie Parameterinfo für Funktionen oder gespeicherte Prozeduren an</span><span class="sxs-lookup"><span data-stu-id="9cac8-108">To view Parameter Info for functions or stored procedures</span></span>  
  
1.  <span data-ttu-id="9cac8-109">Geben Sie nach dem Namen einer Funktion wie gewohnt eine öffnende Klammer ein, um die Parameterliste zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9cac8-109">After the name of a function, type an open parenthesis as you usually type to open the parameters list.</span></span> <span data-ttu-id="9cac8-110">Wenn Sie den Namen einer gespeicherten Prozedur eingegeben haben, geben Sie wie gewohnt ein Leerzeichen ein, um Informationen zu den Prozedurparametern abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9cac8-110">After you type the name of a stored procedure, type a space as you usually type to obtain information about the procedure parameters.</span></span>  
  
     <span data-ttu-id="9cac8-111">IntelliSense zeigt die vollständige Deklaration für die Funktion oder die Parameter für eine gespeicherte Prozedur in einem Popupfenster direkt unter der Einfügemarke an.</span><span class="sxs-lookup"><span data-stu-id="9cac8-111">IntelliSense displays the complete declaration for the function or the parameters for a stored procedure in a pop-up window just under the insertion point.</span></span> <span data-ttu-id="9cac8-112">Der erste Parameter in der Liste wird fett formatiert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cac8-112">The first parameter in the list appears in bold.</span></span>  
  
2.  <span data-ttu-id="9cac8-113">Beim Eingeben der Parameter ändert sich die Fettformatierung, um den nächsten Parameter anzugeben, den Sie eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="9cac8-113">As you type the parameters, the bold font changes to reflect the next parameter that you need to enter.</span></span>  
  
3.  <span data-ttu-id="9cac8-114">Drücken Sie zu einem beliebigen Zeitpunkt die ESC-TASTE, um die Liste zu schließen, oder fahren Sie mit der Eingabe fort, bis die Funktion abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9cac8-114">Press ESC at any time to close the list, or continue typing until you have completed the function.</span></span>  
  
     <span data-ttu-id="9cac8-115">Wenn Sie für eine Funktion die schließende Klammer eingeben, schließen Sie auch die Parameterliste.</span><span class="sxs-lookup"><span data-stu-id="9cac8-115">For a function, if you type the closing parenthesis you also close the parameter list.</span></span>  
  
#### <a name="to-manually-start-parameter-info"></a><span data-ttu-id="9cac8-116">So starten Sie Parameterinfo manuell</span><span class="sxs-lookup"><span data-stu-id="9cac8-116">To manually start Parameter Info</span></span>  
  
1.  <span data-ttu-id="9cac8-117">Wählen Sie im Menü **Bearbeiten** **IntelliSense** und anschließend **Parameterinfo**aus.</span><span class="sxs-lookup"><span data-stu-id="9cac8-117">On the **Edit** menu, select **IntelliSense** and then select **Parameter Info**.</span></span>  
  
2.  <span data-ttu-id="9cac8-118">Drücken Sie die Tastenkombination STRG+UMSCHALT+LEERZEICHEN.</span><span class="sxs-lookup"><span data-stu-id="9cac8-118">Press the CTRL+SHIFT+SPACE keyboard shortcut.</span></span>  
  
 <span data-ttu-id="9cac8-119">Weitere Informationen finden Sie unter [Konfigurieren von IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9cac8-119">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9cac8-120">Die Option **Parameter Info** ist nur für den [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor und den XML-Abfrage-Editor verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9cac8-120">The **Parameter Info** option is available only for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor and the XML Query Editor.</span></span>  
  
  
