---
title: Herstellen einer Verbindung mit einer DB2-Datenbank (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndb2db.f1
ms.assetid: eeef3697-a4fd-4263-ba7e-f86afa1f46cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: f36a583956c1fe75bb0a6acd827d083a6c7562f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610229"
---
# <a name="connect-to-a-db2-database-ssas"></a><span data-ttu-id="5f9cd-102">Mit einer DB2-Datenbank verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="5f9cd-102">Connect to a DB2 Database (SSAS)</span></span>
  <span data-ttu-id="5f9cd-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie Einstellungen angeben, um eine Verbindung mit einer DB2-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a DB2 database.</span></span> <span data-ttu-id="5f9cd-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="5f9cd-105">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f9cd-106">Beim Auswählen einer Datenbank auf dieser Seite werden die Anmeldeinformationen des angegebenen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-106">When selecting a database in this page, the credentials of the user specified are used.</span></span> <span data-ttu-id="5f9cd-107">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="5f9cd-108">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="5f9cd-108">UI element list</span></span>  
 <span data-ttu-id="5f9cd-109">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="5f9cd-110">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="5f9cd-111">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-111">This is a required field.</span></span>  
  
 <span data-ttu-id="5f9cd-112">**Servername**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-112">**Server name**</span></span>  
 <span data-ttu-id="5f9cd-113">Wählen Sie die Serverinstanz aus, zu der eine Verbindung hergestellt werden soll, oder geben Sie sie an.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="5f9cd-114">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-114">**User name**</span></span>  
 <span data-ttu-id="5f9cd-115">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="5f9cd-116">Dieser Benutzername wird beim Erstellen der Verbindungszeichenfolge für die Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="5f9cd-117">Diese Anmeldeinformationen werden auch beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="5f9cd-118">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="5f9cd-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-119">**Password**</span></span>  
 <span data-ttu-id="5f9cd-120">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="5f9cd-121">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-121">**Save my password**</span></span>  
 <span data-ttu-id="5f9cd-122">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="5f9cd-123">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-123">**Database name**</span></span>  
 <span data-ttu-id="5f9cd-124">Wählen Sie aus der Liste der Datenbanken eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="5f9cd-125">**Paketauflistung**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-125">**Package Collection**</span></span>  
 <span data-ttu-id="5f9cd-126">Geben Sie den Namen der Auflistung für die DB2-Pakete an.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-126">Specify the name of the collection for the DB2 packages.</span></span> <span data-ttu-id="5f9cd-127">Ein Anbieter verwendet Pakete zum Ausgeben von SQL-Anweisungen und Aufrufen von gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-127">A provider uses packages to issue SQL statements and call stored procedures.</span></span>  
  
 <span data-ttu-id="5f9cd-128">**Standardschema**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-128">**Default Schema**</span></span>  
 <span data-ttu-id="5f9cd-129">Geben Sie den Namen des Standardschemas für die ausgewählte Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-129">Specify the name of the default schema for the selected database.</span></span>  
  
 <span data-ttu-id="5f9cd-130">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-130">**Advanced**</span></span>  
 <span data-ttu-id="5f9cd-131">Legen Sie zusätzliche Verbindungs Eigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-131">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="5f9cd-132">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="5f9cd-132">**Test Connection**</span></span>  
 <span data-ttu-id="5f9cd-133">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-133">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="5f9cd-134">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="5f9cd-134">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
