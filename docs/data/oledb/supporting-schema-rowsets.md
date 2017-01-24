---
title: "Prise en charge des jeux de lignes du sch&#233;ma | Microsoft Docs"
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
  - "OLE DB (modèles du consommateur), jeux de lignes du schéma"
  - "fournisseurs OLE DB, jeux de lignes du schéma"
  - "OLE DB, jeux de lignes du schéma"
  - "jeux de lignes du schéma"
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des jeux de lignes du sch&#233;ma
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les jeux de lignes du schéma permettent aux consommateurs d'obtenir des informations sur un magasin de données sans connaître sa structure sous\-jacente, ou schéma.  Par exemple, un magasin de données peut avoir des tables organisées selon une hiérarchie définie par l'utilisateur, de sorte que la seule façon de connaître le schéma est de le lire. \(En guise d'exemple supplémentaire, notez que les Assistants Visual C\+\+ utilisent les jeux de lignes du schéma pour générer des accesseurs destinés au consommateur.\) Pour permettre au consommateur d'accomplir cette tâche, l'objet session du fournisseur expose les méthodes sur l'interface [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx).  Dans les applications Visual C\+\+, vous utilisez la classe [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) pour implémenter **IDBSchemaRowset**.  
  
 `IDBSchemaRowsetImpl` prend en charge les méthodes suivantes :  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) vérifie la validité des restrictions par rapport à un jeu de lignes du schéma.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) implémente une fonction du créateur d'objet COM pour l'objet spécifié par le paramètre du modèle.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) spécifie les restrictions que vous prenez en charge sur un jeu de lignes particulier du schéma.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) retourne un jeu de lignes du schéma \(hérité de l'interface\).  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) retourne une liste de jeux de lignes du schéma accessible par `IDBSchemaRowsetImpl::GetRowset` \(héritée de l'interface\).  
  
## Prise en charge de l'Assistant Fournisseur OLE DB ATL  
 L'Assistant Fournisseur OLE DB ATL crée trois classes de schéma dans le fichier d'en\-tête de session :  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 Ces classes répondent aux demandes des consommateurs en matière d'informations sur les schémas ; notez que la spécification OLE DB exige que ces trois jeux de lignes du schéma soient pris en charge :  
  
-   Les handles **C** *ShortName* **SessionTRSchemaRowset** demandent des informations de table \(ensemble de lignes de schéma `DBSCHEMA_TABLES`\).  
  
-   Les handles **C** *ShortName* **SessionColSchemaRowset** demandent des informations sur la colonne \(ensemble de lignes de schéma **DBSCHEMA\_COLUMNS**\).  L'Assistant fournit un exemple d'implémentations de ces classes, qui retournent des informations de schéma pour un fournisseur DOS.  
  
-   Les handles **C***ShortName***SessionPTSchemaRowset** demandent des informations de schéma sur le type de fournisseur \(ensemble de lignes de schéma **DBSCHEMA\_PROVIDER\_TYPES**\).  L'implémentation par défaut fournie par l'Assistant retourne `S_OK`.  
  
 Vous pouvez personnaliser ces classes pour gérer les informations sur le schéma appropriées à votre fournisseur :  
  
-   Dans **C***ShortName***SessionTRSchemaRowset**, vous devez renseigner les champs du catalogue, de la table et de la description \(**trData.m\_szType**, **trData.m\_szTable** et **trData.m\_szDesc**\).  L'exemple généré par l'Assistant utilise une seule ligne \(table\).  D'autres fournisseurs peuvent retourner plusieurs tables.  
  
-   Dans **C***ShortName***SessionColSchemaRowset**, vous devez passer le nom de la table en tant que **DBID**.  
  
## Définition des restrictions  
 Un concept important dans la prise en charge des jeux de lignes du schéma est la définition des restrictions, que vous effectuez à l'aide de `SetRestrictions`.  Les restrictions permettent aux consommateurs d'extraire uniquement les lignes correspondantes \(par exemple, rechercher toutes les colonnes dans la table « MyTable »\).  Les restrictions sont facultatives, et dans le cas où aucune restriction n'est prise en charge \(valeur par défaut\), toutes les données sont retournées.  Pour obtenir un exemple de fournisseur qui prend en charge les restrictions, consultez l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
