---
title: Herstellen einer Verbindung mit einer Microsoft Excel-Datei (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610222"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a><span data-ttu-id="2eb76-102">Mit einer Microsoft Excel-Datei verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="2eb76-102">Connect to a Microsoft Excel File (SSAS)</span></span>
  <span data-ttu-id="2eb76-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie eine Verbindung mit einer Microsoft Excel-Datei herstellen, die auf dem lokalen Computer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2eb76-103">This page of the **Table Import Wizard** enables you to connect to a Microsoft Excel file stored on the local machine.</span></span> <span data-ttu-id="2eb76-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="2eb76-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="2eb76-105">Der entsprechende ACE-Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Microsoft Excel-Datei herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2eb76-105">To connect to a Microsoft Excel file, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="2eb76-106">Weitere Informationen finden Sie unter [Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="2eb76-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2eb76-107">Beim Auswählen einer Datei auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="2eb76-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="2eb76-108">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="2eb76-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2eb76-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="2eb76-109">UI element list</span></span>  
 <span data-ttu-id="2eb76-110">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="2eb76-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="2eb76-111">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="2eb76-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="2eb76-112">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="2eb76-112">This is a required field.</span></span>  
  
 <span data-ttu-id="2eb76-113">**Excel-Dateipfad**</span><span class="sxs-lookup"><span data-stu-id="2eb76-113">**Excel File Path**</span></span>  
 <span data-ttu-id="2eb76-114">Geben Sie den vollständigen Pfad der Excel-Datei an.</span><span class="sxs-lookup"><span data-stu-id="2eb76-114">Specify a full path for the Excel file.</span></span>  
  
 <span data-ttu-id="2eb76-115">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="2eb76-115">**Browse**</span></span>  
 <span data-ttu-id="2eb76-116">Navigieren Sie zu einem Speicherort, an dem eine Excel-Datei verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2eb76-116">Navigate to a location where an Excel file is available.</span></span>  
  
 <span data-ttu-id="2eb76-117">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="2eb76-117">**Advanced**</span></span>  
 <span data-ttu-id="2eb76-118">Legen Sie zusätzliche Verbindungs Eigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="2eb76-118">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="2eb76-119">**Erste Zeile als Spaltenüberschriften verwenden**</span><span class="sxs-lookup"><span data-stu-id="2eb76-119">**Use first row as column headers**</span></span>  
 <span data-ttu-id="2eb76-120">Geben Sie an, ob die erste Datenzeile für die Spaltenüberschriften der Zieltabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2eb76-120">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="2eb76-121">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="2eb76-121">**Test Connection**</span></span>  
 <span data-ttu-id="2eb76-122">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="2eb76-122">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="2eb76-123">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2eb76-123">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
