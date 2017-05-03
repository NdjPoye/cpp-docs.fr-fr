---
title: "Platform::Collections::VectorView, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView (classe)"
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Platform::Collections::VectorView, classe
Représente une vue en lecture seule d'une collection d'objets séquentielle qui peut être accessible individuellement par index. Le type de chaque objet de la collection est défini par le paramètre de modèle.  
  
## Syntaxe  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### Paramètres  
 `T`  
 Type des éléments contenus dans l'objet `VectorView`.  
  
 `E`  
 Spécifie un prédicat binaire pour tester l'égalité des valeurs de type `T`. La valeur par défaut est `std::equal_to<T>`.  
  
## Notes  
 La classe `VectorView` implémente l’interface [Windows::Foundation::Collections::IVectorView\<T\>](http://go.microsoft.com/fwlink/p/?LinkId=262411) et la prise en charge des itérateurs Standard Template Library.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[VectorView::VectorView \(constructeur\)](../cppcx/vectorview-vectorview-constructor.md)|Initialise une nouvelle instance de la classe VectorView.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[VectorView::First \(méthode\)](../cppcx/vectorview-first-method.md)|Retourne un itérateur qui spécifie le premier élément du VectorView.|  
|[VectorView::GetAt \(méthode\)](../cppcx/vectorview-getat-method.md)|Récupère l'élément du VectorView actuel qui est indiqué par l'index spécifié.|  
|[VectorView::GetMany \(méthode\)](../cppcx/vectorview-getmany-method.md)|Récupère une séquence d'éléments du VectorView actif en commençant à l'index spécifié.|  
|[VectorView::IndexOf \(méthode\)](../cppcx/vectorview-indexof-method.md)|Recherche l'élément spécifié dans l'objet VectorView actuel, et s'il existe, retourne l'index de l'élément.|  
|[VectorView::Size, méthode](../cppcx/vectorview-size-method.md)|Retourne le nombre d'éléments dans l'objet VectorView actuel.|  
  
## Hiérarchie d'héritage  
 `VectorView`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Création de composants Windows Runtime en C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)