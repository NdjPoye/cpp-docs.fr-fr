---
title: "CAccessorBase::ReleaseAccessors | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorBase::ReleaseAccessors"
  - "CAccessorBase.ReleaseAccessors"
  - "ReleaseAccessors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAccessors (méthode)"
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase::ReleaseAccessors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère les accesseurs créés par la classe.  
  
## Syntaxe  
  
```  
  
      HRESULT ReleaseAccessors(  
   IUnknown* pUnk   
);  
```  
  
#### Paramètres  
 *pUnk*  
 \[in\] Un pointeur vers une interface de **IUnknown** de l'objet COM pour lequel les accesseurs ont été créés.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Appelée à partir de [CAccessorRowset::Close](../../data/oledb/caccessorrowset-close.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CAccessorBase, classe](../../data/oledb/caccessorbase-class.md)