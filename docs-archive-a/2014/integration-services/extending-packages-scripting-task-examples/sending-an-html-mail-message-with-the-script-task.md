---
title: Senden einer HTML-E-Mail mit dem Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Send Mail task [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], HTML mail message
ms.assetid: dd2b1eef-b04f-4946-87ab-7bc56bb525ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c1a967b52a84e1ff9c2e54c48e40f4d149b2dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695861"
---
# <a name="sending-an-html-mail-message-with-the-script-task"></a><span data-ttu-id="faa0f-102">Senden einer HTML-E-Mail mit dem Skripttask</span><span class="sxs-lookup"><span data-stu-id="faa0f-102">Sending an HTML Mail Message with the Script Task</span></span>
  <span data-ttu-id="faa0f-103">Der Task „Mail senden“ in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] unterstützt nur E-Mails im Nur-Text-Format.</span><span class="sxs-lookup"><span data-stu-id="faa0f-103">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] SendMail task only supports mail messages in plain text format.</span></span> <span data-ttu-id="faa0f-104">Sie können jedoch problemlos HTML-E-Mails mithilfe des Skripttasks und den E-Mail-Funktionen des .NET Framework senden.</span><span class="sxs-lookup"><span data-stu-id="faa0f-104">However you can easily send HTML mail messages by using the Script task and the mail capabilities of the .NET Framework.</span></span>

> [!NOTE]
>  <span data-ttu-id="faa0f-105">Wenn Sie einen Task erstellen möchten, den Sie einfacher in mehreren Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skripttaskbeispiel als Ausgangspunkt für einen benutzerdefinierten Task zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="faa0f-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="faa0f-106">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="faa0f-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="faa0f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="faa0f-107">Description</span></span>
 <span data-ttu-id="faa0f-108">Im folgenden Beispiel wird der `System.Net.Mail`-Namespace verwendet, um eine HTML-E-Mail zu konfigurieren und zu senden.</span><span class="sxs-lookup"><span data-stu-id="faa0f-108">The following example uses the `System.Net.Mail` namespace to configure and send an HTML mail message.</span></span> <span data-ttu-id="faa0f-109">Das Skript ruft den Empfänger, den Absender, den Betreff und den Text der E-Mail aus Paketvariablen ab, verwendet diese zur Erstellung einer neuen `MailMessag`, und legt deren `IsBodyHtml`-Eigenschaft auf `True` fest.</span><span class="sxs-lookup"><span data-stu-id="faa0f-109">The script obtains the To, From, Subject, and body of the e-mail from package variables, uses them to create a new `MailMessag`e, and sets its `IsBodyHtml` property to `True`.</span></span> <span data-ttu-id="faa0f-110">Es ruft dann den SMTP-Servernamen aus einer weiteren Paketvariablen ab, initialisiert eine Instanz von `System.Net.Mail.SmtpClient` und ruft die `Send`-Methode zum Senden der HTML-Nachricht auf.</span><span class="sxs-lookup"><span data-stu-id="faa0f-110">Then it obtains the SMTP server name from another package variable, initializes an instance of `System.Net.Mail.SmtpClient`, and calls its `Send` method to send the HTML message.</span></span> <span data-ttu-id="faa0f-111">Im Beispiel wird die Funktionalität zum Senden der Nachricht in eine Unterroutine gekapselt, die in anderen Skripts wiederverwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="faa0f-111">The sample encapsulates the message sending functionality in a subroutine that could be reused in other scripts.</span></span>

#### <a name="to-configure-this-script-task-example-without-an-smtp-connection-manager"></a><span data-ttu-id="faa0f-112">So konfigurieren Sie dieses Skripttaskbeispiel ohne einen SMTP-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="faa0f-112">To configure this Script Task example without an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="faa0f-113">Erstellen Sie Zeichenfolgenvariablen mit den Namen `HtmlEmailTo`, `HtmlEmailFrom` und `HtmlEmailSubject`, und weisen Sie diesen entsprechende Werte für eine gültige Testnachricht zu.</span><span class="sxs-lookup"><span data-stu-id="faa0f-113">Create string variables named `HtmlEmailTo`, `HtmlEmailFrom`, and `HtmlEmailSubject` and assign appropriate values to them for a valid test message.</span></span>

