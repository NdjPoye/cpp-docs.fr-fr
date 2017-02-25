---
title: "CComCoClass Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComCoClass"
  - "ATL.CComCoClass"
  - "ATL::CComCoClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "CComCoClass class"
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComCoClass Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer des instances d'une classe, et obtenir ses propriétés.  
  
## Syntaxe  
  
```  
  
      template<  
   class T,  
   const CLSID* pclsid = &CLSID_NULL  
>  
class CComCoClass  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `CComCoClass`.  
  
 *pclsid*  
 Un pointeur vers le CLSID de l'objet.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCoClass::CreateInstance](../Topic/CComCoClass::CreateInstance.md)|\(Statique\) crée une instance de la classe et des requêtes pour une interface.|  
|[CComCoClass::Error](../Topic/CComCoClass::Error.md)|\(Statique\) retourne des informations sur l'erreur riches au client.|  
|[CComCoClass::GetObjectCLSID](../Topic/CComCoClass::GetObjectCLSID.md)|\(Statique\) retourne l'identificateur de classe de l'objet.|  
|[CComCoClass::GetObjectDescription](../Topic/CComCoClass::GetObjectDescription.md)|Substitution \(statique\) pour retourner la description de l'objet.|  
  
## Notes  
 `CComCoClass` fournit des méthodes pour récupérer le CLSID d'un objet, définir les informations d'erreur, et créer des instances de la classe.  Toute classe stockée dans [tableau d'objets](http://msdn.microsoft.com/fr-fr/b57619cc-534f-4b8f-bfd4-0c12f937202f) doit être dérivée d' `CComCoClass`.  
  
 `CComCoClass` définit également le modèle par défaut de fabrique de classes et de regroupement pour votre objet.  `CComCoClass` utilise les deux macros suivantes :  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) déclare la fabrique de classe pour être [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) déclare que votre objet peut être regroupé.  
  
 Vous pouvez substituer l'une ou l'autre de ces valeurs par défaut en spécifiant une autre macro dans la définition de classe.  Par exemple, pour utiliser [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) au lieu d' `CComClassFactory`, spécifiez la macro de [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) :  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/CPP/ccomcoclass-class_1.h)]  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)