---
title: Herstellen einer Verbindung mit einer Microsoft Access-Datenbank (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb180a754b6bc276d588997117eb84fd1a5a873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610224"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a><span data-ttu-id="84834-102">Mit einer Microsoft Access-Datenbank verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="84834-102">Connect to a Microsoft Access Database (SSAS)</span></span>
  <span data-ttu-id="84834-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie Einstellungen angeben, um eine Verbindung mit einer Microsoft Access-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="84834-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft Access database.</span></span> <span data-ttu-id="84834-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="84834-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="84834-105">Der entsprechende ACE-Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Microsoft Access-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="84834-105">To connect to a Microsoft Access database, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="84834-106">Weitere Informationen finden Sie unter [Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="84834-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84834-107">Beim Auswählen einer Datei auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="84834-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="84834-108">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="84834-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="84834-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="84834-109">UI element list</span></span>  
 <span data-ttu-id="84834-110">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="84834-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="84834-111">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="84834-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="84834-112">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="84834-112">This is a required field.</span></span>  
  
 <span data-ttu-id="84834-113">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="84834-113">**Database name**</span></span>  
 <span data-ttu-id="84834-114">Geben Sie den vollständigen Pfad für eine Microsoft Access-Datenbankdatei an.</span><span class="sxs-lookup"><span data-stu-id="84834-114">Specify the full path for a Microsoft Access database file.</span></span>  
  
 <span data-ttu-id="84834-115">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="84834-115">**Browse**</span></span>  
 <span data-ttu-id="84834-116">Navigieren Sie zu einem Speicherort, an dem sich eine Microsoft Access-Datenbank-Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="84834-116">Navigate to a location where a Microsoft Access database file is available.</span></span>  
  
 <span data-ttu-id="84834-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="84834-117">**User name**</span></span>  
 <span data-ttu-id="84834-118">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="84834-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="84834-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="84834-119">**Password**</span></span>  
 <span data-ttu-id="84834-120">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="84834-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="84834-121">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="84834-121">**Save my password**</span></span>  
 <span data-ttu-id="84834-122">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="84834-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="84834-123">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="84834-123">**Advanced**</span></span>  
 <span data-ttu-id="84834-124">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="84834-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="84834-125">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="84834-125">**Test Connection**</span></span>  
 <span data-ttu-id="84834-126">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="84834-126">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="84834-127">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="84834-127">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
