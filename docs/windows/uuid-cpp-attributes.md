---
title: UUID (attributs C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.uuid
dev_langs: C++
helpviewer_keywords: uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba35dc89ae2567a499d4623f0c74293d2dbdcca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="uuid-c-attributes"></a>uuid (attributs C++)
Spécifie l’ID unique pour une classe ou interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 *UUID*  
 Identificateur unique de 128 bits.  
  
## <a name="remarks"></a>Notes  
 Si la définition d’une interface ou une classe ne spécifie pas le `uuid` attribut C++, puis le compilateur Visual C++ fournit une. Lorsque vous spécifiez un `uuid`, vous devez inclure les guillemets.  
  
 Si vous ne spécifiez pas `uuid`, le compilateur génère le même GUID pour les interfaces ou classes portant le même nom dans les projets autre attribut sur un ordinateur.  
  
 Vous pouvez utiliser Uuidgen.exe ou Guidgen.exe pour générer votre propre ID unique. (Pour exécuter un de ces outils, cliquez sur **Démarrer** et cliquez sur **exécuter** dans le menu. Entrez le nom de l’outil requis.)  
  
 Lorsqu’il est utilisé dans un projet qui n’utilise pas également ATL, en spécifiant le `uuid` attribut est identique à la [uuid](../cpp/uuid-cpp.md) __declspec (modificateur). Pour récupérer le `uuid` d’une classe, vous pouvez utiliser [__uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>Exemple  
 Consultez le [pouvant être liés](../windows/bindable.md) exemple pour un exemple d’utilisation de `uuid`.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, `interface`, **union**,`enum`|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun.|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs IDL](../windows/idl-attributes.md)   
 [Attributs d’interface](../windows/interface-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [UUID](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
