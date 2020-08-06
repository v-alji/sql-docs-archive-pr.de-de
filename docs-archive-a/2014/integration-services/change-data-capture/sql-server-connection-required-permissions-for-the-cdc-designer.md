---
title: Für SQL Server-Verbindung erforderliche Berechtigungen für den CDC Designer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0815a5d8f1cb66dee0d290a45166ebb395c8efa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608781"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a><span data-ttu-id="60573-102">SQL Server-Verbindung erfordert Berechtigungen für den CDC Designer</span><span class="sxs-lookup"><span data-stu-id="60573-102">SQL Server Connection Required Permissions for the CDC Designer</span></span>
  <span data-ttu-id="60573-103">Die CDC Designer Console erfordert für die Ausführung ihrer Tasks Verbindungsinformationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60573-103">The CDC Designer Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform its tasks.</span></span> <span data-ttu-id="60573-104">In diesem Thema werden die Informationen beschrieben, die im Dialogfeld **Verbindung mit SQL Server herstellen** zum Einrichten der Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="60573-104">This topic describes the information that can be provided in the **Connect to SQL Server** dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="60573-105">Das Dialogfeld **Verbindung mit SQL Server herstellen** wird jeweils bei Bedarf geöffnet, z. B. wenn keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindungsinformationen verfügbar sind oder wenn die Informationen zwar vorhanden sind, aber die Verbindung nicht die erforderlichen Berechtigungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="60573-105">The **Connect to SQL Server** dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="60573-106">In der folgenden Tabelle werden die verschiedenen Tasks beschrieben, für die eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erforderlich ist, sowie die erforderlichen Berechtigungen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benutzer (Anmeldung).</span><span class="sxs-lookup"><span data-stu-id="60573-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="60573-107">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="60573-107">Task</span></span>|<span data-ttu-id="60573-108">Mindestberechtigungen</span><span class="sxs-lookup"><span data-stu-id="60573-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="60573-109">Anzeigen der Liste mit den CDC-Diensten und -Instanzen, die die zugeordnete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz verwenden</span><span class="sxs-lookup"><span data-stu-id="60573-109">View the list of CDC Services and Instances using the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>|<span data-ttu-id="60573-110">`db_datareader` -Rolle für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="60573-110">`db_datareader` role on MSXDBCDC</span></span>|  
|<span data-ttu-id="60573-111">Starten/Beenden von CDC-Instanzen</span><span class="sxs-lookup"><span data-stu-id="60573-111">Start/Stop CDC Instance(s)</span></span>|<span data-ttu-id="60573-112">`db_datareader` und `db_datawriter` für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="60573-112">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="60573-113">Anzeigen des CDC-Instanzstatus</span><span class="sxs-lookup"><span data-stu-id="60573-113">View the CDC Instance status.</span></span>|<span data-ttu-id="60573-114">`db_owner` -Rolle für die CDC-Instanzdatenbank</span><span class="sxs-lookup"><span data-stu-id="60573-114">`db_owner` role on the CDC Instance database</span></span>|  
|<span data-ttu-id="60573-115">Erstellen einer neuen Oracle CDC-Instanzdatenbank</span><span class="sxs-lookup"><span data-stu-id="60573-115">Create a new Oracle CDC Instance database.</span></span>|<span data-ttu-id="60573-116">`dbcreator` Feste Serverrolle</span><span class="sxs-lookup"><span data-stu-id="60573-116">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="60573-117">Erstellen einer neuen Oracle CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="60573-117">Create a new Oracle CDC Instance.</span></span>|<span data-ttu-id="60573-118">`db_datareader` -Rolle für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="60573-118">`db_datareader` role on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="60573-119">`db_owner` -Rolle für die erstellte CDC-Datenbank</span><span class="sxs-lookup"><span data-stu-id="60573-119">`db_owner` role on the CDC database that was created.</span></span>|  
|<span data-ttu-id="60573-120">Abrufen von Bereitstellungsskripts</span><span class="sxs-lookup"><span data-stu-id="60573-120">Get deployment scripts.</span></span>|<span data-ttu-id="60573-121">`db_datareader` und `db_datawriter` für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="60573-121">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="60573-122">`db_owner` -Rolle für die zugehörige CDC-Datenbank</span><span class="sxs-lookup"><span data-stu-id="60573-122">`db_owner` role on the relatedCDC database</span></span>|  
|<span data-ttu-id="60573-123">Ändern der Konfiguration und Hinzufügen/Entfernen von Aufzeichnungsinstanzen</span><span class="sxs-lookup"><span data-stu-id="60573-123">Change configuration and add/remove capture instances.</span></span>|<span data-ttu-id="60573-124">`db_datareader` und `db_datawriter` für MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="60573-124">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="60573-125">`db_owner` -Rolle für die zugehörige CDC-Datenbank</span><span class="sxs-lookup"><span data-stu-id="60573-125">`db_owner` role on the related CDC database</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60573-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60573-126">See Also</span></span>  
 <span data-ttu-id="60573-127">[Zugreifen auf die CDC Designer Console](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="60573-127">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="60573-128">SQL Server-Verbindung für die Instanzerstellung</span><span class="sxs-lookup"><span data-stu-id="60573-128">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
