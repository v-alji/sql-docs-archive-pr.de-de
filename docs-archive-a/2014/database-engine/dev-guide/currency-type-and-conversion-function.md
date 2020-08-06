---
title: Währungstyp und Konvertierungs Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: df516567-8689-45c2-b418-16473f8d43e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 032afa201b6e669baf8934c608792ea6bd7f0e8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726225"
---
# <a name="currency-type-and-conversion-function"></a><span data-ttu-id="0f058-102">Currency-Typ und Konvertierungsfunktion</span><span class="sxs-lookup"><span data-stu-id="0f058-102">Currency Type and Conversion Function</span></span>
  <span data-ttu-id="0f058-103">In diesem Beispiel wird ein benutzerdefinierter Currency-Datentyp mithilfe von C# definiert.</span><span class="sxs-lookup"><span data-stu-id="0f058-103">This example defines a Currency user-defined data type by using C#.</span></span> <span data-ttu-id="0f058-104">Dieser benutzerdefinierte Datentyp kapselt sowohl einen Betrag als auch ein Gebietsschema ein, um die richtige Wiedergabe des Betrags als Währungswert in diesem Gebietsschema zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0f058-104">This user-defined data type encapsulates both an amount and a culture that helps to determine the correct way to render the amount as a currency value in that culture.</span></span> <span data-ttu-id="0f058-105">Dieses Beispiel stellt außerdem eine Währungsumrechnungsfunktion bereit, die eine Instanz des benutzerdefinierten Currency-Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0f058-105">This example also provides a currency conversion function that returns an instance of the Currency user-defined data type.</span></span> <span data-ttu-id="0f058-106">Wenn die AdventureWorks-Datenbank über einen Umrechnungskurs von US-Dollar (USD) in die Währung der angegebenen Kultur verfügt, gibt die Umrechnungsfunktion einen benutzerdefinierten Currency-Datentyp mit dem konvertierten Kurs und einer Kultur zurück, die der angeforderten Kultur entspricht.</span><span class="sxs-lookup"><span data-stu-id="0f058-106">If the AdventureWorks database has a conversion rate from U.S. dollars (USD) to the currency that is associated with the specified culture, the conversion function returns a Currency user-defined data type with the converted rate and a culture that matches the culture requested.</span></span> <span data-ttu-id="0f058-107">Andernfalls wird ein benutzerdefinierter Currency-Datentyp mit dem ursprünglichen Betrag zurückgegeben, d. h. ein USD-Betrag mit der Kultur `en-us`.</span><span class="sxs-lookup"><span data-stu-id="0f058-107">Otherwise, a Currency user-defined data type is returned with the original amount, which should be in USD, with the `en-us` culture.</span></span> <span data-ttu-id="0f058-108">Das Beispiel veranschaulicht auch, wie Sie mithilfe von Transact-SQL CLR (Common Language Runtime)-Methoden und Assemblys registrieren und die Registrierung von CLR-Methoden und Assemblys aufheben können.</span><span class="sxs-lookup"><span data-stu-id="0f058-108">The example also demonstrates how to unregister and register common language runtime (CLR) methods and assemblies by using Transact-SQL.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="0f058-109">Die in diesem Beispiel verwendeten Wechselkurse sind frei erfunden und sollten nicht für tatsächliche finanzielle Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f058-109">The exchange rates used in this sample are fictitious and should not be used for actual financial transactions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f058-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0f058-110">Prerequisites</span></span>  
 <span data-ttu-id="0f058-111">Zum Erstellen und Ausführen dieses Projekts muss die folgende Software installiert sein:</span><span class="sxs-lookup"><span data-stu-id="0f058-111">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f058-112">oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="0f058-112">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="0f058-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express erhalten Sie kostenlos auf der [Website](https://www.microsoft.com/sql-server/sql-server-editions-express) mit der Dokumentation und den Beispielen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="0f058-113">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="0f058-114">Die AdventureWorks-Datenbank, die auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer-[Website](https://go.microsoft.com/fwlink/?linkid=62796) zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f058-114">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="0f058-115">.NET Framework SDK 2.0 oder höher oder Microsoft Visual Studio 2005 oder höher.</span><span class="sxs-lookup"><span data-stu-id="0f058-115">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="0f058-116">Das .NET Framework SDK ist kostenlos erhältlich.</span><span class="sxs-lookup"><span data-stu-id="0f058-116">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="0f058-117">Außerdem müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="0f058-117">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="0f058-118">In der von Ihnen verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz muss die CLR-Integration aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="0f058-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="0f058-119">Führen Sie zum Aktivieren der CLR-Integration die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="0f058-119">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="0f058-120">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="0f058-120">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="0f058-121">Führen Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="0f058-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="0f058-122">Um CLR zu aktivieren, benötigen Sie die `ALTER SETTINGS`-Serverberechtigung, die Mitglieder der festen Serverrollen `sysadmin` und `serveradmin` implizit erhalten.</span><span class="sxs-lookup"><span data-stu-id="0f058-122">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="0f058-123">Die AdventureWorks-Datenbank muss in der von Ihnen verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz installiert sein.</span><span class="sxs-lookup"><span data-stu-id="0f058-123">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="0f058-124">Wenn Sie kein Administrator für die verwendete- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instanz sind, müssen Sie über einen Administrator verfügen, der Ihnen **CreateAssembly** die Berechtigung zum Abschluss der Installation erteilt.</span><span class="sxs-lookup"><span data-stu-id="0f058-124">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="0f058-125">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="0f058-125">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="0f058-126">Verwenden Sie die folgenden Anweisungen, um das Beispiel zu erstellen und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="0f058-126">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="0f058-127">Wechseln Sie zu einer Visual Studio- oder .NET Framework-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="0f058-127">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="0f058-128">Erstellen Sie ggf. ein Verzeichnis für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0f058-128">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="0f058-129">Für dieses Beispiel wird C:\MySample verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f058-129">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="0f058-130">Erstellen Sie in c:\MySample die Datei `Currency.cs`, und kopieren Sie den C#-Beispielcode (unten) in die Datei.</span><span class="sxs-lookup"><span data-stu-id="0f058-130">In c:\MySample, create `Currency.cs` and copy the C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="0f058-131">Kompilieren Sie den Beispielcode von der Befehlszeilen Aufforderung, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="0f058-131">Compile the sample code from the command line prompt by executing:</span></span>  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll  /target:library Currency.cs`  
  
5.  <span data-ttu-id="0f058-132">Kopieren Sie den [!INCLUDE[tsql](../../includes/tsql-md.md)]-Installationscode in eine Datei, und speichern Sie sie als `Install.sql` im Beispielverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f058-132">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="0f058-133">Wenn das Beispiel in einem anderen Verzeichnis als `C:\MySample\` installiert ist, bearbeiten Sie die Datei `Install.sql`wie gezeigt, damit sie auf diesen Speicherort verweist.</span><span class="sxs-lookup"><span data-stu-id="0f058-133">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
7.  <span data-ttu-id="0f058-134">Stellen Sie die Assembly und die gespeicherte Prozedur bereit, indem Sie die folgende Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="0f058-134">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
8.  <span data-ttu-id="0f058-135">Kopieren [!INCLUDE[tsql](../../includes/tsql-md.md)] Sie das Test Befehls Skript in eine Datei, und speichern Sie Sie als `test.sql` im Beispiel Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f058-135">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
9. <span data-ttu-id="0f058-136">Führen Sie das Testskript mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0f058-136">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
10. <span data-ttu-id="0f058-137">Kopieren Sie das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Bereinigungsskript in eine Datei, und speichern Sie diese als `cleanup.sql` im Beispielverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f058-137">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
11. <span data-ttu-id="0f058-138">Führen Sie das Skript mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0f058-138">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="0f058-139">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="0f058-139">Sample Code</span></span>  
 <span data-ttu-id="0f058-140">Die Codelistings für dieses Beispiel lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="0f058-140">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="0f058-141">C#</span><span class="sxs-lookup"><span data-stu-id="0f058-141">C#</span></span>  
  
```  
using System;  
using System.Globalization;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data;  
using System.Data.Sql;  
using System.IO;  
using System.Data.SqlClient;  
  
    /// <summary>  
    ///Defines a class for handing particular amounts of money in a   
    ///particular culture's monetary system.  This class is exposed as   
    ///a SQL Server UDT.  
///   
///Note that we are implementing IComparable to affect comparison behavior   
///only within the CLR.  This does not affect how SQL Server will compare the  
///     the types.  How SQL Server will compare the type is determined by the Write   
///method on IBinarySerialize.  
    /// </summary>  
[Serializable]  
    [SqlUserDefinedType(Format.UserDefined, IsByteOrdered = true, MaxByteSize = 32)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
        const string nullMarker = "\0\0\0\0\0\0\0\0\0\0";  
        const int cultureNameMaxSize = 10;  
  
        private string cultureName;//Who issued the money (en-us, for example)  
  
        private CultureInfo culture;//The object which represents cultureName  
  
        private decimal currencyValue;//The amount of money  
  
        // Public properties for private fields  
        public CultureInfo Culture  
        {  
            get  
            {  
                //A culture name is required.  If not present the entire object is considered null.  
                if (cultureName == null) return null;  
  
                //If we've got a cached copy of the culture return it.  
                if (culture != null) return culture;  
  
                //Otherwise, set the cache and return the culture for the culture name specified.  
                culture = CultureInfo.CreateSpecificCulture(cultureName);  
                return culture;  
            }  
        }  
  
        // Public property for the private field.  
        public decimal CurrencyValue  
        {  
            get  
            {  
                return currencyValue;  
            }  
        }  
  
        // Constructors for when we have the culture or the name of the culture  
  
        public Currency(CultureInfo culture, decimal currencyValue)  
        {  
if (culture == null) throw new ArgumentNullException("culture");  
            this.cultureName = culture.Name;  
            this.culture = culture;  
            this.currencyValue = currencyValue;  
        }  
  
        public Currency(string cultureName, decimal currencyValue)  
        {  
            this.cultureName = cultureName;  
            this.culture = null;  
            this.currencyValue = currencyValue;  
        }  
  
        //Return the string representation for the currency, including the currency symbol.  
        [SqlMethod(IsDeterministic = true,  
            IsPrecise = true, DataAccess = DataAccessKind.None,  
            SystemDataAccess = SystemDataAccessKind.None)]  
        public override string ToString()  
        {  
            if (this.Culture == null) return "null";  
  
            return String.Format(this.Culture, "{0:c}", currencyValue);  
        }  
  
        //The entire value of the currency is considered null if the culture name is null  
        public bool IsNull  
        {  
            get  
            {  
                return cultureName == null;  
            }  
        }  
  
        //The no-argument constructor makes a null currency.  
        public static Currency Null  
        {  
            get  
            {  
                Currency h = new Currency((String)null, 0);  
  
                return h;  
            }  
        }  
  
        //Be sure to set the current UI culture before using this method! Even better, provide the culture  
        //specifically (for the method after this one).  
        [SqlMethod(IsDeterministic = true, IsPrecise = true, DataAccess = DataAccessKind.None, SystemDataAccess = SystemDataAccessKind.None)]  
        public static Currency Parse(SqlString sqlString)  
        {  
            return ParseWithCulture(sqlString, CultureInfo.CurrentUICulture);  
        }  
  
        public static Currency ParseWithCulture(SqlString sqlString, CultureInfo culture)  
        {  
            if (sqlString.IsNull   
|| (string.Compare(sqlString.Value, "null", true, CultureInfo.CurrentUICulture) == 0))  
                return Currency.Null;  
  
            int digitPos = -1;  
            string stringValue = sqlString.Value;  
  
            while (digitPos < stringValue.Length   
                && !Char.IsDigit(stringValue, ++digitPos))  
            {  
            }  
  
            if (digitPos < stringValue.Length)  
                return new Currency(culture, decimal.Parse(  
                    stringValue.Substring(digitPos), culture));  
  
            return Currency.Null;  
        }  
  
        public override int GetHashCode()  
        {  
            if (this.IsNull)  
                return 0;  
  
            return this.ToString().GetHashCode();  
        }  
  
//Note: This only affects the behavior of CLR, not SQL Server.  Comparisions  
//for SQL Server will be determined by the Write method below.  
  
public int CompareTo(object obj)  
        {  
            if (obj == null)  
                return 1; //by definition  
  
            if (obj == null || !(obj is Currency))  
                throw new ArgumentException(  
                    "the argument to compare is not a Currency");  
  
            Currency c = (Currency)obj;  
  
            if (this.IsNull)  
            {  
                if (c.IsNull)  
                    return 0;  
  
                return -1;  
            }  
  
            if (c.IsNull)  
                return 1;  
  
            string thisCultureName = this.Culture.Name;  
            string otherCultureName = c.Culture.Name;  
            if (!thisCultureName.Equals(otherCultureName))  
                return thisCultureName.CompareTo(otherCultureName);  
            return this.CurrencyValue.CompareTo(c.CurrencyValue);  
        }  
        // IBinarySerialize methods  
        // The binary layout is as follow:  
        //    Bytes 0 - 19:Culture name, padded to the right with null characters, UTF-16 encoded  
        //    Bytes 20+:Decimal value of money  
        // If the culture name is empty, the currency is null.  
  
        public void Write(System.IO.BinaryWriter w)  
        {  
if (w == null) throw new ArgumentNullException("w");  
            if (this.IsNull)  
            {  
                w.Write(nullMarker);  
                w.Write((decimal)0);  
                return;  
            }  
  
            if (cultureName.Length > cultureNameMaxSize)  
            {  
                throw new ApplicationException(string.Format(  
                    CultureInfo.InvariantCulture,   
                    "{0} is an invalid culture name for currency as it is too long.",   
                    cultureNameMaxSize));  
            }  
  
            String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
            for (int i = 0; i < cultureNameMaxSize; i++)  
            {  
                w.Write(paddedName[i]);  
            }  
  
            // Normalize decimal value to two places  
            currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
            w.Write(currencyValue);  
        }  
        public void Read(System.IO.BinaryReader r)  
        {  
            char[] name = r.ReadChars(cultureNameMaxSize);  
            int stringEnd = Array.IndexOf(name, '\0');  
  
            if (stringEnd == 0)  
            {  
                cultureName = null;  
                return;  
            }  
  
            cultureName = new String(name, 0, stringEnd);  
            currencyValue = r.ReadDecimal();  
        }  
    }  
  
    /// <summary>  
    /// This class is used to compute the value of US money a given region.  
    /// </summary>  
    public sealed class CurrencyConverter  
    {  
        // Classes with only static members should not be instantiable  
        private CurrencyConverter()  
        {  
        }  
  
        private static readonly CultureInfo USCulture = CultureInfo.CreateSpecificCulture("en-us");  
  
        /// <summary>  
        ///Computes the value of a certain amount of money in the USA in a different region.  
        /// </summary>  
        /// <param name="fromAmount">The quantity of money</param>  
        /// <param name="toCultureName">A culture which is a member of the region of interest</param>  
        /// <returns></returns>  
        [Microsoft.SqlServer.Server.SqlFunction(IsDeterministic = true, DataAccess = Microsoft.SqlServer.Server.DataAccessKind.Read)]  
        public static Currency ConvertCurrency(SqlMoney fromAmount, SqlString toCultureName, SqlDateTime when)  
        {  
            CultureInfo toCulture = CultureInfo.CreateSpecificCulture(toCultureName.Value);  
  
            if (toCulture.Equals(USCulture))  
            {  
                Currency c = new Currency(USCulture, (decimal)fromAmount);  
                return c;  
            }  
  
            String toCurrencyCode = new RegionInfo(toCulture.LCID).ISOCurrencySymbol;  
  
            // Find the rate closest to the specified date  
  
            using (SqlConnection conn = new SqlConnection("context connection=true"))  
            {  
  
                SqlCommand command = conn.CreateCommand();  
                command.CommandType = CommandType.StoredProcedure;  
                command.CommandText = "usp_LookupConversionRate";  
  
                SqlParameter onDateParameter  
                    = new SqlParameter("@OnDate", SqlDbType.DateTime);  
                onDateParameter.Value = when;  
                command.Parameters.Add(onDateParameter);  
  
                SqlParameter toCurrencyCodeParameter  
                    = new SqlParameter("@ToCurrencyCode", SqlDbType.NChar, 3);  
                toCurrencyCodeParameter.Value = toCurrencyCode;  
                command.Parameters.Add(toCurrencyCodeParameter);  
  
                SqlParameter resultParameter  
                    = new SqlParameter("@Result", SqlDbType.Decimal);  
                resultParameter.Precision = 10;  
                resultParameter.Scale = 4;  
                resultParameter.Direction = ParameterDirection.Output;  
                command.Parameters.Add(resultParameter);  
  
                conn.Open();  
                command.ExecuteNonQuery();  
  
                decimal conversionFactor;  
  
                if (resultParameter.Value is decimal)  
                {  
                    conversionFactor = (decimal)(resultParameter.Value);  
                }  
                else  
                {  
                    conversionFactor = 1.0M;  
                    toCulture = USCulture;  
                }  
  
                return new Currency(toCulture, ((decimal)fromAmount * conversionFactor));  
            }  
        }  
    }  
```  
  
 <span data-ttu-id="0f058-142">Dies ist das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Installationsskript (`Install.sql`), das die Assembly bereitstellt und die gespeicherte Prozedur in der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f058-142">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = N'usp_LookupConversionRate')  
DROP PROCEDURE [dbo].[usp_LookupConversionRate]  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE [name] = N'Currency')   
DROP TYPE Currency;  
GO  
  
