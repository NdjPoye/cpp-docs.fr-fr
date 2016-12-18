---
title: "registration_script | Microsoft Docs"
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
  - "vc-attr.registration_script"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registration_script attribute"
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# registration_script
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Exécute le script personnalisé spécifié d'inscription.  
  
## Syntaxe  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### Paramètres  
 *script*  
 Le chemin d'accès complet à un fichier personnalisé du script d'inscription \(.rgs\).  Une valeur d' **Aucun**, tel qu' `script = "none"`, indique que la coclasse n'a pas de spécifications d'inscription.  
  
## Notes  
 l'attribut de **registration\_script** C\+\+ exécute le script personnalisé d'alignement spécifié par **script**.  Si cet attribut n'est pas spécifié, un fichier du standard \(.rgs contenant les informations pour enregistrer le composant\) est utilisé.  Pour plus d'informations sur les fichiers .rgs, consultez [Le composant de Registre ATL \(registre\)](../atl/atl-registry-component-registrar.md).  
  
 Cet attribut requiert que [coclasse](../windows/coclass.md), [progid](../windows/progid.md), ou un attribut de [vi\_progid](../windows/vi-progid.md) \(ou un attribut différent qui implique un d'eux\) également être appliqués au même élément.  
  
## Exemple  
 Le code suivant spécifie que le composant a un script de Registre appelé cpp\_attr\_ref\_registration\_script.rgs.  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Un ou plusieurs des éléments suivants : **coclasse**, **progid**, ou **vi\_progid**.|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)