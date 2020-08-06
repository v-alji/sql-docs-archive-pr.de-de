---
title: 'Aufgabe 9: Konfigurieren eines Verweis Daten dienstanweises | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d0535fce-2bf5-4f6d-b517-ffe6fa13738d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1e7c685de13a2f5c495482f816818ff6b838fc7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726325"
---
# <a name="task-9-configuring-a-reference-data-service"></a><span data-ttu-id="ccb05-102">Aufgabe 9: Konfigurieren eines Verweisdatendiensts</span><span class="sxs-lookup"><span data-stu-id="ccb05-102">Task 9: Configuring a Reference Data Service</span></span>
  <span data-ttu-id="ccb05-103">In dieser Aufgabe konfigurieren Sie DQS für die Verwendung eines Reference Data Service auf Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="ccb05-103">In this task, you configure DQS to use a Reference Data Service on Azure Marketplace.</span></span> <span data-ttu-id="ccb05-104">In der nächsten Aufgabe konfigurieren Sie die **Adress** Überprüfungs Domäne so, dass dieser Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ccb05-104">In the next task, you will configure the **Address Validation** domain to use this service.</span></span> <span data-ttu-id="ccb05-105">Während der Bereinigungs Aktivität übergibt DQS während der Bereinigungs Aktivität die Werte der Domänen in der **Adress** Überprüfungs Domäne an den Dienst für die Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="ccb05-105">At runtime, during cleansing activity, DQS passes the values of domains in the **Address Validation** domain to the service for cleansing.</span></span> <span data-ttu-id="ccb05-106">Weitere Informationen finden [Sie unter Konfigurieren von DQS zum Verwenden von Verweis Daten](https://msdn.microsoft.com/library/hh213070.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ccb05-106">See [Configure DQS to Use Reference Data](https://msdn.microsoft.com/library/hh213070.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="ccb05-107">Klicken Sie im Bereich **Verwaltung** auf der **DQS-Client**-Hauptseite auf **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ccb05-107">In the main page of **DQS Client**, in the **Administration** pane, click **Configuration**.</span></span>  
  
2.  <span data-ttu-id="ccb05-108">Stellen Sie sicher, dass die Registerkarte **Verweis Daten** aktiv ist</span><span class="sxs-lookup"><span data-stu-id="ccb05-108">Ensure that **Reference Data** tab is active.</span></span>  
  
3.  <span data-ttu-id="ccb05-109">Geben Sie im Bereich **Netzwerkeinstellungen** entsprechende Werte in den Feldern **Proxy Server** und **Port** ein, wenn Sie einen Proxy Server zum Herstellen einer Verbindung mit dem Internet verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="ccb05-109">In the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** fields if you need to use a proxy server to connect to Internet.</span></span>  
  
4.  <span data-ttu-id="ccb05-110">Geben Sie Ihren **Azure Marketplace Kontoschlüssel** für das Feld **ID des datamarket-Kontos** ein.</span><span class="sxs-lookup"><span data-stu-id="ccb05-110">Type your **Azure Marketplace Account Key** for the **DataMarket Account ID** field.</span></span>  
  
     <span data-ttu-id="ccb05-111">![Verweisdatendienstkonto für den Azure Data Market](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Verweisdatendienstkonto für den Azure Data Market")</span><span class="sxs-lookup"><span data-stu-id="ccb05-111">![Azure Data Market Reference Data Service Account](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Azure Data Market Reference Data Service Account")</span></span>  
  
5.  <span data-ttu-id="ccb05-112">Klicken **Sie** neben dem Textfeld auf überprüfen, um die Konto-ID zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ccb05-112">Click **Validate** button next to the text box to validate the account ID.</span></span>  
  
6.  <span data-ttu-id="ccb05-113">Klicken Sie im Meldungs Feld auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="ccb05-113">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="ccb05-114">Klicken Sie unten auf der Seite auf **Schließen** , um zur Hauptseite des DQS-Clients zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ccb05-114">Click **Close** at the bottom of the page to switch to the main page of DQS Client.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="ccb05-115">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="ccb05-115">Next Task</span></span>  
 [<span data-ttu-id="ccb05-116">Aufgabe 10: Konfigurieren der Verbunddomäne für die Verwendung von Verweisdatendiensten</span><span class="sxs-lookup"><span data-stu-id="ccb05-116">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>](../../2014/tutorials/task-10-configuring-composite-domain-to-use-reference-data-service.md)  
  
  
