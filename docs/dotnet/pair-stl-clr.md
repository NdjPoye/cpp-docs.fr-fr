---
title: paire (STL/CLR) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair
dev_langs: C++
helpviewer_keywords: pair class [STL/CLR]
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a8c4ae8ee9fbcfddd6009d4e91134d59a9a02cc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pair-stlclr"></a>paire (STL/CLR)
La classe de modèle décrit un objet qui encapsule une paire de valeurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Paramètres  
 Value1  
 Le type de la première valeur encapsulée.  
  
 Value2  
 Le type de la deuxième valeur encapsulée.  
  
## <a name="members"></a>Membres  
  
|Définition de types|Description|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](../dotnet/pair-first-type-stl-clr.md)|Le type de la première valeur encapsulée.|  
|[pair::second_type (STL/CLR)](../dotnet/pair-second-type-stl-clr.md)|Le type de la deuxième valeur encapsulée.|  
  
|Objet membre|Description|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)|La première valeur stockée.|  
|[pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)|La deuxième valeur stockée.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](../dotnet/pair-pair-stl-clr.md)|Construit un objet de la paire.|  
|[pair::swap (STL/CLR)](../dotnet/pair-swap-stl-clr.md)|Échange le contenu de deux paires.|  
  
|Opérateur|Description|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](../dotnet/pair-operator-assign-stl-clr.md)|Remplace la paire de valeurs stockée.|  
  
## <a name="remarks"></a>Notes  
 L’objet stocke une paire de valeurs. Cette classe de modèle vous permet de combiner deux valeurs en un seul objet. Notez que `cliext::pair` (décrite ici) stocke uniquement les types managés ; pour stocker une paire de non managé types utilisent `std::pair`, déclarés dans `<utility>`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/utilitaire >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [make_pair (STL/CLR)](../dotnet/make-pair-stl-clr.md)