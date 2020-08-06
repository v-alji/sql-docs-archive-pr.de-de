---
title: Quellen-Editor für SAP BW (Seite „Erweitert“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c78d40555a30031bf39abda18048fda9c648d01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724026"
---
# <a name="sap-bw-source-editor-advanced-page"></a><span data-ttu-id="7951c-102">Quellen-Editor für SAP BW (Seite Erweitert)</span><span class="sxs-lookup"><span data-stu-id="7951c-102">SAP BW Source Editor (Advanced Page)</span></span>
  <span data-ttu-id="7951c-103">Verwenden Sie die Seite **Erweitert** des **Quellen-Editors für SAP BW** , um die Zeichenkonvertierungsregel und den Timeoutzeitraum anzugeben sowie um den Status einer bestimmten Anforderungs-ID zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7951c-103">Use the **Advanced** page of the **SAP BW Source Editor** to specify the string conversion rule and the time-out period, and also to reset the status of a particular Request ID.</span></span>  
  
 <span data-ttu-id="7951c-104">Weitere Informationen zur SAP BW-Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="7951c-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7951c-105">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="7951c-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="7951c-106">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="7951c-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7951c-107">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="7951c-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="7951c-108">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="7951c-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="7951c-109">**So öffnen Sie die Seite "Verbindungs-Manager"**</span><span class="sxs-lookup"><span data-stu-id="7951c-109">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="7951c-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7951c-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="7951c-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="7951c-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="7951c-112">Klicken Sie im **Quellen-Editor für SAP BW**auf **Erweitert** , um die Seite **Erweitert** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7951c-112">In the **SAP BW Source Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7951c-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7951c-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7951c-114">Wenn Sie nicht alle Werte kennen, die zur Konfiguration der Quelle erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="7951c-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="7951c-115">**Zeichenfolgenkonvertierung**</span><span class="sxs-lookup"><span data-stu-id="7951c-115">**String Conversion**</span></span>  
 <span data-ttu-id="7951c-116">Geben Sie die Regel an, die für die Zeichenfolgenkonvertierung angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7951c-116">Specify the rule to apply for string conversion.</span></span>  
  
|<span data-ttu-id="7951c-117">Option</span><span class="sxs-lookup"><span data-stu-id="7951c-117">Option</span></span>|<span data-ttu-id="7951c-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7951c-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7951c-119">**Automatische Zeichenfolgenkonvertierung**</span><span class="sxs-lookup"><span data-stu-id="7951c-119">**Automatic string conversion**</span></span>|<span data-ttu-id="7951c-120">Konvertieren Sie alle Zeichenfolgen in `nvarchar`, wenn das SAP NetWeaver BW-System ein Unicode-System ist.</span><span class="sxs-lookup"><span data-stu-id="7951c-120">Convert all strings to `nvarchar` when the SAP Netweaver BW system is a Unicode system.</span></span> <span data-ttu-id="7951c-121">Konvertieren Sie andernfalls alle Zeichenfolgen in `varchar`.</span><span class="sxs-lookup"><span data-stu-id="7951c-121">Otherwise, convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="7951c-122">**Zeichenfolgen in varchar konvertieren**</span><span class="sxs-lookup"><span data-stu-id="7951c-122">**Convert strings to varchar**</span></span>|<span data-ttu-id="7951c-123">Konvertieren Sie alle Zeichenfolgen in `varchar`.</span><span class="sxs-lookup"><span data-stu-id="7951c-123">Convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="7951c-124">**Zeichenfolgen in nvarchar konvertieren**</span><span class="sxs-lookup"><span data-stu-id="7951c-124">**Convert strings to nvarchar**</span></span>|<span data-ttu-id="7951c-125">Konvertieren Sie alle Zeichenfolgen in `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="7951c-125">Convert all strings to `nvarchar`.</span></span>|  
  
 <span data-ttu-id="7951c-126">**Timeout (Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="7951c-126">**Timeout (seconds)**</span></span>  
 <span data-ttu-id="7951c-127">Geben Sie die maximale Anzahl von Sekunden an, die die Quelle warten soll.</span><span class="sxs-lookup"><span data-stu-id="7951c-127">Specify the maximum number of seconds that the source should wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7951c-128">Diese Option ist nur gültig, wenn Sie auf der Seite **Verbindungs-Manager** des Editors **W – Benachrichtigung abwarten** als Wert für den **Ausführungsmodus** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="7951c-128">This option is only valid if you have selected **W - Wait for Notify** as the value of **Execution Mode** on the **Connection Manager** page of the editor.</span></span> <span data-ttu-id="7951c-129">Informationen hierzu finden Sie unter [Quellen-Editor für SAP BW &#40;Seite Verbindungs-Manager&#41;](sap-bw-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="7951c-129">For more information, see [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).</span></span>  
  
 <span data-ttu-id="7951c-130">**Anfrage-ID**</span><span class="sxs-lookup"><span data-stu-id="7951c-130">**Request ID**</span></span>  
 <span data-ttu-id="7951c-131">Geben Sie die Anforderungs-ID an, deren Status Sie auf „G – Grün“ zurücksetzen möchten, wenn Sie auf **Zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="7951c-131">Specify the Request ID whose status you want to reset to "G - Green" when you click **Reset**.</span></span>  
  
 <span data-ttu-id="7951c-132">**Zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="7951c-132">**Reset**</span></span>  
 <span data-ttu-id="7951c-133">Mit dieser Option können Sie den Status der angegebenen Anforderungs-ID auf G - Grün zurücksetzen, nachdem Ihre Bestätigung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="7951c-133">Lets you reset the status of the specified Request ID to "G - Green", after prompting you for confirmation.</span></span> <span data-ttu-id="7951c-134">Dies kann hilfreich sein, wenn ein Problem aufgetreten ist und das SAP NetWeaver BW-System die Anforderung mit einem gelben oder roten Status gekennzeichnet hat.</span><span class="sxs-lookup"><span data-stu-id="7951c-134">This can be useful when a problem has occurred, and the SAP Netweaver BW system has flagged the request with a yellow or red status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7951c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7951c-135">See Also</span></span>  
 <span data-ttu-id="7951c-136">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="7951c-136">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="7951c-137">[Quellen-Editor für SAP BW &#40;Seite Spalten&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="7951c-137">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="7951c-138">[Quellen-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="7951c-138">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="7951c-139">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="7951c-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
