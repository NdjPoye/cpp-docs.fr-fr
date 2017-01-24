---
title: "satype | Microsoft Docs"
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
  - "vc-attr.satype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "satype attribute"
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# satype
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie le type de données de la structure de **SAFEARRAY** .  
  
## Syntaxe  
  
```  
  
      [ satype(  
   data_type  
) ]  
```  
  
#### Paramètres  
 *data\_type*  
 Le type de données de la structure des données de **SAFEARRAY** passée comme paramètre à une méthode d'interface.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|paramètre d'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
## Notes  
 l'attribut de **satype** C\+\+ spécifie le type de données de **SAFEARRAY**.  
  
> [!NOTE]
>  Un niveau d'indirection est supprimé du pointeur de **SAFEARRAY** dans le fichier généré .idl de la façon dont il est déclaré dans le fichier .cpp.  
  
## Exemple  
  
```  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## Voir aussi  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [id](../windows/id.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)