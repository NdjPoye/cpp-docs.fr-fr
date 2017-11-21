---
title: HelpFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpfile
dev_langs: C++
helpviewer_keywords: helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6681f8f47895d94935f9fbbb3d93d379a82f7eb6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="helpfile"></a>helpfile
Définit le nom du fichier d’aide pour une bibliothèque de types.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ helpfile(  
   "filename"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *filename*  
 Le nom du fichier qui contient les rubriques d’aide.  
  
## <a name="remarks"></a>Remarques  
 Le **helpfile** attribut C++ a les mêmes fonctionnalités que le [helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) attribut MIDL.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [module](../windows/module-cpp.md) pour obtenir un exemple montrant comment utiliser **helpfile**.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, `typedef`, **classe**, méthode, propriété|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Attributs de méthode](../windows/method-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpContext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
