---
title: "source (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source attribute"
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# source (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

sur une classe, spécifie les interfaces sources de l'objet COM pour des points de connexion.  Sur une propriété ou une méthode, indique que le membre retourne un objet ou a VARIANT qui représentent une source d'événements.  
  
## Syntaxe  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### Paramètres  
 `interfaces`  
 Une ou plusieurs interfaces que vous spécifiez lorsque vous appliquez l'attribut source pour une classe.  Ce paramètre n'est pas utilisé lorsque la source est appliquée à une propriété ou une méthode.  
  
## Notes  
 L'attribut de **source** C\+\+ a les mêmes fonctionnalités que l'attribut de [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL.  
  
 Vous pouvez utiliser l'attribut de [valeur par défaut](../windows/default-cpp.md) pour spécifier l'interface source par défaut pour un objet.  
  
## Exemple  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, `interface`|  
|**reproductible**|Non|  
|**attributs requis**|**coclasse** \(appliqué à la classe ou le struct\)|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)