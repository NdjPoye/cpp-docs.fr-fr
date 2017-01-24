---
title: "coclass | Microsoft Docs"
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
  - "vc-attr.coclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coclass attribute"
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# coclass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

crée un objet COM, qui peut implémenter une interface COM.  
  
## Syntaxe  
  
```  
  
[coclass]  
  
```  
  
## Notes  
 L'attribut de **coclasse** C\+\+ place un élément coclass dans le fichier généré .idl.  
  
 En définissant une coclasse, vous pouvez également spécifier [uuid](../windows/uuid-cpp-attributes.md), [version](../windows/version-cpp.md), [threads](../windows/threading-cpp.md), [vi\_progid](../windows/vi-progid.md), les attributs et de [progid](../windows/progid.md) .  Si l'un quelconque d'entre elles ne sont spécifiés, ils sont générés.  
  
 Si plusieurs fichiers d'en\-tête contiennent des classes avec **coclasse** attribut et ne spécifient pas GUID, le compilateur utilise le même GUID pour les deux classes, et qui provoquera une erreur de MIDL.  Par conséquent, vous devez utiliser l'attribut d' `uuid` lorsque vous utilisez **coclasse**.  
  
 **Projets ATL**  
  
 Lorsque cet attribut précède une définition de classe ou de structure dans un projet ATL, il :  
  
-   Injecte le code ou des données pour prendre en charge l'inscription automatique à l'objet.  
  
-   Injecte le code ou des données pour prendre en charge une fabrique de classe COM pour l'objet.  
  
-   Injecte le code ou des données pour implémenter **IUnknown** et effectuer à l'objet un objet de COM\-creatable.  
  
 spécifiquement, les classes de base suivantes sont ajoutées à l'objet cible :  
  
-   [classe de CComCoClass](../atl/reference/ccomcoclass-class.md) fournit le modèle par défaut de fabrique de classes et de regroupement pour l'objet.  
  
-   [classe de CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) a un modèle selon la classe de modèle de thread spécifié par l'attribut de [threads](../windows/threading-cpp.md) .  si l'attribut de **threads** n'est pas spécifié, le modèle de thread par défaut est cloisonné.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) est ajouté si l'attribut de [noncreatable](../windows/noncreatable.md) n'est pas spécifié pour l'objet de la cible.  
  
 Enfin, toute interface double qui n'est pas définie dans IDL incorporé est remplacée par la classe correspondante d' [IDispatchImpl](../atl/reference/idispatchimpl-class.md) .  Si l'interface double est définie dans IDL incorporé, l'interface particulière dans la liste de base n'est pas modifiée.  
  
 L'attribut de **coclasse** rend également les fonctions suivantes disponibles via le code injecté ; en cas de `GetObjectCLSID`, comme une méthode statique dans la classe de base `CComCoClass`:  
  
-   `UpdateRegistry` enregistre les fabriques de classe de la classe cible.  
  
-   `GetObjectCLSID`, en rapport avec l'alignement, peut également être utilisé pour obtenir le CLSID de la classe cible.  
  
-   **GetObjectFriendlyName** retourne par défaut une chaîne au format « *name\>*`Object`*de classe*d'\<target ».  si cette fonction est déjà présente, elle n'est pas ajoutée.  Ajoutez cette fonction à la classe cible pour retourner un nom plus convivial que celui généré automatiquement.  
  
-   **GetProgID**, en rapport avec l'alignement, retourne la chaîne spécifiée avec l'attribut de [progid](../windows/progid.md) .  
  
-   **GetVersionIndependentProgID** a les mêmes fonctionnalités que **GetProgID**, mais il retourne la chaîne spécifiée avec [vi\_progid](../windows/vi-progid.md).  
  
 Les modifications suivantes, qui sont liées au mappage COM, sont apportées à la classe cible :  
  
-   Un mappage COM est ajouté avec les entrées pour toutes les interfaces que la classe cible dérive de et toutes les entrées spécifiées par [points d'entrée d'interface COM](../mfc/com-interface-entry-points.md) les attribut ou celles requis par l'attribut d' [agrégats](../windows/aggregates.md) .  
  
-   une macro d' [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md) est insérée dans le mappage COM.  Cette macro est semblable à [OBJECT\_ENTRY](http://msdn.microsoft.com/fr-fr/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) en termes de fonctionnalité mais ne doivent pas faire partie du mappage COM de la classe cible.  
  
 Le nom de la coclasse générée dans le fichier .idl pour la classe porte le même nom que la classe.  Par exemple, et qui fait référence à l'exemple suivant, pour accéder à l'ID de classe d'une coclasse CMyClass, dans un client via le fichier d'en\-tête généré par le compilateur MIDL, utilisez CLSID\_CMyClass.  
  
## Exemple  
 Le code suivant montre comment utiliser l'attribut de **coclasse** :  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 L'exemple suivant montre comment substituer l'implémentation par défaut d'une fonction qui apparaît dans le code injecté par un attribut de **coclasse** .  Consultez [\/Fx](../build/reference/fx-merge-injected-code.md) pour plus d'informations sur le code injecté.  Toutes les classes de base ou interfaces que vous utilisez pour une classe seront apparaissent dans le code injecté.   De plus, si une classe est incluse par défaut dans le code injecté et vous spécifiez explicitement cette classe comme base pour votre coclasse, le fournisseur d'attribut utilise le formulaire spécifié dans votre code.  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)