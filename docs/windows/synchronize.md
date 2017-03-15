---
title: "synchronize | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.synchronize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "synchronize attribute"
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# synchronize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

synchronise l'accès à la méthode cible.  
  
## Syntaxe  
  
```  
  
[synchronize]  
  
```  
  
## Notes  
 L'attribut de **synchronisez** C\+\+ implémente une prise en charge de synchroniser la méthode cible d'objet.  La synchronisation permet à plusieurs objets pour utiliser une ressource commune \(telle qu'une méthode de classe\) pour accéder de la méthode cible.  
  
 Le code inséré par cet attribut appelle la méthode appropriée d' `Lock` \(déterminée par le modèle de thread\) au début de la méthode cible.  Lorsque la méthode est quittée, `Unlock` est appelé automatiquement.  Pour plus d'informations sur ces fonctionnalités, consultez [CComAutoThreadModule : : Verrouillage](../Topic/CComAutoThreadModule::Lock.md)  
  
 Cet attribut requiert que [coclasse](../windows/coclass.md), [progid](../windows/progid.md), ou un attribut de [vi\_progid](../windows/vi-progid.md) \(ou un attribut différent qui implique un d'eux\) également être appliqués au même élément.  Si attribut unique en est utilisé, les deux autres sont automatiquement appliqués.  par exemple, si **progid** est appliqué, **vi\_progid** et **coclasse** sont également appliqués.  
  
## Exemple  
 Le code suivant fournit la synchronisation pour la méthode d' `UpdateBalance` d'objet d' `CMyClass` .  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Méthode de la classe, méthode|  
|**reproductible**|Non|  
|**attributs requis**|Un ou plusieurs des éléments suivants : **coclasse**, **progid**, ou **vi\_progid**.|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)