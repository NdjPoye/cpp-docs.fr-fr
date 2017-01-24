---
title: "CTypedPtrMap Class | Microsoft Docs"
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
  - "CTypedPtrMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrMap class"
  - "mappages"
  - "pointer maps"
  - "template classes, CTypedPtrMap class"
  - "type-safe collections"
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un wrapper de type sécurisé pour les objets des classes de pointeur\- mappage `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, et `CMapStringToPtr`.  
  
## Syntaxe  
  
```  
template< class BASE_CLASS, class KEY, class VALUE >  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### Paramètres  
 `BASE_CLASS`  
 Classe de base de la classe typée de mappage de type ; doit être une classe de mappage de type \(`CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, ou `CMapStringToPtr`\).  
  
 `KEY`  
 Classe de l'objet utilisé comme clé dans le mappage.  
  
 `VALUE`  
 Classe de l'objet stocké dans le mappage.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](../Topic/CTypedPtrMap::GetNextAssoc.md)|Obtient l'élément pour itérer.|  
|[CTypedPtrMap::Lookup](../Topic/CTypedPtrMap::Lookup.md)|Retourne `KEY` sur `VALUE`.|  
|[CTypedPtrMap::RemoveKey](../Topic/CTypedPtrMap::RemoveKey.md)|Supprime un élément spécifié par une clé.|  
|[CTypedPtrMap::SetAt](../Topic/CTypedPtrMap::SetAt.md)|Insère un élément dans le mappage ; remplace un élément existant si une clé correspondante est trouvée.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTypedPtrMap::operator](../Topic/CTypedPtrMap::operator.md)|Insère un élément dans le mappage.|  
  
## Notes  
 Lorsque vous utilisez `CTypedPtrMap`, les aide de la fonctionnalité de vérification de type C\+\+ éliminent des erreurs provoquées par les types pointeur incompatibles.  
  
 Étant donné que toutes fonctions d' `CTypedPtrMap` sont inline, l'utilisation de ce modèle n'affecte pas considérablement la taille ou la vitesse de votre code.  
  
 Pour plus d'informations sur l'utilisation `CTypedPtrMap`, consultez les articles [collections](../../mfc/collections.md) et [Classes basée sur les rôles](../../mfc/template-based-classes.md).  
  
## Hiérarchie d'héritage  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## Configuration requise  
 **Header:** afxtempl.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)