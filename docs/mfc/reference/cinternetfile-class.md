---
title: "CInternetFile Class | Microsoft Docs"
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
  - "CInternetFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetFile class"
  - "Internet files"
  - "Internet files, CInternetFile class"
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet l'accès aux fichiers sur les systèmes distants qui utilisent des protocoles Internet.  
  
## Syntaxe  
  
```  
  
class CInternetFile : public CStdioFile  
  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetFile::CInternetFile](../Topic/CInternetFile::CInternetFile.md)|Construit un objet `CInternetFile`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetFile::Abort](../Topic/CInternetFile::Abort.md)|Ferme le fichier, en ignorant tous les avertissements et erreurs.|  
|[CInternetFile::Close](../Topic/CInternetFile::Close.md)|Ferme `CInternetFile` et libère ses ressources.|  
|[CInternetFile::Flush](../Topic/CInternetFile::Flush.md)|Vide le contenu de la mémoire tampon d'écriture et garantit que les données en mémoire sont écrites sur l'ordinateur cible.|  
|[CInternetFile::GetLength](../Topic/CInternetFile::GetLength.md)|Retourne la taille du fichier.|  
|[CInternetFile::Read](../Topic/CInternetFile::Read.md)|Lit le nombre d'octets spécifiés.|  
|[CInternetFile::ReadString](../Topic/CInternetFile::ReadString.md)|Lit un flux de caractères.|  
|[CInternetFile::Seek](../Topic/CInternetFile::Seek.md)|Repositionne le pointeur dans un fichier ouvert.|  
|[CInternetFile::SetReadBufferSize](../Topic/CInternetFile::SetReadBufferSize.md)|Définit la taille de la mémoire tampon où les données sont lues.|  
|[CInternetFile::SetWriteBufferSize](../Topic/CInternetFile::SetWriteBufferSize.md)|Définit la taille de la mémoire tampon où les données sont écrites.|  
|[CInternetFile::Write](../Topic/CInternetFile::Write.md)|Écrit le nombre d'octets spécifiés.|  
|[CInternetFile::WriteString](../Topic/CInternetFile::WriteString.md)|Écrit une chaîne terminée par le caractère NULL dans un fichier.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetFile::operator HINTERNET](../Topic/CInternetFile::operator%20HINTERNET.md)|Un opérateur de cast d'un handle Internet.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CInternetFile::m\_hFile](../Topic/CInternetFile::m_hFile.md)|Un handle vers un fichier.|  
  
## Notes  
 Fournit une classe de base pour [CHttpFile](../../mfc/reference/chttpfile-class.md) et le fichier de [CGopherFile](../../mfc/reference/cgopherfile-class.md) classe.  Vous ne créez jamais directement un objet d' `CInternetFile` .  À la place, créez un objet d'une de ses classes dérivées en appelant [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md) ou [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).  Vous pouvez également créer un objet d' `CInternetFile` en appelant [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md).  
  
 Les fonctions membres d' `CInternetFile`**Ouvrir**, `LockRange`, `UnlockRange`, et `Duplicate` ne sont pas implémentées pour `CInternetFile`.  Si vous appelez ces fonctions sur `CInternetFile` objet, obtiendront vous [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Pour en savoir plus sur la façon dont `CInternetFile` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CStdioFile Class](../../mfc/reference/cstdiofile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)