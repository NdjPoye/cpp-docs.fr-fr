---
title: "restricted | Microsoft Docs"
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
  - "vc-attr.restricted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "restricted attribute"
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# restricted
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie qu'un membre d'un module, d'une interface, ou d'une dispinterface ne peut pas être appelé arbitrairement.  
  
## Syntaxe  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### Paramètres  
 `interfaces`  
 Une ou plusieurs interfaces qui ne peuvent être appelées arbitrairement sur un objet COM.  Ce paramètre est uniquement valide appliqué à une classe.  
  
## Notes  
 L'attribut de **limité** C\+\+ a les mêmes fonctionnalités que l'attribut de [limité](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL.  
  
## Exemple  
 Le code suivant montre comment utiliser l'attribut de **limité** :  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|méthode d'interface, `interface`, **classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|**coclasse** \(appliqué à **classe** ou à `struct`\)|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)