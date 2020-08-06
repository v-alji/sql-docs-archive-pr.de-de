---
title: Vorbereiten von SQL Server für CDC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a327fa18-58f4-4e69-bb87-44faf47e20ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbd285faaa55a28ad82beb673fa783570809bd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694666"
---
# <a name="how-to-prepare-sql-server-for-cdc"></a><span data-ttu-id="673dc-102">Vorbereiten von SQL Server für CDC</span><span class="sxs-lookup"><span data-stu-id="673dc-102">How to Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="673dc-103">Der Oracle CDC Service erfordert, dass alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanzen die MSXDBCDC-Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="673dc-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="673dc-104">Sie erstellen diese Datenbank mithilfe der Aktion Prepare SQL Server in der CDC Service Configuration Console. Dieser Task wird für jede [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz nur einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="673dc-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="673dc-105">Unten wird beschrieben, wie Sie eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank mithilfe der CDC Service Configuration Console auf Oracle Change Data Capture vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="673dc-105">The following describes how to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for Oracle Change Data Capture using the CDC Service Configuration Console.</span></span> <span data-ttu-id="673dc-106">Bei diesem Prozess wird die MSXDBCDC-Datenbank erstellt, und die erforderlichen Tabellen, gespeicherten Prozeduren und anderen erforderlichen Artefakte werden definiert.</span><span class="sxs-lookup"><span data-stu-id="673dc-106">This process creates the MSXDBCDC database and defines the required tables, stored procedures, and other required artifacts.</span></span>  
  
 <span data-ttu-id="673dc-107">Das Vorbereiten von SQL Server for Oracle CDC wird vom Oracle CDC Service-Administrator durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="673dc-107">Preparing the SQL Server for Oracle CDC is done by the Oracle CDC Service Administrator.</span></span> <span data-ttu-id="673dc-108">Weitere Informationen zur CDC Service-Administrator Rolle finden Sie unter [Benutzer Rollen für Change Data Capture Service für Oracle von Attunity](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="673dc-108">For more information about the CDC Service Administrator role, see [User Roles for Change Data Capture Service for Oracle by Attunity](user-roles.md).</span></span>  
  
### <a name="to-enable-sql-server-for-cdc"></a><span data-ttu-id="673dc-109">So aktivieren Sie SQL Server für CDC</span><span class="sxs-lookup"><span data-stu-id="673dc-109">To enable SQL Server for CDC</span></span>  
  
1.  <span data-ttu-id="673dc-110">Wählen Sie im Menü **Start** die Option **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="673dc-110">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="673dc-111">Wählen Sie im linken Bereich die Option **Local CDC Services** , und klicken Sie dann im **Aktionsbereich** auf **Prepare SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="673dc-111">From the left pane, select **Local CDC Services** then from the **Actions** pane, click **Prepare SQL Server**.</span></span>  
  
     <span data-ttu-id="673dc-112">Sie können auch mit der rechten Maustaste auf **Local CDC Services** klicken und **Prepare SQL Server**wählen.</span><span class="sxs-lookup"><span data-stu-id="673dc-112">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
3.  <span data-ttu-id="673dc-113">Geben Sie die erforderlichen Informationen im Dialogfeld Preparing SQL Server Instance for Oracle CDC ein.</span><span class="sxs-lookup"><span data-stu-id="673dc-113">Enter the required information in the Preparing SQL Server Instance for Oracle CDC dialog box.</span></span> <span data-ttu-id="673dc-114">Informationen zum Eingeben der erforderlichen Informationen in dieses Dialogfeld finden Sie unter [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="673dc-114">For information on how to enter the required information into this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span>  
  
     <span data-ttu-id="673dc-115">Um die SQL Server-Instanz für Oracle CDC vorzubereiten, muss die Anmeldung über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="673dc-115">To Prepare the SQL Server instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="673dc-116">Geben Sie die Anmeldeinformationen für eine Anmeldung ein, die über die Schreibberechtigung für die MSXDBCDC-Datenbank verfügt, z. B. als Mitglied der Rolle `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="673dc-116">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
 <span data-ttu-id="673dc-117">**Hinweis**: Sie können auf **Skript anzeigen** klicken, um eine schreibgeschützte Version des Setupskripts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="673dc-117">**Note**: You can click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="673dc-118">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemadministrator kann dieses Skript bei Bedarf in die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console kopieren, um sie zu bearbeiten und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="673dc-118">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console to edit and execute it, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673dc-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="673dc-119">See Also</span></span>  
 [<span data-ttu-id="673dc-120">Vorbereiten von SQL Server für CDC</span><span class="sxs-lookup"><span data-stu-id="673dc-120">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