IF EXISTS (SELECT [name] FROM sys.assemblies WHERE [name] = N'Currency')  
DROP ASSEMBLY Currency;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE ([name] = N'ConvertCurrency') AND ([type] = 'FS'))  
DROP FUNCTION ConvertCurrency;  
GO  
  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = 'C:\MySample\'  
CREATE ASSEMBLY Currency   
FROM @SamplesPath + 'Currency.dll'  
with permission_set = safe;  
  
USE AdventureWorks  
GO  
  
CREATE TYPE Currency EXTERNAL NAME [Currency].[Currency];  
GO  
  
CREATE FUNCTION ConvertCurrency  
(  
@fromAmount AS money,  
@toCultureName AS nvarchar(10),  
@when as DateTime  
)  
RETURNS Currency  
AS EXTERNAL NAME [Currency].[CurrencyConverter].ConvertCurrency;  
GO  
  
CREATE PROCEDURE usp_LookupConversionRate  
(  
@OnDate datetime,  
@ToCurrencyCode nchar(3),  
@Result decimal(10,4) OUTPUT  
)  
AS  
BEGIN  
--It is not permitted to perform certain side-effects in functions, and  
--SET NOCOUNT is one of them.  Since this sproc is called from   
--the ConvertCurrency CLR UDF, we must not do that side-effect or  
--there will be an error at runtime.  
--SET NOCOUNT ON  
  
