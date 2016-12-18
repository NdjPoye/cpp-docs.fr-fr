---
title: "Cr&#233;ation d&#39;un fournisseur actualisable | Microsoft Docs"
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
  - "notifications, prise en charge dans les fournisseurs"
  - "fournisseurs OLE DB, créer"
  - "fournisseurs OLE DB, pouvant être mis à jour"
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un fournisseur actualisable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 6.0 prenait en charge uniquement les fournisseurs en lecture seule.  Visual C\+\+.NET prend en charge des fournisseurs actualisables ou des fournisseurs qui peuvent mettre à jour \(modifier\) le magasin de données.  Cette rubrique explique comment créer des fournisseurs actualisables au moyen de modèles OLE DB.  
  
 Cette rubrique suppose que vous démarrez avec un fournisseur opérationnel.  La création d'un fournisseur actualisable repose sur deux étapes.  Vous devez d'abord déterminer comment le fournisseur apportera des modifications au magasin de données et, notamment, si les modifications doivent être effectuées immédiatement ou différées jusqu'à l'émission d'une commande de mise à jour.  « [Fournisseurs actualisables](#vchowmakingprovidersupdatable) » décrit les modifications et les paramétrages que vous devez effectuer dans le code du fournisseur.  
  
 Ensuite, vous devez vous assurer que le fournisseur offre toutes les fonctionnalités requises pour prendre en charge tout ce que le consommateur peut lui demander.  Si le consommateur souhaite mettre le magasin de données à jour, le fournisseur doit alors contenir le code qui écrit des données permanentes dans le magasin de données.  Par exemple, vous pouvez utiliser la bibliothèque Runtime C ou MFC pour exécuter de telles opérations sur votre source de données.  « [Écriture dans la source de données](#vchowwritingtothedatasource) » décrit comment accéder en écriture à la source de données, se comporter avec la valeur **NULL** et les valeurs par défaut, et définir des indicateurs de colonnes.  
  
> [!NOTE]
>  UpdatePV est un exemple de fournisseur actualisable.  UpdatePV est similaire à MyProv sauf qu'il intègre une prise en charge pour la mise à jour.  
  
##  <a name="vchowmakingprovidersupdatable"></a> Fournisseurs actualisables  
 Pour rendre un fournisseur actualisable, il est essentiel de comprendre les opérations que le fournisseur doit appliquer au magasin de données et comment il doit exécuter ces opérations.  La principale question consiste, plus particulièrement, à savoir si les mises à jour du magasin de données doivent être effectuées de façon immédiate ou différée \(groupées en batch\) jusqu'à l'émission d'une commande de mise à jour.  
  
 Vous devez d'abord déterminer si vous devez hériter des classes `IRowsetChangeImpl` ou `IRowsetUpdateImpl` dans votre classe rowset.  Le fonctionnement des trois méthodes `SetData`, **InsertRows** et `DeleteRows` variera selon l'option que vous avez choisi d'implémenter.  
  
-   Si vous héritez de la classe [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), l'appel de ces trois méthodes modifie immédiatement le magasin de données.  
  
-   Si vous héritez de la classe [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), les méthodes différeront les modifications à apporter au magasin de données jusqu'à ce que vous appeliez **Update**, `GetOriginalData` ou **Undo**.  Si la mise à jour implique plusieurs modifications, qui sont effectuées en mode batch \(les modifications effectuées en mode batch peuvent exiger des ressources mémoire considérables\).  
  
 Notez que la classe `IRowsetUpdateImpl` est dérivée de la classe `IRowsetChangeImpl`.  `IRowsetUpdateImpl` vous fait ainsi bénéficier de la fonction batch en plus de la possibilité de modification.  
  
#### Pour prendre en charge la fonction de mise à jour dans votre fournisseur  
  
1.  Dans votre classe rowset, héritez de `IRowsetChangeImpl` ou de `IRowsetUpdateImpl`.  Ces classes fournissent les interfaces appropriées pour la modification du magasin de données :  
  
     **Ajout de IRowsetChange**  
  
     Ajoutez `IRowsetChangeImpl` à votre chaîne d'héritage en utilisant la forme suivante :  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     Ajoutez également `COM_INTERFACE_ENTRY(IRowsetChange)` à la section `BEGIN_COM_MAP` de votre classe rowset.  
  
     **Ajout de IRowsetUpdate**  
  
     Ajoutez `IRowsetUpdate` à votre chaîne d'héritage en utilisant la forme suivante :  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  Vous devez supprimer la ligne `IRowsetChangeImpl` de votre chaîne d'héritage.  Cette unique exception à la directive mentionnée plus haut doit inclure le code pour `IRowsetChangeImpl`.  
  
2.  Ajoutez le texte suivant à votre mappage COM \(**BEGIN\_COM\_MAP ... END\_COM\_MAP**\) :  
  
    |Si vous implémentez|Ajoutez au mappage COM|  
    |-------------------------|----------------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  Dans votre commande, ajoutez le texte suivant au mappage des jeux de propriétés \(**BEGIN\_PROPSET\_MAP ... END\_PROPSET\_MAP**\) :  
  
    |Si vous implémentez|Ajoutez au mappage des jeux de propriétés|  
    |-------------------------|-----------------------------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  Dans le mappage des jeux de propriétés, vous devez également inclure tous les paramètres suivants, tels qu'ils apparaissent ci\-dessous :  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     Vous trouverez les valeurs utilisées dans ces appels de macros dans Atldb.h pour les valeurs et les ID des propriétés \(si Atldb.h et la documentation en ligne diffèrent, c'est Atldb.h qui prévaut\).  
  
    > [!NOTE]
    >  De nombreux paramètres **VARIANT\_FALSE** et `VARIANT_TRUE` sont requis par les modèles OLE DB ; la spécification OLE DB indique qu'ils peuvent être accessibles en lecture\/écriture, mais les modèles OLE DB ne peuvent prendre en charge qu'une seule valeur.  
  
     **Si vous implémentez IRowsetChangeImpl**  
  
     Si vous implémentez `IRowsetChangeImpl`, vous devez définir les propriétés suivantes sur votre fournisseur.  Ces propriétés sont essentiellement utilisées pour demander les interfaces via **ICommandProperties::SetProperties**.  
  
    -   `DBPROP_IRowsetChange` : sa définition définit automatiquement **DBPROP\_IRowsetChange**.  
  
    -   `DBPROP_UPDATABILITY` : masque de bits qui spécifie les méthodes prises en charge par `IRowsetChange` : `SetData`, `DeleteRows` ou `InsertRow`.  
  
    -   `DBPROP_CHANGEINSERTEDROWS` : le consommateur peut appeler **IRowsetChange::DeleteRows** ou `SetData` pour obtenir les lignes récemment insérées.  
  
    -   `DBPROP_IMMOBILEROWS` : l'ensemble de lignes ne réorganisera pas de nouveau les lignes insérées ou mises à jour.  
  
     **Si vous implémentez IRowsetUpdateImpl**  
  
     Si vous implémentez `IRowsetUpdateImpl`, vous devez définir les propriétés suivantes sur votre fournisseur, en plus de la définition de toutes les propriétés pour `IRowsetChangeImpl` répertoriées précédemment :  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT` : doit être READ\_ONLY et VARIANT\_TRUE.  
  
    -   `DBPROP_OWNUPDATEDELETE` : doit être READ\_ONLY et VARIANT\_TRUE.  
  
    -   `DBPROP_OTHERINSERT` : doit être READ\_ONLY et VARIANT\_TRUE.  
  
    -   `DBPROP_OTHERUPDATEDELETE` : doit être READ\_ONLY et VARIANT\_TRUE.  
  
    -   `DBPROP_REMOVEDELETED` : doit être READ\_ONLY et VARIANT\_TRUE.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  Si vous prenez en charge les notifications, vous pouvez également avoir d'autres propriétés ; consultez la section consacrée à `IRowsetNotifyCP` pour cette liste.  
  
     Pour obtenir un exemple de la manière dont les propriétés sont définies, consultez le mappage du jeu de propriétés dans **CUpdateCommand** \(Rowset.h\) dans [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f).  
  
##  <a name="vchowwritingtothedatasource"></a> Écriture dans la source de données  
 Pour lire dans la source de données, appelez la fonction **Execute**.  Pour écrire dans la source de données, appelez la fonction `FlushData`. \(Dans un sens général, flush signifie enregistrer sur disque les modifications que vous effectuez dans une table ou un index.\)  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 Les arguments handle de ligne \(*HROW*\) et handle d'accesseur \(*HACCESSOR*\) vous permettent de spécifier la zone d'écriture.  En principe, vous accédez en écriture à un seul champ de données à la fois.  
  
 La méthode `FlushData` écrit les données dans le format où elles ont été stockées à l'origine.  Si vous ne substituez pas cette fonction, votre fournisseur fonctionnera correctement, mais les modifications ne seront pas vidées dans le magasin de données.  
  
### Quand effectuer un vidage  
 Les modèles du fournisseur appellent `FlushData` chaque fois que les données doivent être écrites dans le magasin de données ; cela se produit généralement \(mais pas toujours\) à la suite d'appels aux fonctions suivantes :  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** \(si de nouvelles données doivent être insérées dans la ligne\)  
  
-   **IRowsetUpdate::Update**  
  
### Fonctionnement  
 Le consommateur lance un appel qui requiert un vidage \(**Update**, par exemple\) et cet appel est passé au fournisseur, qui effectue toujours les opérations suivantes :  
  
-   appelle `SetDBStatus` chaque fois que vous avez une limite de valeur d'état \(consultez *OLE DB Programmers Reference,* chapitre 6, *Data Parts: Status*\) ;  
  
-   vérifie les indicateurs de colonnes ;  
  
-   appelle `IsUpdateAllowed`.  
  
 Ces trois étapes contribuent à assurer la sécurité.  Ensuite, le fournisseur appelle `FlushData`.  
  
### Comment implémenter FlushData  
 Pour implémenter `FlushData`, vous devez tenir compte de plusieurs points :  
  
-   vous assurer que le magasin de données peut gérer les modifications ;  
  
-   gérer les valeurs **NULL** ;  
  
-   gérer les valeurs par défaut.  
  
 Pour implémenter votre propre méthode `FlushData`, vous devez :  
  
-   accéder à votre classe rowset ;  
  
-   dans la classe rowset, placer la déclaration de :  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   fournir une implémentation de `FlushData`.  
  
 Une implémentation correcte de `FlushData` stocke uniquement les lignes et les colonnes qui sont effectivement mises à jour.  Vous pouvez utiliser les paramètres *HROW* et *HACCESSOR* pour déterminer les ligne et colonne qui sont stockées à des fins d'optimisation.  
  
 En principe, le plus grand défi consiste à travailler avec votre propre magasin de données natif.  Si possible, essayez de :  
  
-   conserver une méthode aussi simple que possible pour l'accès en écriture à votre magasin de données ;  
  
-   gérer les valeurs **NULL** \(facultatives mais conseillées\) ;  
  
-   gérer les valeurs par défaut \(facultatives mais conseillées\).  
  
 La meilleure chose à faire est d'avoir de vraies valeurs spécifiées dans le magasin de données pour les valeurs **NULL** et les valeurs par défaut.  Si vous pouvez extrapoler ces données, c'est encore mieux.  Sinon, il est recommandé de ne pas autoriser les valeurs **NULL** et les valeurs par défaut.  
  
 L'exemple suivant est un exemple de la manière dont la méthode `FlushData` est implémentée dans la classe `RUpdateRowset` de l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f) \(consultez Rowset.h dans l'exemple de code\) :  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
...  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");  
  
    USES_CONVERSION;  
    enum {  
        sizeOfString = 256,  
        sizeOfFileName = MAX_PATH  
    };  
    FILE*    pFile = NULL;  
    TCHAR    szString[sizeOfString];  
    TCHAR    szFile[sizeOfFileName];  
    errcode  err = 0;  
  
    ObjectLock lock(this);  
  
    // From a filename, passed in as a command text,   
    // scan the file placing data in the data array.  
    if (m_strCommandText == (BSTR)NULL)  
    {  
        ATLTRACE( "RRowsetUpdate::FlushData -- "  
                  "No filename specified\n");  
        return E_FAIL;  
    }  
  
    // Open the file  
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));  
    if ((szFile[0] == _T('\0')) ||   
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))  
    {  
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");  
        return DB_E_NOTABLE;  
    }  
  
    // Iterate through the row data and store it.  
    for (long l=0; l<m_rgRowData.GetSize(); l++)  
    {  
        CAgentMan am = m_rgRowData[l];  
  
        _putw((int)am.dwFixed, pFile);  
  
        if (_tcscmp(&am.szCommand[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
    }  
  
    if (fflush(pFile) == EOF || fclose(pFile) == EOF)  
    {  
        ATLTRACE("RRowsetUpdate::FlushData -- "  
                 "Couldn't flush or close file\n");  
    }  
  
    return S_OK;  
}  
```  
  
