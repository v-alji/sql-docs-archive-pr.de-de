---
title: RFC-Ziel suchen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db9404d8-4c42-45e5-a100-c7a84b056109
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 397298fce16509e667aa4baccaee62c6ff0f5cca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724830"
---
# <a name="look-up-rfc-destination"></a><span data-ttu-id="346bc-102">RFC-Ziel suchen</span><span class="sxs-lookup"><span data-stu-id="346bc-102">Look Up RFC Destination</span></span>
  <span data-ttu-id="346bc-103">Verwenden Sie das Dialogfeld **RFC-Ziel suchen** , um ein RFC-Ziel zu suchen, das im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="346bc-103">Use the **Look Up RFC Destination** dialog box to look up an RFC destination that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="346bc-104">Wenn die Liste der verfügbaren RFC-Ziele angezeigt wird, wählen Sie das gewünschte Ziel aus. Daraufhin werden die zugehörigen Optionen von der Komponente mit den erforderlichen Werten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="346bc-104">When the list of available RFC destinations appears, select the destination that you want, and the component will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="346bc-105">Sowohl die SAP BW-Quelle als auch das SAP BW-Ziel verwenden das Dialogfeld **RFC-Ziel suchen** .</span><span class="sxs-lookup"><span data-stu-id="346bc-105">Both the SAP BW source and the SAP BW destination use the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="346bc-106">Weitere Informationen zu den Komponenten von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md) und [SAP BW-Ziel](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="346bc-106">For more information about these components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md) and [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="346bc-107">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="346bc-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="346bc-108">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="346bc-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="346bc-109">**So öffnen Sie das Dialogfeld "RFC-Ziel suchen"**</span><span class="sxs-lookup"><span data-stu-id="346bc-109">**To open the Look Up RFC Destination dialog box**</span></span>  
  
1.  <span data-ttu-id="346bc-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, das die SAP BW-Quelle oder das SAP BW-Ziel enthält.</span><span class="sxs-lookup"><span data-stu-id="346bc-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source or destination.</span></span>  
  
2.  <span data-ttu-id="346bc-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle oder das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="346bc-111">On the **Data Flow** tab, double-click the SAP BW source or destination.</span></span>  
  
3.  <span data-ttu-id="346bc-112">Klicken Sie im **Quellen-Editor für SAP BW** oder im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="346bc-112">In the **SAP BW Source Editor** or the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="346bc-113">Klicken Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **RFC-Ziel** auf **Suchen** , um das Dialogfeld **RFC-Ziel suchen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="346bc-113">On the **Connection Manager** page, in the **RFC Destination** group box, click **Look up** to display the **Look Up RFC Destination** dialog box.</span></span>  
  
     <span data-ttu-id="346bc-114">Das Gruppenfeld **RFC-Ziel**wird im **Quellen-Editor für SAP BW** nur angezeigt, wenn der Wert für **Ausführungsmodus** **P - Prozesskette auslösen** oder **W - Benachrichtigung abwarten**lautet.</span><span class="sxs-lookup"><span data-stu-id="346bc-114">In the **SAP BW Source Editor**, the **RFC Destination** group box appears only if the value for **Execution mode** is **P - Trigger process chain** or **W - Wait for notify**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="346bc-115">Tastatur</span><span class="sxs-lookup"><span data-stu-id="346bc-115">Options</span></span>  
 <span data-ttu-id="346bc-116">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="346bc-116">**Destination**</span></span>  
 <span data-ttu-id="346bc-117">Zeigt den Namen des RFC-Ziels an, das im SAP NetWeaver BW-System definiert ist.</span><span class="sxs-lookup"><span data-stu-id="346bc-117">View the name of the RFC destination that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="346bc-118">**Gatewayhost**</span><span class="sxs-lookup"><span data-stu-id="346bc-118">**Gateway Host**</span></span>  
 <span data-ttu-id="346bc-119">Zeigt den Servernamen oder die IP-Adresse des Gatewayhosts an.</span><span class="sxs-lookup"><span data-stu-id="346bc-119">View the server name or IP address of the gateway host.</span></span> <span data-ttu-id="346bc-120">Normalerweise ist der Name oder die IP-Adresse identisch mit dem SAP-Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="346bc-120">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="346bc-121">**Gatewaydienst**</span><span class="sxs-lookup"><span data-stu-id="346bc-121">**Gateway Service**</span></span>  
 <span data-ttu-id="346bc-122">Zeigt den Namen des Gatewaydiensts im Format `sapgwNN` an, wobei `NN` der Systemnummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="346bc-122">View the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="346bc-123">**Programm-ID**</span><span class="sxs-lookup"><span data-stu-id="346bc-123">**Program ID**</span></span>  
 <span data-ttu-id="346bc-124">Zeigt die Programm-ID an, die dem RFC-Ziel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="346bc-124">View the Program ID that is associated with the RFC destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346bc-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="346bc-125">See Also</span></span>  
 <span data-ttu-id="346bc-126">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="346bc-126">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="346bc-127">[Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="346bc-127">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="346bc-128">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="346bc-128">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
