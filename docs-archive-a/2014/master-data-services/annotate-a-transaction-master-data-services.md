---
title: Hinzufügen einer Anmerkung zu einer Transaktion (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c384f4241d0ddcd78fd8942fe28da8c0b5b1e77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718388"
---
# <a name="annotate-a-transaction-master-data-services"></a><span data-ttu-id="b0815-102">Hinzufügen einer Anmerkung zu einer Transaktion (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b0815-102">Annotate a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="b0815-103">Versehen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Transaktion mit einer Anmerkung, wenn Sie unterstützende Details zur Transaktion zu historischen Zwecken bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0815-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotate a transaction when you want to provide supporting details about the transaction for historical purposes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0815-104">Anmerkungen können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b0815-104">You cannot delete annotations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0815-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b0815-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="b0815-106">Um von Ihnen erstellte Transaktionen mit einer Anmerkung versehen zu können, müssen Sie über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** und mindestens über die Berechtigung **Aktualisieren** für das Modellobjekt verfügen, das Sie mit einer Anmerkung versehen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0815-106">To annotate transactions that you created, you must have permission to access the **Explorer** functional area, and have a minimum of **Update** permission to the model object you want to annotate.</span></span>  
  
-   <span data-ttu-id="b0815-107">Um Transaktionen für alle Benutzer mit einer Anmerkung zu versehen, müssen Sie über die Berechtigung für den Zugriff auf den Funktionsbereich **Versionsverwaltung** verfügen und Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="b0815-107">To annotate transactions for all users, you must have permission to access the **Version Management** functional area and be a model administrator.</span></span> <span data-ttu-id="b0815-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b0815-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-annotate-a-transaction-in-explorer"></a><span data-ttu-id="b0815-109">So versehen Sie im Explorer eine Transaktion mit einer Anmerkung</span><span class="sxs-lookup"><span data-stu-id="b0815-109">To annotate a transaction in Explorer</span></span>  
  
1.  <span data-ttu-id="b0815-110">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="b0815-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="b0815-111">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="b0815-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="b0815-112">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b0815-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="b0815-113">Zeigen Sie in der Menüleiste auf **Entitäten** und klicken Sie auf die Entität mit dem Element mit einer Transaktion, die Sie mit einer Anmerkung versehen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0815-113">From the menu bar, point to **Entities** and click the entity that contains the member with a transaction you want to annotate.</span></span>  
  
5.  <span data-ttu-id="b0815-114">Klicken Sie im Raster auf die Zeile des Elements.</span><span class="sxs-lookup"><span data-stu-id="b0815-114">In the grid, click the row of the member.</span></span>  
  
6.  <span data-ttu-id="b0815-115">Klicken Sie auf **Transaktionen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b0815-115">Click **View Transactions**.</span></span>  
  
7.  <span data-ttu-id="b0815-116">Klicken Sie im Dialogfeld **Transaktionen anzeigen** auf die Transaktion, die Sie mit einer Anmerkung versehen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0815-116">In the **View Transactions** dialog box, click the transaction you want to annotate.</span></span>  
  
8.  <span data-ttu-id="b0815-117">Geben Sie die Anmerkung im Feld am unteren Rand des Dialogfelds ein.</span><span class="sxs-lookup"><span data-stu-id="b0815-117">In the box at the bottom of the dialog box, type your annotation.</span></span>  
  
9. <span data-ttu-id="b0815-118">Klicken Sie auf **Anmerkung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b0815-118">Click **Add Annotation**.</span></span> <span data-ttu-id="b0815-119">Die Anmerkung wird im Bereich **Anmerkungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0815-119">The annotation is displayed in the **Annotations** pane.</span></span>  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a><span data-ttu-id="b0815-120">So versehen Sie in der Versionsverwaltung eine Transaktion mit einer Anmerkung (nur Administratoren)</span><span class="sxs-lookup"><span data-stu-id="b0815-120">To annotate a transaction in Version Management (administrators only)</span></span>  
  
1.  <span data-ttu-id="b0815-121">Klicken Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="b0815-121">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="b0815-122">Klicken Sie in der Menüleiste auf **Transaktionen**.</span><span class="sxs-lookup"><span data-stu-id="b0815-122">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="b0815-123">Klicken Sie im Bereich **Transaktionen** auf die Zeile im Raster für die Transaktion, die Sie mit einer Anmerkung versehen möchten.</span><span class="sxs-lookup"><span data-stu-id="b0815-123">In the **Transactions** pane, click the row in the grid for the transaction you want to annotate.</span></span>  
  
4.  <span data-ttu-id="b0815-124">Geben Sie die Anmerkung im Bereich **Transaktionsanmerkungen** im Feld **Anmerkung** ein.</span><span class="sxs-lookup"><span data-stu-id="b0815-124">In the **Transaction Annotations** pane, in the **Annotation** box, type your annotation.</span></span>  
  
5.  <span data-ttu-id="b0815-125">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0815-125">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0815-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0815-126">See Also</span></span>  
 <span data-ttu-id="b0815-127">[Anmerkungen &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b0815-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span></span>  
 [<span data-ttu-id="b0815-128">Transaktionen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b0815-128">Transactions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/transactions-master-data-services.md)  
  
  
