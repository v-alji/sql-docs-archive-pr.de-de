---
title: Öffnen einer Vorlage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- templates [Transact-SQL], opening
- opening templates
ms.assetid: 605b0f4c-5ba1-4249-ad1c-6341df77cd7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 43b75d68fafea759e4d7873c1fb738d7964dcf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619514"
---
# <a name="open-a-template"></a><span data-ttu-id="c11b4-102">Öffnen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="c11b4-102">Open a Template</span></span>
  <span data-ttu-id="c11b4-103">Sie können eine Vorlage über den Vorlagen-Explorer öffnen.</span><span class="sxs-lookup"><span data-stu-id="c11b4-103">You can open a template from Template Explorer.</span></span>  
  
## <a name="to-open-a-template-from-template-explorer"></a><span data-ttu-id="c11b4-104">So öffnen Sie eine Vorlage über den Vorlagen-Explorer</span><span class="sxs-lookup"><span data-stu-id="c11b4-104">To open a template from Template Explorer</span></span>  
 <span data-ttu-id="c11b4-105">Vorlagen lassen sich über den Vorlagen-Explorer öffnen.</span><span class="sxs-lookup"><span data-stu-id="c11b4-105">You can open templates from the Template Explorer.</span></span>  
  
1.  <span data-ttu-id="c11b4-106">Klicken Sie zum Öffnen des Vorlagen-Explorers im Menü **Ansicht** auf **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c11b4-106">To open Template Explorer, on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="c11b4-107">Erweitern Sie in der Liste mit Vorlagenkategorien die Kategorie mit der zu öffnenden Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c11b4-107">In the list of template categories, expand the category that contains the template you want to open.</span></span>  
  
3.  <span data-ttu-id="c11b4-108">Die Vorlage lässt sich anhand von drei Methoden öffnen:</span><span class="sxs-lookup"><span data-stu-id="c11b4-108">There are three ways to open the template:</span></span>  
  
    1.  <span data-ttu-id="c11b4-109">Doppelklicken Sie auf die Vorlage, um sie in einem Code-Editor-Fenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c11b4-109">Double-click the template to open it in a code editor window.</span></span>  
  
    2.  <span data-ttu-id="c11b4-110">Klicken Sie mit der rechten Maustaste auf die Vorlage, und wählen Sie **Öffnen** aus, um die Vorlage in einem Code-Editor-Fenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c11b4-110">Right-click the template and select **Open** to open it in a code editor window.</span></span>  
  
    3.  <span data-ttu-id="c11b4-111">Ziehen Sie die Vorlage in ein Code-Editor-Fenster, um dem Inhalt des Editor-Fensters den Vorlagencode hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c11b4-111">Drag the template into a code editor window to add the template code to the contents of the editor window.</span></span>  
  
 <span data-ttu-id="c11b4-112">Sobald die Vorlage geöffnet ist, können Sie im Dialogfeld **Vorlagenparameter ersetzen** die Parameter in der Vorlage durch Ihre eigenen Werte ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c11b4-112">After the template is open, use the **Replace Template Parameters** dialog box to replace the template parameters with your values.</span></span>  
  
 <span data-ttu-id="c11b4-113">Wird durch das Öffnen einer Vorlage ein neues Editor-Fenster geöffnet, erfolgt dies mit den Anmeldeinformationen der aktuellen aktiven Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c11b4-113">If opening a template launches a new editor window, the window will open with the credentials of the current active connection.</span></span> <span data-ttu-id="c11b4-114">Ist beispielsweise beim Öffnen einer CREATE DATABASE-Vorlage eine [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Instanz im Objekt-Explorer fokussiert, wird ein neues Editor-Fenster mit einer Verbindung zu dieser Instanz geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c11b4-114">For example, if you are focused on an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in Object Explorer when you open the CREATE DATABASE template, a new editor window will be opened using a connection to that instance.</span></span> <span data-ttu-id="c11b4-115">Ist keine aktive Verbindung vorhanden, gibt [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ein Anmeldedialogfeld zurück.</span><span class="sxs-lookup"><span data-stu-id="c11b4-115">If there is no active connection, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] will present a login dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11b4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c11b4-116">See Also</span></span>  
 <span data-ttu-id="c11b4-117">[Vorlagen-Explorer](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="c11b4-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="c11b4-118">Vorlagenparameter ersetzen</span><span class="sxs-lookup"><span data-stu-id="c11b4-118">Replace Template Parameters</span></span>](replace-template-parameters.md)  
  
  
