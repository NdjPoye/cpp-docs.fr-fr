---
title: "CSimpleException Class | Microsoft Docs"
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
  - "CSimpleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleException class"
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est une classe de base des exceptions critiques ressource MFC.  
  
## Syntaxe  
  
```  
  
class AFX_NOVTABLE CSimpleException : public CException  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleException::CSimpleException](../Topic/CSimpleException::CSimpleException.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSimpleException::GetErrorMessage](../Topic/CSimpleException::GetErrorMessage.md)|Fournit le texte sur une erreur qui s'est produite.|  
  
## Notes  
 `CSimpleException` est la classe de base des exceptions critiques ressource MFC et traite la propriété et l'initialisation d'un message d'erreur.  Les classes suivantes utilisent `CSimpleException` comme leur classe de base :  
  
|||  
|-|-|  
|[Classe de CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Exception de mémoire insuffisante|  
|[Classe de CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Demandes d'une opération non prise en charge|  
|[Classe de CResourceException](../../mfc/reference/cresourceexception-class.md)|Ressource est introuvable ou non être créés|  
|[Classe de CUserException](../../mfc/reference/cuserexception-class.md)|Exception qui indique une ressource est introuvable|  
|[Classe de CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Exception qui indique un argument non valide|  
  
 Étant donné qu' `CSimpleException` est une classe de base abstraite, vous ne pouvez pas déclarer un objet d' `CSimpleException` directement.  À la place, vous devez déclarer des objets dérivés telles que celle\-ci dans le tableau précédent.  Si vous déclarez votre propre classe dérivée, utilisez les classes précédentes comme modèle.  
  
 Pour plus d'informations, consultez la rubrique et le [gestion des exceptions \(MFC\)](../../mfc/exception-handling-in-mfc.md)de [classe de CException](../../mfc/reference/cexception-class.md) .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Gestion des exceptions](../../mfc/exception-handling-in-mfc.md)