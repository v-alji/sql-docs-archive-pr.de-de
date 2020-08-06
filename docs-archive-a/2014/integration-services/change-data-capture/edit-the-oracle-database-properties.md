---
title: Bearbeiten der Oracle-Datenbankeigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraProp
ms.assetid: 58dc99f1-ee6b-4508-bb66-2bc589611ff7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3cad2735e6cd6095f9730f3b4e7228526451d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616137"
---
# <a name="edit-the-oracle-database-properties"></a><span data-ttu-id="def27-102">Bearbeiten der Oracle-Datenbankeigenschaften</span><span class="sxs-lookup"><span data-stu-id="def27-102">Edit the Oracle Database Properties</span></span>
  <span data-ttu-id="def27-103">Verwenden Sie die Registerkarte Oracle im Eigenschaften-Editor, um Änderungen an der Beschreibung vorzunehmen, die Sie im Assistenten für neue Instanzen auf der Seite Create CDC database angegeben haben, und um Änderungen an den Verbindungsinformationen zur Oracle Log Mining-Datenbank vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="def27-103">Use the Oracle tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
 <span data-ttu-id="def27-104">Im Folgenden werden die Informationen auf der Registerkarte **Oracle** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="def27-104">The following describes the information in the **Oracle** tab.</span></span>  
  
 <span data-ttu-id="def27-105">**Name**</span><span class="sxs-lookup"><span data-stu-id="def27-105">**Name**</span></span>  
 <span data-ttu-id="def27-106">Der Name der CDC-Instanz, die Sie im Assistenten für neue Instanzen auf der Seite Create CDC Database eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="def27-106">The name of the CDC Instance that you entered in the Create CDC Database page in the New Instance wizard.</span></span> <span data-ttu-id="def27-107">Dieses Feld ist schreibgeschützt, und Sie können diese Informationen nicht bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="def27-107">This field is read only and you cannot edit this information.</span></span>  
  
 <span data-ttu-id="def27-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="def27-108">**Description**</span></span>  
 <span data-ttu-id="def27-109">Sie können die Beschreibung der neuen Instanz bearbeiten oder eine Beschreibung hinzufügen, falls Sie diesen Schritt beim Erstellen der CDC-Instanz nicht ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="def27-109">You can edit the description of the new instance or add one if you did not do so when creating the CDC Instance.</span></span>  
  
 <span data-ttu-id="def27-110">**Oracle Connect String**</span><span class="sxs-lookup"><span data-stu-id="def27-110">**Oracle Connect String**</span></span>  
 <span data-ttu-id="def27-111">Dies ist die Oracle-Verbindungszeichenfolge zum Computer mit der verwendeten Oracle-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="def27-111">The Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="def27-112">Dieses Feld ist schreibgeschützt, und Sie können diese Informationen nicht bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="def27-112">This field is read only and you cannot edit this information.</span></span> <span data-ttu-id="def27-113">Dies liegt daran, dass bei bestimmten Änderungen an der Verbindungszeichenfolge für die Oracle CDC-Instanz möglicherweise auf eine völlig andere Oracle-Datenbank verwiesen wird, sodass der in der Tabelle **cdc.xdbcdc_config** gespeicherte CDC-Instanzstatus beschädigt wird.</span><span class="sxs-lookup"><span data-stu-id="def27-113">This is because some changes to the connect string may point the Oracle CDC Instance to another Oracle database entirely, corrupting the CDC Instance state as stored in the **cdc.xdbcdc_config** table.</span></span> <span data-ttu-id="def27-114">Wenn kleinere Änderungen erforderlich sind, können Sie die Verbindungszeichenfolge mithilfe von SQL Server Management Studio direkt in der Konfigurationstabelle ändern.</span><span class="sxs-lookup"><span data-stu-id="def27-114">If minor changes are needed, you can change the connect string directly in the configuration table using SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="def27-115">**Oracle Log Mining Authentication**</span><span class="sxs-lookup"><span data-stu-id="def27-115">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="def27-116">Um die Authentifizierungsinformationen für die Oracle-Datenbank einzugeben, in der die Log Mining-Komponente enthalten ist, wählen Sie unter **Authentifizierung**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="def27-116">To enter the authentication credentials for the Oracle database that contains the log miner, select one of the following under **Authentication**:</span></span>  
  
-   <span data-ttu-id="def27-117">**Windows-Authentifizierung**: Wählen Sie diese Option, um die aktuellen Anmeldeinformationen für die Windows-Domäne zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="def27-117">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="def27-118">Sie können diese Option nur verwenden, wenn die Oracle-Datenbank für die Nutzung der Windows-Authentifizierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="def27-118">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="def27-119">**Oracle Authentication**: Wenn Sie diese Option aktivieren, müssen Sie **Benutzername** und **Kennwort** für den Benutzer der Oracle-Datenbank eingeben, mit der Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="def27-119">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
 <span data-ttu-id="def27-120">Sie können die Oracle-Datenbankeigenschaften im Viewer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="def27-120">You can view the Oracle database properties in the viewer.</span></span> <span data-ttu-id="def27-121">Beim Verwenden des Viewers sind die Informationen schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="def27-121">When using the viewer the information is read only.</span></span> <span data-ttu-id="def27-122">Der Viewer enthält auch eine Liste der aufgezeichneten Spalten in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="def27-122">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="def27-123">Informationen zum Zugriff auf den Viewer finden Sie unter [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="def27-123">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def27-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="def27-124">See Also</span></span>  
 <span data-ttu-id="def27-125">[Verwalten eines CDC Service über die CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="def27-125">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 <span data-ttu-id="def27-126">[Herstellen einer Verbindung mit einer Oracle-Quelldatenbank](connect-to-an-oracle-source-database.md) </span><span class="sxs-lookup"><span data-stu-id="def27-126">[Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md) </span></span>  
 [<span data-ttu-id="def27-127">Herstellen einer Verbindung mit Oracle</span><span class="sxs-lookup"><span data-stu-id="def27-127">Connect to Oracle</span></span>](connect-to-oracle.md)  
  
  
