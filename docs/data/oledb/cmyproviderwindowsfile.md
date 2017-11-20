---
title: CMyProviderWindowsFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cmyproviderwindowsfile
dev_langs: C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 63143532c5f5ad770c6234a24fbedf1b478ba143
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile
L’Assistant crée une classe pour contenir une ligne de données ; Dans ce cas, il est appelé `CMyProviderWindowsFile`. Le code suivant pour `CMyProviderWindowsFile` est généré par un Assistant et répertorie tous les fichiers dans un répertoire à l’aide de la **WIN32_FIND_DATA** structure. `CMyProviderWindowsFile`hérite de la **WIN32_FIND_DATA** structure :  
  
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
  
 `CMyProviderWindowsFile`est appelé le [classe d’enregistrement utilisateur](../../data/oledb/user-record.md) car elle contient également un mappage décrivant les colonnes dans l’ensemble de lignes du fournisseur. Le mappage de colonnes du fournisseur contient une entrée pour chaque champ dans l’ensemble de lignes à l’aide de macros PROVIDER_COLUMN_ENTRY. Les macros de spécifient le nom de colonne ordinal et l’offset à une entrée de la structure. Dans le code ci-dessus, les entrées de colonnes du fournisseur contiennent des offsets dans le **WIN32_FIND_DATA** structure. Lorsque le consommateur appelle **IRowset::GetData**, les données sont transférées dans une mémoire tampon contiguë. Plutôt que d’effectuer d’effectuer l’opération arithmétique de pointeur, le mappage permet de spécifier un membre de données.  
  
 Le `CMyProviderRowset` classe contient également le `Execute` (méthode). `Execute`est en fait, ce qui lit les données dans la source native. Le code suivant illustre la générées par l’Assistant `Execute` (méthode). La fonction utilise Win32 **FindFirstFile** et `FindNextFile` API pour extraire des informations sur les fichiers dans le répertoire et les placer dans des instances de la `CMyProviderWindowsFile` classe.  
  
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
  
 Le répertoire à Explorer est représenté par `m_strCommandText`; il contient le texte représenté par le `ICommandText` interface dans l’objet de commande. Si aucun répertoire n’est spécifié, il utilise le répertoire actif.  
  
 La méthode crée une entrée pour chaque fichier (correspondant à une ligne) et le place dans le **m_rgRowData** membre de données. Le `CRowsetImpl` classe définit les **m_rgRowData** membre de données. Les données de ce tableau représentent la table entière et sont utilisées dans tous les modèles.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers générés par l’Assistant Fournisseur](../../data/oledb/provider-wizard-generated-files.md)