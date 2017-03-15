---
title: "CMyProviderWindowsFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderwindowsfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderWindowsFile (classe)"
  - "fournisseurs OLE DB, fichiers générés par l'Assistant"
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CMyProviderWindowsFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Assistant crée une classe devant contenir une ligne de données ; en l'occurrence, elle s'appelle `CMyProviderWindowsFile`.  Le code suivant pour `CMyProviderWindowsFile` est généré par un Assistant et répertorie tous les fichiers dans un répertoire à l'aide de la structure **WIN32\_FIND\_DATA**.  `CMyProviderWindowsFile` hérite de la structure **WIN32\_FIND\_DATA** :  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
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
  
 `CMyProviderWindowsFile` est appelée [classe de l'enregistrement utilisateur](../../data/oledb/user-record.md) car elle contient également un mappage décrivant les colonnes dans le jeu de lignes du fournisseur.  Le mappage de colonnes du fournisseur contient une entrée pour chaque champ dans le jeu de lignes en utilisant les macros PROVIDER\_COLUMN\_ENTRY.  Ces macros spécifient le nom de colonne, l'ordinal et l'offset pour une entrée de structure.  Dans le code ci\-dessus, les entrées de colonnes du fournisseur contiennent des offsets dans la structure **WIN32\_FIND\_DATA**.  Quand le consommateur appelle **IRowset::GetData**, les données sont transférées dans une mémoire tampon contiguë.  Au lieu de vous obliger à faire des opérations arithmétiques sur les pointeurs, le mappage vous permet de spécifier des données membres.  
  
 La classe `CMyProviderRowset` contient aussi la méthode `Execute`.  `Execute` est l'élément qui effectue la lecture des données dans la source native.  Le code suivant montre la méthode `Execute` générée par l'Assistant.  La fonction utilise les API Win32 **FindFirstFile** et `FindNextFile` pour récupérer des informations sur les fichiers dans le répertoire et les placer dans des instances de la classe `CMyProviderWindowsFile`.  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
   hFile = FindFirstFile(szDir, &wf);  
   if (hFile == INVALID_HANDLE_VALUE)  
      return DB_E_ERRORSINCOMMAND;  
   LONG cFiles = 1;  
   BOOL bMoreFiles = TRUE;  
   while (bMoreFiles)  
   {  
      if (!m_rgRowData.Add(wf))  
         return E_OUTOFMEMORY;  
      bMoreFiles = FindNextFile(hFile, &wf);  
      cFiles++;  
   }  
   FindClose(hFile);  
   if (pcRowsAffected != NULL)  
      *pcRowsAffected = cFiles;  
   return S_OK;  
}  
```  
  
 Le répertoire à explorer est représenté par `m_strCommandText`, qui contient le texte désigné par l'interface `ICommandText` dans l'objet command.  Si aucun répertoire n'est spécifié, le répertoire en cours est utilisé par défaut.  
  
 La méthode crée une entrée pour chaque fichier \(correspondant à une ligne\) et la place dans les données membres **m\_rgRowData**.  La classe `CRowsetImpl` définit les données membres **m\_rgRowData**.  Les données de ce tableau représentent la table entière et sont utilisées dans tous les modèles.  
  
## Voir aussi  
 [Fichiers générés par l'Assistant Fournisseur](../../data/oledb/provider-wizard-generated-files.md)