---
title: "Impl&#233;mentation d&#39;un consommateur simple | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clients, créer"
  - "consommateurs OLE DB, implémenter"
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impl&#233;mentation d&#39;un consommateur simple
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les rubriques suivantes montrent comment modifier les fichiers créés par l'Assistant Application MFC et l'Assistant Consommateur OLE DB ATL pour créer un consommateur simple.  Cet exemple comprend les parties suivantes :  
  
-   La section « Récupération de données à l'aide du consommateur » explique comment implémenter le code dans le consommateur qui lit toutes les données, ligne par ligne, d'une table de base de données.  
  
-   La section « Ajout de la prise en charge de signets à un consommateur » explique comment ajouter une prise en charge des signets dans le consommateur.  
  
-   La section « Ajout de la prise en charge XML au consommateur » explique comment modifier le code du consommateur pour obtenir la sortie des données du jeu de lignes récupérées sous forme de données XML.  
  
> [!NOTE]
>  Vous pouvez utiliser l'application consommateur décrite dans cette section pour tester les exemples de fournisseurs MyProv et Provider.  
  
> [!NOTE]
>  Pour générer une application consommateur en vue de tester MyProv \(le même fournisseur décrit dans [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md)\), vous devez inclure une prise en charge des signets comme indiqué dans la section « Ajout de la prise en charge de signets à un consommateur ».  
  
> [!NOTE]
>  Pour générer une application consommateur en vue de tester Provider, abandonnez la prise en charge des signets décrite dans « Ajout de la prise en charge de signets à un consommateur » et ignorez la section « Ajout de la prise en charge XML au consommateur ».  
  
## Récupération de données à l'aide du consommateur  
  
#### Pour modifier l'application console en vue d'utiliser le consommateur OLE DB  
  
1.  Dans MyCons.cpp, modifiez le code principal en insérant le texte en gras, comme ci\-dessous :  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);        // Instantiate rowset    CProducts rs;        hr = rs.OpenAll();    ATLASSERT( SUCCEEDED( hr ) );    hr = rs.MoveFirst();        // Iterate through the rowset    while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )    {       // Print out the column information for each row       printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",              rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );       hr = rs.MoveNext();    }        rs.Close();    rs.ReleaseCommand();        CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## Ajout de la prise en charge de signets à un consommateur  
 Un signet est une colonne qui identifie de manière unique chaque ligne d'une table.  En principe, il s'agit de la colonne clé, mais pas toujours ; il est spécifique du fournisseur.  Cette section vous explique comment ajouter la prise en charge de signets.  Pour ce faire, vous devez effectuer les tâches suivantes dans la classe d'enregistrement utilisateur :  
  
-   Instanciez les signets.  Il s'agit d'objets de type [CBookmark](../../data/oledb/cbookmark-class.md).  
  
-   Demandez une colonne signet au fournisseur en définissant la propriété **DBPROP\_IRowsetLocate**.  
  
-   Ajoutez une entrée signet dans le mappage de colonnes en utilisant la macro [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
 Les étapes précédentes vous fournissent une prise en charge de signets et un objet signet avec lequel travailler.  Cet exemple de code illustre l'utilisation d'un signet, de la manière suivante :  
  
-   Ouvrez un fichier pour l'écriture.  
  
-   Effectuez une sortie des données du jeu de lignes dans le fichier, ligne par ligne.  
  
-   Déplacez le curseur du jeu de lignes jusqu'au signet en appelant [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).  
  
-   Effectuez la sortie de la ligne marquée par un signet, en l'ajoutant à la fin du fichier.  
  
> [!NOTE]
>  Si vous utilisez cette application consommateur pour tester l'application fournisseur de l'exemple Provider, abandonnez la prise en charge de signets décrite dans cette section.  
  
#### Pour instancier le signet  
  
1.  L'accesseur doit contenir un objet de type [CBookmark](../../data/oledb/cbookmark-class.md).  Le paramètre `nSize` spécifie la taille de la mémoire tampon du signet en octets \(généralement, 4 pour les plateformes 32 bits et 8 pour les plateformes 64 bits\).  Ajoutez la déclaration suivante aux données membres des colonnes dans la classe d'enregistrement utilisateur :  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### Pour demander une colonne signet au fournisseur  
  
1.  Ajoutez le code suivant à la méthode `GetRowsetProperties` dans la classe d'enregistrement utilisateur :  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks    pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### Pour ajouter une entrée de signet dans le mappage de colonnes  
  
1.  Ajoutez l'entrée suivante au mappage de colonnes dans la classe d'enregistrement utilisateur :  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### Pour ajouter un signet à votre code principal  
  
1.  Dans le fichier MyCons.cpp de l'application console que vous avez créée précédemment, remplacez le code principal par le texte suivant.  Pour utiliser des signets, le code principal doit instancier son propre objet signet \(`myBookmark`\) ; celui\-ci est différent de celui de l'accesseur \(`m_bookmark`\).  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       hr = rs.OpenAll();  
       hr = rs.MoveFirst();  
  
       // Cast CURRENCY m_UnitPrice to a long value  
       LONGLONG lPrice = rs.m_UnitPrice.int64;  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // Instantiate a bookmark object myBookmark for the main code  
       CBookmark<4> myBookmark;  
       int nCounter = 0;  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "initial row dump" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if( nCounter == 5 )  
             myBookmark = rs.bookmark;  
          // Output the column information for each row:  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       // Move cursor to bookmark  
       hr = rs.MoveToBookmark(myBookmark);  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "row dump starting from bookmarked row" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          // Output the column information for each row  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
 Pour plus d'informations sur les signets, consultez [Utilisation des signets](../../data/oledb/using-bookmarks.md).  L'utilisation des signets est également illustrée par des exemples dans [Mise à jour des jeux de lignes](../../data/oledb/updating-rowsets.md).  
  
## Ajout de la prise en charge XML au consommateur  
 Comme expliqué dans [Accès aux données XML](../../data/oledb/accessing-xml-data.md), il existe deux façons de récupérer des données XML d'une source de données : utiliser [CStreamRowset](../../data/oledb/cstreamrowset-class.md) ou [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  Cet exemple utilise `CStreamRowset`, qui est plus efficace mais requiert que SQL Server 2000 soit actif sur l'ordinateur sur lequel vous exécutez cet exemple d'application.  
  
#### Pour modifier la classe de commande en vue d'hériter de CStreamRowset  
  
1.  Dans l'application consommateur créée précédemment, modifiez la déclaration `CCommand` de façon à spécifier `CStreamRowset` comme classe rowset, de la manière suivante :  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### Pour modifier le code principal afin de récupérer et d'obtenir une sortie des données XML  
  
1.  Dans le fichier MyCons.cpp de l'application console que vous avez créée précédemment, remplacez le code principal par le texte suivant :  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
          HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## Voir aussi  
 [Création d'un consommateur OLE DB en utilisant l'Assistant](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)