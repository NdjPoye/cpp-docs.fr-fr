---
title: Utilisation de plusieurs accesseurs sur un ensemble de lignes | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a30108ec344091631094cd55f6a3bd3f0f4a4a54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="using-multiple-accessors-on-a-rowset"></a>Utilisation de plusieurs accesseurs dans un jeu de lignes
Il existe trois principaux scénarios dans lesquels vous devez utiliser plusieurs accesseurs :  
  
-   **Plusieurs ensembles de lignes en lecture/écriture.** Dans ce scénario, vous avez une table avec une clé primaire. Vous souhaitez être en mesure de lire toutes les colonnes de la ligne, y compris la clé primaire. Vous souhaitez également en mesure d’écrire des données à toutes les colonnes à l’exception de la clé primaire (car vous ne peut pas écrire dans la colonne clé primaire). Dans ce cas, vous pouvez configurer deux accesseurs :  
  
    -   L’accesseur 0 contient toutes les colonnes.  
  
    -   L’accesseur 1 contient toutes les colonnes à l’exception de la clé primaire.  
  
-   **Performances** Dans ce scénario, une ou plusieurs colonnes contiennent une grande quantité de données, par exemple, aux fichiers de graphiques, audio ou vidéo. Chaque fois que vous déplacez vers une ligne, vous probablement ne souhaitez pas extraire la colonne avec le fichier de données de grande taille, car cela risque de ralentir les performances de votre application.  
  
     Vous pouvez définir des accesseurs distincts dans lequel le premier accesseur contient toutes les colonnes sauf celle contenant une grande quantité de données, et il récupère des données à partir de ces colonnes automatiquement ; Il s’agit de l’accesseur automatique. Le deuxième accesseur récupère seulement la colonne contenant les données de grande taille, mais ne récupère pas les données de cette colonne de façon automatique. Vous pouvez avoir d’autres méthodes mettre à jour ou récupèrent les données volumineuses à la demande.  
  
    -   L’accesseur 0 est un accesseur automatique ; Il récupère toutes les colonnes sauf celle contenant une grande quantité de données.  
  
    -   L’accesseur 1 n’est pas un accesseur automatique ; Il récupère la colonne avec des données volumineuses.  
  
     Utilisez l’argument automatique pour spécifier si l’accesseur est un accesseur automatique.  
  
-   **Plusieurs colonnes ISequentialStream.** Dans ce scénario, vous avez plus d’une colonne contenant `ISequentialStream` données. Toutefois, chaque accesseur est limité à un `ISequentialStream` flux de données. Pour résoudre ce problème, configurez plusieurs accesseurs, chacun contenant un seul `ISequentialStream` pointeur.  
  
 Normalement, vous créez des accesseurs en utilisant le [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) et [END_ACCESSOR](../../data/oledb/end-accessor.md) macros. Vous pouvez également utiliser le [db_accessor](../../windows/db-accessor.md) attribut. (Les accesseurs sont décrits plus en détail dans [enregistrements utilisateur](../../data/oledb/user-records.md).) Les macros ou l’attribut spécifient si un accesseur est automatique ou un accesseur non automatique :  
  
-   Dans un accesseur automatique, les méthodes de déplacement telles que **MoveFirst**, `MoveLast`, `MoveNext`, et `MovePrev` récupérer des données pour toutes les colonnes spécifiées automatiquement. L’accesseur 0 doit être l’accesseur automatique.  
  
-   Dans un accesseur non automatique, la récupération ne se produit pas jusqu'à ce que vous appelez explicitement une méthode telle que **mise à jour**, **insérer**, **Fetch**, ou **supprimer**. Dans les scénarios décrits ci-dessus, vous pouvez récupérer toutes les colonnes à chaque déplacement. Vous pouvez placer une ou plusieurs colonnes dans un accesseur séparé et en faire un accesseur non automatique, comme indiqué ci-dessous.  
  
 L’exemple suivant utilise plusieurs accesseurs pour lire et écrire dans la table des tâches de la base de données pubs de SQL Server à l’aide de plusieurs accesseurs. Il s’agit le plus souvent utilisés des accesseurs multiples ; consultez le scénario « plusieurs ensembles de lignes en lecture/écriture » ci-dessus.  
  
 La classe d’enregistrement utilisateur est comme suit. Elle définit deux accesseurs : l’accesseur 0 contient uniquement la colonne clé primaire (ID) et l’accesseur 1 contient d’autres colonnes.  
  
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
  
 Le code principal est la suivante. Appel de `MoveNext` récupère automatiquement des données à partir de l’ID de colonne de clé primaire à l’aide de l’accesseur 0. Notez comment la **insérer** méthode près de l’accesseur utilise 1 pour éviter d’écrire dans la colonne clé primaire.  
  
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
            CTable<CAccessor<CJobs>> jobs;  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation d’accesseurs](../../data/oledb/using-accessors.md)   
 [Enregistrements utilisateur](../../data/oledb/user-records.md)