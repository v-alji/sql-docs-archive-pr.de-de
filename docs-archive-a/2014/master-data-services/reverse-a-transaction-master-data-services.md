---
title: Umkehren einer Transaktion (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fb5b1b0932b65b1d6f8fe7b1bc842836e21aaca6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698343"
---
# <a name="reverse-a-transaction-master-data-services"></a><span data-ttu-id="51655-102">Umkehren einer Transaktion (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="51655-102">Reverse a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="51655-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie eine Transaktion umkehren, wenn eine Aktion rückgängig gemacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="51655-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], administrators can reverse a transaction when an action needs to be undone.</span></span> <span data-ttu-id="51655-104">Beispiele für Transaktionen sind Attributwertänderungen, Hierarchieverschiebungen oder Elementlöschungen.</span><span class="sxs-lookup"><span data-stu-id="51655-104">Examples of transactions are attribute value changes, hierarchy moves, or member deletions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51655-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="51655-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="51655-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Versionsverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="51655-106">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="51655-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="51655-107">You must be a model administrator.</span></span> <span data-ttu-id="51655-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="51655-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reverse-a-transaction"></a><span data-ttu-id="51655-109">So kehren Sie eine Transaktion um</span><span class="sxs-lookup"><span data-stu-id="51655-109">To reverse a transaction</span></span>  
  
1.  <span data-ttu-id="51655-110">Klicken Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="51655-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="51655-111">Klicken Sie in der Menüleiste auf **Transaktionen**.</span><span class="sxs-lookup"><span data-stu-id="51655-111">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="51655-112">Wählen Sie auf der Seite **Transaktionen** in der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="51655-112">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="51655-113">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="51655-113">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="51655-114">Klicken Sie auf die Zeile im Raster für die Transaktion, die Sie umkehren möchten.</span><span class="sxs-lookup"><span data-stu-id="51655-114">Click the row in the grid for the transaction you want to reverse.</span></span>  
  
6.  <span data-ttu-id="51655-115">Klicken Sie auf **Transaktion umkehren**.</span><span class="sxs-lookup"><span data-stu-id="51655-115">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="51655-116">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="51655-116">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="51655-117">Dem Raster wird eine weitere Transaktion hinzugefügt, um die umgekehrte Transaktion aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="51655-117">Another transaction is added to the grid to record the reversed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51655-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51655-118">See Also</span></span>  
 <span data-ttu-id="51655-119">[Transaktionen &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51655-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span></span>  
 [<span data-ttu-id="51655-120">Reaktivieren eines Elements oder einer Sammlung &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="51655-120">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
  
  
