---
title: Herstellen einer Verbindung mit einer Microsoft SQL Server Datenbank (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserverdb.f1
ms.assetid: 6ebfe029-dbba-4f0d-a556-328e79ef629f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64267cd65836cf8e6c8d8b26a177de595894b601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610223"
---
# <a name="connect-to-a-microsoft-sql-server-database-ssas"></a><span data-ttu-id="085ae-102">Mit einer Microsoft SQL Server-Datenbank verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="085ae-102">Connect to a Microsoft SQL Server Database (SSAS)</span></span>
  <span data-ttu-id="085ae-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie Einstellungen angeben, um eine Verbindung mit einer Microsoft SQL Server-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="085ae-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server database.</span></span> <span data-ttu-id="085ae-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="085ae-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="085ae-105">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="085ae-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="085ae-106">Beim Auswählen einer Datenbank auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="085ae-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="085ae-107">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="085ae-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="085ae-108">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="085ae-108">UI element list</span></span>  
 <span data-ttu-id="085ae-109">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="085ae-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="085ae-110">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="085ae-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="085ae-111">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="085ae-111">This is a required field.</span></span>  
  
 <span data-ttu-id="085ae-112">**Servername**</span><span class="sxs-lookup"><span data-stu-id="085ae-112">**Server name**</span></span>  
 <span data-ttu-id="085ae-113">Wählen Sie den Namen der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz aus, mit der eine Verbindung hergestellt werden soll, oder geben Sie den Namen oder die IP-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="085ae-113">Select the name, or type the name or IP address, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to.</span></span>  
  
 <span data-ttu-id="085ae-114">Sie können einen Punkt (.), (local) oder localhost zum Angeben des lokalen Servers verwenden.</span><span class="sxs-lookup"><span data-stu-id="085ae-114">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
 <span data-ttu-id="085ae-115">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="085ae-115">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="085ae-116">Geben Sie an, ob die Windows-Authentifizierung verwendet werden soll, um eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]herzustellen.</span><span class="sxs-lookup"><span data-stu-id="085ae-116">Specify whether Windows Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="085ae-117">Der Windows-Authentifizierungsmodus ermöglicht Benutzern das Herstellen einer Verbindung über ein Windows-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="085ae-117">Windows Authentication mode enables a user to connect by using a Windows user account.</span></span> <span data-ttu-id="085ae-118">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="085ae-118">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="085ae-119">Wenn die Windows-Authentifizierung verwendet wird, werden die Anmeldeinformationen des aktuellen Benutzers beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="085ae-119">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="085ae-120">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="085ae-120">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="085ae-121">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="085ae-121">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="085ae-122">Geben Sie an, ob die SQL Server-Authentifizierung verwendet werden soll, um eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]herzustellen.</span><span class="sxs-lookup"><span data-stu-id="085ae-122">Specify whether SQL Server Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="085ae-123">Mit der SQL Server-Authentifizierung führt SQL Server die Authentifizierung selbst aus, indem überprüft wird, ob ein SQL Server-Anmeldekonto eingerichtet wurde und ob das angegebene Kennwort mit dem zuvor aufgezeichneten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="085ae-123">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="085ae-124">Die SQL Server-Authentifizierung wird zum Erstellen der Verbindungszeichenfolge für die Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="085ae-124">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="085ae-125">Diese Anmeldeinformationen werden auch beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="085ae-125">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="085ae-126">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="085ae-126">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="085ae-127">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="085ae-127">**User name**</span></span>  
 <span data-ttu-id="085ae-128">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="085ae-128">Specify a user name for the database connection.</span></span> <span data-ttu-id="085ae-129">Diese Option ist nur verfügbar, wenn Sie die SQL Server-Authentifizierung für die Verbindungsherstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="085ae-129">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="085ae-130">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="085ae-130">**Password**</span></span>  
 <span data-ttu-id="085ae-131">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="085ae-131">Specify a password for the database connection.</span></span> <span data-ttu-id="085ae-132">Sie können diese Option nur bearbeiten, wenn Sie zum Verbinden die SQL Server-Authentifizierung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="085ae-132">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="085ae-133">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="085ae-133">**Save my password**</span></span>  
 <span data-ttu-id="085ae-134">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="085ae-134">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="085ae-135">Diese Option ist nur verfügbar, wenn Sie die SQL Server-Authentifizierung für die Verbindungsherstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="085ae-135">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="085ae-136">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="085ae-136">**Database name**</span></span>  
 <span data-ttu-id="085ae-137">Wählen Sie aus der Liste der Datenbanken eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="085ae-137">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="085ae-138">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="085ae-138">**Advanced**</span></span>  
 <span data-ttu-id="085ae-139">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="085ae-139">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="085ae-140">Weitere Informationen finden Sie unter [Festlegen von erweiterten Eigenschaften &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="085ae-140">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="085ae-141">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="085ae-141">**Test Connection**</span></span>  
 <span data-ttu-id="085ae-142">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="085ae-142">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="085ae-143">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="085ae-143">A message is displayed indicating whether the connection was successful.</span></span>  
  
  
