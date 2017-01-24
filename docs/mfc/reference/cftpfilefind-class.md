---
title: "CFtpFileFind Class | Microsoft Docs"
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
  - "CFtpFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpFileFind class"
  - "recherches dans des fichiers (C++)"
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFtpFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aide dans les recherches de fichier Internet des serveurs FTP.  
  
## Syntaxe  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFtpFileFind::CFtpFileFind](../Topic/CFtpFileFind::CFtpFileFind.md)|Construit un objet `CFtpFileFind`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md)|Recherche un fichier sur un serveur FTP.|  
|[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)|Continue la recherche d'un appel précédent à [FindFile](../Topic/CFtpFileFind::FindFile.md).|  
|[CFtpFileFind::GetFileURL](../Topic/CFtpFileFind::GetFileURL.md)|Obtient l'URL, y compris le chemin d'accès, le fichier rencontrée.|  
  
## Notes  
 `CFtpFileFind` inclut les fonctions membres qui démarrent une recherche, recherchez un fichier, et retournent l'URL ou d'autres informations descriptives sur le fichier.  
  
 D'autres classes MFC conçues pour Internet et fichiers local trouvé incluent [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) et [CFileFind](../../mfc/reference/cfilefind-class.md).  Membres ont en qu' `CFtpFileFind`, ces classes fournissent un mécanisme transparente pour le client recherche des fichiers spécifiques, indépendamment du protocole de serveur ou du type de fichier \(un ordinateur local ou un serveur distant\).  Notez qu'il n'y a aucune classe MFC pour rechercher sur les serveurs HTTP parce que HTTP ne prend pas en charge la manipulation de fichiers direct requise pour les recherches.  
  
 Pour plus d'informations sur l'utilisation `CFtpFileFind` et les autres classes WinInet, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Exemple  
 Le code suivant montre comment énumérer tous les fichiers du répertoire actif du serveur FTP.  
  
 [!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/CPP/cftpfilefind-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)