---
title: "Comment&#160;: marshaler un SAFEARRAY pour ADO.NET (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET (C++), marshaler des types SAFEARRAY"
  - "SAFEARRAY, marshaling"
ms.assetid: 1034b9d7-ecf1-40f7-a9ee-53180e87a58c
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler un SAFEARRAY pour ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Montre comment ajouter un `SAFEARRAY` natif à une base de données et comment marshaler un tableau managé d'une base de données vers un `SAFEARRAY` natif.  
  
## Exemple  
 Dans cet exemple, la classe DatabaseClass est créée pour interagir avec un objet <xref:System.Data.DataTable> ADO.NET.  Notez que cette classe est une `class` C\+\+ native \(comparée à une `ref class` ou `value class`\).  Cela est nécessaire, car nous souhaitons utiliser cette classe à partir de code natif et il est impossible d'utiliser des types managés en code natif.  Cette classe sera compilée pour cibler le CLR, comme indiqué par la directive `#pragma managed` précédant la déclaration de classe.  Pour plus d'informations sur cette directive, consultez [managé, non managé](../preprocessor/managed-unmanaged.md).  
  
 Notez le membre privé de la classe DatabaseClass : `gcroot<DataTable ^> table`.  Les types natifs ne pouvant pas contenir de types managés, le mot clé `gcroot` est nécessaire.  Pour plus d'informations sur `gcroot`, consultez [Comment : déclarer des handles dans les types natifs](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Le reste du code dans cet exemple est du code C\+\+ natif, comme indiqué par la directive `#pragma unmanaged` précédant `main`.  Dans cet exemple, nous créons une nouvelle instance de DatabaseClass et appelons ses méthodes pour créer une table et remplir quelques lignes dans la table.  Notez que les types `SAFEARRAY` natifs sont passés en tant que valeurs pour la colonne de base de données ArrayIntsCol.  Au sein de DatabaseClass, ces types `SAFEARRAY` sont marshalés vers des objets managés à l'aide des fonctionnalités de marshaling trouvées dans l'espace de noms <xref:System.Runtime.InteropServices?displayProperty=fullName>.  Plus précisément, la méthode <xref:System.Runtime.InteropServices.Marshal.Copy%2A> est utilisée pour marshaler un `SAFEARRAY` vers un tableau managé d'entiers, et la méthode <xref:System.Runtime.InteropServices.Marshal.Copy%2A> est utilisée pour marshaler un tableau managé d'entiers vers un `SAFEARRAY`.  
  
```  
// adonet_marshal_safearray.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(SAFEARRAY *arrayIntsColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        int len = arrayIntsColValue->rgsabound[0].cElements;  
        array<int> ^arr = gcnew array<int>(len);  
  
        int *pData;  
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);  
        Marshal::Copy(IntPtr(pData), arr, 0, len);  
        SafeArrayUnaccessData(arrayIntsColValue);  
  
        row["ArrayIntsCol"] = arr;  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",  
            Type::GetType("System.Int32[]"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed array  
            // of Int32s to a SAFEARRAY of type VT_I4.  
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);  
            int *pData;  
            SafeArrayAccessData(values[i], (void **)&pData);  
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,  
                IntPtr(pData), 10);  
            SafeArrayUnaccessData(values[i]);  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    // Create a standard array.  
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
    // Create a SAFEARRAY.  
    SAFEARRAY *psa;  
    psa = SafeArrayCreateVector(VT_I4, 0, 10);  
  
    // Copy the data from the original array to the SAFEARRAY.  
    int *pData;  
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);  
    memcpy(pData, &originalArray, 40);  
    SafeArrayUnaccessData(psa);  
    db->AddRow(psa);  
  
    // Now retrieve the rows and display their contents.  
    SAFEARRAY *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ArrayIntsCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        int *pData;  
        SafeArrayAccessData(values[i], (void **)&pData);  
        for (int j = 0; j < 10; j++)  
        {  
            cout << pData[j] << " ";  
        }  
        cout << endl;  
        SafeArrayUnaccessData(values[i]);  
  
        // Deallocate the memory allocated using  
        // SafeArrayCreateVector.  
        SafeArrayDestroy(values[i]);  
    }  
  
    SafeArrayDestroy(psa);  
    delete db;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**    
## Compilation du code  
  
-   Pour compiler le code depuis la ligne de commande, enregistrez l'exemple de code dans un fichier nommé adonet\_marshal\_safearray.cpp et saisissez l'instruction suivante :  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp  
    ```  
  
## Sécurité .NET Framework  
 Pour plus d'informations sur les problèmes de sécurité impliquant ADO.NET, consultez [Sécurisation des applications ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Voir aussi  
 <xref:System.Runtime.InteropServices>   
 [Accès aux données](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/fr-fr/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)