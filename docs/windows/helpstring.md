---
title: HelpString | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstring
dev_langs: C++
helpviewer_keywords: helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f3df545f5d87d36c26d999dc3a5fbee8720830c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="helpstring"></a>helpstring
Spécifie une chaîne de caractères qui est utilisée pour décrire l’élément auquel elle s’applique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 `string`  
 Le texte de la chaîne d’aide.  
  
## <a name="remarks"></a>Notes  
 Le **helpstring** attribut C++ a les mêmes fonctionnalités que le [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [defaultvalue](../windows/defaultvalue.md) pour obtenir un exemple montrant comment utiliser **helpstring**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, `typedef`, **classe**, méthode, propriété|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpFile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
