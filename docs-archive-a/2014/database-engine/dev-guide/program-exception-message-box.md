---
title: Programm Ausnahme Meldungs Feld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- exception message box [SQL Server]
- displaying exception message box
ms.assetid: c771985b-149c-459a-b3cb-7b15fde01150
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9d49bdf8c73f86b2c334018d40510b4ae67c85ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724910"
---
# <a name="program-exception-message-box"></a><span data-ttu-id="6c40c-102">Programmieren eines Ausnahmemeldungsfelds</span><span class="sxs-lookup"><span data-stu-id="6c40c-102">Program Exception Message Box</span></span>
  <span data-ttu-id="6c40c-103">Mit dem Ausnahmemeldungsfeld können Sie in Ihren Anwendungen das Verhalten von Meldungen erheblich besser bestimmen als mit der <xref:System.Windows.Forms.MessageBox>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6c40c-103">You can use the exception message box in your applications to provide significantly more control over the messaging experience than is provided by the <xref:System.Windows.Forms.MessageBox> class.</span></span> <span data-ttu-id="6c40c-104">Weitere Informationen finden Sie unter [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span><span class="sxs-lookup"><span data-stu-id="6c40c-104">For more information, see [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span></span> <span data-ttu-id="6c40c-105">Weitere Informationen zum Abrufen und Bereitstellen der DLL-Assembly für das Ausnahmemeldungsfeld finden Sie unter [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span><span class="sxs-lookup"><span data-stu-id="6c40c-105">For information about how to obtain and deploy the exception message box .dll, see [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="6c40c-106">Verfahren</span><span class="sxs-lookup"><span data-stu-id="6c40c-106">Procedure</span></span>  
  
#### <a name="to-handle-an-exception-by-using-the-exception-message-box"></a><span data-ttu-id="6c40c-107">So behandeln Sie eine Ausnahme mit dem Ausnahmemeldungsfeld</span><span class="sxs-lookup"><span data-stu-id="6c40c-107">To handle an exception by using the exception message box</span></span>  
  
