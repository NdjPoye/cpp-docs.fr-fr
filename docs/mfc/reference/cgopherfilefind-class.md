---
title: "CGopherFileFind Class | Microsoft Docs"
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
  - "CGopherFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFileFind class"
  - "recherches dans des fichiers (C++)"
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aide dans les recherches de fichier Internet des serveurs Gopher.  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres ont été déconseillées car elles ne fonctionnent pas à la plateforme Windows XP, mais ils continueront à travailler sur les plateformes antérieures.  
  
## Syntaxe  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherFileFind::CGopherFileFind](../Topic/CGopherFileFind::CGopherFileFind.md)|Construit un objet `CGopherFileFind`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md)|Recherche un fichier sur un serveur Gopher.|  
|[CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md)|Continue la recherche d'un appel précédent à [FindFile](../Topic/CGopherFileFind::FindFile.md).|  
|[CGopherFileFind::GetCreationTime](../Topic/CGopherFileFind::GetCreationTime.md)|Obtient le moment où le fichier spécifié a été créé.|  
|[CGopherFileFind::GetLastAccessTime](../Topic/CGopherFileFind::GetLastAccessTime.md)|Obtient le moment où le fichier spécifié a été demandé pour la dernière fois.|  
|[CGopherFileFind::GetLastWriteTime](../Topic/CGopherFileFind::GetLastWriteTime.md)|Obtient le moment où le fichier spécifié a été en dernier entré à.|  
|[CGopherFileFind::GetLength](../Topic/CGopherFileFind::GetLength.md)|Obtient la longueur du fichier trouvée, en octets.|  
|[CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md)|Obtenez un objet d' `CGopherLocator` .|  
|[CGopherFileFind::GetScreenName](../Topic/CGopherFileFind::GetScreenName.md)|Obtient le nom d'un écran de Gopher.|  
|[CGopherFileFind::IsDots](../Topic/CGopherFileFind::IsDots.md)|Tests pour les marques de répertoire actif et de répertoire parent en itérant au sein de les fichiers.|  
  
## Notes  
 `CGopherFileFind` inclut les fonctions membres qui démarrent une recherche, recherchez un fichier, et retournent l'URL d'un fichier.  
  
 D'autres classes MFC conçues pour Internet et fichiers local trouvé incluent [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) et [CFileFind](../../mfc/reference/cfilefind-class.md).  Membres ont en qu' `CGopherFileFind`, ces classes fournissent un mécanisme transparente pour que l'utilisateur recherche des fichiers spécifiques, indépendamment du protocole de serveur, du type de fichier, ou de l'emplacement \(un ordinateur local ou un serveur distant.\) Notez qu'il n'y a aucune classe MFC pour rechercher sur les serveurs HTTP parce que HTTP ne prend pas en charge la manipulation de fichiers direct requises par les recherches.  
  
> [!NOTE]
>  `CGopherFileFind` ne prend pas en charge les fonctions membres suivantes de sa classe de base [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
-   [GetRoot](../Topic/CFileFind::GetRoot.md)  
  
-   [GetFileName](../Topic/CFileFind::GetFileName.md)  
  
-   [GetFilePath](../Topic/CFileFind::GetFilePath.md)  
  
-   [GetFileTitle](../Topic/CFileFind::GetFileTitle.md)  
  
-   [GetFileURL](../Topic/CFileFind::GetFileURL.md)  
  
 De plus, lorsqu'elle est utilisée avec `CGopherFileFind`, la fonction membre [IsDots](../Topic/CFileFind::IsDots.md) d' `CFileFind` est toujours **FALSE**.  
  
 Pour plus d'informations sur l'utilisation `CGopherFileFind` et les autres classes WinInet, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)