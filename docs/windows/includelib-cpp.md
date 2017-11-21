---
title: includelib (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.includelib
dev_langs: C++
helpviewer_keywords: includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 31b9abdb8795d5814afe73fd7d48fb0e62ac8802
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="includelib-c"></a>includelib (C++)
Génère un fichier .idl ou .h à inclure dans le fichier .idl généré.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Name.idl*  
 Le nom du fichier .idl que vous souhaitez inclus dans le fichier .idl généré.  
  
## <a name="remarks"></a>Remarques  
 Le `includelib` attribut C++ génère un fichier .idl ou .h à inclure dans le fichier .idl généré, après la `importlib` instruction.  
  
## <a name="example"></a>Exemple  
 Le code suivant figure dans un fichier .cpp :  
  
```  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|N'importe où|  
|**Renouvelable**|Oui|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs autonomes](../windows/stand-alone-attributes.md)   
 [importation](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [inclure](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
