---
title: Importieren von Informationen zum registrierten Server
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.importregisteredservers.f1
helpviewer_keywords:
- transferring registered server information
- Registered Servers [SQL Server], importing
- importing registered server information
ms.assetid: cc497a14-1360-4887-b70c-002f042823b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f2eddb3b83f73253e977316767f2b930bc8ab9ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722165"
---
# <a name="import-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="d3875-102">Importieren von Informationen zum registrierten Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d3875-102">Import Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d3875-103">In diesem Thema wird beschrieben, wie Sie gespeicherte Informationen zu registrierten Servern in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]importieren.</span><span class="sxs-lookup"><span data-stu-id="d3875-103">This topic describes how to import saved registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d3875-104">Durch das Exportieren und Importieren von Dateien mit registrierten Servern können Sie schnell und einfach mehrere Computer mit denselben Servern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d3875-104">Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="d3875-105">Besonders hilfreich ist dies, wenn Sie eine große Anzahl von Servern auf Computern an mehreren Standorten verwalten oder Sie für einen weniger erfahrenen Benutzer die grundlegenden Verbindungseinstellungen konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d3875-105">This is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less-experienced user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3875-106">Sie können keine registrierten Serverinformationen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aus früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]importieren.</span><span class="sxs-lookup"><span data-stu-id="d3875-106">You cannot import registered server information into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-import-registered-server-information"></a><span data-ttu-id="d3875-107">So importieren Sie Informationen zum registrierten Server</span><span class="sxs-lookup"><span data-stu-id="d3875-107">To import registered server information</span></span>  
  
1.  <span data-ttu-id="d3875-108">Klicken Sie in Registrierte Server auf der Symbolleiste Registrierte Server auf den Servertyp.</span><span class="sxs-lookup"><span data-stu-id="d3875-108">In Registered Servers, click the server type on the Registered Servers toolbar.</span></span> <span data-ttu-id="d3875-109">Der Servertyp muss mit dem Exportdateityp des registrierten Servers identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d3875-109">The server type must be the same as the registered server export file type.</span></span> <span data-ttu-id="d3875-110">Wenn Sie z. B. Informationen zum registrierten Server von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exportiert haben, müssen Sie auf der Symbolleiste Registrierte Server auf **SQL Server** klicken.</span><span class="sxs-lookup"><span data-stu-id="d3875-110">For example, if you have exported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registered server information, you must click **SQL Server** on the Registered Servers toolbar.</span></span>  
  
2.  <span data-ttu-id="d3875-111">Klicken Sie mit der rechten Maustaste auf eine Servergruppe, und klicken Sie dann auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="d3875-111">Right-click a server group, and select **Import**.</span></span>  
  
3.  <span data-ttu-id="d3875-112">Wählen Sie im Dialogfeld **Registrierte Server importieren** die zu importierende Datei mit den registrierten Servern aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3875-112">In the **Import Registered Servers** dialog box, select the registered servers file to import, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d3875-113">**Importdatei**</span><span class="sxs-lookup"><span data-stu-id="d3875-113">**Import file**</span></span>  
     <span data-ttu-id="d3875-114">Geben Sie den Namen der Importdatei in das Textfeld ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen ( **...** ), um eine Importdatei auf dem Clientcomputer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d3875-114">Type the name of the import file in the text box, or click the Browse button (**...**) to locate the import file on the client computer.</span></span> <span data-ttu-id="d3875-115">Wenn Sie eine vorhandene Datei auswählen, werden die Daten der registrierten Server an die Datei angehängt.</span><span class="sxs-lookup"><span data-stu-id="d3875-115">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="d3875-116">Die Importdatei kann nur eine zuvor exportierte Datei mit registrierten Servern sein.</span><span class="sxs-lookup"><span data-stu-id="d3875-116">The import file can only be a previously exported registered server file.</span></span> <span data-ttu-id="d3875-117">Dateien mit registrierten Servern haben die Dateierweiterung .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="d3875-117">Registered server files have a .regsrvr extension.</span></span>  
  
     <span data-ttu-id="d3875-118">**Wählen Sie die Servergruppe für den Import aus**</span><span class="sxs-lookup"><span data-stu-id="d3875-118">**Select the server group to import to**</span></span>  
     <span data-ttu-id="d3875-119">Wählen Sie einen Stammknoten oder eine bestimmte Servergruppe aus, in den/die die Einträge zu den registrierten Servern in der Datei importiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3875-119">Select the root node or a particular server group to which the registered server entries in the file will be imported.</span></span> <span data-ttu-id="d3875-120">Sie können alle registrierten Server, die registrierten Server in einer bestimmten Servergruppe oder einzelne registrierte Server in die Exportdatei importieren.</span><span class="sxs-lookup"><span data-stu-id="d3875-120">You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="d3875-121">Die Importfunktion ist rekursiv. Wenn z. B. Servergruppe A die Servergruppe B enthält und Servergruppe B die Servergruppen C und D enthält, werden beim Import von Servergruppe A alle Einträge in A, B, C und D exportiert.</span><span class="sxs-lookup"><span data-stu-id="d3875-121">The import functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, importing server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="d3875-122">In der Servergruppe werden nur die Servergruppen der Baumstruktur des aktuellen registrierten Servers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3875-122">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="d3875-123">Wenn Sie eine vorhandene Servergruppe oder einen vorhandenen Server importieren, werden Sie in einer Meldung darauf hingewiesen, dass bei diesem Vorgang ein vorhandener Server oder eine vorhandene Servergruppe überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d3875-123">If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.</span></span>  
  
 <span data-ttu-id="d3875-124">Serverregistrierungen, die die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung nutzen, speichern die Kennwörter auf Benutzerbasis.</span><span class="sxs-lookup"><span data-stu-id="d3875-124">Server registrations that use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="d3875-125">Nach dem Importieren der Serverregistrierungen müssen Benutzer beim ersten Herstellen der Verbindung für jeden Server ein Kennwort eingeben. Diese werden in den Listen der registrierten Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d3875-125">After importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="d3875-126">Bei Servern, die mithilfe der Windows-Authentifizierung registriert wurden, ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3875-126">This is not necessary for servers registered through Windows Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3875-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3875-127">See Also</span></span>  
 <span data-ttu-id="d3875-128">[Ändern Sie die Registrierungs &#40;eines Servers SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) die [Informationen zum registrierten Server &#40;SQL Server Management Studio exportieren&#41;](export-registered-server-information-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d3875-128">[Change a Server's Registration &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Export Registered Server Information &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="d3875-129">Erstellen eines neuen registrierten Servers &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d3875-129">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)  
  
  
