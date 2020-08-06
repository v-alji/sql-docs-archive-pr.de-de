---
title: Herstellen einer Verbindung mit einer Informix-Datenbank (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conninformixdb.f1
ms.assetid: b01d537c-1c04-4d7d-9146-051c249b08e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35c7263ce9b0432802cd24b6df9165151b279d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610217"
---
# <a name="connect-to-an-informix-database-ssas"></a><span data-ttu-id="f408d-102">Mit einer Informix-Datenbank verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f408d-102">Connect to an Informix Database (SSAS)</span></span>
  <span data-ttu-id="f408d-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie Einstellungen angeben, um eine Verbindung mit einer Informix-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f408d-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Informix database.</span></span> <span data-ttu-id="f408d-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="f408d-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="f408d-105">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f408d-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f408d-106">Beim Auswählen einer Datenbank auf dieser Seite werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="f408d-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="f408d-107">Der Import ist jedoch nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="f408d-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f408d-108">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="f408d-108">UI element list</span></span>  
 <span data-ttu-id="f408d-109">**Anzeigename der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="f408d-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="f408d-110">Geben Sie einen eindeutigen Namen für diese Datenquellenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="f408d-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="f408d-111">Dies ist ein Pflichtfeld.</span><span class="sxs-lookup"><span data-stu-id="f408d-111">This is a required field.</span></span>  
  
 <span data-ttu-id="f408d-112">**Servername**</span><span class="sxs-lookup"><span data-stu-id="f408d-112">**Server name**</span></span>  
 <span data-ttu-id="f408d-113">Wählen Sie den Namen der Serverinstanz aus, zu der eine Verbindung hergestellt werden soll, oder geben Sie ihn an.</span><span class="sxs-lookup"><span data-stu-id="f408d-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="f408d-114">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="f408d-114">**User name**</span></span>  
 <span data-ttu-id="f408d-115">Geben Sie einen Benutzernamen für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="f408d-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="f408d-116">Dieser Benutzername wird beim Erstellen der Verbindungszeichenfolge für die Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="f408d-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="f408d-117">Diese Anmeldeinformationen werden auch beim Anzeigen von Daten in der Vorschau und beim Filtern von Daten im Fenster Tabelleneigenschaften und im Import-Assistenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="f408d-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="f408d-118">Diese Anmeldeinformationen werden nicht zum Importieren oder Aktualisieren von Daten verwendet, stattdessen werden die auf der Seite Identitätswechselinformationen angegebenen Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f408d-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="f408d-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="f408d-119">**Password**</span></span>  
 <span data-ttu-id="f408d-120">Geben Sie ein Kennwort für die Datenbankverbindung an.</span><span class="sxs-lookup"><span data-stu-id="f408d-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="f408d-121">**Kennwort speichern**</span><span class="sxs-lookup"><span data-stu-id="f408d-121">**Save my password**</span></span>  
 <span data-ttu-id="f408d-122">Geben Sie an, ob das Kennwort, das Sie im Feld **Kennwort** eingegeben haben, gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f408d-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="f408d-123">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="f408d-123">**Advanced**</span></span>  
 <span data-ttu-id="f408d-124">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="f408d-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="f408d-125">Weitere Informationen finden Sie unter [Festlegen von erweiterten Eigenschaften &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="f408d-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="f408d-126">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="f408d-126">**Test Connection**</span></span>  
 <span data-ttu-id="f408d-127">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="f408d-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="f408d-128">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f408d-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
