---
title: Herstellen einer Verbindung mit einem MDS-Repository (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698379"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a><span data-ttu-id="5078e-102">Herstellen einer Verbindung mit einem MDS-Repository (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="5078e-102">Connect to an MDS Repository (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5078e-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]müssen Sie eine Verbindung mit einem MDS-Repository herstellen, bevor Sie Daten laden oder veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="5078e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must connect to an MDS repository before you can load or publish data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5078e-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5078e-104">Prerequisites</span></span>  
 <span data-ttu-id="5078e-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="5078e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5078e-106">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="5078e-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-connect-to-an-mds-repository"></a><span data-ttu-id="5078e-107">So stellen Sie eine Verbindung mit einem MDS-Repository her</span><span class="sxs-lookup"><span data-stu-id="5078e-107">To connect to an MDS repository</span></span>  
  
1.  <span data-ttu-id="5078e-108">Klicken Sie in MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]auf die Registerkarte **Masterdaten** , klicken Sie in der Gruppe **Verbinden und Laden** auf den Pfeil unter der Schaltfläche **Verbinden** , und klicken Sie auf **Verbindungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="5078e-108">In the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], on the **Master Data** tab, in the **Connect and Load** group, click the arrow under the **Connect** button and click **Manage Connections**.</span></span>  
  
2.  <span data-ttu-id="5078e-109">Klicken Sie im Dialogfeld **Verbindungen verwalten** im Abschnitt **Neue Verbindung** auf **Neue Verbindung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5078e-109">On the **Manage Connections** dialog box, in the **New connection** section, click **Create a new connection**.</span></span>  
  
3.  <span data-ttu-id="5078e-110">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="5078e-110">Click **New**.</span></span>  
  
4.  <span data-ttu-id="5078e-111">Geben Sie im Dialogfeld **Neue Verbindung hinzufügen** im Feld **Beschreibung** eine Beschreibung für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="5078e-111">On the **Add New Connection** dialog box, in the **Description** field, type a description for your connection.</span></span> <span data-ttu-id="5078e-112">Diese Verbindung wird angezeigt, wenn Sie auf den Pfeil unter der Schaltfläche **Verbinden** auf der Symbolleiste klicken.</span><span class="sxs-lookup"><span data-stu-id="5078e-112">This connection will be displayed when you click the arrow under the **Connect** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="5078e-113">Geben Sie im Feld **MDS-Serveradresse** die URL der [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]-Webanwendung ein, z.B. http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="5078e-113">In the **MDS server address** box, type the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5078e-114">Stellen Sie sicher, dass Sie den Computernamen verwenden und nicht „localhost“.</span><span class="sxs-lookup"><span data-stu-id="5078e-114">Ensure that you use the computer name; do not use "localhost".</span></span>  
  
6.  <span data-ttu-id="5078e-115">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5078e-115">Click **OK**.</span></span> <span data-ttu-id="5078e-116">Der Name wird im Abschnitt **Vorhandene Verbindungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5078e-116">The name is displayed in the **Existing Connections** section.</span></span>  
  
7.  <span data-ttu-id="5078e-117">Klicken Sie optional auf **Testen** , um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="5078e-117">Optionally, click **Test** to test the connection.</span></span> <span data-ttu-id="5078e-118">Ein Bestätigungs- oder Fehlerdialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5078e-118">A confirmation or error dialog is displayed.</span></span> <span data-ttu-id="5078e-119">Klicken Sie auf **OK** , um es zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5078e-119">Click **OK** to close it.</span></span>  
  
8.  <span data-ttu-id="5078e-120">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="5078e-120">Click **Connect**.</span></span> <span data-ttu-id="5078e-121">Der Bereich **Master Data Services** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5078e-121">The **Master Data Services** pane is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5078e-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5078e-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="5078e-123">Laden von Daten aus MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="5078e-123">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)  
  
-   [<span data-ttu-id="5078e-124">Daten vor dem Laden &#40;MDS-Add-in für Excel Filtern&#41;</span><span class="sxs-lookup"><span data-stu-id="5078e-124">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="5078e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5078e-125">See Also</span></span>  
 [<span data-ttu-id="5078e-126">Verbindungen &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5078e-126">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
  
