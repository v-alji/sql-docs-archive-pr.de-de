---
title: Herstellen einer Verbindung mit einem Microsoft SQL Server parallel Data Warehouse (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlparadatawh.f1
ms.assetid: 98c879ee-7257-40c9-bc85-6766bd3b4885
author: minewiskan
ms.author: owend
ms.openlocfilehash: 082d6b34077d1bde11b527d3bfff907073eed16e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610216"
---
# <a name="connect-to-a-microsoft-sql-server-parallel-data-warehouse-ssas"></a><span data-ttu-id="fd4ac-102">Verbindung mit Microsoft SQL Server Parallel Data Warehouse herstellen (SSAS)</span><span class="sxs-lookup"><span data-stu-id="fd4ac-102">Connect to a Microsoft SQL Server Parallel Data Warehouse (SSAS)</span></span>
  <span data-ttu-id="fd4ac-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie Einstellungen angeben, um eine Verbindung mit Microsoft SQL Server Parallel Data Warehouse (PDW) herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server Parallel Data Warehouse (PDW).</span></span> <span data-ttu-id="fd4ac-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="fd4ac-105">SQL Server PDW ist eine hochskalierbare Anwendung, die Leistung zu niedrigen Preisen durch massive Parallelverarbeitung bietet.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-105">SQL Server PDW is a highly scalable appliance that delivers performance at low cost through massively parallel processing.</span></span> <span data-ttu-id="fd4ac-106">Weitere Informationen zu SQL Server PDW finden Sie auf der Website [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span><span class="sxs-lookup"><span data-stu-id="fd4ac-106">For more information about SQL Server PDW, see the web site [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span></span> <span data-ttu-id="fd4ac-107">Sie stellen mithilfe der SQL Server-Authentifizierung eine Verbindung mit dem Data Warehouse her.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-107">You connect to the data warehouse by using SQL Server Authentication.</span></span> <span data-ttu-id="fd4ac-108">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd4ac-109">Beim Auswählen einer Datenbank auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="fd4ac-110">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="fd4ac-111">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="fd4ac-111">UI element list</span></span>  
 <span data-ttu-id="fd4ac-112">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="fd4ac-113">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="fd4ac-114">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-114">This is a required field.</span></span>  
  
 <span data-ttu-id="fd4ac-115">**Servername**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-115">**Server name**</span></span>  
 <span data-ttu-id="fd4ac-116">Geben Sie den Namen oder die IP-Adresse des Servers ein, zu dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="fd4ac-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-117">**User name**</span></span>  
 <span data-ttu-id="fd4ac-118">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="fd4ac-119">Dieser Benutzername wird beim Erstellen der Verbindungszeichenfolge für die Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="fd4ac-120">Diese Anmeldeinformationen werden auch beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="fd4ac-121">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="fd4ac-122">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-122">**Password**</span></span>  
 <span data-ttu-id="fd4ac-123">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="fd4ac-124">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-124">**Save my password**</span></span>  
 <span data-ttu-id="fd4ac-125">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="fd4ac-126">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-126">**Database name**</span></span>  
 <span data-ttu-id="fd4ac-127">Wählen Sie aus der Liste der Datenbanken eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="fd4ac-128">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-128">**Advanced**</span></span>  
 <span data-ttu-id="fd4ac-129">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="fd4ac-130">Weitere Informationen finden Sie unter [Festlegen von erweiterten Eigenschaften &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="fd4ac-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="fd4ac-131">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="fd4ac-131">**Test Connection**</span></span>  
 <span data-ttu-id="fd4ac-132">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="fd4ac-133">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fd4ac-133">A message displays and indicates whether the connection is successful.</span></span>  
  
  
