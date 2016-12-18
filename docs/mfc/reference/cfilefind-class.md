---
title: "CFileFind Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileFind class"
  - "fichiers (C++), rechercher"
  - "Internet files [C++], rechercher"
  - "local files"
  - "local files, rechercher"
  - "URLs [C++], rechercher"
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exécute la recherche de fichiers local et est la classe de base pour [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) et [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), qui exécutent des recherches de fichier Internet.  
  
## Syntaxe  
  
```  
class CFileFind : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileFind::CFileFind](../Topic/CFileFind::CFileFind.md)|Construit un objet `CFileFind`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileFind::Close](../Topic/CFileFind::Close.md)|Ferme la demande de recherche.|  
|[CFileFind::FindFile](../Topic/CFileFind::FindFile.md)|Recherche un répertoire d'un nom de fichier spécifié.|  
|[CFileFind::FindNextFile](../Topic/CFileFind::FindNextFile.md)|Continue la recherche d'un appel précédent à [FindFile](../Topic/CFileFind::FindFile.md).|  
|[CFileFind::GetCreationTime](../Topic/CFileFind::GetCreationTime.md)|Obtient le moment où le fichier a été créé.|  
|[CFileFind::GetFileName](../Topic/CFileFind::GetFileName.md)|Obtient le nom, y compris l'extension, le fichier rencontrée|  
|[CFileFind::GetFilePath](../Topic/CFileFind::GetFilePath.md)|Obtient le chemin d'accès complet du fichier rencontrée.|  
|[CFileFind::GetFileTitle](../Topic/CFileFind::GetFileTitle.md)|Obtient le titre du fichier rencontrée.  Le titre n'inclut pas l'extension.|  
|[CFileFind::GetFileURL](../Topic/CFileFind::GetFileURL.md)|Obtient l'URL, y compris le chemin d'accès, le fichier rencontrée.|  
|[CFileFind::GetLastAccessTime](../Topic/CFileFind::GetLastAccessTime.md)|Obtient le temps que le fichier a été demandé pour la dernière fois.|  
|[CFileFind::GetLastWriteTime](../Topic/CFileFind::GetLastWriteTime.md)|Obtient le moment où le fichier a été en dernier modifié et enregistré.|  
|[CFileFind::GetLength](../Topic/CFileFind::GetLength.md)|Obtient la longueur du fichier trouvée, en octets.|  
|[CFileFind::GetRoot](../Topic/CFileFind::GetRoot.md)|Obtient le répertoire racine du fichier rencontrée.|  
|[CFileFind::IsArchived](../Topic/CFileFind::IsArchived.md)|Détermine si le fichier rencontrée est archivé.|  
|[CFileFind::IsCompressed](../Topic/CFileFind::IsCompressed.md)|Détermine si le fichier rencontrée est compressé.|  
|[CFileFind::IsDirectory](../Topic/CFileFind::IsDirectory.md)|Détermine si le fichier rencontrée est un répertoire.|  
|[CFileFind::IsDots](../Topic/CFileFind::IsDots.md)|Détermine si le nom de fichier rencontrée est le nom « . » ou. « .  », indiquant qui est réellement un répertoire.|  
|[CFileFind::IsHidden](../Topic/CFileFind::IsHidden.md)|Détermine si le fichier rencontrée est masqué.|  
|[CFileFind::IsNormal](../Topic/CFileFind::IsNormal.md)|Détermine si le fichier rencontrée est normal \(en d'autres termes, n'a aucun attribut\).|  
|[CFileFind::IsReadOnly](../Topic/CFileFind::IsReadOnly.md)|Détermine si le fichier rencontrée est en lecture seule.|  
|[CFileFind::IsSystem](../Topic/CFileFind::IsSystem.md)|Détermine si le fichier rencontrée est un fichier système.|  
|[CFileFind::IsTemporary](../Topic/CFileFind::IsTemporary.md)|Détermine si le fichier rencontrée est temporaire.|  
|[CFileFind::MatchesMask](../Topic/CFileFind::MatchesMask.md)|Indique les attributs de fichier souhaités du fichier à rechercher.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileFind::CloseContext](../Topic/CFileFind::CloseContext.md)|Ferme le fichier spécifié par le handle actuel de recherche.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileFind::m\_pTM](../Topic/CFileFind::m_pTM.md)|Pointeur vers un objet d' `CAtlTransactionManager` .|  
  
## Notes  
 `CFileFind` inclut les fonctions membres qui démarrent une recherche, recherchez un fichier, et retournent le titre, le nom, ou le chemin d'accès du fichier.  Pour les recherches Internet, la fonction membre [GetFileURL](../Topic/CFileFind::GetFileURL.md) retourne l'URL du fichier.  
  
 `CFileFind` est la classe de base pour deux autres classes MFC conçues pour rechercher les types de serveur spécifiques : `CGopherFileFind` fonctionne en particulier avec des serveurs Gopher, et des travaux d' `CFtpFileFind` spécifiquement avec des serveurs FTP.  Ensemble, ces trois classes fournissent un mécanisme transparente pour le client recherche des fichiers, indépendamment du protocole de serveur, du type de fichier, ou de l'emplacement, sur un ordinateur local ou un serveur distant.  
  
 Le code suivant énumèrera tous les fichiers dans le répertoire actif, l'impression le nom de chaque fichier :  
  
 [!code-cpp[NVC_MFCFiles#31](../../mfc/codesnippet/CPP/cfilefind-class_1.cpp)]  
  
 Pour que l'exemple simple, ce code utilise la classe standard d' `cout` de bibliothèque C\+\+.  La ligne d' `cout` peut être remplacée par un appel à `CListBox::AddString`, par exemple, dans un programme avec une interface utilisateur graphique.  
  
 Pour plus d'informations sur l'utilisation `CFileFind` et les autres classes WinInet, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)