---
title: "CRuntimeClass Structure | Microsoft Docs"
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
  - "CRuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRuntimeClass structure"
  - "dynamic class information"
  - "run-time class, CRuntimeClass structure"
  - "runtime, class information"
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRuntimeClass Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Chaque classe dérivée d' `CObject` est associée à une structure d' `CRuntimeClass` que vous pouvez utiliser pour obtenir des informations sur un objet ou sa classe de base au moment de l'exécution.  
  
## Syntaxe  
  
```  
struct CRuntimeClass  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRuntimeClass::CreateObject](../Topic/CRuntimeClass::CreateObject.md)|Crée un objet au moment de l'exécution.|  
|[CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md)|Crée un objet au moment de l'exécution à l'aide de le nom de classe familier.|  
|[CRuntimeClass::IsDerivedFrom](../Topic/CRuntimeClass::IsDerivedFrom.md)|Détermine si la classe est dérivée de la classe spécifiée.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRuntimeClass::m\_lpszClassName](../Topic/CRuntimeClass::m_lpszClassName.md)|Nom de la classe.|  
|[CRuntimeClass::m\_nObjectSize](../Topic/CRuntimeClass::m_nObjectSize.md)|Taille de l'objet en octets.|  
|[CRuntimeClass::m\_pBaseClass](../Topic/CRuntimeClass::m_pBaseClass.md)|Un pointeur vers la structure d' `CRuntimeClass` de la classe de base.|  
|[CRuntimeClass::m\_pfnCreateObject](../Topic/CRuntimeClass::m_pfnCreateObject.md)|Un pointeur vers une fonction qui crée dynamiquement l'objet.|  
|[CRuntimeClass::m\_pfnGetBaseClass](../Topic/CRuntimeClass::m_pfnGetBaseClass.md)|Retourne la structure d' `CRuntimeClass` \(uniquement disponible une fois lié dynamiquement\).|  
|[CRuntimeClass::m\_wSchema](../Topic/CRuntimeClass::m_wSchema.md)|Le nombre de schéma schéma de la classe.|  
  
## Notes  
 `CRuntimeClass` est une structure et n'a pas de classe de base.  
  
 La capacité de déterminer la classe d'un objet est au moment de l'exécution utile lorsque la vérification de type supplémentaire des arguments de fonction est nécessaire, ou lorsque vous devez écrire le code pour un objectif particulier selon la classe d'un objet.  Les informations sur la classe à l'exécution ne sont pas prises en charge directement par le langage C\+\+.  
  
 `CRuntimeClass` fournit des informations sur l'objet associé C\+\+, tel qu'un pointeur vers `CRuntimeClass` de la classe de base et le nom de classe ASCII de la classe connexe.  Cette structure implémente également les différentes fonctions qui peuvent être utilisées pour créer dynamiquement des objets, en spécifiant le type d'objet à l'aide d'un nom connu, et le déterminer si la classe connexe est dérivée d'une classe spécifique.  
  
 Pour plus d'informations sur l'utilisation `CRuntimeClass`, consultez l'article [Les informations sur la classe à l'exécution d'accès](../../mfc/accessing-run-time-class-information.md).  
  
## Hiérarchie d'héritage  
 `CRuntimeClass`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../Topic/CObject::GetRuntimeClass.md)   
 [CObject::IsKindOf](../Topic/CObject::IsKindOf.md)   
 [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)   
 [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)   
 [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)   
 [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)