1.  <span data-ttu-id="6c40c-108">Fügen Sie einen Verweis auf die Microsoft.ExceptionMessageBox.dll-Assembly in das Projekt mit verwaltetem Code ein.</span><span class="sxs-lookup"><span data-stu-id="6c40c-108">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="6c40c-109">Optionale Fügen Sie eine- `using` Direktive (c#) oder- `Imports` [!INCLUDE[msCoName](../../includes/msconame-md.md)] Anweisung (Visual Basic .net) hinzu, um den <xref:Microsoft.SqlServer.MessageBox> Namespace zu verwenden</span><span class="sxs-lookup"><span data-stu-id="6c40c-109">(Optional) Add a `using` (C#) or `Imports` ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="6c40c-110">Erstellen Sie einen try/catch-Block, um die erwartete Ausnahme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="6c40c-110">Create a try-catch block to handle the anticipated exception.</span></span>  
  
4.  <span data-ttu-id="6c40c-111">Erstellen Sie innerhalb des `catch`-Blocks eine Instanz der <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6c40c-111">Within the `catch` block, create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="6c40c-112">Übergeben Sie das <xref:System.Exception> vom-Block behandelte-Objekt `try` - `catch` .</span><span class="sxs-lookup"><span data-stu-id="6c40c-112">Pass the <xref:System.Exception> object handled by the `try`-`catch` block.</span></span>  
  
5.  <span data-ttu-id="6c40c-113">(Optional) Legen Sie eine oder mehrere der folgenden Eigenschaften für <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> fest:</span><span class="sxs-lookup"><span data-stu-id="6c40c-113">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="6c40c-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Enumeration, die die Schaltflächen angibt, die im Ausnahme Meldungs Feld angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6c40c-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>-Enumeration, die die Standard Schaltfläche für das Ausnahme Meldungs Feld angibt.</span><span class="sxs-lookup"><span data-stu-id="6c40c-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Enumeration, die Sie verwenden, um das andere Verhalten des Ausnahme Meldungs Felds zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6c40c-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Enumeration, die das Symbol angibt, das im Ausnahme Meldungs Feld angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c40c-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
6.  <span data-ttu-id="6c40c-118">Rufen Sie die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="6c40c-118">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="6c40c-119">Übergeben Sie das übergeordnete Fenster, zu dem das Ausnahmemeldungsfeld gehört.</span><span class="sxs-lookup"><span data-stu-id="6c40c-119">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="6c40c-120">Optionale Beachten Sie den Wert der zurückgegebenen <xref:System.Windows.Forms.DialogResult> Enumeration, wenn Sie bestimmen müssen, auf welche Schaltfläche der Benutzer geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="6c40c-120">(Optional) Note the value of returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-without-an-exception"></a><span data-ttu-id="6c40c-121">So zeigen Sie das Ausnahmemeldungsfeld ohne Ausnahme an</span><span class="sxs-lookup"><span data-stu-id="6c40c-121">To display the exception message box without an exception</span></span>  
  
1.  <span data-ttu-id="6c40c-122">Fügen Sie einen Verweis auf die Microsoft.ExceptionMessageBox.dll-Assembly in das Projekt mit verwaltetem Code ein.</span><span class="sxs-lookup"><span data-stu-id="6c40c-122">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="6c40c-123">Optionale Fügen Sie eine- `using` Direktive (c#) oder- `Imports` Anweisung (Visual Basic .net) hinzu, um den <xref:Microsoft.SqlServer.MessageBox> Namespace zu verwenden</span><span class="sxs-lookup"><span data-stu-id="6c40c-123">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="6c40c-124">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6c40c-124">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="6c40c-125">Übergeben Sie den Meldungstext als <xref:System.String>-Wert.</span><span class="sxs-lookup"><span data-stu-id="6c40c-125">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="6c40c-126">(Optional) Legen Sie eine oder mehrere der folgenden Eigenschaften für <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> fest:</span><span class="sxs-lookup"><span data-stu-id="6c40c-126">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="6c40c-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Enumeration, die die Schaltflächen angibt, die im Ausnahme Meldungs Feld angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6c40c-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialogfeldbeschriftung des Ausnahmemeldungsfelds.</span><span class="sxs-lookup"><span data-stu-id="6c40c-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialog box caption of the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>-Enumeration, die die Standard Schaltfläche für das Dialogfeld des Ausnahme Meldungs Felds angibt.</span><span class="sxs-lookup"><span data-stu-id="6c40c-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the dialog box of the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Enumeration, die Sie verwenden, um das andere Verhalten des Ausnahme Meldungs Felds zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6c40c-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="6c40c-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Enumeration, die das Symbol angibt, das im Ausnahme Meldungs Feld angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c40c-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
5.  <span data-ttu-id="6c40c-132">Rufen Sie die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="6c40c-132">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="6c40c-133">Übergeben Sie das übergeordnete Fenster, zu dem das Ausnahmemeldungsfeld gehört.</span><span class="sxs-lookup"><span data-stu-id="6c40c-133">Pass the parent window to which the exception message box belongs.</span></span>  
  
6.  <span data-ttu-id="6c40c-134">(Optional) Notieren Sie den Wert der zurückgegebenen <xref:System.Windows.Forms.DialogResult>-Enumeration, wenn Sie bestimmen müssen, auf welche Schaltfläche der Benutzer geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="6c40c-134">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-with-customized-buttons"></a><span data-ttu-id="6c40c-135">So zeigen Sie das Ausnahmemeldungsfeld mit benutzerdefinierten Schaltflächen an</span><span class="sxs-lookup"><span data-stu-id="6c40c-135">To display the exception message box with customized buttons</span></span>  
  
1.  <span data-ttu-id="6c40c-136">Fügen Sie einen Verweis auf die Microsoft.ExceptionMessageBox.dll-Assembly in das Projekt mit verwaltetem Code ein.</span><span class="sxs-lookup"><span data-stu-id="6c40c-136">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="6c40c-137">Optionale Fügen Sie eine- `using` Direktive (c#) oder- `Imports` Anweisung (Visual Basic .net) hinzu, um den <xref:Microsoft.SqlServer.MessageBox> Namespace zu verwenden</span><span class="sxs-lookup"><span data-stu-id="6c40c-137">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="6c40c-138">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>-Klasse. Hierzu haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="6c40c-138">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="6c40c-139">Übergibt das <xref:System.Exception> von einem-Block behandelte-Objekt `try` - `catch` .</span><span class="sxs-lookup"><span data-stu-id="6c40c-139">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="6c40c-140">Übergeben Sie den Meldungstext als <xref:System.String>-Wert.</span><span class="sxs-lookup"><span data-stu-id="6c40c-140">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="6c40c-141">Legen Sie für <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> einen der folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="6c40c-141">Set one of the following values for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span></span>  
  
    -   <span data-ttu-id="6c40c-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore>-zeigt die Schaltflächen **Abbrechen**, **wiederholen**und **ignorieren** an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore> - displays the **Abort**, **Retry**, and **Ignore** buttons.</span></span>  
  
    -   <span data-ttu-id="6c40c-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - zeigt benutzerdefinierte Schaltflächen an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - displays custom buttons.</span></span>  
  
    -   <span data-ttu-id="6c40c-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK>-zeigt die Schaltfläche **OK** an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK> - displays the **OK** button.</span></span>  
  
    -   <span data-ttu-id="6c40c-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel>-zeigt die Schaltflächen **OK** und **Abbrechen** an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel> - displays the **OK** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="6c40c-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel>-zeigt die Schalt **Flächen wiederholen** und **Abbrechen** an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel> - displays the **Retry** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="6c40c-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo>-zeigt die Schaltflächen **Ja** und **Nein** an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo> - displays **Yes** and **No** buttons.</span></span>  
  
    -   <span data-ttu-id="6c40c-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel>-zeigt die Schaltflächen **Ja**, **Nein**und **Abbrechen** an.</span><span class="sxs-lookup"><span data-stu-id="6c40c-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel> - displays **Yes**, **No**, and **Cancel** buttons.</span></span>  
  
5.  <span data-ttu-id="6c40c-149">(Optional) Wenn Sie benutzerdefinierte Schaltflächen verwenden, rufen Sie eine der Überladungen der <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A>-Methode auf, um Text für bis zu fünf benutzerdefinierte Schaltflächen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6c40c-149">(Optional) If you use custom buttons, call one of the overloads of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> method to specify text for up to five custom buttons.</span></span>  
  
6.  <span data-ttu-id="6c40c-150">Rufen Sie die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="6c40c-150">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="6c40c-151">Übergeben Sie das übergeordnete Fenster, zu dem das Ausnahmemeldungsfeld gehört.</span><span class="sxs-lookup"><span data-stu-id="6c40c-151">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="6c40c-152">(Optional) Notieren Sie den Wert der zurückgegebenen <xref:System.Windows.Forms.DialogResult>-Enumeration, wenn Sie bestimmen müssen, auf welche Schaltfläche der Benutzer geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="6c40c-152">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span> <span data-ttu-id="6c40c-153">Wenn Sie benutzerdefinierte Schaltflächen verwenden, notieren Sie den Wert von <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> für die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A>-Eigenschaft, um zu ermitteln, auf welche benutzerdefinierte Schaltfläche der Benutzer geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="6c40c-153">If you use custom buttons, note the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> for the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> property to determine which of the custom buttons the user clicked.</span></span>  
  
#### <a name="to-allow-users-to-decide-whether-to-show-the-exception-message-box"></a><span data-ttu-id="6c40c-154">So ermöglichen Sie Benutzern die Entscheidung darüber, ob das Ausnahmemeldungsfeld angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="6c40c-154">To allow users to decide whether to show the exception message box</span></span>  
  
1.  <span data-ttu-id="6c40c-155">Fügen Sie einen Verweis auf die Microsoft.ExceptionMessageBox.dll-Assembly in das Projekt mit verwaltetem Code ein.</span><span class="sxs-lookup"><span data-stu-id="6c40c-155">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="6c40c-156">Optionale Fügen Sie eine- `using` Direktive (c#) oder- `Imports` Anweisung (Visual Basic .net) hinzu, um den <xref:Microsoft.SqlServer.MessageBox> Namespace zu verwenden</span><span class="sxs-lookup"><span data-stu-id="6c40c-156">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="6c40c-157">Erstellen Sie eine Instanz der <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>-Klasse. Hierzu haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="6c40c-157">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="6c40c-158">Übergibt das <xref:System.Exception> von einem-Block behandelte-Objekt `try` - `catch` .</span><span class="sxs-lookup"><span data-stu-id="6c40c-158">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="6c40c-159">Übergeben Sie den Meldungstext als <xref:System.String>-Wert.</span><span class="sxs-lookup"><span data-stu-id="6c40c-159">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="6c40c-160">Legen Sie die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="6c40c-160">Set the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="6c40c-161">(Optional) Geben Sie den Text an, mit dem der Benutzer aufgefordert wird, zu entscheiden, ob das Ausnahmemeldungsfeld für <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A> erneut angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c40c-161">(Optional) Specify the text that asks the user to decide whether to show the exception message box again for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span></span> <span data-ttu-id="6c40c-162">Der Standardtext lautet: "Diese Meldung nicht mehr anzeigen."</span><span class="sxs-lookup"><span data-stu-id="6c40c-162">The default text is "Do not show this message again."</span></span>  
  
6.  <span data-ttu-id="6c40c-163">Wenn die Entscheidung des Benutzers nur für die Dauer der Anwendungsausführung gültig sein soll, legen Sie den Wert von <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> auf eine globale <xref:System.Boolean>-Variable fest.</span><span class="sxs-lookup"><span data-stu-id="6c40c-163">If you need to keep the user's decision only for the duration of the application's execution, set the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> to a global <xref:System.Boolean> variable.</span></span> <span data-ttu-id="6c40c-164">Werten Sie diesen Wert aus, bevor Sie eine Instanz des Ausnahmemeldungsfelds erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c40c-164">Evaluate this value before creating an instance of the exception message box.</span></span>  
  
7.  <span data-ttu-id="6c40c-165">Wenn Sie die Entscheidung eines Benutzers dauerhaft speichern müssen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="6c40c-165">If you need to store a user's decision permanently, do the following:</span></span>  
  
    1.  <span data-ttu-id="6c40c-166">Rufen Sie die CreateSubKey-Methode auf, um einen von Ihrer Anwendung verwendeten benutzerdefinierten Registrierungsschlüssel zu öffnen, und legen Sie <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> auf das zurückgegebene RegistryKey-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="6c40c-166">Call the CreateSubKey method to open a custom registry key that your application uses, and set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> to the returned RegistryKey object.</span></span>  
  
    2.  <span data-ttu-id="6c40c-167">Legen Sie <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> auf den Namen des verwendeten Registrierungswerts fest.</span><span class="sxs-lookup"><span data-stu-id="6c40c-167">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> to the name of the registry value that is used.</span></span>  
  
    3.  <span data-ttu-id="6c40c-168">Legen Sie <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="6c40c-168">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> to `true`.</span></span>  
  
    4.  <span data-ttu-id="6c40c-169">Rufen Sie die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="6c40c-169">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="6c40c-170">Der angegebene Registrierungsschlüssel wird ausgewertet, und das Ausnahmemeldungsfeld wird nur angezeigt, wenn die im Registrierungsschlüssel gespeicherten Daten 0 sind.</span><span class="sxs-lookup"><span data-stu-id="6c40c-170">The specified registry key is evaluated, and the exception message box is displayed only if the data stored in the registry key is 0.</span></span> <span data-ttu-id="6c40c-171">Wenn das Dialogfeld angezeigt wird und der Benutzer das Kontrollkästchen aktiviert, bevor er auf eine Schaltfläche klickt, werden die Daten im Registrierungsschlüssel auf 1 gesetzt.</span><span class="sxs-lookup"><span data-stu-id="6c40c-171">If the dialog box is displayed and the user selects the check box before clicking a button, the data in the registry key is set to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c40c-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c40c-172">Example</span></span>  
 <span data-ttu-id="6c40c-173">In diesem Beispiel wird das Ausnahme Meldungs Feld nur mit der Schaltfläche **OK** verwendet, um Informationen aus einer Anwendungs Ausnahme anzuzeigen, die die behandelte Ausnahme sowie zusätzliche anwendungsspezifische Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="6c40c-173">This example uses the exception message box with only the **OK** button to display information from an application exception that includes the handled exception along with additional application-specific information.</span></span>  
  
 [!code-csharp[HowTo#emb_showOKbutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showokbutton)]  
  
 [!code-vb[HowTo#emb_vb_showOKbutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showokbutton)]  
  
## <a name="example"></a><span data-ttu-id="6c40c-174">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c40c-174">Example</span></span>  
 <span data-ttu-id="6c40c-175">In diesem Beispiel wird das Ausnahme Meldungs Feld mit den Schaltflächen **Ja** und **Nein** verwendet, von denen der Benutzer auswählt.</span><span class="sxs-lookup"><span data-stu-id="6c40c-175">This example uses the exception message box with **Yes** and **No** buttons from which the user chooses.</span></span>  
  
 [!code-csharp[HowTo#emb_showYesNobutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showyesnobutton)]  
  
 [!code-vb[HowTo#emb_vb_showYesNobutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showyesnobutton)]  
  
## <a name="example"></a><span data-ttu-id="6c40c-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c40c-176">Example</span></span>  
 <span data-ttu-id="6c40c-177">In diesem Beispiel wird das Ausnahmemeldungsfeld mit benutzerdefinierten Schaltflächen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c40c-177">This example uses the exception message box with custom buttons.</span></span>  
  
 [!code-csharp[HowTo#emb_showcustombutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showcustombutton)]  
  
 [!code-vb[HowTo#emb_vb_showcustombutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showcustombutton)]  
  
## <a name="example"></a><span data-ttu-id="6c40c-178">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c40c-178">Example</span></span>  
 <span data-ttu-id="6c40c-179">In diesem Beispiel wird das Kontrollkästchen verwendet, um zu bestimmen, ob das Ausnahmemeldungsfeld angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c40c-179">This example uses the check box to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_usecheckbox](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_usecheckbox)]  
  
 [!code-vb[HowTo#emb_vb_usecheckbox](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_usecheckbox)]  
  
## <a name="example"></a><span data-ttu-id="6c40c-180">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c40c-180">Example</span></span>  
 <span data-ttu-id="6c40c-181">In diesem Beispiel werden das Kontrollkästchen und ein Registrierungsschlüssel verwendet, um zu bestimmen, ob das Ausnahmemeldungsfeld angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c40c-181">This example uses the check box and a registry key to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_useregkey](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_useregkey)]  
  
 [!code-vb[HowTo#emb_vb_useregkey](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_useregkey)]  
  
## <a name="example"></a><span data-ttu-id="6c40c-182">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c40c-182">Example</span></span>  
 <span data-ttu-id="6c40c-183">In diesem Beispiel wird das Ausnahmemeldungsfeld verwendet, um weitere Informationen anzuzeigen, die bei der Problembehandlung oder beim Debuggen hilfreich sein können.</span><span class="sxs-lookup"><span data-stu-id="6c40c-183">This example uses the exception message box to show additional information that is helpful when troubleshooting or debugging.</span></span>  
  
 [!code-csharp[HowTo#emb_moreinfo](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_moreinfo)]  
  
 [!code-vb[HowTo#emb_vb_moreinfo](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_moreinfo)]  
  
  
