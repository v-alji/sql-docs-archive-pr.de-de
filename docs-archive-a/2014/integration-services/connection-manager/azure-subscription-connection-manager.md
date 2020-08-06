---
title: Azure-Abonnementverbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpsubscrconn.f1
- sql11.dts.designer.afpsubscrconn.f1
ms.assetid: e1225327-c308-4c50-8f44-c411f52ef378
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bff1286525983b32c2191f1f8864a0f2bef0e6b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618223"
---
# <a name="azure-subscription-connection-manager"></a><span data-ttu-id="bc2bd-102">Azure-Abonnementverbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="bc2bd-102">Azure Subscription Connection Manager</span></span>
  <span data-ttu-id="bc2bd-103">Der Azure HDInsight-Verbindungs-Manager ermöglicht die Verbindung eines SSIS-Pakets mit einem Azure-Abonnement, indem die Werte verwendet werden, die Sie für die folgenden Eigenschaften angeben: Azure-Abonnement-ID und das Verwaltungszertifikat.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-103">The Azure HDInsight connection manager enables an SSIS package to connect to an Azure subscription by using the values you specify for the properties: Azure Subscription ID and Management Certificate.</span></span>

1.  <span data-ttu-id="bc2bd-104">Wählen Sie im oben angezeigten Dialogfeld **SSIS-Verbindungs-Manager hinzufügen** die Option **Azure-Abonnement**aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-104">In the **Add SSIS Connection Manager** dialog box shown above, you select **Azure Subscription**, and click **Add**.</span></span>  <span data-ttu-id="bc2bd-105">Das Dialogfeld **Azure-Abonnementverbindungs-Manager-Editor** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-105">You should see the following **Azure Subscription Connection Manager Editor** dialog box.</span></span>

     <span data-ttu-id="bc2bd-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span><span class="sxs-lookup"><span data-stu-id="bc2bd-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span></span>

2.  <span data-ttu-id="bc2bd-107">Geben Sie Ihre Azure-Abonnement-ID, die ein Azure-Abonnement eindeutig identifiziert, in **Azure-Abonnement-ID**ein.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-107">Enter your Azure subscription ID, which uniquely identifies an Azure subscription, for the **Azure subscription ID**.</span></span>  <span data-ttu-id="bc2bd-108">Der Wert befindet sich im [Azure-Verwaltungsportal](https://manage.windowsazure.com) auf der Seite **Einstellungen** :</span><span class="sxs-lookup"><span data-stu-id="bc2bd-108">The value can be found on the [Azure Management Portal](https://manage.windowsazure.com) under **Settings** page:</span></span>

     <span data-ttu-id="bc2bd-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span><span class="sxs-lookup"><span data-stu-id="bc2bd-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span></span>

3.  <span data-ttu-id="bc2bd-110">Wählen Sie **Verwaltungszertifikatspeicherort** und **Verwaltungszertifikatspeichername** aus den Dropdownlisten aus.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-110">Choose **Management certificate store location** and **Management certificate store name** from the drop-down lists.</span></span>

4.  <span data-ttu-id="bc2bd-111">Geben Sie **Management certificate thumbprint** (Fingerabdruck für as Verwaltungszertifikat) ein, oder klicken Sie auf **Durchsuchen...**, um ein Zertifikat aus dem ausgewählten Store auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-111">Enter **Management certificate thumbprint** or click the **Browse...** to choose a certificate from the selected store.</span></span> <span data-ttu-id="bc2bd-112">Das Zertifikat muss als Verwaltungszertifikat für das Abonnement hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-112">The certificate must be uploaded as a management certificate for the subscription.</span></span> <span data-ttu-id="bc2bd-113">Klicken Sie hierzu auf der folgenden Seite des Azure-Portals auf **Hochladen** (in diesem [MSDN-Beitrag](https://msdn.microsoft.com/library/azure/gg551722.aspx) finden Sie weitere Informationen).</span><span class="sxs-lookup"><span data-stu-id="bc2bd-113">To do so, click **Upload** on the following page of the Azure Portal (see this [MSDN post](https://msdn.microsoft.com/library/azure/gg551722.aspx) for more detail).</span></span>

     <span data-ttu-id="bc2bd-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span><span class="sxs-lookup"><span data-stu-id="bc2bd-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span></span>

5.  <span data-ttu-id="bc2bd-115">Klicken Sie auf **Verbindung testen** , um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-115">Click **Test Connection** to test the connection.</span></span>

6.  <span data-ttu-id="bc2bd-116">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bc2bd-116">Click **OK** to close the dialog box.</span></span>


