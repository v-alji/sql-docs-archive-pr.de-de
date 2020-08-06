---
title: Verwalten eines Oracle CDC Service | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 5972cee3-b1a9-4c56-aed6-bdddf84af283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5fbe769980297a06b7958ecad04bfed85b9b714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695953"
---
# <a name="manage-an-oracle-cdc-service"></a><span data-ttu-id="f43ed-102">Manage an Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="f43ed-102">Manage an Oracle CDC Service</span></span>
  <span data-ttu-id="f43ed-103">Sie können die CDC Service Configuration Console verwenden, um einen bestimmten CDC Service zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f43ed-103">You can use the CDC Service Configuration Console to manage a specific CDC Service.</span></span>  
  
 <span data-ttu-id="f43ed-104">**So wählen Sie den gewünschten CDC Service aus**</span><span class="sxs-lookup"><span data-stu-id="f43ed-104">**To select the CDC service you want to work with**</span></span>  
  
1.  <span data-ttu-id="f43ed-105">Erweitern Sie links in der CDC Service Configuration Console den Punkt **Local CDC Services**.</span><span class="sxs-lookup"><span data-stu-id="f43ed-105">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
2.  <span data-ttu-id="f43ed-106">Wählen Sie den CDC-Dienst aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f43ed-106">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="f43ed-107">Sie können auch mit der rechten Maustaste auf den gewünschten CDC-Dienst klicken und die gewünschte Aktion auswählen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-107">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="f43ed-108">Siehe [Mögliche Verwendung eines CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="f43ed-108">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
 <span data-ttu-id="f43ed-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="f43ed-109">**OR**</span></span>  
  
1.  <span data-ttu-id="f43ed-110">Wählen Sie im linken Bereich der CDC Service Configuration Console die Option **Local CDC Services** .</span><span class="sxs-lookup"><span data-stu-id="f43ed-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console.</span></span>  
  
2.  <span data-ttu-id="f43ed-111">Wählen Sie im mittleren Bereich der CDC Service Configuration Console den Dienst aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f43ed-111">From the middle section of the CDC Service Configuration Console, select the service you want to work with.</span></span>  
  
     <span data-ttu-id="f43ed-112">Sie können auch mit der rechten Maustaste auf den gewünschten CDC-Dienst klicken und die gewünschte Aktion auswählen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-112">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="f43ed-113">Siehe [Mögliche Verwendung eines CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="f43ed-113">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
##  <a name="what-can-you-do-with-a-cdc-service"></a><a name="BKMK_WhatcandowithCDCService"></a> <span data-ttu-id="f43ed-114">Mögliche Verwendung eines CDC Service</span><span class="sxs-lookup"><span data-stu-id="f43ed-114">What can you do with a CDC Service</span></span>  
 <span data-ttu-id="f43ed-115">Beim Verwenden eines CDC-Diensts können Sie die folgenden Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-115">You can carry out the following actions when working with a CDC service.</span></span>  
  
### <a name="delete-the-service"></a><span data-ttu-id="f43ed-116">Löschen des Diensts</span><span class="sxs-lookup"><span data-stu-id="f43ed-116">Delete the service</span></span>  
 <span data-ttu-id="f43ed-117">Klicken Sie im **Aktionsbereich** rechts in der CDC Service Configuration Console auf **Löschen** , um den Dienst zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-117">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
 <span data-ttu-id="f43ed-118">Sie können auch mit der rechten Maustaste auf den CDC-Dienst klicken, den Sie löschen möchten, und dann **Löschen**wählen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-118">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
 <span data-ttu-id="f43ed-119">**Hinweis**: Falls der Dienst beim Löschen des Diensts ausgeführt wird, wird der Dienst vor dem Löschvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="f43ed-119">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
 <span data-ttu-id="f43ed-120">Zum Löschen der Definition des Oracle CDC-Windows-Diensts benötigt das Programm Aktualisierungszugriff auf die MSXDBCDC-Datenbank in der zugeordneten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="f43ed-120">To delete the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="f43ed-121">Wenn Sie auf OK klicken, um den Dienst zu löschen, versucht das Programm, die Oracle CDC Service-Registrierung in der MSXDBCDC-Datenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-121">When you click OK to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="f43ed-122">Wenn das Programm die Oracle CDC Service-Registrierung nicht löschen kann, weil es nicht über die richtigen Berechtigungen verfügt, wird der Benutzer aufgefordert, eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung mit Aktualisierungsberechtigungen für die MSXDBCDC-Datenbank einzugeben.</span><span class="sxs-lookup"><span data-stu-id="f43ed-122">If the program cannot delete the Oracle CDC Service registration because it does not have the proper permissions, it prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with update permissions to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="f43ed-123">Informationen zu den Daten, die Sie im Dialogfeld Verbindung mit SQL Server herstellen eingeben müssen, finden Sie unter [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="f43ed-123">For information about the data you must enter in the Connect to SQL Server dialog box, see [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
### <a name="edit-the-cdc-service-properties"></a><span data-ttu-id="f43ed-124">Bearbeiten der Eigenschaften des CDC Service</span><span class="sxs-lookup"><span data-stu-id="f43ed-124">Edit the CDC Service Properties</span></span>  
 <span data-ttu-id="f43ed-125">Klicken Sie im **Aktionsbereich** rechts in der CDC Service Configuration Console auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f43ed-125">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
 <span data-ttu-id="f43ed-126">Sie können auch mit der rechten Maustaste auf den CDC-Dienst klicken, für den Sie die Eigenschaften bearbeiten möchten, und dann **Eigenschaften**wählen.</span><span class="sxs-lookup"><span data-stu-id="f43ed-126">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43ed-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f43ed-127">See Also</span></span>  
 [<span data-ttu-id="f43ed-128">Verwalten eines lokalen CDC Service</span><span class="sxs-lookup"><span data-stu-id="f43ed-128">How to Manage a Local CDC Service</span></span>](how-to-manage-a-local-cdc-service.md)  
