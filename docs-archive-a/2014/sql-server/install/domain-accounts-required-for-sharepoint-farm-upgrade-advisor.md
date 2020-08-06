---
title: Erforderliche Domänen Konten für die SharePoint-Farm (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 90cd6d3e-a271-4cb8-81f2-fc555b2d3cab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7d180fbc12a264256156c878916838f7caeec723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622403"
---
# <a name="domain-accounts-required-for-sharepoint-farm-upgrade-advisor"></a><span data-ttu-id="754d7-102">Erforderliche Domänenkonten für SharePoint-Farmen (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="754d7-102">Domain accounts required for SharePoint farm (Upgrade Advisor)</span></span>
  <span data-ttu-id="754d7-103">SharePoint-Produkte, die für eine Farmumgebung konfiguriert werden, erfordern die Verwendung von Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="754d7-103">SharePoint products that are configured for a farm environment require that you use domain accounts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="754d7-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Im SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="754d7-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="754d7-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="754d7-105">Component</span></span>  
 [!INCLUDE[ssRS](../../includes/ssrs.md)]  
  
### <a name="description"></a><span data-ttu-id="754d7-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="754d7-106">Description</span></span>  
 <span data-ttu-id="754d7-107">SharePoint-Produkte, die für eine Farmumgebung konfiguriert werden, erfordern die Verwendung von Domänenkonten für Dienste und Datenbankverbindungen.</span><span class="sxs-lookup"><span data-stu-id="754d7-107">SharePoint products that are configured for a farm environment require that you use domain accounts for services and database connections.</span></span> <span data-ttu-id="754d7-108">Dies schließt das Konto ein, das Sie für das Reporting Services-Dienstkonto angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="754d7-108">This includes the account you have specified for the Reporting Services service account.</span></span>  
  
 <span data-ttu-id="754d7-109">SharePoint 2010 Central Administration-Seiten sind eine Stelle, an der Probleme entstehen, wenn Sie kein Domänenbenutzerkonto für Reporting Services verwenden.</span><span class="sxs-lookup"><span data-stu-id="754d7-109">SharePoint 2010 Central Administration pages are one place you will see problems if you are not using a domain user account for Reporting Services.</span></span> <span data-ttu-id="754d7-110">Wenn Sie versuchen, die Reporting Services-Integration zu konfigurieren, wird Ihnen eine Fehlermeldung wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="754d7-110">When you try to configure Reporting Services integration, you will see an error message similar to the following:</span></span>  
  
 <span data-ttu-id="754d7-111">"Der Berichtsserver wird auf dem integrierten NT AUTHORITY\NETWORK SERVICE-Konto ausgeführt, das von einer SharePoint-Farminstallation nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="754d7-111">"The report server is running under the built-in NT AUTHORITY\NETWORK SERVICE account, which is not supported by a SharePoint farm installation.</span></span> <span data-ttu-id="754d7-112">Konfigurieren Sie den Berichtsserver neu, sodass dieser unter einem Domänenkonto ausgeführt wird."</span><span class="sxs-lookup"><span data-stu-id="754d7-112">Please reconfigure the report server to run under a domain account."</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="754d7-113">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="754d7-113">Corrective Action</span></span>  
 <span data-ttu-id="754d7-114">[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Verwenden Sie für und frühere Versionen die Konfigurations-Manager für Reporting Services, um das Konto zu ändern, das als Berichts Server-Dienst Konto zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="754d7-114">For [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and previous versions, use the Reporting Services Configuration Manager to change the account that is assigned as the report server service account.</span></span>  
  
#### <a name="to-change-the-service-account-from-configuration-manager"></a><span data-ttu-id="754d7-115">So ändern Sie das Dienstkonto im Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="754d7-115">To change the service account from Configuration Manager</span></span>  
  
1.  <span data-ttu-id="754d7-116">Wählen Sie im **Startmenü** **Alle Programme**aus, und klicken Sie dann auf **Microsoft SQL Server 2008 R2**.</span><span class="sxs-lookup"><span data-stu-id="754d7-116">From the **Start** menu, select **All Programs**, and then click **Microsoft SQL Server 2008 R2**.</span></span>  
  
2.  <span data-ttu-id="754d7-117">Wählen Sie **Konfigurationstools**aus, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="754d7-117">Select **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="754d7-118">Wählen Sie in Configuration Manager die Registerkarte **Dienst Konto** aus.</span><span class="sxs-lookup"><span data-stu-id="754d7-118">In Configuration Manager, select the **Service Account** tab.</span></span>  
  
4.  <span data-ttu-id="754d7-119">Wählen Sie **anderes Konto verwenden** aus, und geben Sie die Anmelde Informationen eines Domänen Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="754d7-119">Select **Use another account** and enter the credentials for a domain account.</span></span>  
  
5.  <span data-ttu-id="754d7-120">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="754d7-120">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754d7-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="754d7-121">See Also</span></span>  
 [<span data-ttu-id="754d7-122">Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="754d7-122">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
  
  
