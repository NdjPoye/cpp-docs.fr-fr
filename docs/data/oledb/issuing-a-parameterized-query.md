---
title: "&#201;mission d&#39;une requ&#234;te param&#233;tr&#233;e | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "requêtes avec paramètres, exécuter avec la classe CCommand"
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# &#201;mission d&#39;une requ&#234;te param&#233;tr&#233;e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple suivant émet une requête paramétrée simple qui récupère des enregistrements à l'aide d'un champ d'âge \(supérieur à 30\) à partir d'une table dans une base de données Microsoft Access.  Pour prendre en charge le paramètre, l'enregistrement utilisateur doit disposer d'un mappage supplémentaire.  Le code suivant utilise, dans un projet ATL, la classe `CCommand` à la place de la classe `CTable` utilisée dans l'exemple précédent, [Parcours d'un jeu de lignes simple](../../data/oledb/traversing-a-simple-rowset.md).  
  
```  
#include <atldbcli.h>  
  
CDataSource connection;  
CSession session;  
CCommand<CAccessor<CArtists> > artists;  
  
// Open the connection, session, and table, specifying authentication   
// using Windows NT integrated security. Hard-coding a password is a major   
// security weakness.  
connection.Open(CLSID_MSDASQL, "NWind", NULL, NULL,   
DBPROP_AUTH_INTEGRATED);  
session.Open(connection);  
  
// Set the parameter for the query  
artists.m_nAge = 30;  
artists.Open(session, "select * from artists where age > ?");  
  
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
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## Voir aussi  
 [Utilisation des modèles du consommateur OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)