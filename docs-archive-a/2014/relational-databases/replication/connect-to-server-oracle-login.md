---
title: Verbindung mit Server herstellen (Oracle), Anmeldename | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23f5b515fcb1e80416d860e2ff3a2e6be5431819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608574"
---
# <a name="connect-to-server-oracle-login"></a><span data-ttu-id="f12b4-102">Verbindung mit Server herstellen (Oracle), Anmeldename</span><span class="sxs-lookup"><span data-stu-id="f12b4-102">Connect to Server (Oracle), Login</span></span>
  <span data-ttu-id="f12b4-103">Auf der Registerkarte **Anmeldename** des Dialogfelds **Verbindung mit Server herstellen** können Sie das Konto angeben, unter dem der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verteiler Verbindungen mit dem Oracle-Verleger herstellt.</span><span class="sxs-lookup"><span data-stu-id="f12b4-103">Use the **Login** tab of the **Connect to Server** dialog box to specify the account under which connections are made from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher.</span></span> <span data-ttu-id="f12b4-104">Sie müssen dafür dasselbe Konto verwenden wie für das Schema des administrativen Replikationsbenutzers, das Sie bei der Konfiguration des Verlegers angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f12b4-104">You must use the same account as the one specified for the replication administrative user schema during configuration of the Publisher.</span></span> <span data-ttu-id="f12b4-105">Weitere Informationen finden Sie unter [Konfigurieren eines Oracle-Verlegers](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="f12b4-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f12b4-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f12b4-106">Options</span></span>  
 <span data-ttu-id="f12b4-107">**Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="f12b4-107">**Server instance**</span></span>  
 <span data-ttu-id="f12b4-108">Der TNS-Name (Transparent Network Substrate) des Oracle-Verlegers, der bei Konfiguration der auf dem Verteiler installierten Oracle-Clientsoftware angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f12b4-108">The Transparent Network Substrate (TNS) name of the Oracle Publisher, which is specified during configuration of the Oracle client software installed on the Distributor.</span></span>  
  
 <span data-ttu-id="f12b4-109">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="f12b4-109">**Authentication**</span></span>  
 <span data-ttu-id="f12b4-110">Wählen Sie **Oracle-Standardauthentifizierung** (empfohlen) oder **Windows-Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="f12b4-110">Select **Oracle Standard Authentication** (recommended) or **Windows Authentication**.</span></span> <span data-ttu-id="f12b4-111">Bei Auswahl von **Windows-Authentifizierung**:</span><span class="sxs-lookup"><span data-stu-id="f12b4-111">If you select **Windows Authentication**:</span></span>  
  
-   <span data-ttu-id="f12b4-112">Der Oracle-Server muss so konfiguriert sein, dass mit den Windows-Anmeldeinformationen Verbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f12b4-112">The Oracle server must be configured to allow connections using Windows credentials.</span></span> <span data-ttu-id="f12b4-113">Weitere Informationen finden Sie in der Oracle-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f12b4-113">For more information, see the Oracle documentation.</span></span>  
  
-   <span data-ttu-id="f12b4-114">Sie müssen dazu auf demselben [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto angemeldet sein, wie für das Schema des administrativen Replikationsbenutzers angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f12b4-114">You must be currently logged in with the same [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account you specified for the replication administrative user schema.</span></span>  
  
 <span data-ttu-id="f12b4-115">**Anmeldename** und **Kennwort**</span><span class="sxs-lookup"><span data-stu-id="f12b4-115">**Login** and **Password**</span></span>  
 <span data-ttu-id="f12b4-116">Wenn Sie für die **Authentifizierung** die Option **Oracle-Standardauthentifizierung** ausgewählt haben, geben Sie den zu verwendenden Anmeldenamen und das Kennwort an. Verwenden Sie dabei dieselben Angaben wie für das Schema des administrativen Replikationsbenutzers.</span><span class="sxs-lookup"><span data-stu-id="f12b4-116">If you selected **Oracle Standard Authentication** for the **Authentication** option, specify the login and password to use, which must be the same as those specified for the replication administrative user schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12b4-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f12b4-117">See Also</span></span>  
 [<span data-ttu-id="f12b4-118">Begriffe im Zusammenhang mit dem Veröffentlichen von Oracle-Daten</span><span class="sxs-lookup"><span data-stu-id="f12b4-118">Glossary of Terms for Oracle Publishing</span></span>](non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
