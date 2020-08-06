---
title: Exportieren von Informationen zum registrierten Server
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 03092de2d722e8f8b807dbb3d23c4b4e2b91f6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722162"
---
# <a name="export-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="aa716-102">Exportieren von Informationen zum registrierten Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="aa716-102">Export Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="aa716-103">In diesem Thema wird beschrieben, wie Sie Informationen zum registrierten Server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]speichern und exportieren und an andere Mitarbeiter oder Server verteilen.</span><span class="sxs-lookup"><span data-stu-id="aa716-103">This topic describes how to save and export registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]and distribute it to other employees or servers.</span></span> <span data-ttu-id="aa716-104">Diese Exportfunktion ermöglicht eine konsistente Benutzeroberfläche auf mehreren Computern.</span><span class="sxs-lookup"><span data-stu-id="aa716-104">You can use this export feature to present a consistent user interface on multiple computers.</span></span>  
  
 <span data-ttu-id="aa716-105">Durch Exportieren und Reimportieren von Dateien mit registrierten Servern können Sie schnell und einfach mehrere Computer mit denselben Servern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="aa716-105">Exporting and then importing Registered Server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="aa716-106">Besonders hilfreich ist dies, wenn Sie eine große Anzahl von Servern über Computer an mehreren Standorten verwalten oder einen weniger erfahrenden Benutzer mit elementaren Verbindungseinstellungen konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="aa716-106">This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa716-107">Serverregistrierungen, die die SQL Server-Authentifizierung nutzen, speichern die Kennwörter auf Benutzerbasis.</span><span class="sxs-lookup"><span data-stu-id="aa716-107">Server registrations that use SQL Server Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="aa716-108">Nach dem Export und Reimport der Serverregistrierungen müssen Benutzer beim ersten Herstellen der Verbindung für jeden Server ein Kennwort eingeben. Diese werden in den Listen der registrierten Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="aa716-108">After exporting and importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="aa716-109">Bei Servern, die mit der Windows-Authentifizierung registriert wurden, ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aa716-109">This is not necessary for servers registered using Windows Authentication.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a><span data-ttu-id="aa716-110">So exportieren Sie Informationen zum registrierten Server</span><span class="sxs-lookup"><span data-stu-id="aa716-110">To export registered server information</span></span>  
  
1.  <span data-ttu-id="aa716-111">Klicken Sie unter „Registrierte Server“ mit der rechten Maustaste auf eine Servergruppe, und klicken Sie dann auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="aa716-111">In Registered Servers, right-click a server group, and then click **Export**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aa716-112">Sie können einen einzelnen Server, die gesamte Struktur registrierter Server oder eine Teilmenge der Struktur registrierter Server exportieren.</span><span class="sxs-lookup"><span data-stu-id="aa716-112">You can export an individual server, all of the registered server tree, or a subset of the registered server tree.</span></span>  
  
2.  <span data-ttu-id="aa716-113">Nehmen Sie im Dialogfeld **Registrierte Server exportieren** die folgenden Einstellungen vor.</span><span class="sxs-lookup"><span data-stu-id="aa716-113">In the **Export Registered Servers** dialog box, make the following selections.</span></span>  
  
     <span data-ttu-id="aa716-114">**Servergruppe**</span><span class="sxs-lookup"><span data-stu-id="aa716-114">**Server group**</span></span>  
     <span data-ttu-id="aa716-115">Geben Sie die zu exportierende Servergruppe an.</span><span class="sxs-lookup"><span data-stu-id="aa716-115">Specify the server group which will be exported.</span></span> <span data-ttu-id="aa716-116">Sie können alle registrierten Server, die registrierten Server in einer bestimmten Servergruppe bzw. einzelne registrierte Server in die Exportdatei exportieren.</span><span class="sxs-lookup"><span data-stu-id="aa716-116">Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="aa716-117">Die Exportfunktion ist rekursiv. Wenn z. B. Servergruppe A die Servergruppe B enthält und Servergruppe B die Servergruppen C und D enthält, werden beim Export von Servergruppe A alle Einträge in A, B, C und D exportiert.</span><span class="sxs-lookup"><span data-stu-id="aa716-117">The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="aa716-118">In der Servergruppe werden nur die Servergruppen der Baumstruktur des aktuellen registrierten Servers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa716-118">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="aa716-119">**Datei exportieren**</span><span class="sxs-lookup"><span data-stu-id="aa716-119">**Export file**</span></span>  
     <span data-ttu-id="aa716-120">Geben Sie den Namen der Exportdatei in das Textfeld ein, oder verwenden Sie die Schaltfläche zum Durchsuchen ( **...** ), um eine Exportdatei auf dem Clientcomputer zu suchen.</span><span class="sxs-lookup"><span data-stu-id="aa716-120">Type the name of the export file in the text box or use the Browse button (**...**) to locate an export file on the client computer.</span></span> <span data-ttu-id="aa716-121">Wenn Sie eine vorhandene Datei auswählen, werden die Daten der registrierten Server an die Datei angehängt.</span><span class="sxs-lookup"><span data-stu-id="aa716-121">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="aa716-122">Verwenden Sie die Erweiterung .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="aa716-122">Use the .regsrvr extension.</span></span> <span data-ttu-id="aa716-123">Wenn die Informationen zum registrierten Server für andere Benutzer oder einen anderen Computer verfügbar sein sollen, können Sie die Datei im Netzwerk speichern.</span><span class="sxs-lookup"><span data-stu-id="aa716-123">If you want your registered server information to be available to other users or another computer, you can save the file on the network.</span></span> <span data-ttu-id="aa716-124">Andere Benutzer können auf die Datei zugreifen und die Informationen zum registrierten Server vollständig oder teilweise importieren.</span><span class="sxs-lookup"><span data-stu-id="aa716-124">Other users can access the file and import part or all of the registered server information.</span></span> <span data-ttu-id="aa716-125">Wenn Sie eine vorhandene Datei als Exportdatei auswählen, wird der Inhalt der Datei mit den Informationen zum registrierten Server überschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa716-125">If you select an existing file as your export file, the contents of the file are overwritten with the server registration information.</span></span>  
  
     <span data-ttu-id="aa716-126">**Benutzernamen und Kennwörter nicht in die Exportdatei einschließen**</span><span class="sxs-lookup"><span data-stu-id="aa716-126">**Do not include user names and passwords in the export file**</span></span>  
     <span data-ttu-id="aa716-127">Schließen Sie Benutzernamen vom Export in die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="aa716-127">Exclude user names when exporting the file.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="aa716-128">Die Exportdateien sind zwar verschlüsselt, der Zugriff auf die Datei sollte dennoch sorgfältig kontrolliert werden, wenn diese Benutzernamen und SQL Server-Authentifizierungskennwörter enthält.</span><span class="sxs-lookup"><span data-stu-id="aa716-128">Although the export files are encrypted, if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled.</span></span> <span data-ttu-id="aa716-129">Benutzernamen und Kennwörter werden deshalb standardmäßig von der Exportdatei ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aa716-129">User names and passwords are therefore excluded from the export file by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa716-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa716-130">See Also</span></span>  
 <span data-ttu-id="aa716-131">[Importieren Sie die Informationen zum registrierten Server &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Erstellen Sie einen neuen registrierten Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="aa716-131">[Import Registered Server Information &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span></span>  
  
  