### Gestion des modifications  
 Pour que votre fournisseur gère les modifications, vous devrez d'abord vous assurer que le magasin de données \(comme un fichier texte ou un fichier vidéo\) dispose des fonctionnalités requises vous permettant d'effectuer les modifications voulues.  Si ce n'est pas le cas, vous devez créer ce code séparément du projet fournisseur.  
  
### Gestion des données NULL  
 Il est possible qu'un utilisateur final envoie des données de type **NULL**.  Lorsque vous écrivez des valeurs **NULL** dans des champs de la source de données, vous pouvez rencontrer des problèmes.  Imaginez une application de prise de commandes qui accepte des valeurs pour la ville et le code postal ; elle peut accepter l'une ou l'autre valeur ou les deux mais pas aucune valeur, car dans ce cas la distribution ne serait pas possible.  Vous devez donc restreindre certaines combinaisons de valeurs **NULL** aux champs qui ont un sens logique dans votre application.  
  
 En tant que développeur de fournisseurs, vous devez réfléchir à la façon dont vous stockerez les données, à la manière dont vous lirez ces données à partir du magasin de données et à la manière dont vous spécifierez tout cela à l'utilisateur.  Plus précisément, vous devez songer à la façon de changer l'état des données du jeu de lignes dans la source de données \(par exemple, DataStatus \= **NULL**\).  Vous déterminez la valeur à retourner quand un consommateur accède à un champ contenant une valeur **NULL**.  
  
 Examinez le code dans l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f) ; il illustre la façon dont un fournisseur peut gérer des données **NULL**.  Dans UpdatePV, le fournisseur stocke les données **NULL** en écrivant la chaîne « NULL » dans le magasin de données.  Quand il lit des données **NULL** à partir du magasin de données, il visualise cette chaîne puis vide la mémoire tampon, créant une chaîne **NULL**.  Il dispose également d'une substitution de `IRowsetImpl::GetDBStatus` dans laquelle il retourne **DBSTATUS\_S\_ISNULL** si cette valeur de données est vide.  
  