SELECT @Result = (SELECT TOP 1 AverageRate FROM Sales.CurrencyRate   
WHERE CurrencyRateDate <= @OnDate AND FromCurrencyCode = N'USD'   
AND ToCurrencyCode = @ToCurrencyCode   
ORDER BY CurrencyRateDate DESC);  
  
IF (@Result IS NULL)  
SELECT @Result = (SELECT TOP 1 AverageRate FROM Sales.CurrencyRate   
WHERE CurrencyRateDate > @OnDate AND FromCurrencyCode = N'USD'   
AND ToCurrencyCode = @ToCurrencyCode  
ORDER BY CurrencyRateDate ASC);  
END;  
  
```  
  
 <span data-ttu-id="0f058-143">Dies ist die Datei `test.sql`, die das Beispiel durch das Ausführen der Funktionen testet.</span><span class="sxs-lookup"><span data-stu-id="0f058-143">This is `test.sql`, which tests the sample by executing the functions.</span></span>  
  
```  
use AdventureWorks  
GO  
  
DECLARE @TwoBitsEuro Currency;  
SELECT @TwoBitsEuro = dbo.ConvertCurrency(CAST('.25' as money), 'FR-FR', GetDate());  
PRINT '$0.25 in USD is equivalent to ' + @TwoBitsEuro.ToString();  
```  
  
 <span data-ttu-id="0f058-144">Im folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code werden die Assembly, der Typ und die Funktionen aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="0f058-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly, type and functions from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = N'usp_LookupConversionRate')  
DROP PROCEDURE [dbo].[usp_LookupConversionRate]  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f058-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f058-145">See Also</span></span>  
 [<span data-ttu-id="0f058-146">Verwendungsszenarios und Beispiele für Common Language Runtime-Integration &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="0f058-146">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
