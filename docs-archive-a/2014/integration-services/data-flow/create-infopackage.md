---
title: InfoPackage erstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9cd4a848-409f-4681-a390-1c49a2aadbd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95f6ddce4e97c0c21d9f77c432231d414770dbce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695929"
---
# <a name="create-infopackage"></a><span data-ttu-id="1f950-102">InfoPackage erstellen</span><span class="sxs-lookup"><span data-stu-id="1f950-102">Create InfoPackage</span></span>
  <span data-ttu-id="1f950-103">Verwenden Sie das Dialogfeld **InfoPackage erstellen** , um ein neues InfoPackage im SAP NetWeaver BW-System zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f950-103">Use the **Create InfoPackage** dialog box to create a new InfoPackage in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="1f950-104">Sie können das Dialogfeld **InfoPackage erstellen** auf der Seite **Verbindungs-Manager** im **Ziel-Editor für SAP BW**öffnen.</span><span class="sxs-lookup"><span data-stu-id="1f950-104">You can open the **Create InfoPackage** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="1f950-105">Weitere Informationen zum SAP BW-Ziel finden Sie unter [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="1f950-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1f950-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="1f950-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1f950-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="1f950-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="1f950-108">**So öffnen Sie das Dialogfeld "InfoPackage erstellen"**</span><span class="sxs-lookup"><span data-stu-id="1f950-108">**To open the Create InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="1f950-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1f950-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="1f950-110">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="1f950-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="1f950-111">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1f950-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="1f950-112">Wählen Sie auf der Seite **Verbindungs-Manager** im Gruppenfeld **SAP BW-Objekte erstellen** die Option **InfoPackage**aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1f950-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoPackage**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f950-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="1f950-113">Options</span></span>  
 <span data-ttu-id="1f950-114">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="1f950-114">**InfoSource**</span></span>  
 <span data-ttu-id="1f950-115">Geben Sie den Namen der InfoSource ein, auf der das neue InfoPackage basieren soll.</span><span class="sxs-lookup"><span data-stu-id="1f950-115">Enter the name of the InfoSource on which the new InfoPackage should be based.</span></span>  
  
 <span data-ttu-id="1f950-116">**Kurzbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="1f950-116">**Short description**</span></span>  
 <span data-ttu-id="1f950-117">Geben Sie eine Beschreibung für das neue InfoPackage ein.</span><span class="sxs-lookup"><span data-stu-id="1f950-117">Enter a description for the new InfoPackage.</span></span>  
  
 <span data-ttu-id="1f950-118">**Quellsystem**</span><span class="sxs-lookup"><span data-stu-id="1f950-118">**Source system**</span></span>  
 <span data-ttu-id="1f950-119">Wählen Sie das Quellsystem aus, dem das neue InfoPackage zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f950-119">Select the source system with which the new InfoPackage should be associated.</span></span>  
  
 <span data-ttu-id="1f950-120">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="1f950-120">**Attributes**</span></span>  
 <span data-ttu-id="1f950-121">Gibt an, dass vom InfoPackage Attributdaten geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1f950-121">Indicates that the InfoPackage will load attribute data.</span></span>  
  
 <span data-ttu-id="1f950-122">**Texte**</span><span class="sxs-lookup"><span data-stu-id="1f950-122">**Texts**</span></span>  
 <span data-ttu-id="1f950-123">Gibt an, dass vom InfoPackage Textdaten geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1f950-123">Indicates that the InfoPackage will load text data.</span></span>  
  
 <span data-ttu-id="1f950-124">**Transaktion**</span><span class="sxs-lookup"><span data-stu-id="1f950-124">**Transaction**</span></span>  
 <span data-ttu-id="1f950-125">Gibt an, dass vom InfoPackage Transaktionsdaten geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1f950-125">Indicates that the InfoPackage will load transaction data.</span></span>  
  
 <span data-ttu-id="1f950-126">**Speichern und aktivieren**</span><span class="sxs-lookup"><span data-stu-id="1f950-126">**Save & Activate**</span></span>  
 <span data-ttu-id="1f950-127">Speichern und aktivieren Sie das neue InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="1f950-127">Save and activate the new InfoPackage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f950-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f950-128">See Also</span></span>  
 [<span data-ttu-id="1f950-129">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="1f950-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
