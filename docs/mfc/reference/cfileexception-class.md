---
title: "CFileException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFile class, exceptions of"
  - "CFileException class"
  - "exceptions, file type"
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CFileException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une condition d'exception reliée aux données.  
  
## Syntaxe  
  
```  
class CFileException : public CException  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileException::CFileException](../Topic/CFileException::CFileException.md)|Construit un objet `CFileException`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileException::ErrnoToException](../Topic/CFileException::ErrnoToException.md)|Code de cause de la valeur qui correspond à un numéro d'erreur d'exécution.|  
|[CFileException::GetErrorMessage](../Topic/CFileException::GetErrorMessage.md)|Récupère le message décrivant une exception.|  
|[CFileException::OsErrorToException](../Topic/CFileException::OsErrorToException.md)|Retourne un code d'erreur correspondant au code d'erreur du système d'exploitation.|  
|[CFileException::ThrowErrno](../Topic/CFileException::ThrowErrno.md)|Lève une exception de fichier sur un numéro d'erreur d'exécution.|  
|[CFileException::ThrowOsError](../Topic/CFileException::ThrowOsError.md)|Lève une exception de fichier sur un numéro d'erreur du système d'exploitation.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileException::m\_cause](../Topic/CFileException::m_cause.md)|Contient le code portable correspondant à la cause de l'exception.|  
|[CFileException::m\_lOsError](../Topic/CFileException::m_lOsError.md)|Contient le numéro d'erreur du système d'exploitation associé.|  
|[CFileException::m\_strFileName](../Topic/CFileException::m_strFileName.md)|Contient le nom du fichier de cette exception.|  
  
## Notes  
 La classe d' `CFileException` inclut les données membres publiques qui contiennent le code portable cause et le numéro d'erreur de fonctionnement\-système\- détail.  La classe fournit également des fonctions membres static pour lever des exceptions de fichier et pour retourner des codes de provoque des erreurs du système d'exploitation et des erreurs de runtime C.  
  
 Les objets d'`CFileException` sont construits et levée dans les fonctions membres d' `CFile` et dans les fonctions membres des classes dérivées.  Vous pouvez accéder à ces objets dans la portée d'une expression de **collecteur** .  Pour la portabilité, utilisez uniquement le code de cause pour obtenir la raison d'une exception.  Pour plus d'informations sur les exceptions, consultez l'article [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Traitement des exceptions](../../mfc/reference/exception-processing.md)