---
title: Für SQL Server-Verbindung erforderliche Berechtigungen für den CDC Service | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9e968f9-180c-4fa0-a849-98f2b1942330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e63b98ffd0371bd5b70ecc0ac843ad40a4a5d03e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616635"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-service"></a><span data-ttu-id="5af2e-102">Für SQL Server-Verbindung erforderliche Berechtigungen für den CDC Service</span><span class="sxs-lookup"><span data-stu-id="5af2e-102">SQL Server Connection Required Permissions for the CDC Service</span></span>
  <span data-ttu-id="5af2e-103">Die CDC Service Configuration Console erfordert Verbindungsinformationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , um die damit verbundenen Tasks auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5af2e-103">The CDC Service Configuration Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform their tasks.</span></span> <span data-ttu-id="5af2e-104">In diesem Thema werden die Informationen beschrieben, die im Dialogfeld Verbindung mit SQL Server herstellen zum Einrichten der Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="5af2e-104">This topic describes the information that can be provided in the Connect to SQL Server dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5af2e-105">Das Dialogfeld Verbindung mit SQL Server herstellen wird jeweils bei Bedarf geöffnet, z. B. wenn keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindungsinformationen verfügbar sind oder wenn die Informationen zwar vorhanden sind, aber die Verbindung nicht die erforderlichen Berechtigungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="5af2e-105">The Connect to SQL Server dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="5af2e-106">In der folgenden Tabelle werden die verschiedenen Tasks beschrieben, für die eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erforderlich ist, sowie die erforderlichen Berechtigungen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer (Anmeldung).</span><span class="sxs-lookup"><span data-stu-id="5af2e-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="5af2e-107">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5af2e-107">Task</span></span>|<span data-ttu-id="5af2e-108">Mindestberechtigungen</span><span class="sxs-lookup"><span data-stu-id="5af2e-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="5af2e-109">Vorbereiten der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz</span><span class="sxs-lookup"><span data-stu-id="5af2e-109">Prepare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance.</span></span>|<span data-ttu-id="5af2e-110">`dbcreator` Feste Serverrolle</span><span class="sxs-lookup"><span data-stu-id="5af2e-110">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="5af2e-111">Erstellen einer Oracle CDC Service-SQL Server-Anmeldung zur Verwendung durch den Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="5af2e-111">Create an Oracle CDC Service-SQL Server login for use by the Oracle CDC service.</span></span>|<span data-ttu-id="5af2e-112">`public` Feste Serverrolle</span><span class="sxs-lookup"><span data-stu-id="5af2e-112">`public` fixed-server role</span></span>|  
|<span data-ttu-id="5af2e-113">Erstellen einer Oracle CDC Service-Anmeldung, die zum Registrieren des neuen Diensts in MSXDBCDC verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="5af2e-113">Create an Oracle CDC Service-login to use for registering the new service in MSXDBCDC.</span></span>|<span data-ttu-id="5af2e-114">`db_datareader` und `db_datawriter` für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="5af2e-114">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="5af2e-115">Bearbeiten einer Oracle CDC Service-Anmeldung, die zum Aktualisieren der Registrierung des Diensts in MSXDBCDC verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="5af2e-115">Edit an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="5af2e-116">`db_datareader` und `db_datawriter` für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="5af2e-116">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="5af2e-117">Löschen einer Oracle CDC Service-Anmeldung, die zum Aktualisieren der Registrierung des Diensts in MSXDBCDC verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="5af2e-117">Delete an Oracle CDC Service-login to use for updating the registration of the service in MSXDBCDC.</span></span>|<span data-ttu-id="5af2e-118">`db_datareader` und `db_datawriter` für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="5af2e-118">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5af2e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5af2e-119">See Also</span></span>  
 <span data-ttu-id="5af2e-120">[Verbindung zu SQL Server](connection-to-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5af2e-120">[Connection to SQL Server](connection-to-sql-server.md) </span></span>  
 [<span data-ttu-id="5af2e-121">Verbindung zu SQL Server zum Löschen</span><span class="sxs-lookup"><span data-stu-id="5af2e-121">Connection to SQL Server for Delete</span></span>](connection-to-sql-server-for-delete.md)  
  
  
