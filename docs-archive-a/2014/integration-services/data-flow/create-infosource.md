---
title: InfoSource erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7db233b-5464-43de-9d26-6dd24c7ac1b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9620d3170310322c79679e8298ffe465067ae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695913"
---
# <a name="create-infosource"></a><span data-ttu-id="5de2a-102">InfoSource erstellen</span><span class="sxs-lookup"><span data-stu-id="5de2a-102">Create InfoSource</span></span>
  <span data-ttu-id="5de2a-103">Verwenden Sie das Dialogfeld **InfoSource erstellen** , um eine neue InfoSource zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5de2a-103">Use the **Create InfoSource** dialog box to create a new InfoSource.</span></span> <span data-ttu-id="5de2a-104">Zum Erstellen der neuen InfoSource verwenden Sie entweder das Dialogfeld **InfoSource für Transaktionsdaten erstellen** oder **InfoSource für Masterdaten erstellen** .</span><span class="sxs-lookup"><span data-stu-id="5de2a-104">To create the new InfoSource, you use either the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span>  
  
 <span data-ttu-id="5de2a-105">Sie können das Dialogfeld **InfoSource erstellen** über die Seite **Verbindungs-Manager** im **Ziel-Editor für SAP BW**öffnen.</span><span class="sxs-lookup"><span data-stu-id="5de2a-105">You can open the **Create InfoSource** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="5de2a-106">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="5de2a-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5de2a-107">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="5de2a-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="5de2a-108">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5de2a-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="5de2a-109">**So öffnen Sie das Dialogfeld "InfoSource erstellen"**</span><span class="sxs-lookup"><span data-stu-id="5de2a-109">**To open the Create InfoSource dialog box**</span></span>  
  
1.  <span data-ttu-id="5de2a-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5de2a-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="5de2a-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="5de2a-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="5de2a-112">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5de2a-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="5de2a-113">Wählen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** die Option **InfoSource**aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5de2a-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5de2a-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5de2a-114">Options</span></span>  
 <span data-ttu-id="5de2a-115">**Transaktionsdaten**</span><span class="sxs-lookup"><span data-stu-id="5de2a-115">**Transaction data**</span></span>  
 <span data-ttu-id="5de2a-116">Erstellen Sie eine neue InfoSource für Transaktionsdaten.</span><span class="sxs-lookup"><span data-stu-id="5de2a-116">Create a new InfoSource for transaction data.</span></span>  
  
 <span data-ttu-id="5de2a-117">Wenn Sie diese Option auswählen, wird auch das Dialogfeld **InfoSource für Transaktionsdaten erstellen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5de2a-117">If you select this option, the **Create InfoSource for Transaction Data** dialog box opens.</span></span> <span data-ttu-id="5de2a-118">Sie verwenden das Dialogfeld **InfoSource für Transaktionsdaten erstellen** , um die neue InfoSource zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5de2a-118">You use the **Create InfoSource for Transaction Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="5de2a-119">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="5de2a-119">For more information about this dialog box, see [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span></span>  
  
 <span data-ttu-id="5de2a-120">**Masterdaten**</span><span class="sxs-lookup"><span data-stu-id="5de2a-120">**Master data**</span></span>  
 <span data-ttu-id="5de2a-121">Erstellen Sie eine neue InfoSource für Masterdaten.</span><span class="sxs-lookup"><span data-stu-id="5de2a-121">Create a new InfoSource for master data.</span></span>  
  
 <span data-ttu-id="5de2a-122">Wenn Sie diese Option auswählen, wird auch das Dialogfeld **InfoSource für Masterdaten erstellen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5de2a-122">If you select this option, the **Create InfoSource for Master Data** dialog box opens.</span></span> <span data-ttu-id="5de2a-123">Sie verwenden das Dialogfeld **InfoSource für Masterdaten erstellen** , um die neue InfoSource zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5de2a-123">You use the **Create InfoSource for Master Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="5de2a-124">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="5de2a-124">For more information about this dialog box, see [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de2a-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5de2a-125">See Also</span></span>  
 [<span data-ttu-id="5de2a-126">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="5de2a-126">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
