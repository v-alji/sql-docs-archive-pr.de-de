---
title: Oracle-Verleger | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.selectoraclepublisher.f1
ms.assetid: 019b7c49-dcca-445d-8969-5982a8ccbc1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: db52b93b3d260ff58a151e7238bbbe065bc47bc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608552"
---
# <a name="oracle-publisher"></a><span data-ttu-id="111f6-102">Oracle-Verleger</span><span class="sxs-lookup"><span data-stu-id="111f6-102">Oracle Publisher</span></span>
  <span data-ttu-id="111f6-103">Ab [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] erlaubt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Ihnen das Veröffentlichen von Daten aus einer Oracle-Datenbank mithilfe einer Momentaufnahme und der Transaktionsreplikation.</span><span class="sxs-lookup"><span data-stu-id="111f6-103">Beginning with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to publish data from an Oracle database using snapshot and transactional replication.</span></span> <span data-ttu-id="111f6-104">Weitere Informationen finden Sie unter [Veröffentlichungen mit Oracle (Übersicht)](non-sql/oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="111f6-104">For more information, see [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="111f6-105">Der Oracle-Verleger muss einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Remoteverteiler verwenden, und auf diesem Server muss der Assistent ausgeführt werden, nachdem die erforderliche Oracle-Netzwerksoftware installiert und getestet wurde.</span><span class="sxs-lookup"><span data-stu-id="111f6-105">The Oracle Publisher must use a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor; this wizard must be run on that server after the necessary Oracle networking software has been installed and tested.</span></span> <span data-ttu-id="111f6-106">Weitere Informationen finden Sie unter [Konfigurieren eines Oracle-Verlegers](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="111f6-106">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="111f6-107">Wenn ein anderer Administrator die Oracle-Datenbank als Verleger konfiguriert hat, werden Sie nach dem Klicken auf **Weiter** aufgefordert, das Kennwort für die Replikationsanmeldung einzugeben, die zum Herstellen der Verbindung mit der Oracle-Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="111f6-107">If another administrator configured the Oracle database as a Publisher, after clicking **Next** you will be prompted to enter the password for the replication login used to connect to the Oracle database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="111f6-108">erstellt dann eine Zuordnung zwischen der Anmeldung und der Verbindung des Verbindungsservers mit der Oracle-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="111f6-108">will then create a mapping between your login and the linked server connection to the Oracle database.</span></span> <span data-ttu-id="111f6-109">Bei den folgenden Verbindungen mit der Oracle-Datenbank werden Sie nicht mehr aufgefordert, ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="111f6-109">You will not be required to enter a password for subsequent connections to the Oracle database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="111f6-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="111f6-110">Options</span></span>  
 <span data-ttu-id="111f6-111">**Oracle-Verleger**</span><span class="sxs-lookup"><span data-stu-id="111f6-111">**Oracle Publishers**</span></span>  
 <span data-ttu-id="111f6-112">Wählen Sie einen Oracle-Verleger aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="111f6-112">Select an Oracle Publisher from the list.</span></span> <span data-ttu-id="111f6-113">Die Liste enthält die Oracle-Verleger, die zuvor für die Verwendung des Servers konfiguriert wurden, für den der Assistent nun als Verteiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="111f6-113">This list contains Oracle Publishers that have previously been configured to use the server against which the wizard is running as their Distributor.</span></span> <span data-ttu-id="111f6-114">Wenn die Liste keine Einträge enthält oder den von Ihnen gewünschten Oracle-Verleger nicht beinhaltet, klicken Sie auf **Oracle-Verleger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="111f6-114">If the list is empty, or the Oracle Publisher you want to use is not in the list, click **Add Oracle Publisher**.</span></span>  
  
 <span data-ttu-id="111f6-115">**Oracle-Verleger hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="111f6-115">**Add Oracle Publisher**</span></span>  
 <span data-ttu-id="111f6-116">Klicken Sie auf diese Option, um das Dialogfeld **Verteilereigenschaften** zu starten.</span><span class="sxs-lookup"><span data-stu-id="111f6-116">Click to launch the **Distributor Properties** dialog box.</span></span> <span data-ttu-id="111f6-117">Klicken Sie im Dialogfeld auf **Hinzufügen**, und klicken Sie auf **Oracle-Verleger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="111f6-117">In this dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span> <span data-ttu-id="111f6-118">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** den Oracle-Servernamen sowie den Anmeldenamen und das Kennwort für das Schema des administrativen Replikationsbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="111f6-118">In the **Connect to Server** dialog box, specify the Oracle server name, and the login and password for the replication administrative user schema.</span></span> <span data-ttu-id="111f6-119">Weitere Informationen finden Sie unter [Verbindung mit Server herstellen &#40;Oracle&#41;, Anmeldename](connect-to-server-oracle-login.md).</span><span class="sxs-lookup"><span data-stu-id="111f6-119">For more information, see [Connect to Server &#40;Oracle&#41;, Login](connect-to-server-oracle-login.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="111f6-120">Wenn der Server, für den der Assistent ausgeführt wird, noch nicht als Verteiler konfiguriert ist, werden Sie aufgefordert, ihn jetzt zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="111f6-120">If the server against which the wizard is running has not yet been configured as a Distributor, you are prompted to configure it now.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111f6-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="111f6-121">See Also</span></span>  
 [<span data-ttu-id="111f6-122">Erstellen einer Veröffentlichung aus einer Oracle-Datenbank</span><span class="sxs-lookup"><span data-stu-id="111f6-122">Create a Publication from an Oracle Database</span></span>](publish/create-a-publication-from-an-oracle-database.md)   

  
  
