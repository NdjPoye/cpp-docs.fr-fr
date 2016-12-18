---
title: "CHttpFile Class | Microsoft Docs"
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
  - "CHttpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpFile class"
  - "fichiers HTTP"
  - "HTTP requests, requesting and reading files"
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHttpFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités pour demander et lire des fichiers sur un serveur HTTP.  
  
## Syntaxe  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CHttpFile::CHttpFile](../Topic/CHttpFile::CHttpFile.md)|Crée un objet `CHttpFile`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md)|Ajoute des en\-têtes à la demande envoyée à un serveur HTTP.|  
|[CHttpFile::EndRequest](../Topic/CHttpFile::EndRequest.md)|Termine une demande envoyée à un serveur HTTP avec la fonction membre de [SendRequestEx](../Topic/CHttpFile::SendRequestEx.md) .|  
|[CHttpFile::GetFileURL](../Topic/CHttpFile::GetFileURL.md)|Obtient l'URL du fichier spécifié.|  
|[CHttpFile::GetObject](../Topic/CHttpFile::GetObject.md)|Obtient l'objet cible du verbe dans une requête à un serveur HTTP.|  
|[CHttpFile::GetVerb](../Topic/CHttpFile::GetVerb.md)|Obtient le verbe utilisé dans une requête à un serveur HTTP.|  
|[CHttpFile::QueryInfo](../Topic/CHttpFile::QueryInfo.md)|Retourne la réponse ou les en\-têtes de requête du serveur HTTP.|  
|[CHttpFile::QueryInfoStatusCode](../Topic/CHttpFile::QueryInfoStatusCode.md)|Récupère le code d'état associé à une requête HTTP et le place dans le paramètre fourni d' `dwStatusCode` .|  
|[CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md)|Envoie une requête à un serveur HTTP.|  
|[CHttpFile::SendRequestEx](../Topic/CHttpFile::SendRequestEx.md)|Envoie une requête à un serveur HTTP à l'aide de les méthodes d' [Écriture](../Topic/CInternetFile::Write.md) ou de [WriteString](../Topic/CInternetFile::WriteString.md) d' `CInternetFile`.|  
  
## Notes  
 Si votre session Internet lit les données d'un serveur HTTP, vous devez créer une instance d' `CHttpFile`.  
  
 Pour en savoir plus sur la façon dont `CHttpFile` fonctionne avec les autres classes Internet MFC, consultez l'article [Programmation avec Internet WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## Configuration requise  
 **Header:** afxinet.h  
  
## Voir aussi  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)