### Marquage des colonnes autorisant la valeur Null  
 Si vous implémentez également des rowsets du schéma \(consultez `IDBSchemaRowsetImpl`\), votre implémentation doit spécifier dans le jeu de lignes **DBSCHEMA\_COLUMNS** \(généralement marqué dans le fournisseur par **C***xxx***SchemaColSchemaRowset**\) que la colonne autorise la valeur Null.  
  
 Vous devez aussi spécifier que toutes les colonnes autorisant la valeur Null contiennent la valeur **DBCOLUMNFLAGS\_ISNULLABLE** dans votre version de `GetColumnInfo`.  
  
 Dans l'implémentation des modèles OLE DB, si vous ne marquez pas les colonnes comme autorisant la valeur Null, le fournisseur suppose qu'elles doivent contenir une valeur et ne permet pas au consommateur de lui envoyer des valeurs null.  
  
 L'exemple suivant montre comment la fonction **CommonGetColInfo** est implémentée dans **CUpdateCommand** \(consultez UpProvRS.cpp\) dans UpdatePV.  Notez comment la valeur **DBCOLUMNFLAGS\_ISNULLABLE** se présente pour les colonnes autorisant la valeur Null.  
  
```  
/////////////////////////////////////////////////////////////////////////////  
// CUpdateCommand (in UpProvRS.cpp)  
  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)  
{  
    static ATLCOLUMNINFO _rgColumns[6];  
    ULONG ulCols = 0;  
  
    if (bBookmark)  
    {  
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,  
                            sizeof(DWORD), DBTYPE_BYTES,  
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,  
                            DBCOLUMNFLAGS_ISBOOKMARK)  
        ulCols++;  
    }  
  
    // Next set the other columns up.  
    // Add a fixed length entry for OLE DB conformance testing purposes  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,  
                        10, 255, GUID_NULL, CAgentMan, dwFixed,   
                        DBCOLUMNFLAGS_WRITE |   
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand,  
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,   
                        255, 255, GUID_NULL, CAgentMan, szText,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szText2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    if (pcCols != NULL)  
    {  
        *pcCols = ulCols;  
    }  
  
    return _rgColumns;  
}  
```  
  
