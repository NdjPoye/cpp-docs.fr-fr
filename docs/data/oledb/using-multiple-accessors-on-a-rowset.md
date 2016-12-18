---
title: "Utilisation de plusieurs accesseurs dans un jeu de lignes | Microsoft Docs"
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
  - "BEGIN_ACCESSOR (macro)"
  - "BEGIN_ACCESSOR (macro), accesseurs multiples"
  - "jeux de lignes (C++), accesseurs multiples"
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de plusieurs accesseurs dans un jeu de lignes
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Il existe trois scénarios de base dans lesquels vous devez utiliser des accesseurs multiples :  
  
-   **Plusieurs jeux de lignes en lecture\/écriture.** Dans ce scénario, vous avez une table avec une clé primaire.  Vous voulez pouvoir lire toutes les colonnes de la ligne, y compris celle de la clé primaire.  Vous voulez également pouvoir écrire les données dans toutes les colonnes, sauf dans celle de la clé primaire \(car vous ne pouvez pas écrire dans la colonne de la clé primaire\).  En ce cas, vous définissez deux accesseurs :  
  
    -   L'accesseur 0 contient toutes les colonnes.  
  
    -   L'accesseur 1 contient toutes les colonnes sauf celle de la clé primaire.  
  
-   **Performances.** Dans ce scénario, plusieurs colonnes contiennent une grande quantité de données ; par exemple, des fichiers graphiques, son ou vidéo.  Vous ne souhaiterez probablement pas récupérer la colonne contenant le fichier de données volumineux chaque fois que vous changez de ligne, car cela risque de ralentir l'exécution de l'application.  
  
     Vous pouvez définir des accesseurs distincts dans lequel le premier accesseur contient toutes les colonnes sauf celle contenant une grande quantité de données et récupère les données de ces colonnes automatiquement ; il s'agit de l'accesseur automatique.  Le deuxième accesseur récupère seulement la colonne contenant une grande quantité de données, mais ne récupère pas les données de cette colonne de façon automatique.  Vous pouvez avoir d'autres méthodes qui actualisent ou récupèrent les données volumineuses à la demande.  
  
    -   L'accesseur 0 est un accesseur automatique ; il récupère toutes les colonnes sauf celle contenant une grande quantité de données.  
  
    -   L'accesseur 1 n'est pas un accesseur automatique ; il récupère la colonne contenant une grande quantité de données.  
  
     Utilisez l'argument automatique pour spécifier si l'accesseur est un accesseur automatique.  
  
-   **Plusieurs colonnes ISequentialStream.** Dans ce scénario, vous avez plusieurs colonnes contenant des données `ISequentialStream`.  Cependant, chaque accesseur est limité à un seul flux de données `ISequentialStream`.  Pour résoudre ce problème, configurez plusieurs accesseurs, chacun contenant un seul pointeur `ISequentialStream`.  
  
 Normalement, vous créez des accesseurs en utilisant les macros [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) et [END\_ACCESSOR](../../data/oledb/end-accessor.md).  Vous pouvez également utiliser l'attribut [db\_accessor](../../windows/db-accessor.md). \(Les accesseurs sont décrits plus en détail dans [Enregistrements utilisateur](../../data/oledb/user-records.md).\) Les macros ou l'attribut spécifient si un accesseur est un accesseur automatique ou non automatique :  
  
-   Dans un accesseur automatique, les méthodes de déplacement telles que **MoveFirst**, `MoveLast`, `MoveNext` et `MovePrev` récupèrent des données automatiquement pour toutes les colonnes spécifiées.  L'accesseur 0 doit être l'accesseur automatique.  
  
