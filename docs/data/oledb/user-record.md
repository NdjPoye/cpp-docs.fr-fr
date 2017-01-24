---
title: "Enregistrement utilisateur | Microsoft Docs"
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
  - "fournisseurs OLE DB, enregistrement utilisateur"
  - "enregistrements, utilisateur"
  - "jeux de lignes, enregistrement utilisateur"
  - "enregistrements utilisateur"
  - "enregistrements utilisateur, description"
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Enregistrement utilisateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'enregistrement utilisateur fournit le code et la structure de données représentant les données de colonne d'un jeu de lignes.  Un enregistrement utilisateur peut être créé au moment de la compilation ou de l'exécution.  Lorsque vous créez un fournisseur par l'intermédiaire de l'Assistant Fournisseur OLE DB ATL, l'Assistant crée un enregistrement utilisateur par défaut qui ressemble à celui\-ci \(à supposer que vous ayez spécifié un nom de fournisseur \[nom court\] « MyProvider »\) :  
  
```  
class CWindowsFile:  
   public WIN32_FIND_DATA  
{  
public:  
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
  
};  
```  
  
 Les modèles du fournisseur OLE DB gèrent toutes les particularités OLE DB concernant les interactions avec le client.  Pour acquérir les données d'une colonne nécessaires pour une réponse, le fournisseur appelle la fonction `GetColumnInfo`, que vous devez placer dans l'enregistrement utilisateur.  Vous pouvez substituer explicitement `GetColumnInfo` dans l'enregistrement utilisateur en la déclarant, par exemple, dans le fichier .h comme illustré ici :  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Ceci équivaut à :  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Vous devez également implémenter `GetColumnInfo` dans le fichier .cpp de l'enregistrement utilisateur.  
  
 Les macros PROVIDER\_COLUMN\_MAP facilitent la création d'une fonction `GetColumnInfo` :  
  
-   BEGIN\_PROVIDER\_COLUMN\_MAP définit le prototype de la fonction et un tableau statique de structures **ATLCOLUMNINFO**.  
  
-   PROVIDER\_COLUMN\_ENTRY définit et initialise une structure **ATLCOLUMNINFO** unique.  
  
-   END\_PROVIDER\_COLUMN\_MAP ferme le tableau et la fonction.  Elle place également le décompte des éléments du tableau dans le paramètre `pcCols`.  
  
 Quand un enregistrement utilisateur est créé au moment de l'exécution, **GetColumnInfo** utilise le paramètre `pThis` pour recevoir un pointeur désignant une instance de rowset ou de command.  Les commandes et les jeux de lignes doivent prendre en charge l'interface `IColumnsInfo`, de façon que les informations des colonnes puissent être obtenues à partir de ce pointeur.  
  
 **CommandClass** et **RowsetClass** correspondent aux interfaces command et rowset qui utilisent l'enregistrement utilisateur.  
  
 Pour obtenir un exemple plus détaillé de la façon de substituer `GetColumnInfo` dans un enregistrement utilisateur, consultez [Détermination de manière dynamique des colonnes retournées au consommateur](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)