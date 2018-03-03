---
title: threads (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e44fec96391fff6700ecf4a453d7455bd75e9df7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="threading-c"></a>thread (C++)
Spécifie le modèle de thread pour un objet COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### <a name="parameters"></a>Paramètres  
 ***modèle*** (facultatif)  
 L’un des modèles de threads suivants :  
  
-   **cloisonnement** (cloisonnement des threads)  
  
-   **neutre** (composants de .NET Framework sans interface utilisateur)  
  
-   **seul** (thread simple)  
  
-   **libre** (libre de threads)  
  
-   **les deux** (thread cloisonné et libre)  
  
 La valeur par défaut est **cloisonnement**.  
  
## <a name="remarks"></a>Notes  
 Le **threading** attribut C++ n’apparaît pas dans le fichier .idl généré, mais sera utilisé dans l’implémentation de votre objet COM.  
  
 Dans les projets ATL, si le [coclasse](../windows/coclass.md) attribut est également présent, le modèle de thread spécifié par *modèle* est passé comme paramètre de modèle pour le [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) classe , inséré par le **coclasse** attribut.  
  
 Le **threading** attribut protège également l’accès à un [event_source](../windows/event-source.md).  
  
## <a name="example"></a>Exemple  
 Consultez le [concédé sous licence](../windows/licensed.md) exemple pour un exemple d’utilisation de **threading**.  
  
## <a name="requirements"></a>Configuration requise  
  
### <a name="attribute-context"></a>Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**class**, `struct`|  
|**Renouvelable**|Non|  
|**Attributs requis**|**coclass**|  
|**Attributs non valides**|Aucun.|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs COM](../windows/com-attributes.md)   
 [TypeDef, Enum, Union et Struct (attributs)](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributs de classe](../windows/class-attributes.md)   
 [Prise en charge le multithreading pour un Code plus ancien (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Cloisonnements neutres](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
