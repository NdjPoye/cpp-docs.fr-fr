---
title: vi_progid | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7581a4a10d9f101526aeb1a17ba7e26c4646b39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="viprogid"></a>vi_progid
Spécifie un formulaire indépendant de la version du ProgID.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>Paramètres  
 *name*  
 Le ProgID indépendants de la version qui représente l’objet.  
  
 ProgID présentent une version lisible de l’identificateur de classe (CLSID) utilisé pour identifier les objets COM/ActiveX.  
  
## <a name="remarks"></a>Notes  
 Le **vi_progid** attribut C++ vous permet de spécifier un ProgID indépendants de la version d’un objet COM. Un ProgID présente sous la forme *name1.name2.version*. Un ProgID indépendants de la version n’a pas un *version*. Il est possible de spécifier à la fois le **progid** et **vi_progid** les attributs d’une coclasse. Si vous ne spécifiez pas **vi_progid**, les ProgID indépendants de la version est la valeur spécifiée par la [progid](../windows/progid.md) attribut.  
  
 **vi_progid** implique la **coclasse** d’attribut, autrement dit, si vous spécifiez **vi_progid**, il s’agit de la même chose que la spécification de la **coclasse** et **vi_progid** attributs.  
  
 Le **vi_progid** attribut entraîne une classe soit automatiquement inscrite sous le nom spécifié. Le fichier .idl généré n’affichera pas la valeur ProgID.  
  
 Dans les projets ATL, si le [coclasse](../windows/coclass.md) attribut est également présent, le ProgID spécifié est utilisé par le **GetVersionIndependentProgID** (fonction) (insérées par le **coclasse** (attribut).  
  
## <a name="example"></a>Exemple  
 Consultez le [coclasse](../windows/coclass.md) exemple pour un exemple d’utilisation de **vi_progid**.  
  
## <a name="requirements"></a>Spécifications  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**class**, `struct`|  
|**Renouvelable**|Aucune|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Clé progID](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
