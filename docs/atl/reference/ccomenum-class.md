---
title: "CComEnum Class | Microsoft Docs"
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
  - "CComEnum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnum class"
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnum Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe définit un objet énumérateur COM selon un tableau.  
  
## Syntaxe  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class ThreadModel = CcomObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnum :  
   public CComEnumImpl<Base, piid, T, Copy>,  
   public CComObjectRootEx< ThreadModel >  
```  
  
#### Paramètres  
 `Base`  
 Une interface d'énumérateur COM \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\).  
  
 `piid`  
 Pointeur vers l'ID d'interface de l'interface d'énumérateur.  
  
 `T`  
 Le type d'élément exposé par l'interface d'énumérateur.  
  
 `Copy`  
 [classe de stratégie de copie](../../atl/atl-copy-policy-classes.md)homogène.  
  
 `ThreadModel`  
 Le modèle de thread de la classe.  Ce paramètre a la valeur par défaut au modèle de thread global d'objet utilisé dans votre projet.  
  
## Notes  
 `CComEnum` définit un objet énumérateur COM selon un tableau.  Cette classe est analogue à [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) qui implémente un énumérateur sur un conteneur STL.  Les étapes standard pour l'utilisation de cette classe sont dessinées les grandes lignes ci\-dessous.  Pour plus d'informations, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Pour utiliser cette classe :  
  
-   `typedef` une spécialisation de cette classe.  
  
-   Utilisez `typedef` comme argument template dans une spécialisation d' `CComObject`.  
  
-   Créez une instance de la spécialisation d' `CComObject` .  
  
-   Initialisez l'objet énumérateur en appelant [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md).  
  
-   Retourne l'interface de l'énumérateur au client.  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Exemple  
 Le code indiqué ci\-dessous fournit une fonction réutilisable pour créer et initialiser un objet énumérateur.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/CPP/ccomenum-class_1.h)]  
  
 Cette fonction de modèle peut être utilisée pour implémenter la propriété d' `_NewEnum` d'une interface de collection comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/CPP/ccomenum-class_2.h)]  
  
 Ce code crée `typedef` pour `CComEnum` qui expose un vecteur de **variant**s via l'interface d' **IEnumVariant** .  La classe de **CVariantArrayCollection** spécialise simplement **CreateEnumerator** pour utiliser les objets énumérateurs de ce type et passe les arguments nécessaires.  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [CComEnumImpl Class](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)