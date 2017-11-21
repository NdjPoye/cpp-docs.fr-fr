---
title: length_is | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.length_is
dev_langs: C++
helpviewer_keywords: length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6051502e81593bdb13f32d7904f912cc6f294cef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="lengthis"></a>length_is
Spécifie le nombre d’éléments de tableau doit être transmis.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *expression*  
 Une ou plusieurs expressions de langage C. Emplacements d’arguments vide sont autorisées.  
  
## <a name="remarks"></a>Remarques  
 Le **length_is** attribut C++ a les mêmes fonctionnalités que le [length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez [first_is](../windows/first-is.md) pour obtenir un exemple montrant comment spécifier une section d’un tableau.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Champ `struct` ou **union**, paramètre de l’interface, méthode d’interface|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributs de paramètre](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   
