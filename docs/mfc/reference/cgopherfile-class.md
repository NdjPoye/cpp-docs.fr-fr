---
title: "CGopherFile Class | Microsoft Docs"
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
  - "CGopherFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFile (classe)"
  - "gopher protocol files"
  - "Internet, gopher"
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités pour rechercher et lire des fichiers sur un serveur Gopher.  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres ont été déconseillées car elles ne fonctionnent pas à la plateforme Windows XP, mais ils continueront à travailler sur les plateformes antérieures.  
  
## Syntaxe  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CGopherFile::CGopherFile](../Topic/CGopherFile::CGopherFile.md)|Construit un objet `CGopherFile`.|  
  
## Notes  
 Le service de Gopher ne permet pas aux utilisateurs de modifier des données d'écriture dans un fichier de Gopher car les fonctions de ce service principalement en tant qu'interface pilotée par menu pour rechercher les informations.  Les fonctions membres d' `CGopherFile`**Write**, `WriteString`, et `Flush` ne sont pas implémentées pour `CGopherFile`.  En appelant les fonctions sur `CGopherFile` objet, retourne [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Pour en savoir plus sur la façon dont `CGopherFile` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator Class](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)