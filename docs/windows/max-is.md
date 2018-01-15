---
title: max_is | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.max_is
dev_langs: C++
helpviewer_keywords: max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d43ed06797ed79942a43612ab4c9ae774c4fcf17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="maxis"></a>max_is
Désigne la valeur maximale pour un index de tableau valide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *expression*  
 Une ou plusieurs expressions de langage C. Emplacements d’arguments vide sont autorisées.  
  
## <a name="remarks"></a>Notes  
 Le **max_is** attribut C++ a les mêmes fonctionnalités que le [max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) attribut MIDL.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Champ `struct` ou **union**, paramètre de l’interface, méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|**size_is**|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Exemple  
 Consultez [first_is](../windows/first-is.md) pour obtenir un exemple montrant comment spécifier une section d’un tableau.  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributs de paramètre](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
