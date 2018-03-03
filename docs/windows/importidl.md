---
title: importidl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3fb56898107b1eca7cd30e06d75d253a02655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="importidl"></a>importidl
Insère le fichier .idl spécifié dans le fichier .idl généré.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Paramètres  
 `idl_file`  
 Identifie le nom du fichier .idl que vous souhaitez fusionner avec le fichier .idl qui sera généré pour votre application.  
  
## <a name="remarks"></a>Notes  
 Le **importidl** attribut C++ place la section en dehors du bloc de bibliothèque (dans `idl_file`) dans le fichier .idl généré de votre programme et de la section de la bibliothèque (dans `idl_file`) dans la section de la bibliothèque de votre programme fichier .idl généré.  
  
 Il pouvez que vous souhaitez utiliser **importidl**, par exemple, si vous souhaitez utiliser un fichier .idl de codé manuellement votre fichier .idl généré.  
  
## <a name="example"></a>Exemple  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
```  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|N'importe où|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs du compilateur](../windows/compiler-attributes.md)   
 [Attributs autonomes](../windows/stand-alone-attributes.md)   
 [importation](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [inclure](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
