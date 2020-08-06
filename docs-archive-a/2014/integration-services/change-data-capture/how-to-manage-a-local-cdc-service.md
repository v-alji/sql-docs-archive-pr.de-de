---
title: Verwalten eines lokalen CDC Service | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 437590d4b91f2fc80d5bb8a90251bf0dc7c8e18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694673"
---
# <a name="how-to-manage-a-local-cdc-service"></a><span data-ttu-id="331ba-102">Verwalten eines lokalen CDC Service</span><span class="sxs-lookup"><span data-stu-id="331ba-102">How to Manage a Local CDC Service</span></span>
  <span data-ttu-id="331ba-103">In diesem Verfahren wird beschrieben, wie Sie die CDC Service Configuration Console zum Verwalten bestimmter CDC-Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="331ba-103">This procedure describes how to use the CDC Service Configuration Console to manage specific CDC services.</span></span>  
  
### <a name="to-manage-a-specific-cdc-service"></a><span data-ttu-id="331ba-104">So verwalten Sie einen bestimmten CDC Service</span><span class="sxs-lookup"><span data-stu-id="331ba-104">To manage a specific CDC Service</span></span>  
  
1.  <span data-ttu-id="331ba-105">Wählen Sie im Menü **Start** die Option **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="331ba-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="331ba-106">Erweitern Sie links in der CDC Service Configuration Console den Punkt **Local CDC Services**.</span><span class="sxs-lookup"><span data-stu-id="331ba-106">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
3.  <span data-ttu-id="331ba-107">Wählen Sie den CDC-Dienst aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="331ba-107">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="331ba-108">Sie können auch mit der rechten Maustaste auf den gewünschten CDC-Dienst klicken und die gewünschte Aktion auswählen.</span><span class="sxs-lookup"><span data-stu-id="331ba-108">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
     <span data-ttu-id="331ba-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="331ba-109">**OR**</span></span>  
  
     <span data-ttu-id="331ba-110">Wählen Sie links in der CDC Service Configuration Console die Option **Local CDC Services** und dann im mittleren Bereich der CDC Service Configuration Console den Dienst aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="331ba-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console then select the service you want to work with from the middle section of the CDC Service Configuration Console.</span></span>  
  
     <span data-ttu-id="331ba-111">Sie können auch mit der rechten Maustaste auf den gewünschten CDC-Dienst klicken und die gewünschte Aktion auswählen.</span><span class="sxs-lookup"><span data-stu-id="331ba-111">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
4.  <span data-ttu-id="331ba-112">Beim Verwenden eines CDC-Diensts können Sie die folgenden Tasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="331ba-112">You can carry out the following tasks when working with a CDC service.</span></span>  
  
    -   <span data-ttu-id="331ba-113">**Löschen des Diensts**</span><span class="sxs-lookup"><span data-stu-id="331ba-113">**Delete the service**</span></span>  
  
         <span data-ttu-id="331ba-114">Klicken Sie im **Aktionsbereich** rechts in der CDC Service Configuration Console auf **Löschen** , um den Dienst zu löschen.</span><span class="sxs-lookup"><span data-stu-id="331ba-114">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
         <span data-ttu-id="331ba-115">Sie können auch mit der rechten Maustaste auf den CDC-Dienst klicken, den Sie löschen möchten, und dann **Löschen**wählen.</span><span class="sxs-lookup"><span data-stu-id="331ba-115">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
         <span data-ttu-id="331ba-116">**Hinweis**: Falls der Dienst beim Löschen des Diensts ausgeführt wird, wird der Dienst vor dem Löschvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="331ba-116">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
         <span data-ttu-id="331ba-117">Zum Löschen der Definition des Oracle CDC-Windows-Diensts benötigt das Programm Aktualisierungszugriff auf die MSXDBCDC-Datenbank in der zugeordneten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz.</span><span class="sxs-lookup"><span data-stu-id="331ba-117">To delete an Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="331ba-118">Wenn Sie auf **OK** klicken, um den Dienst zu löschen, versucht das Programm, die Oracle CDC Service-Registrierung in der MSXDBCDC-Datenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="331ba-118">When you click **OK** to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="331ba-119">Falls bei dem Vorgang aufgrund fehlender Berechtigungen ein Fehler auftritt, wird der Benutzer über ein angezeigtes Dialogfeld aufgefordert, eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung mit Aktualisierungszugriff auf die MSXDBCDC-Datenbank einzugeben.</span><span class="sxs-lookup"><span data-stu-id="331ba-119">If it fails due to lack of permissions, a dialog box is displayed to prompt the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
         <span data-ttu-id="331ba-120">Informationen zu den Daten, die Sie im Dialogfeld Verbindung mit SQL Server herstellen eingeben müssen, finden Sie unter [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) und [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="331ba-120">For information about the data you must enter in the Connect to SQL Server dialog box, see [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) and [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
    -   <span data-ttu-id="331ba-121">**Bearbeiten der Eigenschaften des CDC Service**</span><span class="sxs-lookup"><span data-stu-id="331ba-121">**Edit the CDC Service Properties**</span></span>  
  
         <span data-ttu-id="331ba-122">Klicken Sie im **Aktionsbereich** rechts in der CDC Service Configuration Console auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="331ba-122">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
         <span data-ttu-id="331ba-123">Sie können auch mit der rechten Maustaste auf den CDC-Dienst klicken, für den Sie die Eigenschaften bearbeiten möchten, und dann **Eigenschaften**wählen.</span><span class="sxs-lookup"><span data-stu-id="331ba-123">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="331ba-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="331ba-124">See Also</span></span>  
 [<span data-ttu-id="331ba-125">Verwalten eines Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="331ba-125">Manage an Oracle CDC Service</span></span>](manage-an-oracle-cdc-service.md)  
  
  
