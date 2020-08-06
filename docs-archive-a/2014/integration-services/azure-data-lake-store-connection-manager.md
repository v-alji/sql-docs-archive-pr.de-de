---
title: Azure Data Lake Store-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSCM.F1
- SQL11.DTS.DESIGNER.AFPADLSCM.F1
ms.assetid: 7f1323f9-9dc3-4378-9c70-bbc65bfeabfd
author: yualan
ms.author: chugu
ms.openlocfilehash: 1ab6e90aad6472cc10bbb12cf4ca17def501bf00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724054"
---
# <a name="azure-data-lake-store-connection-manager"></a><span data-ttu-id="e8c02-102">Azure Data Lake Store-Verbindungsmanager</span><span class="sxs-lookup"><span data-stu-id="e8c02-102">Azure Data Lake Store Connection Manager</span></span>
  <span data-ttu-id="e8c02-103">Der **Azure Data Lake Store-Verbindungsmanager** ermöglicht, dass ein SSIS-Paket eine Verbindung mit einem Azure Data Lake Store-Dienst durch zwei Authentifizierungstypen herstellt: Azure AD User Identity und Azure AD Service Identity.</span><span class="sxs-lookup"><span data-stu-id="e8c02-103">The **Azure Data Lake Store connection manager** enables an SSIS package to connect to an Azure Data Lake Store service through two authentication types: Azure AD User Identity and Azure AD Service Identity.</span></span>  

## <a name="configure-the-azure-data-lake-store-connection-manager"></a><span data-ttu-id="e8c02-104">Konfigurieren des Azure Data Lake Store-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="e8c02-104">Configure the Azure Data Lake Store Connection Manager</span></span> 
  
1.  <span data-ttu-id="e8c02-105">Wählen Sie im Dialogfeld **SSIS-Verbindungs-Manager hinzufügen** die Option **AzureDataLake**aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e8c02-105">In the **Add SSIS Connection Manager** dialog box, select **AzureDataLake**, and click **Add**.</span></span>   
  
2.  <span data-ttu-id="e8c02-106">Geben Sie im Dialogfeld Azure Data Lake Store-Verbindungsmanager-Editor die URL des Azure Data Lake Store-Host in das Feld **ADLS Host** ein.</span><span class="sxs-lookup"><span data-stu-id="e8c02-106">In the Azure Data Lake Store Connection Manager Editor dialog box, type in the Azure Data Lake Store host URL in **ADLS Host** field.</span></span> <span data-ttu-id="e8c02-107">Beispiel: https: \/ /Test.azuredatalakestore.net oder Test.azuredatalakestore.net.</span><span class="sxs-lookup"><span data-stu-id="e8c02-107">For example: https:\//test.azuredatalakestore.net or test.azuredatalakestore.net.</span></span>
  
3.  <span data-ttu-id="e8c02-108">Wählen Sie den entsprechenden Authentifizierungstyp für den Zugriff auf Azure Data Lake Store-Daten aus.</span><span class="sxs-lookup"><span data-stu-id="e8c02-108">Choose corresponding authentication type to access Azure Data Lake Store data.</span></span>

    1.  <span data-ttu-id="e8c02-109">Wenn Sie die Option **Azure AD User Identity** ausgewählt haben, führen Sie folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e8c02-109">If you selected **Azure AD User Identity** authentication option, do the following:</span></span>

        1. <span data-ttu-id="e8c02-110">Geben Sie Werte für die Felder **Benutzername** und **Kennwort** an.</span><span class="sxs-lookup"><span data-stu-id="e8c02-110">Specify values for the **User Name** and **Password** field.</span></span> 
    
        2. <span data-ttu-id="e8c02-111">Klicken Sie auf die Schaltfläche **Verbindung testen** , um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="e8c02-111">Click **Test Connection** button to test the connection.</span></span> <span data-ttu-id="e8c02-112">Wenn Sie und der Mandantenadministrator vorher nicht zugestimmt haben, dass SSIS auf Azure Data Lake Store-Daten zugreift, müssen Sie auf die Schaltfläche **Annehmen** klicken, um im Popout-Dialog die Zustimmung zu erteilen, dass SSIS auf Ihre Azure Data Lake Store-Daten zugreifen darf.</span><span class="sxs-lookup"><span data-stu-id="e8c02-112">If you and your tenant administrator didn't consent SSIS to access your Azure Data Lake Store data before, you need click **Accept** button to consent SSIS to access your Azure Data Lake Store data in the pop out dialog.</span></span> <span data-ttu-id="e8c02-113">Weitere Informationen über diese Zustimmungsoberfläche finden Sie unter [Integrieren von Anwendungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="e8c02-113">For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span></span>
    
        > [!NOTE] 
        > <span data-ttu-id="e8c02-114">Bei der Authentifizierungsoption „Azure AD User Identity“ werden die mehrstufige Authentifizierung und das Microsoft-Konto NICHT unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8c02-114">For Azure AD User Identity authentication option, multi-factor authentication and Microsoft account is NOT supported.</span></span>
    
    2.  <span data-ttu-id="e8c02-115">Wenn Sie die Option **Azure AD Service Identity** ausgewählt haben, führen Sie Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="e8c02-115">If you selected **Azure AD Service Identity** authentication option, do the following:</span></span>
        1. <span data-ttu-id="e8c02-116">Erstellen Sie eine AAD-Anwendung und ein Dienstprinzipal, die auf Azure Data Lake-Ressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e8c02-116">Create an AAD application and service principal that can access Azure Data Lake resources.</span></span>
    
        2. <span data-ttu-id="e8c02-117">Weisen Sie dieser AAD-Anwendung die entsprechenden Berechtigungen zu, um auf Ihre Azure Data Lake-Ressourcen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e8c02-117">Assign this AAD application corresponding permissions to access your Azure Data Lake resources.</span></span> <span data-ttu-id="e8c02-118">Weitere Informationen zu dieser Authentifizierungsoption finden Sie unter [Use portal to create Active Directory application and service principal that can access resources (Verwenden von Portal zum Erstellen von Active Directory-Anwendungen und Dienstprinzipal zum Zugriff auf Ressourcen)](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="e8c02-118">For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>
    
        3. <span data-ttu-id="e8c02-119">Geben Sie Werte für die Felder **Client-ID**, **Geheimer Schlüssel** , und **Mandantenname** an.</span><span class="sxs-lookup"><span data-stu-id="e8c02-119">Specify values for **Client Id**, **Secret Key** and **Tenant Name** field.</span></span>
    
        4. <span data-ttu-id="e8c02-120">Klicken Sie auf die Schaltfläche **Verbindung testen** , um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="e8c02-120">Click **Test Connection** button to test the connection.</span></span>  
  
4.  <span data-ttu-id="e8c02-121">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e8c02-121">Click **OK** to close the dialog box.</span></span>  
  
    <span data-ttu-id="e8c02-122">Die Eigenschaften des Verbindungs-Managers, die Sie im Fenster **Eigenschaften** erstellt haben, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8c02-122">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
