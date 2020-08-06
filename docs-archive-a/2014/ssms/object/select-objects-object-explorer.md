---
title: Objekte auswählen (Objekt-Explorer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.selectobjects.f1
ms.assetid: 692477fe-dd7c-403d-acd2-bb108b6077f1
author: stevestein
ms.author: sstein
ms.openlocfilehash: ceec604d9fe07b339af11ed69226d41a7f616678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695218"
---
# <a name="select-objects-object-explorer"></a><span data-ttu-id="06e95-102">Objekte auswählen (Objekt-Explorer)</span><span class="sxs-lookup"><span data-stu-id="06e95-102">Select Objects (Object Explorer)</span></span>
  <span data-ttu-id="06e95-103">Verwenden Sie das Dialogfeld **Objekte auswählen** , um der Liste in einem anderen Dialogfeld ein Objekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="06e95-103">Use the **Select Objects** dialog box to add an object to a list in another dialog box.</span></span> <span data-ttu-id="06e95-104">Der Titel des Dialogfelds und die darin verfügbaren Optionen hängen davon ab, wie es geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="06e95-104">The dialog box title and the options available in the dialog box depend upon how it was opened.</span></span> <span data-ttu-id="06e95-105">Es werden nur verfügbare Optionen angezeigt. Wenn Sie z. B. einen Besitzer für ein neues Objekt auswählen, sind nur Benutzernamen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06e95-105">Only available options appear; for instance, only logins are available when you are selecting an owner for a new object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06e95-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="06e95-106">Options</span></span>  
 <span data-ttu-id="06e95-107">**Wählen Sie Objekttypen aus**</span><span class="sxs-lookup"><span data-stu-id="06e95-107">**Select these object types**</span></span>  
 <span data-ttu-id="06e95-108">Zeigt eine Liste der Typen an, zu denen die auszuwählenden Objekte gehören.</span><span class="sxs-lookup"><span data-stu-id="06e95-108">Displays a list of the types of which the objects to be selected belong.</span></span> <span data-ttu-id="06e95-109">Zu diesen Typen gehören auch Prinzipale und sicherungsfähige Typen auf [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ebene und Datenbankebene.</span><span class="sxs-lookup"><span data-stu-id="06e95-109">The types include [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] level and database level principals and securables.</span></span> <span data-ttu-id="06e95-110">Dieses Feld wird anhand der Auswahl im Dialogfeld **Objekttypen auswählen** ausgefüllt, auf das über die Schaltfläche **Objekttypen** zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="06e95-110">This box is populated from the selections made from the **Select Object Types** dialog box, accessed from the **Objects Type** button.</span></span>  
  
 <span data-ttu-id="06e95-111">**Geben Sie die Namen der auszuwählenden Objekte ein**</span><span class="sxs-lookup"><span data-stu-id="06e95-111">**Enter the object names to select**</span></span>  
 <span data-ttu-id="06e95-112">Geben Sie eine durch Semikolons getrennte Liste der auszuwählenden Objekte ein.</span><span class="sxs-lookup"><span data-stu-id="06e95-112">Enter a semicolon-separated list of names of the objects to be selected.</span></span> <span data-ttu-id="06e95-113">Auszuwählende Objekte müssen zu einem Typ gehören, der im Feld **Wählen Sie Objekttypen aus** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="06e95-113">Objects to be selected must be of a type listed in the **Select these object types** box.</span></span> <span data-ttu-id="06e95-114">Die Objekte können aus einer Liste ausgewählt werden, auf die per Mausklick auf die Schaltfläche **Durchsuchen** zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="06e95-114">Objects can be selected from a list accessed by clicking the **Browse** button.</span></span>  
  
 <span data-ttu-id="06e95-115">**Objekttypen**</span><span class="sxs-lookup"><span data-stu-id="06e95-115">**Object Types**</span></span>  
 <span data-ttu-id="06e95-116">Zeigt eine Liste von Objekttypen an.</span><span class="sxs-lookup"><span data-stu-id="06e95-116">Displays a list of object types.</span></span> <span data-ttu-id="06e95-117">Wählen Sie einen oder mehrere Objekttypen aus, indem Sie die entsprechenden Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06e95-117">Select one or more by selecting the check box corresponding to the type.</span></span>  
  
 <span data-ttu-id="06e95-118">**Namen überprüfen**</span><span class="sxs-lookup"><span data-stu-id="06e95-118">**Check Names**</span></span>  
 <span data-ttu-id="06e95-119">Überprüft die Objektnamen im Feld **Geben Sie die Namen der auszuwählenden Objekte ein** .</span><span class="sxs-lookup"><span data-stu-id="06e95-119">Validates the object names in the **Enter the object names to select** box.</span></span> <span data-ttu-id="06e95-120">Wenn in der Liste ein ungültiger Objektname vorkommt, wird das Dialogfeld **Name nicht gefunden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06e95-120">If an object name that is not valid is listed, the **Name not Found** dialog box is presented.</span></span> <span data-ttu-id="06e95-121">Mithilfe dieses Dialogfelds kann der Name korrigiert oder aus der Liste der auszuwählenden Objekte entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="06e95-121">With this dialog box, the name can be corrected or removed from the list of objects to select.</span></span>  
  
 <span data-ttu-id="06e95-122">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="06e95-122">**Browse**</span></span>  
 <span data-ttu-id="06e95-123">Zeigt das Dialogfeld **Nach Objekten suchen** an.</span><span class="sxs-lookup"><span data-stu-id="06e95-123">Presents the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="06e95-124">Es enthält eine Liste der Objekte, deren Typen im Feld **Wählen Sie Objekttypen aus** aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="06e95-124">This contains a list of objects of the types listed in the **Select These Object Types** box.</span></span> <span data-ttu-id="06e95-125">Wählen Sie aus dieser Liste Objekte aus, indem Sie die entsprechenden Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06e95-125">Select objects from this list by selecting the corresponding check boxes.</span></span>  
  
  
