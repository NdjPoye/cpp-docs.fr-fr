---
title: "CTypedPtrArray Class | Microsoft Docs"
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
  - "CTypedPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrArray class"
  - "pointer arrays"
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un wrapper de type sécurisé pour les objets de classe `CPtrArray` ou `CObArray`.  
  
## Syntaxe  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### Paramètres  
 `BASE_CLASS`  
 Classe de base de la classe typée de tableau de pointeurs ; doit être une classe de tableau \(`CObArray` ou `CPtrArray`\).  
  
 `TYPE`  
 Type des éléments stockés dans le tableau de classe de base.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTypedPtrArray::Add](../Topic/CTypedPtrArray::Add.md)|Ajoute un élément à la fin d'un tableau.  Élève le tableau si nécessaire|  
|[CTypedPtrArray::Append](../Topic/CTypedPtrArray::Append.md)|Ajoute le contenu d'un tableau à la fin de les autres.  Élève le tableau si nécessaire|  
|[CTypedPtrArray::Copy](../Topic/CTypedPtrArray::Copy.md)|Copie une autre tableau au tableau ; élève le tableau si nécessaire.|  
|[CTypedPtrArray::ElementAt](../Topic/CTypedPtrArray::ElementAt.md)|Retourne une référence temporaire au pointeur d'élément dans le tableau.|  
|[CTypedPtrArray::GetAt](../Topic/CTypedPtrArray::GetAt.md)|Retourne la valeur à un index donné.|  
|[CTypedPtrArray::InsertAt](../Topic/CTypedPtrArray::InsertAt.md)|Insère un élément \(ou les éléments dans un autre tableau\) à un index spécifié.|  
|[CTypedPtrArray::SetAt](../Topic/CTypedPtrArray::SetAt.md)|Définit la valeur pour un index donné ; tableau non \- autorisée pour développer.|  
|[CTypedPtrArray::SetAtGrow](../Topic/CTypedPtrArray::SetAtGrow.md)|Définit la valeur pour un index donné ; élève le tableau si nécessaire.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CTypedPtrArray::operator](../Topic/CTypedPtrArray::operator.md)|Définit ou obtient l'élément à l'index spécifié.|  
  
## Notes  
 Lorsque vous utilisez `CTypedPtrArray` plutôt qu' `CPtrArray` ou `CObArray`, les aide de la fonctionnalité de vérification de type C\+\+ éliminent des erreurs provoquées par les types pointeur incompatibles.  
  
 En outre, le wrapper d' `CTypedPtrArray` effectue une grande partie du cast qui est nécessaire si vous avez utilisé `CObArray` ou `CPtrArray`.  
  
 Étant donné que toutes fonctions d' `CTypedPtrArray` sont inline, l'utilisation de ce modèle n'affecte pas considérablement la taille ou la vitesse de votre code.  
  
 Pour plus d'informations sur l'utilisation `CTypedPtrArray`, consultez les articles [collections](../../mfc/collections.md) et [Classes basée sur les rôles](../../mfc/template-based-classes.md).  
  
## Hiérarchie d'héritage  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## Configuration requise  
 **Header:** afxtempl.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)