---
title: range_adapter (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- range_adapter class [STL/CLR]
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b9adb22c14fb5b59dfb4e89e69c724ca8c7462bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="rangeadapter-stlclr"></a>range_adapter (STL/CLR)
Classe de modèle qui encapsule une paire d’itérateurs qui permettent d’implémenter plusieurs interfaces de la bibliothèque de classes de Base (BCL). Le range_adapter vous permettent de manipuler une plage STL/CLR comme s’il s’agissait d’une collection BCL.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Paramètres  
 Iter  
 Le type associé aux itérateurs encapsulées.  
  
## <a name="members"></a>Membres  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[range_adapter::range_adapter (STL/CLR)](../dotnet/range-adapter-range-adapter-stl-clr.md)|Construit un objet d’adaptateur.|  
  
|Opérateur|Description|  
|--------------|-----------------|  
|[range_adapter::operator= (STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)|Remplace la paire itérateur stocké.|  
  
## <a name="interfaces"></a>Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|Parcourt les éléments dans la collection.|  
|<xref:System.Collections.ICollection>|Gère un groupe d’éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Itère au sein des éléments typés dans la collection...|  
|<xref:System.Collections.Generic.ICollection%601>|Gère un groupe d’éléments typés.|  
  
## <a name="remarks"></a>Notes  
 La range_adapter stocke une paire d’itérateurs, qui à son tour délimiter une séquence d’éléments. L’objet implémente quatre interfaces BCL qui vous permettent de parcourir les éléments, dans l’ordre. Cette classe de modèle vous permet de manipuler des plages comme BCL conteneurs STL/CLR.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<cliext/carte >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)