### Valeurs par défaut  
 Comme avec les données **NULL**, il vous appartient de traiter les valeurs par défaut qui peuvent être modifiées.  
  
 `FlushData` et **Execute** retournent `S_OK` par défaut.  Par conséquent, si vous ne substituez pas cette fonction, vous avez l'impression que les modifications ont réussi \(`S_OK` est retourné\), mais celles\-ci ne sont pas transmises au magasin de données.  
  
 Dans l'exemple [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f) \(dans Rowset.h\), la méthode `SetDBStatus` gère les valeurs par défaut de la façon suivante :  
  
```  
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,  
                            ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);  
  
    void* pData = NULL;  
    char* pDefaultData = NULL;  
    DWORD* pFixedData = NULL;  
  
    switch (*pdbStatus)  
    {  
        case DBSTATUS_S_DEFAULT:  
            pData = (void*)&m_rgRowData[pRow->m_iRowset];  
            if (pColInfo->wType == DBTYPE_STR)  
            {  
                pDefaultData = (char*)pData + pColInfo->cbOffset;  
                strcpy_s(pDefaultData, "Default");  
            }  
            else  
            {  
                pFixedData = (DWORD*)((BYTE*)pData +   
                                          pColInfo->cbOffset);  
                *pFixedData = 0;  
                return S_OK;  
            }  
            break;  
        case DBSTATUS_S_ISNULL:  
        default:  
            break;  
    }  
    return S_OK;  
}  
```  
  
