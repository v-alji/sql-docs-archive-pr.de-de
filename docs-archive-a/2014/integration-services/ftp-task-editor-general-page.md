---
title: Editor für den FTP-Task (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.general.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 28b46fdd-b04a-4f97-a99f-883f5735a6d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0cb4ffe2fa44e76890f6b70912f84dbcaa8f2cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615441"
---
# <a name="ftp-task-editor-general-page"></a><span data-ttu-id="36119-102">Editor für den FTP-Task (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="36119-102">FTP Task Editor (General Page)</span></span>
  <span data-ttu-id="36119-103">Mithilfe der Seite **Allgemein** des Dialogfelds **Editor für den FTP-Task** können Sie den FTP-Verbindungs-Manager angeben, der die Verbindung mit dem FTP-Server herstellt, mit dem der Task kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="36119-103">Use the **General** page of the **FTP Task Editor** dialog box to specify the FTP connection manager that connects to the FTP server that the task communicates with.</span></span> <span data-ttu-id="36119-104">Sie können den FTP-Task außerdem benennen und eine Beschreibung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36119-104">You can also name and describe the FTP task.</span></span>  
  
 <span data-ttu-id="36119-105">Informationen zu diesem Task finden Sie unter [FTP-Task](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="36119-105">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="36119-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="36119-106">Options</span></span>  
 <span data-ttu-id="36119-107">**FtpConnection**</span><span class="sxs-lookup"><span data-stu-id="36119-107">**FtpConnection**</span></span>  
 <span data-ttu-id="36119-108">Wählen Sie einen vorhandenen FTP-Verbindungs-Manager aus, oder klicken Sie auf \<**New connection...**>, um einen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="36119-108">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="36119-109">Der FTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="36119-109">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="36119-110">Er unterstützt keine Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="36119-110">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="36119-111">**Verwandte Themen:** [FTP-Verbindungs-Manager](connection-manager/ftp-connection-manager.md), [FTP-Verbindungs-Manager-Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="36119-111">**Related Topics**: [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="36119-112">**StopOnFailure**</span><span class="sxs-lookup"><span data-stu-id="36119-112">**StopOnFailure**</span></span>  
 <span data-ttu-id="36119-113">Geben Sie an, ob der FTP-Task beendet wird, wenn ein FTP-Vorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="36119-113">Indicate whether the FTP task terminates if an FTP operation fails.</span></span>  
  
 <span data-ttu-id="36119-114">**Name**</span><span class="sxs-lookup"><span data-stu-id="36119-114">**Name**</span></span>  
 <span data-ttu-id="36119-115">Geben Sie einen eindeutigen Namen für den FTP-Task an.</span><span class="sxs-lookup"><span data-stu-id="36119-115">Provide a unique name for the FTP task.</span></span> <span data-ttu-id="36119-116">Dieser Name wird im Tasksymbol als Bezeichnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="36119-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36119-117">Tasknamen müssen innerhalb eines Pakets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="36119-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="36119-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="36119-118">**Description**</span></span>  
 <span data-ttu-id="36119-119">Geben Sie eine Beschreibung des FTP-Tasks ein.</span><span class="sxs-lookup"><span data-stu-id="36119-119">Type a description of the FTP task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36119-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36119-120">See Also</span></span>  
 <span data-ttu-id="36119-121">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="36119-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="36119-122">[FTP-Task-Editor &#40;Seite "Dateiübertragung"&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="36119-122">[FTP Task Editor &#40;File Transfer Page&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span></span>  
 [<span data-ttu-id="36119-123">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="36119-123">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