## Définition du mappage du schéma  
 Définissez un mappage du schéma comme celui\-ci dans Session.h \(UpdatePV\) :  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Pour prendre en charge **IDBSchemaRowset**, vous devez prendre en charge `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** et **DBSCHEMA\_PROVIDER\_TYPES**.  Vous pouvez ajouter des jeux de lignes du schéma supplémentaires selon vos besoins.  
  
 Déclarez une classe de jeu de lignes du schéma à l'aide d'une méthode `Execute` telle que `CUpdateSessionTRSchemaRowset` dans UpdatePV :  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Notez que la classe `CUpdateSession` hérite de `IDBSchemaRowsetImpl`, de sorte qu'elle possède toutes les méthodes de gestion des restrictions.  Faites appel à `CSchemaRowsetImpl` pour déclarer trois classes enfant \(énumérées dans le mappage du schéma ci\-dessus\) : `CUpdateSessionTRSchemaRowset` et `CUpdateSessionColSchemaRowset`, `CUpdateSessionPTSchemaRowset`.  Chacune de ces classes enfant possède une méthode `Execute` qui gère son jeu de restrictions respectif \(critères de recherche\).  Chaque méthode `Execute` compare les valeurs des paramètres `cRestrictions` et `rgRestrictions`.  Consultez la description de ces paramètres dans [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 Pour plus d'informations sur les restrictions correspondant à un jeu de lignes du schéma particulier, consultez la table des GUID des rowsets du schéma dans [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans le *Guide de référence du programmeur OLE DB* du [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 Par exemple, si vous avez pris en charge la restriction **TABLE\_NAME** sur `DBSCHEMA_TABLES`, vous devez procéder de la façon suivante :  
  
 D'abord, consultez `DBSCHEMA_TABLES` et vérifiez que ce type prend en charge quatre restrictions \(dans l'ordre\).  
  
|Restriction de jeu de lignes du schéma|Valeur de restriction|  
|--------------------------------------------|---------------------------|  
|**TABLE\_CATALOG**|0x1 \(binaire 1\)|  
|**TABLE\_SCHEMA**|0x2 \(binaire 10\)|  
|**TABLE\_NAME**|0x4 \(binaire 100\)|  
|**TABLE\_TYPE**|0x8 \(binaire 1000\)|  
  
 Ensuite, notez qu'à chaque restriction correspond un bit.  Dans la mesure où vous voulez prendre en charge **TABLE\_NAME** uniquement, vous devez retourner 0x4 dans l'élément `rgRestrictions`.  Si vous prenez en charge **TABLE\_CATALOG** et **TABLE\_NAME**, vous devrez retourner 0x5 \(binaire 101\).  
  
 Par défaut, l'implémentation retourne 0 \(ne prend en charge aucune restriction\) pour n'importe quelle demande.  UpdatePV est un exemple de fournisseur qui prend en charge les restrictions.  
  
### Exemple  
 Ce code provient de l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f).  UpdatePv prend en charge les trois jeux de lignes du schéma requis : `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** et **DBSCHEMA\_PROVIDER\_TYPES**.  En tant qu'exemple du mode d'implémentation de la prise en charge du schéma dans votre fournisseur, cette rubrique vous initie à l'implémentation du jeu de lignes **DBSCHEMA\_TABLE**.  
  
> [!NOTE]
>  Si l'exemple de code et le texte répertorié dans les rubriques suivantes diffèrent, c'est l'exemple de code qui doit être considéré comme étant la version la plus récente.  
  
 Lors de l'ajout de la prise en charge du schéma, la première étape consiste à déterminer les restrictions que vous allez prendre en charge.  Pour déterminer les restrictions disponibles pour votre jeu de lignes du schéma, examinez la spécification OLE DB pour la définition de **IDBSchemaRowset**.  Après la définition principale, vous allez voir une table contenant le nom du jeu de lignes du schéma, le nombre de restrictions et les colonnes des restrictions.  Sélectionnez le jeu de lignes du schéma que vous souhaitez prendre en charge, puis notez le nombre de restrictions et de colonnes des restrictions.  Par exemple, `DBSCHEMA_TABLES` prend en charge quatre restrictions \(**TABLE\_CATALOG**, **TABLE\_SCHEMA**, **TABLE\_NAME** et **TABLE\_TYPE**\) :  
  
