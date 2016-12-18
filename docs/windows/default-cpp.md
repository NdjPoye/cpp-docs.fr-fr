---
title: "default (C++) | Microsoft Docs"
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
  - "vc-attr.default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attribut par défaut"
  - "attributs [C#], attribut par défaut"
  - "valeurs par défaut, attribut par défaut"
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique que l’interface personnalisée ou dispinterface définie dans une coclasse représente l’interface de programmabilité par défaut.  
  
## Syntaxe  
  
```  
  
[ default(  
interface1  
,  
   interface2  
) ]  
  
```  
  
#### Paramètres  
 *interface1*  
 Interface par défaut qui sera accessible aux environnements de script qui créent un objet en fonction de la classe définie avec l’attribut **default**.  
  
 Si aucune interface par défaut n’est spécifiée, la première occurrence d’une interface non source est utilisée par défaut.  
  
 *interface2*\(facultatif\)  
 Interface source par défaut. Vous devez aussi spécifier cette interface avec l’attribut [source](../windows/source-cpp.md).  
  
 Si aucune interface source par défaut n’est spécifiée, la première interface source est utilisée par défaut.  
  
## Notes  
 L’attribut C\+\+ **default** a les mêmes fonctionnalités que l’attribut MIDL [default](http://msdn.microsoft.com/library/windows/desktop/aa366787). L’attribut **default** est aussi utilisé avec l’attribut [case](../windows/case-cpp.md).  
  
## Exemple  
 Le code suivant montre comment l’attribut **default** est utilisé dans la définition d’une coclasse pour spécifier **ICustomDispatch** comme interface de programmabilité par défaut :  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 Il existe aussi un exemple pour l’attribut [source](../windows/source-cpp.md) qui montre comment utiliser **default**.  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, membre de données|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclasse** \(quand il s’applique à une **classe** ou un `struct`\)|  
|**Attributs non valides**|None|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)