2.  <span data-ttu-id="faa0f-114">Erstellen Sie eine Zeichenfolgenvariable mit dem Namen `HtmlEmailBody`, und weisen Sie dieser eine Zeichenfolge eines HTML-Markups zu.</span><span class="sxs-lookup"><span data-stu-id="faa0f-114">Create a string variable named `HtmlEmailBody` and assign a string of HTML markup to it.</span></span> <span data-ttu-id="faa0f-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="faa0f-115">For example:</span></span>

    ```
    <html><body><h1>Testing</h1><p>This is a <b>test</b> message.</p></body></html>
    ```

3.  <span data-ttu-id="faa0f-116">Erstellen Sie eine Zeichenfolgenvariable mit dem Namen `HtmlEmailServer`, und weisen Sie den Namen eines verfügbaren SMTP-Servers zu, der anonyme ausgehende Nachrichten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="faa0f-116">Create a string variable named `HtmlEmailServer` and assign the name of an available SMTP server that accepts anonymous outgoing messages.</span></span>

4.  <span data-ttu-id="faa0f-117">Weisen Sie alle fünf Variablen der **ReadOnlyVariables**-Eigenschaft eines neuen Skripttasks zu.</span><span class="sxs-lookup"><span data-stu-id="faa0f-117">Assign all five of these variables to the **ReadOnlyVariables** property of a new Script task.</span></span>

5.  <span data-ttu-id="faa0f-118">Importieren Sie die Namespaces `System.Net` und `System.Net.Mail` in Ihren Code.</span><span class="sxs-lookup"><span data-stu-id="faa0f-118">Import the `System.Net` and `System.Net.Mail` namespaces into your code.</span></span>

 <span data-ttu-id="faa0f-119">In dem Beispielcode in diesem Thema wird der Name des SMTP-Servers aus einer Paketvariablen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="faa0f-119">The sample code in this topic obtains the SMTP server name from a package variable.</span></span> <span data-ttu-id="faa0f-120">Sie könnten jedoch auch einen SMTP-Verbindungs-Manager nutzen, um die Verbindungsinformationen zu kapseln, und den Servernamen aus dem Verbindungs-Manager in Ihrem Code extrahieren.</span><span class="sxs-lookup"><span data-stu-id="faa0f-120">However, you could also take advantage of an SMTP connection manager to encapsulate the connection information, and extract the server name from the connection manager in your code.</span></span> <span data-ttu-id="faa0f-121">Die <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A>-Methode des SMTP-Verbindungs-Managers gibt eine Zeichenfolge im folgenden Format zurück:</span><span class="sxs-lookup"><span data-stu-id="faa0f-121">The <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> method of the SMTP connection manager returns a string in the following format:</span></span>

 `SmtpServer=smtphost;UseWindowsAuthentication=False;EnableSsl=False;`

 <span data-ttu-id="faa0f-122">Sie können die `String.Split`-Methode verwenden, um diese Argumentliste bei jedem Semikolon (;) oder Gleichheitszeichen (=) in ein Array einzelner Zeichenfolgen zu trennen und das zweite Argument (Subskript 1) dann als Servernamen aus dem Array extrahieren.</span><span class="sxs-lookup"><span data-stu-id="faa0f-122">You can use the `String.Split` method to separate this argument list into an array of individual strings at each semicolon (;) or equal sign (=), and then extract the second argument (subscript 1) from the array as the server name.</span></span>

#### <a name="to-configure-this-script-task-example-with-an-smtp-connection-manager"></a><span data-ttu-id="faa0f-123">So konfigurieren Sie dieses Skripttaskbeispiel mit einem SMTP-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="faa0f-123">To configure this Script Task example with an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="faa0f-124">Ändern Sie den zuvor konfigurierten Skripttask, indem Sie die `HtmlEmailServer`-Variable aus der Liste von **ReadOnlyVariables**-Variablen entfernen.</span><span class="sxs-lookup"><span data-stu-id="faa0f-124">Modify the Script task configured earlier by removing the `HtmlEmailServer` variable from the list of **ReadOnlyVariables**.</span></span>