```  
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,   
   ULONG* rgRestrictions)  
{  
    for (ULONG l=0; l<cRestrictions; l++)  
    {  
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
            rgRestrictions[l] = 0x0C;  
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))  
                 rgRestrictions[l] = 0x04;  
             else if (InlineIsEqualGUID(rguidSchema[l],  
                                        DBSCHEMA_PROVIDER_TYPES))  
                      rgRestrictions[l] = 0x00;  
   }  
}  
```  
  
 Chaque colonne de restriction est représentée par un bit.  Si vous souhaitez prendre en charge une restriction \(autrement dit, vous pouvez l'utiliser pour lancer une requête\), affectez la valeur 1 à ce bit.  Si vous ne souhaitez pas prendre en charge une restriction, affectez la valeur zéro à ce bit.  À partir de la ligne de code ci\-dessus, UpdatePV prend en charge les restrictions **TABLE\_NAME** et **TABLE\_TYPE** sur le jeu de lignes `DBSCHEMA_TABLES`.  Il s'agit des troisième \(masque binaire 100\) et quatrième \(masque binaire 1000\) restrictions.  Par conséquent, le masque de bits pour UpdatePv équivaut à 1100 \(ou 0x0C\) :  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 La fonction `Execute` suivante est similaire à celles qui figurent dans des jeux de lignes ordinaires.  Vous avez trois arguments : `pcRowsAffected`, `cRestrictions` et `rgRestrictions`.  La variable `pcRowsAffected` est un paramètre de sortie permettant au fournisseur de retourner le nombre de lignes dans le jeu de lignes du schéma.  Le paramètre `cRestrictions` est un paramètre d'entrée contenant le nombre de restrictions passées par le consommateur au fournisseur.  Le paramètre `rgRestrictions` est un tableau de valeurs **VARIANT** contenant les valeurs de restriction.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 La variable `cRestrictions` repose sur le nombre total de restrictions pour un jeu de lignes du schéma, que le fournisseur les prenne en charge ou non.  Dans la mesure où UpdatePv prend en charge deux restrictions \(les troisième et quatrième\), ce code recherche uniquement une valeur `cRestrictions` supérieure ou égale à trois.  
  
 La valeur de la restriction **TABLE\_NAME** est stockée dans `rgRestrictions[2]` \(de nouveau, la troisième restriction dans un tableau basé sur zéro est 2\).  Vous devez vérifier que la restriction est différente de `VT_EMPTY` pour pouvoir en fait la prendre en charge.  Notez que **VT\_NULL** n'est pas égale à `VT_EMPTY`.  **VT\_NULL** spécifie une valeur de restriction valide.  
  
 La définition UpdatePv d'un nom de table est un nom de chemin d'accès complet à un fichier texte.  Extrayez la valeur de restriction, puis essayez d'ouvrir le fichier afin de vous assurer que le fichier existe réellement.  Si le fichier n'existe pas, retournez `S_OK`.  Cela peut sembler être un retour en arrière mais ce que le code indique vraiment au consommateur c'est qu'aucune table portant le nom spécifié n'est prise en charge.  Le retour de `S_OK` signifie que le code a été exécuté correctement.  
  
```  
USES_CONVERSION;  
enum {  
            sizeOfszFile = 255  
};  
CTABLESRow  trData;  
FILE        *pFile = NULL;  
TCHAR       szFile[ sizeOfszFile ];  
errcode     err = 0;  
  
// Handle any restrictions sent to us. This only handles  
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th   
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets   
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04   
// for a total of (0x0C)  
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)  
{  
    CComBSTR bstrName = rgRestrictions[2].bstrVal;  
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))  
    {  
        // Check to see if the file exists  
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));  
        if (szFile[0] == _T('\0') ||   
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))  
        {  
            return S_OK;// Their restriction was invalid return no data  
        }  
        else  
        {  
            fclose(pFile);  
        }  
    }  
}  
```  
  
 La prise en charge de la quatrième restriction \(**TABLE\_TYPE**\) est similaire à celle de la troisième restriction.  Vérifiez que la valeur est différente de `VT_EMPTY`.  Cette restriction retourne uniquement le type de table, **TABLE**.  Pour déterminer les valeurs valides pour `DBSCHEMA_TABLES`, consultez l'annexe B du manuel *OLE DB Programmer's Reference* dans la section du jeu de lignes **TABLES**.  
  
```  
// TABLE_TYPE restriction:  
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)  
{  
    CComBSTR bstrType = rgRestrictions[3].bstrVal;  
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))  
    {  
        // This is kind of a blind restriction.  
        // This only actually supports  
        // TABLES so if you get anything else,   
        // just return an empty rowset.  
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)  
            return S_OK;  
    }  
}  
```  
  
 C'est là où vous créez en fait une entrée de ligne pour le jeu de lignes.  La variable `trData` correspond à **CTABLESRow**, une structure définie dans les modèles du fournisseur OLE DB.  **CTABLESRow** correspond à la définition du jeu de lignes **TABLES** dans l'annexe B de la spécification OLE DB.  Vous n'avez qu'une ligne à ajouter car vous ne pouvez prendre en charge qu'une table à la fois.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  
wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  
wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV définit trois colonnes seulement : **TABLE\_NAME**, **TABLE\_TYPE** et **DESCRIPTION**.  Vous devez noter les colonnes pour lesquelles vous retournez des informations, car vous avez besoin de ces informations lors de l'implémentation de `GetDBStatus` :  
  
```  
    _ATLTRY  
    {  
        m_rgRowData.Add(trData);  
    }  
    _ATLCATCHALL()  
    {  
        return E_OUTOFMEMORY;  
    }  
    //if (!m_rgRowData.Add(trData))  
    //    return E_OUTOFMEMORY;  
    *pcRowsAffected = 1;  
    return S_OK;  
}  
```  
  
 La fonction `GetDBStatus` est très importante pour le fonctionnement correct du jeu de lignes du schéma.  Dans la mesure où vous ne retournez pas de données pour chaque colonne dans le jeu de lignes **TABLES**, vous devez spécifier les colonnes pour lesquelles vous retournez des données et celles pour lesquelles vous ne retournez pas de données.  
  
```  
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pColInfo != NULL);  
  
    switch(pColInfo->iOrdinal)  
    {  
    case 3:     // TABLE_NAME  
    case 4:     // TABLE_TYPE  
    case 6:     // DESCRIPTION  
        return DBSTATUS_S_OK;  
        break;  
    default:  
        return DBSTATUS_S_ISNULL;  
    break;  
    }  
}  
```  
  
 Comme votre fonction `Execute` retourne des données pour les champs **TABLE\_NAME**, **TABLE\_TYPE** et **DESCRIPTION** depuis l'ensemble de lignes **TABLES**, vous pouvez consulter l'Annexe B de la spécification OLE DB et déterminer \(en comptant du haut vers le bas\) qu'ils sont les ordinaux 3, 4 et 6.  Pour chacune de ces colonnes, retournez **DBSTATUS\_S\_OK**.  Pour toutes les autres colonnes, retournez **DBSTATUS\_S\_ISNULL**.  Il est important de retourner cet état, car le consommateur peut ne pas comprendre que la valeur que vous retournez est égale à **NULL** ou à une autre valeur.  Notez encore une fois que la valeur **NULL** ne signifie pas vide.  
  
 Pour plus d'informations sur l'interface du jeu de lignes du schéma OLE DB, consultez l'interface [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) dans le manuel OLE DB Programmer's Reference.  
  
 Pour plus d'informations sur la façon dont les consommateurs peuvent utiliser les méthodes **IDBSchemaRowset**, consultez [Récupération de métadonnées à l'aide de jeux de lignes du schéma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Pour obtenir un exemple de fournisseur qui prend en charge les jeux de lignes du schéma, consultez l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
## Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)