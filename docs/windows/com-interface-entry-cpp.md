---
title: "com_interface_entry (C++) | Microsoft Docs"
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
  - "vc-attr.com_interface_entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com_interface_entry attribute"
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# com_interface_entry (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ajoute une entrée d'interface dans le mappage COM de la classe cible.  
  
## Syntaxe  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### Paramètres  
 *com\_interface\_entry*  
 Chaîne contenant le texte réel de l'entrée.  Pour une liste des valeurs possibles, consultez [macros de COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20Macros.md).  
  
## Notes  
 L'attribut d' `com_interface_entry` C\+\+ insère le contenu intégral d'une chaîne de caractères dans le mappage d'interfaces COM de l'objet de la cible.  Si l'attribut est appliqué qu'une seule fois à l'objet cible, l'entrée est insérée dans le début du mappage d'interfaces existant.  Si l'attribut est appliqué à plusieurs reprises au même objet cible, les entrées sont insérées au début du mappage d'interfaces dans l'ordre dans lequel elles sont reçues.  
  
 Cet attribut requiert que [coclasse](../windows/coclass.md), [progid](../windows/progid.md), ou un attribut de [vi\_progid](../windows/vi-progid.md) \(ou un attribut différent qui implique un d'eux\) également être appliqués au même élément.  Si attribut unique en est utilisé, les deux autres sont automatiquement appliqués.  par exemple, si **progid** est appliqué, **vi\_progid** et **coclasse** sont également appliqués.  
  
 Étant donné que la première utilisation d' `com_interface_entry` provoque la nouvelle interface à insérer au début du mappage d'interface, il doit être l'un des types suivants de COM\_INTERFACE\_ENTRY :  
  
-   COM\_INTERFACE\_ENTRY  
  
-   COM\_INTERFACE\_ENTRY\_IID  
  
-   COM\_INTERFACE\_ENTRY2  
  
-   COM\_INTERFACE\_ENTRY2\_IID  
  
 les utilisations supplémentaires de l'attribut d' `com_interface_entry` peuvent utiliser tous les types pris en charge de COM\_INTERFACE\_ENTRY.  
  
 Cette restriction est nécessaire car ATL utilise la première entrée dans la table d'interface comme identité **IUnknown**; par conséquent, l'entrée doit être une interface valide.  Par exemple, l'exemple de code suivant est pas valide car la première entrée dans la table d'interface ne spécifie pas une interface COM réelle.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## Exemple  
 Le code suivant ajoute deux entrées au mappage d'IU existant COM de **CMyBaseClass**.  La première est une interface standard, et la deuxième masque l'interface d' **IDebugTest** .  
  
```  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 Le mappage résultant d'objet COM pour **CMyBaseClass** est la suivante :  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Oui|  
|**attributs requis**|Un ou plusieurs des éléments suivants : **coclasse**, **progid**, ou **vi\_progid**.|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)