2.  <span data-ttu-id="faa0f-125">Ersetzen Sie die folgende Codezeile, die den Servernamen abruft:</span><span class="sxs-lookup"><span data-stu-id="faa0f-125">Replace the line of code that obtains the server name:</span></span>

    ```
    Dim smtpServer As String = _
      Dts.Variables("HtmlEmailServer").Value.ToString
    ```

     <span data-ttu-id="faa0f-126">durch die folgenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="faa0f-126">with the following lines:</span></span>

    ```
    Dim smtpConnectionString As String = _
      DirectCast(Dts.Connections("SMTP Connection Manager").AcquireConnection(Dts.Transaction), String)
    Dim smtpServer As String = _
      smtpConnectionString.Split(New Char() {"="c, ";"c})(1)
    ```

## <a name="code"></a><span data-ttu-id="faa0f-127">Code</span><span class="sxs-lookup"><span data-stu-id="faa0f-127">Code</span></span>

```vb
Public Sub Main()

  Dim htmlMessageTo As String = _
    Dts.Variables("HtmlEmailTo").Value.ToString
  Dim htmlMessageFrom As String = _
    Dts.Variables("HtmlEmailFrom").Value.ToString
  Dim htmlMessageSubject As String = _
    Dts.Variables("HtmlEmailSubject").Value.ToString
  Dim htmlMessageBody As String = _
    Dts.Variables("HtmlEmailBody").Value.ToString
  Dim smtpServer As String = _
    Dts.Variables("HtmlEmailServer").Value.ToString

  SendMailMessage( _
      htmlMessageTo, htmlMessageFrom, _
      htmlMessageSubject, htmlMessageBody, _
      True, smtpServer)

  Dts.TaskResult = ScriptResults.Success

End Sub

Private Sub SendMailMessage( _
    ByVal SendTo As String, ByVal From As String, _
    ByVal Subject As String, ByVal Body As String, _
    ByVal IsBodyHtml As Boolean, ByVal Server As String)

  Dim htmlMessage As MailMessage
  Dim mySmtpClient As SmtpClient

  htmlMessage = New MailMessage( _
    SendTo, From, Subject, Body)
  htmlMessage.IsBodyHtml = IsBodyHtml

  mySmtpClient = New SmtpClient(Server)
  mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials
  mySmtpClient.Send(htmlMessage)

End Sub
```

```csharp
public void Main()
        {

            string htmlMessageTo = Dts.Variables["HtmlEmailTo"].Value.ToString();
            string htmlMessageFrom = Dts.Variables["HtmlEmailFrom"].Value.ToString();
            string htmlMessageSubject = Dts.Variables["HtmlEmailSubject"].Value.ToString();
            string htmlMessageBody = Dts.Variables["HtmlEmailBody"].Value.ToString();
            string smtpServer = Dts.Variables["HtmlEmailServer"].Value.ToString();

            SendMailMessage(htmlMessageTo, htmlMessageFrom, htmlMessageSubject, htmlMessageBody, true, smtpServer);

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private void SendMailMessage(string SendTo, string From, string Subject, string Body, bool IsBodyHtml, string Server)
        {

            MailMessage htmlMessage;
            SmtpClient mySmtpClient;

            htmlMessage = new MailMessage(SendTo, From, Subject, Body);
            htmlMessage.IsBodyHtml = IsBodyHtml;

            mySmtpClient = new SmtpClient(Server);
            mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials;
            mySmtpClient.Send(htmlMessage);

        }
```

<span data-ttu-id="faa0f-128">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="faa0f-128">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="faa0f-129">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="faa0f-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="faa0f-130">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="faa0f-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="faa0f-131">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="faa0f-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="faa0f-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="faa0f-132">See Also</span></span>
 [<span data-ttu-id="faa0f-133">Mail senden (Task)</span><span class="sxs-lookup"><span data-stu-id="faa0f-133">Send Mail Task</span></span>](../control-flow/send-mail-task.md)


