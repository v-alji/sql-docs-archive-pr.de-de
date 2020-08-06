---
title: Herstellen einer Verbindung mit Microsoft SQL Server Analysis Services (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
author: minewiskan
ms.author: owend
ms.openlocfilehash: 984979480e3ea54c86c986fa6dd9771aaf879cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610200"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a><span data-ttu-id="4be22-102">Verbindung mit Microsoft SQL Server Analysis Services herstellen (SSAS)</span><span class="sxs-lookup"><span data-stu-id="4be22-102">Connect to Microsoft SQL Server Analysis Services (SSAS)</span></span>
  <span data-ttu-id="4be22-103">Auf dieser Seite des **Tabellen Import-Assistenten** können Sie Einstellungen für das Importieren von Daten aus einem Microsoft SQL Server Analysis Services Cube oder einer auf SharePoint gehosteten Power Pivot-Arbeitsmappe angeben.</span><span class="sxs-lookup"><span data-stu-id="4be22-103">This page of the **Table Import Wizard** enables you to specify settings to import data from a Microsoft SQL Server Analysis Services cube or a PowerPivot workbook that is hosted on SharePoint.</span></span> <span data-ttu-id="4be22-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="4be22-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="4be22-105">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4be22-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4be22-106">Beim Auswählen einer Datenbank auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="4be22-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="4be22-107">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="4be22-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="4be22-108">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="4be22-108">UI element list</span></span>  
 <span data-ttu-id="4be22-109">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="4be22-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="4be22-110">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="4be22-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="4be22-111">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="4be22-111">This is a required field.</span></span>  
  
 <span data-ttu-id="4be22-112">**Server- oder Dateiname**</span><span class="sxs-lookup"><span data-stu-id="4be22-112">**Server or File Name**</span></span>  
 <span data-ttu-id="4be22-113">Geben Sie eine der folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="4be22-113">Enter one of the following:</span></span>  
  
-   <span data-ttu-id="4be22-114">Geben Sie den Namen oder die IP-Adresse des SQL Server Analysis Services-Servers ein, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4be22-114">Type the name or IP address of the SQL Server Analysis Services server to connect to.</span></span>  
  
     <span data-ttu-id="4be22-115">Sie können einen Punkt (.), (local) oder localhost zum Angeben des lokalen Servers verwenden.</span><span class="sxs-lookup"><span data-stu-id="4be22-115">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
-   <span data-ttu-id="4be22-116">Geben Sie die URL einer PowerPivot-Arbeitsmappe ein, die in SharePoint veröffentlicht ist.</span><span class="sxs-lookup"><span data-stu-id="4be22-116">Type the URL of a PowerPivot workbook that is published to SharePoint.</span></span>  
  
 <span data-ttu-id="4be22-117">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="4be22-117">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="4be22-118">Geben Sie an, ob die Windows-Authentifizierung verwendet wird, um eine Verbindung mit einem SQL Server Analysis Services-Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4be22-118">Specify whether Windows Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="4be22-119">Der Windows-Authentifizierungsmodus ermöglicht Benutzern das Herstellen einer Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="4be22-119">Windows Authentication mode enables a user to connect through a Windows user account.</span></span> <span data-ttu-id="4be22-120">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4be22-120">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="4be22-121">Wenn die Windows-Authentifizierung verwendet wird, werden die Anmeldeinformationen des aktuellen Benutzers beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="4be22-121">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="4be22-122">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4be22-122">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="4be22-123">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="4be22-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="4be22-124">Geben Sie an, ob die SQL Server-Authentifizierung verwendet wird, um eine Verbindung mit einem SQL Server Analysis Services-Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4be22-124">Specify whether SQL Server Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="4be22-125">Mit der SQL Server-Authentifizierung führt SQL Server die Authentifizierung selbst aus, indem überprüft wird, ob ein SQL Server-Anmeldekonto eingerichtet wurde und ob das angegebene Kennwort mit dem zuvor aufgezeichneten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4be22-125">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="4be22-126">Die SQL Server-Authentifizierung wird zum Erstellen der Verbindungszeichenfolge für die Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="4be22-126">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="4be22-127">Diese Anmeldeinformationen werden auch beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="4be22-127">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="4be22-128">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4be22-128">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="4be22-129">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="4be22-129">**User name**</span></span>  
 <span data-ttu-id="4be22-130">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="4be22-130">Specify a user name for the database connection.</span></span> <span data-ttu-id="4be22-131">Diese Option ist nur verfügbar, wenn Sie die Windows-Authentifizierung für die Verbindungsherstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4be22-131">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="4be22-132">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="4be22-132">**Password**</span></span>  
 <span data-ttu-id="4be22-133">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="4be22-133">Specify a password for the database connection.</span></span> <span data-ttu-id="4be22-134">Sie können diese Option nur bearbeiten, wenn Sie zum Verbinden die SQL Server-Authentifizierung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4be22-134">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="4be22-135">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="4be22-135">**Save my password**</span></span>  
 <span data-ttu-id="4be22-136">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4be22-136">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="4be22-137">Diese Option ist nur verfügbar, wenn Sie die SQL Server-Authentifizierung für die Verbindungsherstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4be22-137">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="4be22-138">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="4be22-138">**Database name**</span></span>  
 <span data-ttu-id="4be22-139">Wählen Sie aus der Liste der Datenbanken eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="4be22-139">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="4be22-140">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="4be22-140">**Advanced**</span></span>  
 <span data-ttu-id="4be22-141">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="4be22-141">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="4be22-142">Weitere Informationen finden Sie unter [Festlegen von erweiterten Eigenschaften &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="4be22-142">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="4be22-143">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="4be22-143">**Test Connection**</span></span>  
 <span data-ttu-id="4be22-144">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="4be22-144">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="4be22-145">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4be22-145">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
