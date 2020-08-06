---
title: Datenquellen Eigenschaften (Dialog Feld), Anmelde Informationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.credentials.f1
- "10100"
ms.assetid: 14c3eeb6-d37b-4fda-967b-43afcdb48119
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 491da16e6cd38db54c4d27bd8497ca7fdfaae5b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618546"
---
# <a name="data-source-properties-dialog-box-credentials"></a><span data-ttu-id="edcd8-102">Datenquelleneigenschaften (Dialogfeld), Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="edcd8-102">Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="edcd8-103">Wählen Sie im Dialogfeld **Datenquelleneigenschaften** die Option **Anmeldeinformationen** aus, um die Anmeldeinformationen für eine Datenquelle im Bericht anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="edcd8-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to a data source in the report.</span></span> <span data-ttu-id="edcd8-104">Die von Ihnen bereitgestellten Anmeldeinformationen werden für den Zugriff auf die Datenquelle und zum Zwischenspeichern einer Kopie der Daten für die Berichtsvorschau verwendet.</span><span class="sxs-lookup"><span data-stu-id="edcd8-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="edcd8-105">Weitere Informationen dazu, wie Vorschaudaten zwischengespeichert werden, finden Sie unter [Ausführen einer Vorschau für Berichte](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="edcd8-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="edcd8-106">Weitere Anmeldeinformationen finden Sie unter [Angeben der Anmeldeinformationen und Verbindungsinformationen für Berichtsdatenquellen](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="edcd8-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="edcd8-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="edcd8-107">Options</span></span>  
 <span data-ttu-id="edcd8-108">**Windows-Authentifizierung verwenden (Integrierte Sicherheit)**</span><span class="sxs-lookup"><span data-stu-id="edcd8-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="edcd8-109">Wählen Sie diese Option aus, um die Windows-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="edcd8-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="edcd8-110">**Diesen Benutzernamen und dieses Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="edcd8-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="edcd8-111">Wählen Sie diese Option aus, um einen bestimmten Benutzernamen und ein bestimmtes Kennwort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="edcd8-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="edcd8-112">Für freigegebene Datenquellen gilt Folgendes: Wenn Sie das Berichtsserverprojekt auf dem Zielserver veröffentlichen, werden der Benutzername und das Kennwort als gespeicherte Anmeldeinformationen für die Datenbank gesichert.</span><span class="sxs-lookup"><span data-stu-id="edcd8-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="edcd8-113">Wenn Sie den Benutzernamen und das Kennwort als Windows-Anmeldeinformationen verwenden möchten, können Sie die Eigenschaften für die veröffentlichte freigegebene Datenquelle auf dem Zielserver bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="edcd8-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="edcd8-114">Weitere Informationen finden Sie unter [Erstellen, Löschen oder Ändern einer freigegebenen Datenquelle &#40;Berichts-Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="edcd8-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="edcd8-115">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="edcd8-115">**User name**</span></span>  
 <span data-ttu-id="edcd8-116">Geben Sie einen Benutzernamen ein, der beim Anmelden an der Datenquelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="edcd8-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="edcd8-117">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="edcd8-117">**Password**</span></span>  
 <span data-ttu-id="edcd8-118">Geben Sie ein Kennwort ein, das beim Anmelden an der Datenquelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="edcd8-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="edcd8-119">**Eingabeaufforderung zu Anmeldeinformationen**</span><span class="sxs-lookup"><span data-stu-id="edcd8-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="edcd8-120">Wählen Sie diese Option aus, um beim Ausführen des Berichts Anmeldeinformationen anzufordern.</span><span class="sxs-lookup"><span data-stu-id="edcd8-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="edcd8-121">**Eingabeaufforderungs-Zeichenfolge eingeben**</span><span class="sxs-lookup"><span data-stu-id="edcd8-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="edcd8-122">Geben Sie einen Satz ein, mit dem der Benutzer zur Eingabe von Anmeldeinformationen für die Datenquelle aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="edcd8-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="edcd8-123">**Keine Anmelde Informationen**</span><span class="sxs-lookup"><span data-stu-id="edcd8-123">**No credentials**</span></span>  
 <span data-ttu-id="edcd8-124">Wählen Sie diese Option aus, wenn keine Anmeldeinformationen für die Datenquelle bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="edcd8-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="edcd8-125">Diese Option kann nur verwendet werden, wenn die Datenquelle keine Anmeldeinformationen annimmt oder wenn Sie Anmeldeinformationen auf andere Art übergeben.</span><span class="sxs-lookup"><span data-stu-id="edcd8-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcd8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edcd8-126">See Also</span></span>  
 <span data-ttu-id="edcd8-127">[Dialog Feld "Datenquellen Eigenschaften", "Allgemein"](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span><span class="sxs-lookup"><span data-stu-id="edcd8-127">[Data Source Properties Dialog Box, General](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span></span>  
 <span data-ttu-id="edcd8-128">[Angeben der Anmeldeinformationen und Verbindungsinformationen für Berichtsdatenquellen](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="edcd8-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="edcd8-129">Datenverbindungen, Datenquellen und Verbindungszeichenfolgen in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="edcd8-129">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
