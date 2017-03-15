---
title: "Comment&#160;: marshaler un VARIANT pour ADO.NET (C++/CLI) | Microsoft Docs"
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
  - "ADO.NET (C++), marshaler des types VARIANT"
  - "VARIANT"
  - "VARIANT, marshaling"
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler un VARIANT pour ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Montre comment ajouter un `VARIANT` natif à une base de données et comment marshaler un <xref:System.Object?displayProperty=fullName> d'une base de données vers un `VARIANT` natif.  
  
## Exemple  
 Dans cet exemple, la classe DatabaseClass est créée pour interagir avec un objet <xref:System.Data.DataTable> ADO.NET.  Notez que cette classe est une `class` C\+\+ native \(comparée à une `ref class` ou `value class`\).  Cela est nécessaire, car nous souhaitons utiliser cette classe à partir de code natif et il est impossible d'utiliser des types managés en code natif.  Cette classe sera compilée pour cibler le CLR, comme indiqué par la directive `#pragma managed` précédant la déclaration de classe.  Pour plus d'informations sur cette directive, consultez [managé, non managé](../preprocessor/managed-unmanaged.md).  
  
 Notez le membre privé de la classe DatabaseClass : `gcroot<DataTable ^> table`.  Les types natifs ne pouvant pas contenir de types managés, le mot clé `gcroot` est nécessaire.  Pour plus d'informations sur `gcroot`, consultez [Comment : déclarer des handles dans les types natifs](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Le reste du code dans cet exemple est du code C\+\+ natif, comme indiqué par la directive `#pragma unmanaged` précédant `main`.  Dans cet exemple, nous créons une nouvelle instance de DatabaseClass et appelons ses méthodes pour créer une table et remplir quelques lignes dans la table.  Notez que les types `VARIANT` natifs sont passés en tant que valeurs pour la colonne de base de données ObjectCol.  Au sein de DatabaseClass, ces types `VARIANT` sont marshalés vers des objets managés à l'aide des fonctionnalités de marshaling trouvées dans l'espace de noms <xref:System.Runtime.InteropServices?displayProperty=fullName>.  En particulier, la méthode <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> est utilisée pour marshaler un `VARIANT` vers un <xref:System.Object> et la méthode <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> est utilisée pour marshaler un <xref:System.Object> vers un `VARIANT`.  
  
```  
// adonet_marshal_variant.cpp  
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
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
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
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
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
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
  **ObjectCol: This is a BSTR in a VARIANT.**  
**ObjectCol: 42**   
## Compilation du code  
  
-   Pour compiler le code depuis la ligne de commande, enregistrez l'exemple de code dans un fichier nommé adonet\_marshal\_variant.cpp et saisissez l'instruction suivante :  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## Sécurité .NET Framework  
 Pour plus d'informations sur les problèmes de sécurité impliquant ADO.NET, consultez [Sécurisation des applications ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Voir aussi  
 <xref:System.Runtime.InteropServices>   
 [Accès aux données](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/fr-fr/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)