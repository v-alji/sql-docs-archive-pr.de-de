---
title: Vorschau | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a795338122c1e7a37a23fdb6af6153f74b927e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615467"
---
# <a name="preview"></a><span data-ttu-id="0eb52-102">Vorschau</span><span class="sxs-lookup"><span data-stu-id="0eb52-102">Preview</span></span>
  <span data-ttu-id="0eb52-103">Verwenden Sie das Dialogfeld **Vorschau** , um die von der SAP BW-Quelle extrahierten Daten in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0eb52-103">Use the **Preview** dialog box to preview the data that the SAP BW source will extract.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0eb52-104">Die Daten werden tatsächlich mithilfe der Option **Vorschau** extrahiert, die im **Quellen-Editor für SAP BW** auf der Seite **Verbindungs-Manager**verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0eb52-104">The **Preview** option, that is available on the **Connection Manager** page of the **SAP BW Source Editor**, actually extracts data.</span></span> <span data-ttu-id="0eb52-105">Wenn Sie SAP NetWeaver BW so konfiguriert haben, dass nur Daten extrahiert werden, die sich seit der letzten Extrahierung geändert haben, schließen Sie die in der Vorschau angezeigten Daten durch Auswahl von **Vorschau** aus der nachfolgenden Extrahierung aus.</span><span class="sxs-lookup"><span data-stu-id="0eb52-105">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="0eb52-106">Weitere Informationen zur SAP BW-Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="0eb52-106">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0eb52-107">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="0eb52-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="0eb52-108">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="0eb52-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0eb52-109">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="0eb52-109">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="0eb52-110">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="0eb52-110">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="0eb52-111">**So öffnen Sie das Dialogfeld "Vorschau"**</span><span class="sxs-lookup"><span data-stu-id="0eb52-111">**To open the Preview dialog box**</span></span>  
  
1.  <span data-ttu-id="0eb52-112">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0eb52-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="0eb52-113">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="0eb52-113">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="0eb52-114">Klicken Sie im **Quellen-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0eb52-114">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="0eb52-115">Konfigurieren Sie die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="0eb52-115">Configure the SAP BW source.</span></span>  
  
5.  <span data-ttu-id="0eb52-116">Nachdem Sie die SAP BW-Quelle konfiguriert haben, klicken Sie auf der Seite **Verbindungs-Manager** auf **Vorschau** , um die Daten im Dialogfeld **Vorschau** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0eb52-116">After you configure the SAP BW source, on the **Connection Manager** page, click **Preview** to preview the data in the **Preview** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0eb52-117">Durch Klicken auf die Schaltfläche **Vorschau** öffnen Sie auch das Dialogfeld **Anforderungsprotokoll** .</span><span class="sxs-lookup"><span data-stu-id="0eb52-117">Clicking **Preview** also opens the **Request Log** dialog box.</span></span> <span data-ttu-id="0eb52-118">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="0eb52-118">For more information about this dialog box, see [Request Log](request-log.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0eb52-119">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0eb52-119">Options</span></span>  
 <span data-ttu-id="0eb52-120">Im Dialogfeld **Vorschau** werden die Zeilen angezeigt, die vom SAP NetWeaver BW-System angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0eb52-120">The **Preview** dialog box displays the rows that are requested from the SAP Netweaver BW system.</span></span> <span data-ttu-id="0eb52-121">Die angezeigten Spalten entsprechen den in den Quelldaten definierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="0eb52-121">The columns that are displayed are the columns that are defined in the source data.</span></span>  
  
 <span data-ttu-id="0eb52-122">Das Dialogfeld verfügt über keinen weiteren Optionen.</span><span class="sxs-lookup"><span data-stu-id="0eb52-122">There are no other options in this dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb52-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0eb52-123">See Also</span></span>  
 <span data-ttu-id="0eb52-124">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="0eb52-124">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="0eb52-125">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="0eb52-125">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
