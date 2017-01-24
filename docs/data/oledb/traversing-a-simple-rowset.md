---
title: "Parcours d&#39;un jeu de lignes simple | Microsoft Docs"
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
  - "accesseurs (C++), jeux de lignes"
  - "accès aux données (C++), jeux de lignes"
  - "OLE DB (consommateurs) (C++), attributs de bases de données"
  - "jeux de lignes (C++), accéder"
  - "jeux de lignes simples"
ms.assetid: b45acf16-4029-429d-ab8d-b7fba98b9740
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Parcours d&#39;un jeu de lignes simple
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant montre un accès rapide et simple à la base de données, qui ne met pas en œuvre des commandes.  Le code de consommateur suivant, dans un projet ATL, récupère des enregistrements d'une table appelée *Artists* dans une base de données Microsoft Access en utilisant le fournisseur Microsoft OLE DB pour ODBC.  Le code crée un objet de table [CTable](../../data/oledb/ctable-class.md) avec un accesseur reposant sur la classe d'enregistrement utilisateur `CArtists`.  Il ouvre une connexion, ouvre une session sur la connexion, puis ouvre la table sur la session.  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CTable<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major  
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
session.Open(connection);  
artists.Open(session, "Artists");  
  
// Get data from the rowset  
while (artists.MoveNext() == S_OK)  
{  
   cout << artists.m_szFirstName;  
   cout << artists.m_szLastName;  
}  
```  
  
 L'enregistrement utilisateur, `CArtists`, ressemble au texte suivant :  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
```  
  
## Voir aussi  
 [Utilisation des modèles du consommateur OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)