---
title: HOST_NAME-Werte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609086"
---
# <a name="host_name-values"></a><span data-ttu-id="776b0-102">HOST_NAME-Werte</span><span class="sxs-lookup"><span data-stu-id="776b0-102">HOST_NAME Values</span></span>
  <span data-ttu-id="776b0-103">In Mergeveröffentlichungen mit parametrisierten Filtern werden zum Filtern der Daten die SUSER_SNAME()-Funktion und/oder die HOST_NAME()-Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="776b0-103">Merge publications with parameterized filters use the SUSER_SNAME() function and/or the HOST_NAME() function to filter data.</span></span> <span data-ttu-id="776b0-104">Die Funktion wird im Assistenten für neue Veröffentlichung oder im Dialogfeld **Veröffentlichungseigenschaften** angegeben.</span><span class="sxs-lookup"><span data-stu-id="776b0-104">The function is specified in the New Publication Wizard or the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="776b0-105">Standardmäßig wird durch die HOST_NAME()-Funktion der Name des Computers zurückgegeben, der die Verbindung mit dem Verleger herstellt.</span><span class="sxs-lookup"><span data-stu-id="776b0-105">By default, the HOST_NAME() function returns the name of the computer connecting to the Publisher.</span></span> <span data-ttu-id="776b0-106">Wenn Sie parametrisierte Filter verwenden, wird dieser Wert normalerweise überschrieben, indem Sie auf dieser Seite des Assistenten einen Wert bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="776b0-106">When using parameterized filters, it is common to override this value by supplying a value on this page of the wizard.</span></span> <span data-ttu-id="776b0-107">Daraufhin wird durch die HOST_NAME()-Funktion nicht der Name des Computers, sondern der von Ihnen angegebene Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="776b0-107">The HOST_NAME() function then returns the value you specify rather than the name of the computer.</span></span> <span data-ttu-id="776b0-108">Weitere Informationen finden Sie im Abschnitt „Überschreiben des HOST_NAME()-Wertes“ in [Parametrisierte Zeilenfilter](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="776b0-108">For more information, see the "Overriding the HOST_NAME() Value" section of [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="776b0-109">Wenn Sie HOST_NAME() überschreiben, wird für sämtliche Aufrufe der HOST_NAME()-Funktion der von Ihnen angegebene Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="776b0-109">If you override HOST_NAME(), all calls to the HOST_NAME() function will return the value you specify.</span></span> <span data-ttu-id="776b0-110">Stellen Sie sicher, dass keine andere Anwendung darauf angewiesen ist, dass HOST_NAME() den Computernamen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="776b0-110">Ensure that other applications are not depending on HOST_NAME() returning the computer name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="776b0-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="776b0-111">Options</span></span>  
 <span data-ttu-id="776b0-112">**Abonnementeigenschaften**</span><span class="sxs-lookup"><span data-stu-id="776b0-112">**Subscription properties**</span></span>  
 <span data-ttu-id="776b0-113">Geben Sie in der **HOST_NAME Value** -Spalte für jeden Abonnenten einen Wert ein, oder übernehmen Sie den als Standardwert angegebenen Namen des Abonnentencomputers.</span><span class="sxs-lookup"><span data-stu-id="776b0-113">Enter a value for each Subscriber in the **HOST_NAME Value** column or accept the default, which is the name of the Subscriber computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776b0-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="776b0-114">See Also</span></span>  
 <span data-ttu-id="776b0-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="776b0-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="776b0-116">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="776b0-116">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="776b0-117">[Anzeigen und Ändern der Eigenschaften von Pullabonnements](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="776b0-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="776b0-118">[Anzeigen und Ändern der Eigenschaften von Pushabonnements](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="776b0-118">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="776b0-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="776b0-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span></span>  
 [<span data-ttu-id="776b0-120">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="776b0-120">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
