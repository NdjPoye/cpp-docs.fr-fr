---
title: "CComPtr Class | Microsoft Docs"
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
  - "CComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtr class"
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe intelligente de pointeur pour gérer des pointeurs d'interface COM.  
  
## Syntaxe  
  
```  
  
      template<  
   class T   
>  
class CComPtr  
```  
  
#### Paramètres  
 `T`  
 Une interface COM qui spécifie le type de pointeur à enregistrer.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)|Constructeur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPtr::operator \=](../Topic/CComPtr::operator%20=.md)|Assigne un pointeur vers un pointeur de membre.|  
  
## Notes  
 ATL utilise `CComPtr` et [CComQIPtr](../../atl/reference/ccomqiptr-class.md) pour gérer des pointeurs d'interface COM.  Les deux sont dérivés de [CComPtrBase](../../atl/reference/ccomptrbase-class.md), et elles effectuent un décompte de références automatique.  
  
 Les classes de **CComPtr** et de [CComQIPtr](../../atl/reference/ccomqiptr-class.md) peuvent aider à éviter des fuites de mémoire en exécutant le décompte de références automatique.  Les fonctions suivantes elles exécutent les mêmes opérations logiques ; toutefois, notez comment la deuxième version peut être moins sujette aux erreurs à l'aide de la classe de **CComPtr** :  
  
 [!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/CPP/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/CPP/ccomptr-class_2.cpp)]  
  
 Dans les versions debug, lien atlsd.lib pour le traçage de code.  
  
## Hiérarchie d'héritage  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [Class Overview](../../atl/atl-class-overview.md)