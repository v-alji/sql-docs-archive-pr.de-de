---
title: Herstellen einer Verbindung mit einer Azure SQL-Datenbank (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlazure.f1
ms.assetid: 4e0344e9-1822-4698-ad22-05f1f341ced7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91ae6f0f5ab95d3013b6348bd43ddb746fff1c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610213"
---
# <a name="connect-to-an-azure-sql-database-ssas"></a><span data-ttu-id="a17ee-102">Mit einer Azure SQL-Datenbank verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="a17ee-102">Connect to an Azure SQL Database (SSAS)</span></span>
  <span data-ttu-id="a17ee-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie eine Verbindung mit einer [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)]herstellen.</span><span class="sxs-lookup"><span data-stu-id="a17ee-103">This page of the **Table Import Wizard** enables you to connect to a [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="a17ee-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="a17ee-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a17ee-105">Wenn Sie eine Verbindung mit einem Azure DataMarket-Dataset herstellen, gehen Sie zu [Mit einem Bericht oder Datenfeed verbinden &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-105">If you are connecting to an Azure DataMarket dataset, see [Connect to a Report or Data Feed &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span></span>  
  
 <span data-ttu-id="a17ee-106">Die [!INCLUDE[ssSDS](../includes/sssds-md.md)] ist eine gehostete, relationale Datenbank, mit der Sie eine Verbindung unter Verwendung der SQL Server-Authentifizierung herstellen.</span><span class="sxs-lookup"><span data-stu-id="a17ee-106">The [!INCLUDE[ssSDS](../includes/sssds-md.md)] is a hosted, relational database that you connect to by using SQL Server Authentication.</span></span> <span data-ttu-id="a17ee-107">Weitere Informationen zu [!INCLUDE[ssSDS](../includes/sssds-md.md)]finden Sie auf der Website zu [SQL-Datenbanken](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="a17ee-107">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)], see the web site [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span> <span data-ttu-id="a17ee-108">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a17ee-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a17ee-109">Beim Auswählen einer Datenbank auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="a17ee-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="a17ee-110">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="a17ee-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a17ee-111">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="a17ee-111">UI element list</span></span>  
 <span data-ttu-id="a17ee-112">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="a17ee-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="a17ee-113">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="a17ee-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="a17ee-114">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="a17ee-114">This is a required field.</span></span>  
  
 <span data-ttu-id="a17ee-115">**Servername**</span><span class="sxs-lookup"><span data-stu-id="a17ee-115">**Server name**</span></span>  
 <span data-ttu-id="a17ee-116">Geben Sie den Namen oder die IP-Adresse des Servers ein, zu dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a17ee-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="a17ee-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="a17ee-117">**User name**</span></span>  
 <span data-ttu-id="a17ee-118">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="a17ee-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="a17ee-119">Dieser Benutzername wird beim Erstellen der Verbindungszeichenfolge für die Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="a17ee-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="a17ee-120">Diese Anmeldeinformationen werden auch beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a17ee-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="a17ee-121">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a17ee-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="a17ee-122">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="a17ee-122">**Password**</span></span>  
 <span data-ttu-id="a17ee-123">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="a17ee-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="a17ee-124">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="a17ee-124">**Save my password**</span></span>  
 <span data-ttu-id="a17ee-125">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a17ee-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="a17ee-126">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="a17ee-126">**Database name**</span></span>  
 <span data-ttu-id="a17ee-127">Wählen Sie aus der Liste der Datenbanken eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="a17ee-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="a17ee-128">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="a17ee-128">**Advanced**</span></span>  
 <span data-ttu-id="a17ee-129">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="a17ee-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="a17ee-130">Weitere Informationen finden Sie unter [Festlegen von erweiterten Eigenschaften &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="a17ee-131">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="a17ee-131">**Test Connection**</span></span>  
 <span data-ttu-id="a17ee-132">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="a17ee-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="a17ee-133">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a17ee-133">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