### Indicateurs de colonnes  
 Si vous prenez en charge les valeurs par défaut de vos colonnes, vous devez définit cette fonction à l'aide de métadonnées dans la classe**\<***classe fournisseur***\>SchemaRowset**.  Paramétrez *m\_bColumnHasDefault* \= `VARIANT_TRUE`.  
  
 Il vous revient également de définir les indicateurs de colonnes, qui sont spécifiés à l'aide du type énuméré **DBCOLUMNFLAGS**.  Les indicateurs de colonnes décrivent les caractéristiques des colonnes.  
  
 Par exemple, au sein de la classe `CUpdateSessionColSchemaRowset` dans [UpdatePV](http://msdn.microsoft.com/fr-fr/c8bed873-223c-4a7d-af55-f90138c6f38f) \(Session.h\), la première colonne est définie de la façon suivante :  
  
```  
// Set up column 1  
trData[0].m_ulOrdinalPosition = 1;  
trData[0].m_bIsNullable = VARIANT_FALSE;  
trData[0].m_bColumnHasDefault = VARIANT_TRUE;  
trData[0].m_nDataType = DBTYPE_UI4;  
trData[0].m_nNumericPrecision = 10;  
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |  
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;  
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));  
m_rgRowData.Add(trData[0]);  
```  
  
 Ce code spécifie, entre autres, que la colonne prend en charge une valeur par défaut 0, qu'elle est modifiable et que toutes les données qu'elle contient ont la même longueur.  Si vous voulez que les données d'une colonne aient une longueur variable, évitez alors de définir cet indicateur.  
  
## Voir aussi  
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)