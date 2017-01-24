---
title: "Utilisation d&#39;accesseurs dynamiques | Microsoft Docs"
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
  - "accesseurs (C++), dynamiques"
  - "accesseurs dynamiques"
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;accesseurs dynamiques
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les accesseurs dynamiques vous permettent d'accéder à une source de données lorsque vous ignorez tout du schéma de la base de données \(sa structure sous\-jacente\).  La bibliothèque des modèles OLE DB contient plusieurs classes destinées à vous aider à accomplir cette tâche.  
  
 L'exemple [DynamicConsumer](http://msdn.microsoft.com/fr-fr/2ccc4c61-6749-4e83-aa81-00f8009c0dc3) montre comment utiliser les classes d'accesseurs dynamiques pour obtenir des informations sur les colonnes et créer des accesseurs de manière dynamique.  
  
## Utilisation de CDynamicAccessor  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) vous permet d'accéder à une source de données lorsque vous n'avez aucune connaissance du schéma de la base de données \(la structure sous\-jacente de la base de données\).  Les méthodes `CDynamicAccessor` obtiennent des informations sur la colonne telles que les noms de colonne, nombre et type de données.  Vous utilisez ces informations sur les colonnes pour créer un accesseur de manière dynamique au moment de l'exécution.  Les informations sur les colonnes sont stockées dans une mémoire tampon qui est créé et managée par cette classe.  Récupérez les données à partir de la mémoire tampon en utilisant la méthode [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
## Exemple  
  
### Code  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## Utilisation de CDynamicStringAccessor  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) fonctionne comme [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), sauf sur un plan important.  Alors que `CDynamicAccessor` demande des données dans le format natif indiqué par le fournisseur, `CDynamicStringAccessor` demande que le fournisseur récupère toutes les données ayant fait l'objet d'un accès à partir du magasin de données en tant que données de type chaîne.  Cette approche est particulièrement utile pour des tâches simples qui n'exigent pas de calcul de valeurs dans le magasin de données, comme l'affichage ou l'impression du contenu du magasin de données.  
  
 Utilisez les méthodes `CDynamicStringAccessor` pour récupérer des informations sur les colonnes.  Vous utilisez ces informations sur les colonnes pour créer un accesseur de manière dynamique au moment de l'exécution.  Les informations sur les colonnes sont stockées dans une mémoire tampon qui est créée et managée par cette classe.  Récupérez les données à partir de la mémoire tampon en utilisant [CDynamicStringAccessor::GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), ou stockez\-les dans la mémoire tampon à l'aide de [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
## Exemple  
  
### Code  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## Utilisation de CDynamicParameterAccessor  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) est similaire à [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), sauf que `CDynamicParameterAccessor` récupère les informations sur les paramètres à définir en appelant l'interface [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx).  Le fournisseur doit prendre en charge `ICommandWithParameters` pour que le consommateur puisse utiliser cette classe.  
  
 Les informations sur les paramètres sont stockées dans une mémoire tampon qui est créée et managée par cette classe.  Récupérez les données des paramètres à partir de la mémoire tampon en utilisant [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) et [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Pour obtenir un exemple montrant comment utiliser cette classe afin d'exécuter une procédure stockée SQL Server et avoir les valeurs des paramètres de sortie, consultez l'article de la Base de connaissances Q058860, « HOWTO: Execute Stored Procedure using CDynamicParameterAccessor ». Knowledge Base articles are available in the MSDN Library Visual Studio documentation or at [http:\/\/support.microsoft.com](http://support.microsoft.com/).  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer Sample](http://msdn.microsoft.com/fr-fr/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)