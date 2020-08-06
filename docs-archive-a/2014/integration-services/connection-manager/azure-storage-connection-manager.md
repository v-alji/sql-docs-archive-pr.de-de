---
title: Azure Storage-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpstorageconn.f1
- sql11.dts.designer.afpstorageconn.f1
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47580d8d1d961df9fbcbed0bd7164f1c54792b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618228"
---
# <a name="azure-storage-connection-manager"></a><span data-ttu-id="41b41-102">Azure Storage-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="41b41-102">Azure Storage Connection Manager</span></span>
  <span data-ttu-id="41b41-103">Der Azure Storage-Verbindungs-Manager ermöglicht das Verbinden eines SSIS-Pakets mit einem Azure Storage-Konto mit den Werten, die Sie für die Eigenschaften angeben: Speicherkontoname und Kontoschlüssel.</span><span class="sxs-lookup"><span data-stu-id="41b41-103">The Azure Storage connection manager enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.</span></span>  
  
1.  <span data-ttu-id="41b41-104">Wählen Sie im Dialogfeld **SSIS-Verbindungs-Manager hinzufügen** die Option **AzureStorage**aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="41b41-104">In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="41b41-105">Wählen Sie im Editor-Dialogfeld „Azure Storage-Verbindungs-Manager“ **Azure-Konto verwenden** aus, um eine Verbindung zu einem Azure Storage-Dienst über das Internet herzustellen, oder wählen Sie **Lokales Entwicklerkonto verwenden** aus, um eine Verbindung zum lokalen Dienst herzustellen, der vom Azure Storage-Emulator gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="41b41-105">In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.</span></span>  
  
3.  <span data-ttu-id="41b41-106">Gehen Sie bei Auswahl von **Azure-Konto verwenden** folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="41b41-106">If you selected **Use Azure account** option, do the following:</span></span>  
  
    1.  <span data-ttu-id="41b41-107">Geben Sie Werte in die Felder **Speicherkontoname** und **Kontoschlüssel** an.</span><span class="sxs-lookup"><span data-stu-id="41b41-107">Specify values for the **Storage account name** and **Account key** field.</span></span> <span data-ttu-id="41b41-108">Diese Werte werden als vertrauliche Daten im SSIS-Paket gespeichert.</span><span class="sxs-lookup"><span data-stu-id="41b41-108">These values will be stored as sensitive data in SSIS package.</span></span>  
  
    2.  <span data-ttu-id="41b41-109">Wählen Sie **HTTPS verwenden** aus, wenn Sie HTTPS anstelle von HTTP für die Verbindung mit dem Azure Storage-Dienst verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41b41-109">Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.</span></span>  
  
4.  <span data-ttu-id="41b41-110">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="41b41-110">Click **OK** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="41b41-111">Die Eigenschaften des Verbindungs-Managers, die Sie im Fenster **Eigenschaften** erstellt haben, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41b41-111">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
