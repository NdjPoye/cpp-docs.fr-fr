---
title: "pragma | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.pragma"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pragma attribute"
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# pragma
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Effectue la chaîne spécifiée dans le fichier généré .idl sans utiliser des guillemets.  .  
  
## Syntaxe  
  
```  
  
      [ pragma(  
   pragma_statement  
) ];  
```  
  
#### Paramètres  
 *pragma\_statement*  
 Le pragma que vous souhaitez déplacer dans le fichier généré .idl.  
  
## Notes  
 L'attribut de **pragma** C\+\+ a les mêmes fonctionnalités que l'attribut de [pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL.  
  
## Exemple  
  
```  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|n'importe où|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)