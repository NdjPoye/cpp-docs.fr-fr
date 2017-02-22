---
title: "CStdioFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStdioFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStdioFile class"
  - "I/O [MFC], stream"
  - "stream I/O"
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CStdioFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente le fichier à l'exécution de flux c comme ouvert par la fonction runtime [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## Syntaxe  
  
```  
class CStdioFile : public CFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStdioFile::CStdioFile](../Topic/CStdioFile::CStdioFile.md)|Construit un objet d' `CStdioFile` d'un chemin d'accès ou d'un pointeur de fichier.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStdioFile::Open](../Topic/CStdioFile::Open.md)|Surchargé.  Open est destiné à une utilisation avec le constructeur par défaut d' `CStdioFile` \(substitutions [CFile::Open](../Topic/CFile::Open.md)\).|  
|[CStdioFile::ReadString](../Topic/CStdioFile::ReadString.md)|Lit une ligne de texte.|  
|[CStdioFile::Seek](../Topic/CStdioFile::Seek.md)|Positionne le pointeur de fichier en cours.|  
|[CStdioFile::WriteString](../Topic/CStdioFile::WriteString.md)|Écrit une ligne de texte.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStdioFile::m\_pStream](../Topic/CStdioFile::m_pStream.md)|Contient un pointeur vers un fichier ouvert.|  
  
## Notes  
 Les fichiers de flux sont mis en mémoire tampon et peuvent être ouverts en mode texte \(par défaut\) ou le mode binaire.  
  
 Le mode texte fournit un traitement spécial pour les paires saut de ligne\-retour chariot.  Lorsque vous écrivez un caractère de saut de ligne \(0x0A\) à un objet d' `CStdioFile` de vue de texte, la paire d'octets \(0x0D, 0x0A\) est envoyée au fichier.  Lorsque vous lisez, la paire d'octets \(0x0D, 0x0A\) est traduite à un octet 0x0A unique.  
  
 [fichier C](../../mfc/reference/cfile-class.md) fonctionne [double](../Topic/CFile::Duplicate.md), [LockRange](../Topic/CFile::LockRange.md), et [UnlockRange](../Topic/CFile::UnlockRange.md) ne sont pas pris en charge pour `CStdioFile`.  
  
 Si vous appelez ces fonctions sur `CStdioFile`, vous obtiendrez [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Pour plus d'informations sur l'utilisation `CStdioFile`, consultez les articles [fichiers dans MFC](../../mfc/files-in-mfc.md) et [gestion de fichiers](../../c-runtime-library/file-handling.md) dans *la référence de la bibliothèque Runtime*.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../Topic/CFile::Duplicate.md)   
 [CFile::LockRange](../Topic/CFile::LockRange.md)   
 [CFile::UnlockRange](../Topic/CFile::UnlockRange.md)   
 [CNotSupportedException Class](../../mfc/reference/cnotsupportedexception-class.md)   
 [Comment faire : utilisez la classe de fichier C ?](http://go.microsoft.com/fwlink/?LinkId=128046)