-   Dans un accesseur non automatique, la récupération ne se produit que lorsque vous appelez de manière explicite une méthode telle que **Update**, **Insert**, **Fetch** ou **Delete**.  Dans les scénarios décrits ci\-dessus, vous ne souhaiterez peut\-être pas récupérer toutes les colonnes à chaque déplacement.  Vous pouvez placer plusieurs colonnes dans un accesseur séparé et en faire un accesseur non automatique, comme indiqué ci\-dessous.  
  
 L'exemple suivant utilise plusieurs accesseurs pour lire et écrire dans la table des tâches de la base de données pubs de SQL Server utilisant plusieurs accesseurs.  C'est l'application la plus répandue des accesseurs multiples ; consultez ci\-dessus « jeux de lignes multiples en lecture\/écriture ».  
  
 La classe d'enregistrement utilisateur est comme ci\-dessous.  Elle définit deux accesseurs : l'accesseur 0 contient uniquement la colonne de la clé primaire \(ID\) ; l'accesseur 1 contient d'autres colonnes.  
  
```  
class CJobs  
{  
public:  
    enum {  
        sizeOfDescription = 51  
    };  
  
    short nID;  
    char szDescription[ sizeOfDescription ];  
    short nMinLvl;  
    short nMaxLvl;  
  
    DWORD dwID;  
    DWORD dwDescription;  
    DWORD dwMinLvl;  
    DWORD dwMaxLvl;  
  
BEGIN_ACCESSOR_MAP(CJobs, 2)  
    // Accessor 0 is the automatic accessor  
    BEGIN_ACCESSOR(0, true)  
        COLUMN_ENTRY_STATUS(1, nID, dwID)  
    END_ACCESSOR()  
    // Accessor 1 is the non-automatic accessor  
    BEGIN_ACCESSOR(1, true)  
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)  
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)  
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)  
    END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 Le code principal se présente comme ci\-après.  L'appel de `MoveNext` récupère automatiquement des données de l'ID de colonne de clé primaire à l'aide d'un accesseur 0.  Notez comment la méthode **Insert** vers la fin utilise l'accesseur 1 pour éviter d'écrire dans la colonne de clé primaire.  
  
```  
int main(int argc, char* argv[])  
{  
    // Initalize COM  
    ::CoInitialize(NULL);  
  
    // Create instances of the data source and session  
    CDataSource source;  
    CSession session;  
    HRESULT hr = S_OK;  
  
    // Set initialization properties  
    CDBPropSet dbinit(DBPROPSET_DBINIT);  
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));  
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));  
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));  
  
    hr = source.Open("SQLOLEDB.1", &dbinit);  
    if (hr == S_OK)  
    {  
        hr = session.Open(source);  
        if (hr == S_OK)  
        {  
            // Ready to fetch/access data  
            CTable<CAccessor<CJobs> > jobs;  
  
            // Set properties for making the rowset a read/write cursor  
            CDBPropSet dbRowset(DBPROPSET_ROWSET);  
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);  
            dbRowset.AddProperty(DBPROP_UPDATABILITY,  
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |  
                DBPROPVAL_UP_DELETE);  
  
            hr = jobs.Open(session, "jobs", &dbRowset);  
            if (hr == S_OK)  
            {  
                // Calling MoveNext automatically retrieves ID  
                // (using accessor 0)  
                while(jobs.MoveNext() == S_OK)  
                   printf_s("Description = %s\n", jobs.szDescription);  
  
                hr = jobs.MoveFirst();  
                if (hr == S_OK)  
                {  
                    jobs.nID = 25;  
                    strcpy_s(&jobs.szDescription[0],  
                             jobs.sizeOfDescription,  
                             "Developer");  
                    jobs.nMinLvl = 10;  
                    jobs.nMaxLvl = 20;  
  
                    jobs.dwDescription = DBSTATUS_S_OK;  
                    jobs.dwID = DBSTATUS_S_OK;  
                    jobs.dwMaxLvl = DBSTATUS_S_OK;  
                    jobs.dwMinLvl = DBSTATUS_S_OK;  
  
                    // Insert method uses accessor 1  
                    // (to avoid writing to the primary key column)  
                    hr = jobs.Insert(1);     
                }  
                jobs.Close();  
            }  
            session.Close();  
        }  
        source.Close();  
    }  
  
    // Uninitialize COM  
    ::CoUninitialize();  
    return 0;  
}  
```  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)   
 [Enregistrements utilisateur](../../data/oledb/user-records.md)